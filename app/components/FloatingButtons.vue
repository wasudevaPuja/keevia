<template>
  <div v-if="isPlaying !== null" class="fixed bottom-6 right-6 z-[9999]">
    <button @click="toggleAudio" :class="[
      'group relative w-14 h-14 rounded-full flex items-center justify-center',
      'bg-white/10 backdrop-blur-xl border border-white/20',
      'text-white shadow-[0_10px_35px_rgba(0,0,0,0.45)]',
      'transition-all duration-300',
      'hover:scale-110 hover:bg-pink-400/80 hover:border-pink-300',
      isPlaying ? 'animate-[softPulse_3s_ease-in-out_infinite]' : ''
    ]">
      <!-- Icon ketika musik ON -->
      <span v-if="isPlaying">
        <UIcon name="mdi:volume-high"
          class="w-5 h-5 transition-transform duration-500 group-hover:rotate-12 group-hover:scale-110" />
      </span>

      <!-- Icon ketika musik OFF -->
      <span v-else>
        <UIcon name="mdi:volume-off"
          class="w-5 h-5 opacity-70 transition-transform duration-300 group-hover:scale-110" />
      </span>

      <!-- Soft Glow saat musik aktif -->
      <span v-if="isPlaying" class="absolute inset-0 rounded-full bg-pink-400/20 blur-xl -z-10" />


    </button>
  </div>

</template>

<script setup lang="ts">
import type { Ref } from 'vue'
import { inject } from 'vue'

const audioControl = inject('audioControl') as {
  isPlaying: Ref<boolean>
  toggleAudio: () => void
  audio: Ref<HTMLAudioElement | null>
} | undefined

const isPlaying = audioControl?.isPlaying
const toggleAudio = audioControl?.toggleAudio
</script>
