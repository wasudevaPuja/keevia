<template>
  <div
    v-if="isPlaying !== null"
    class="fixed bottom-6 right-6 z-[9999]"
  >
    <button
      :class="[
        'group relative w-14 h-14 rounded-full flex items-center justify-center transition-all duration-500',
        'backdrop-blur-xl border border-white/20 text-white shadow-[0_10px_40px_rgba(0,0,0,0.5)]',
        // BLOSSOM THEME Styles
        currentTheme === 'blossom' ? 'bg-pink-500/20 hover:scale-110 hover:bg-pink-400 hover:border-pink-300' : '',
        // BALI THEME Styles
        currentTheme === 'bali' ? 'bg-[#4a3f35]/20 hover:scale-110 hover:bg-[#4a3f35] hover:border-amber-400/50' : '',
        isPlaying ? 'animate-[softPulse_3s_ease-in-out_infinite]' : ''
      ]"
      @click="toggleAudio"
    >
      <!-- Icon based on state -->
      <span class="relative z-10 transition-transform duration-500 group-hover:scale-110">
        <UIcon
          :name="isPlaying ? 'mdi:volume-high' : 'mdi:volume-off'"
          class="w-5 h-5"
          :class="[
            !isPlaying ? 'opacity-70' : '',
            currentTheme === 'bali' && isPlaying ? 'text-amber-200' : ''
          ]"
        />
      </span>

      <!-- Dynamic Glow based on theme -->
      <span
        v-if="isPlaying"
        class="absolute inset-0 rounded-full blur-2xl -z-10 transition-colors duration-500"
        :class="[
          currentTheme === 'blossom' ? 'bg-pink-400/30' : '',
          currentTheme === 'bali' ? 'bg-amber-400/20' : ''
        ]"
      />
      
      <!-- Hover Shine -->
      <div class="absolute inset-0 rounded-full bg-gradient-to-tr from-white/10 to-transparent opacity-0 group-hover:opacity-100 transition-opacity" />
    </button>
  </div>
</template>

<script setup lang="ts">
import type { Ref } from 'vue'
import { inject } from 'vue'

const audioControl = inject('audioControl') as {
  isPlaying: Ref<boolean>
  currentTheme: Ref<string>
  toggleAudio: () => void
  play: () => void
  pause: () => void
} | undefined

const isPlaying = audioControl?.isPlaying
const currentTheme = audioControl?.currentTheme
const toggleAudio = audioControl?.toggleAudio
</script>
