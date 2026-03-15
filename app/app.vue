<script setup lang="ts">
import { ref, provide } from 'vue'

const url = useRequestURL()
const route = useRoute()

const PROD_DOMAINS = ['keevia.id', 'www.keevia.id', 'undangandigital.keevia.id']

const isProdDomain
  = import.meta.env.PROD
    && PROD_DOMAINS.includes(url.hostname)

useHead(() => {
  const meta = [
    {
      name: 'Permissions-Policy',
      content: 'compute-pressure=()'
    }
  ]

  if (!isProdDomain) {
    return {
      meta,
      link: [
        {
          rel: 'icon',
          type: 'image/x-icon',
          href: '/favicon.ico'
        },
        {
          rel: 'icon',
          type: 'image/png',
          sizes: '32x32',
          href: '/favicon.png'
        },
        {
          rel: 'icon',
          type: 'image/png',
          sizes: '16x16',
          href: '/favicon.png'
        }
      ]
    }
  }

  // production domain → inject canonical dynamic
  return {
    meta,
    link: [
      {
        rel: 'canonical',
        href: `https://keevia.id${route.fullPath}`
      },
      {
        rel: 'icon',
        type: 'image/x-icon',
        href: '/favicon.ico'
      },
      {
        rel: 'icon',
        type: 'image/png',
        sizes: '32x32',
        href: '/favicon.png'
      },
      {
        rel: 'icon',
        type: 'image/png',
        sizes: '16x16',
        href: '/favicon.png'
      }
    ]
  }
})

const isPlaying = ref(false)
const currentTheme = ref('blossom') // 'blossom' | 'bali'
const currentMusicId = ref('Aa29L3jtg-o') // Default music
let player: any = null

const toggleAudio = () => {
  if (player) {
    if (isPlaying.value) {
      player.pauseVideo()
    } else {
      player.playVideo()
    }
  }
  isPlaying.value = !isPlaying.value
}

const play = () => {
  if (player) {
    player.playVideo()
    isPlaying.value = true
  }
}

const pause = () => {
  if (player) {
    player.pauseVideo()
    isPlaying.value = false
  }
}

const setMusicId = (id: string) => {
  if (currentMusicId.value !== id) {
    currentMusicId.value = id
    if (player && player.loadVideoById) {
      player.loadVideoById({
        videoId: id,
        suggestedQuality: 'default'
      })
      // If it was playing, keep playing. If it was paused, keep paused.
      // Usually loadVideoById starts playing automatically unless specified.
      if (!isPlaying.value) {
        player.pauseVideo()
      }
    }
  }
}

onMounted(() => {
  // Load YouTube IFrame API
  const tag = document.createElement('script')
  tag.src = 'https://www.youtube.com/iframe_api'
  const firstScriptTag = document.getElementsByTagName('script')[0]
  if (firstScriptTag && firstScriptTag.parentNode) {
    firstScriptTag.parentNode.insertBefore(tag, firstScriptTag)
  }

  // Initialize player when API is ready
  ;(window as any).onYouTubeIframeAPIReady = () => {
    player = new (window as any).YT.Player('youtube-player', {
      height: '1',
      width: '1',
      videoId: currentMusicId.value,
      playerVars: {
        autoplay: 0,
        loop: 1,
        playlist: currentMusicId.value,
        controls: 0,
        showinfo: 0,
        autohide: 1,
        modestbranding: 1,
        mute: 0,
      },
      events: {
        onReady: (event: any) => {
          console.log('YouTube Player Ready')
        },
        onStateChange: (event: any) => {
          // Sync state if player is controlled externally
          if (event.data === (window as any).YT.PlayerState.PLAYING) {
            isPlaying.value = true
          } else if (event.data === (window as any).YT.PlayerState.PAUSED) {
            isPlaying.value = false
          }
        },
      },
    })
  }
})

provide('audioControl', {
  isPlaying,
  currentTheme,
  currentMusicId,
  toggleAudio,
  play,
  pause,
  setMusicId
})
</script>

<template>
  <div>
    <!-- <Navbar /> -->

    <main>
      <NuxtPage />
      <!-- Global Audio Player - Fixed for Mobile compatibility using YT API -->
      <div id="youtube-player" class="fixed -top-[100px] left-0 pointer-events-none opacity-0 invisible"></div>
      <FloatingButtons />
    </main>
  </div>
</template>
