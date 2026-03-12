<template>
  <div class="flex w-full min-h-[100dvh]">
    <!-- PRELOADER SPLASH SCREEN -->
    <transition name="fade">
      <div 
        v-if="isLoading" 
        class="fixed inset-0 z-[100] bg-[#1a1a1a] text-white flex flex-col items-center justify-center font-sans tracking-wide"
      >
        <!-- Center Content -->
        <div class="flex flex-col items-center space-y-6">
          <p class="text-[10px] md:text-xs uppercase tracking-[0.3em] text-white/70">{{ t("weddingOf") }}</p>
          <div class="w-40 h-56 md:w-32 md:h-40 overflow-hidden rounded-md border border-white/10 shadow-lg relative">
            <div class="absolute inset-0 bg-black/20 z-10"></div>
            <img src="/img/gian/loading_img.JPEG" alt="Preloading" class="w-full h-full object-cover grayscale opacity-80" />
          </div>
          <p class="text-sm md:text-base font-medium tracking-[0.2em] uppercase mt-2">GIAN <span class="text-pink-300/80">&</span> KRISTIANI</p>
        </div>

        <!-- Progress Text -->
        <div class="absolute bottom-8 left-8 md:bottom-12 md:left-12">
          <p class="text-[10px] md:text-xs tracking-[0.15em] text-white/50">LOADING... {{ loadingProgress }}%</p>
        </div>
      </div>
    </transition>

    <!-- LEFT PANEL (80%) -->
    <div class="hidden md:block flex-1 sticky top-0 self-start h-[100dvh] md:h-screen relative overflow-hidden">
      <!-- Background Image -->

      <img
        src="/img/gian/cover.webp"
        class="absolute inset-0 w-full h-full object-cover scale-105"
      >

      <!-- Elegant Overlay -->

      <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-black/30 to-black/10" />
      <div class="absolute inset-0 bg-gradient-to-r from-black/60 via-transparent to-transparent" />

      <!-- Content -->

      <div
        class="absolute bottom-16 left-16 text-white z-10 max-w-xl"
      >
        <!-- Small Label -->
        <div
          class="flex items-center gap-4 mb-4"
        >
          <div class="w-12 h-px bg-pink-300" />
          <p class="tracking-[0.35em] text-xs uppercase text-pink-200">{{ t("weddingOf") }}</p>
        </div>

        <!-- Names -->
        <h1 class="text-6xl lg:text-7xl font-light font-serif leading-tight tracking-wide">
          Gian <span class="text-pink-200">&</span><br>
          Kristiani
        </h1>

        <!-- Date -->
        <p class="mt-6 text-sm tracking-[0.25em] uppercase text-white/80">{{ t("dateFull") }}</p>
      </div>
    </div>

    <div
      :class="[
        'relative shrink-0 w-full md:w-7/12 lg:w-5/12 xl:w-4/12 xxl:w-[600px] max-w-full h-[100dvh] md:h-screen transition-all duration-700 z-20 shadow-[-10px_0_30px_rgba(0,0,0,0.5)] bg-[#1a1a1a] border-l border-white/5',
        isOpen ? 'overflow-x-hidden overflow-y-auto' : 'overflow-hidden'
      ]"
    >
      <!-- BACKGROUND PHOTO UTAMA (FAST LOAD) -->
      <div class="absolute inset-0 -z-10 bg-[#1a1a1a]">
        <img 
          src="/img/gian/cover.webp"
          class="absolute inset-0 w-full h-full object-cover scale-105 z-0 opacity-80"
          alt="Hero Background"
        >
        <!-- Overlay Gradient over the image to make text readable -->
        <div class="absolute inset-0 bg-gradient-to-t from-black/80 via-black/40 to-black/20 z-20 pointer-events-none" />
      </div>

      <!-- HERO CONTENT -->
      <div
        class="relative z-10 h-[100dvh] md:h-screen flex flex-col justify-between text-white text-center px-8 py-10 pb-20 md:pb-10"
      >
        <!-- Heading -->
        <div class="space-y-6">
          <p class="tracking-[0.5em] text-[10px] md:text-xs mb-4 uppercase text-white/70">{{ t("weddingOf") }}</p>

          <h1 class="text-4xl md:text-5xl lg:text-6xl font-light font-serif tracking-wide leading-tight">
            Gian <span class="text-pink-200">&</span> Kristiani
          </h1>

          <p class="mt-6 text-sm md:text-base text-white/80 tracking-[0.2em] uppercase font-light">{{ t("dateFull") }}</p>
        </div>

        <!-- Invitation Box -->
        <div class="max-w-md mx-auto text-center">
          <template v-if="!isOpen">
            <p class="text-xs tracking-[0.3em] uppercase text-white/70">{{ t("toYth") }}</p>

            <p class="text-xl font-light mt-3 text-white">
              {{ guestName }}
            </p>

            <p class="text-[11px] text-white/60 mt-4 leading-relaxed">{{ t("openingMsg") }}</p>

            <button
              class="mt-6 px-8 py-3 bg-white/20 backdrop-blur-md border border-white/30 text-white rounded-full hover:bg-white/30 transition-all tracking-[0.25em] text-xs hover:scale-105 cursor-pointer"
              @click="openInvitation"
            >{{ t("openBtn") }}</button>
          </template>

          <template v-else>
            <p class="text-sm md:text-base italic leading-relaxed text-white/90">{{ t("bibleQuote") }}</p>

            <p class="text-xs mt-3 text-pink-200 tracking-wide">{{ t("bibleVerse") }}</p>
          </template>
        </div>
      </div>

      <!-- SCROLL CONTENT -->
      <div
        v-if="isOpen"
        class="relative z-10 bg-transparent text-white w-full"
      >
        <!-- MEMPELAI (The Couple) -->
        <section class="relative w-full bg-[#1a1a1a]">
          <!-- Vertical Layout (Stacked) -->
          <div class="flex flex-col w-full text-left">
            <!-- MEMPELAI PRIA -->
            <div class="relative w-full min-h-[85dvh] lg:h-screen group overflow-hidden border-b border-white/5">
              <img
                src="/img/gian/the_groom.jpg"
                alt="Groom Gian Felix Sinaga"
                class="absolute inset-0 w-full h-full object-cover transition-transform duration-[10000ms] ease-linear group-hover:scale-110"
              >
              <!-- Elegant Overlay Gradients -->
              <div class="absolute inset-0 bg-gradient-to-t from-black via-black/40 to-black/20" />
              <div class="absolute inset-0 bg-gradient-to-r from-black/60 to-transparent" />

              <!-- Content -->
              <div class="absolute inset-0 flex flex-col justify-end p-8 pb-36 md:p-12 md:pb-36 lg:p-16 lg:pb-36 z-10 w-full mx-auto">
                <div class="opacity-0 transition-all ease-[cubic-bezier(0.25,1,0.5,1)] scroll-animate translate-y-16 duration-[1500ms] space-y-4 max-w-sm"
                >
                  <div class="flex items-center gap-4">
                    <div class="w-12 h-px bg-pink-300" />
                    <p class="text-xs tracking-[0.3em] uppercase text-pink-200">{{ t("theGroom") }}</p>
                  </div>

                  <h2 class="text-4xl lg:text-5xl font-light text-white font-serif tracking-wide leading-tight">
                    Gian Felix<br><span class="italic text-pink-100">Sinaga</span>
                  </h2>

                  <div class="pt-4 space-y-1">
                    <p class="text-base md:text-lg text-white/80 font-light">{{ t("sonOf") }}</p>
                    <p class="text-base md:text-lg text-white font-medium">{{ t("parentsGroom") }}</p>
                  </div>

                  <!-- Sosial Media -->
                  <div
                    class="pt-4 opacity-100 md:opacity-0 md:group-hover:opacity-100 transition-opacity duration-500 delay-100"
                  >
                    <a
                      href="https://instagram.com/gianfelixs_"
                      target="_blank"
                      rel="noopener noreferrer"
                      class="inline-flex items-center justify-center w-12 h-12 rounded-full bg-white/10 backdrop-blur-md border border-white/20 text-white hover:bg-pink-400 hover:border-pink-300 transition-all hover:scale-110"
                    >
                      <UIcon
                        name="mdi:instagram"
                        class="w-6 h-6"
                      />
                    </a>
                  </div>
                </div>
              </div>
            </div>

            <!-- MEMPELAI WANITA -->
            <div class="relative w-full min-h-[85dvh] lg:h-screen group overflow-hidden border-b border-white/5">
              <img
                src="/img/gian/the_bride.jpg"
                alt="Bride Kristiani Munthe"
                class="absolute inset-0 w-full h-full object-cover transition-transform duration-[10000ms] ease-linear group-hover:scale-110"
              >
              <!-- Elegant Overlay Gradients -->
              <div class="absolute inset-0 bg-gradient-to-t from-black via-black/40 to-black/20" />
              <div class="absolute inset-0 bg-gradient-to-l from-black/60 to-transparent" />

              <!-- Content (Aligned right on all screens to balance the Groom) -->
              <div
                class="absolute inset-0 flex flex-col justify-end p-8 pb-36 md:p-12 md:pb-36 lg:p-16 lg:pb-36 z-10 items-end text-right w-full mx-auto"
              >
                <div class="opacity-0 transition-all ease-[cubic-bezier(0.25,1,0.5,1)] scroll-animate translate-y-16 duration-[1500ms] space-y-4 max-w-sm flex flex-col items-end"
                >
                  <div class="flex items-center gap-4 flex-row-reverse">
                    <div class="w-12 h-px bg-pink-300" />
                    <p class="text-xs tracking-[0.3em] uppercase text-pink-200">{{ t("theBride") }}</p>
                  </div>

                  <h2 class="text-4xl lg:text-5xl font-light text-white font-serif tracking-wide leading-tight">
                    Kristiani<br><span class="italic text-pink-100">Munthe</span>
                  </h2>

                  <div class="pt-4 space-y-1">
                    <p class="text-base md:text-lg text-white/80 font-light">{{ t("daughterOf") }}</p>
                    <p class="text-base md:text-lg text-white font-medium">{{ t("parentsBride") }}</p>
                  </div>

                  <!-- Sosial Media -->
                  <div
                    class="pt-4 opacity-100 md:opacity-0 md:group-hover:opacity-100 transition-opacity duration-500 delay-100"
                  >
                    <a
                      href="https://instagram.com/kristianymth_"
                      target="_blank"
                      rel="noopener noreferrer"
                      class="inline-flex items-center justify-center w-12 h-12 rounded-full bg-white/10 backdrop-blur-md border border-white/20 text-white hover:bg-pink-400 hover:border-pink-300 transition-all hover:scale-110"
                    >
                      <UIcon
                        name="mdi:instagram"
                        class="w-6 h-6"
                      />
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>

        <!-- JOURNEY OF LOVE -->
        <section class="min-h-[100dvh] md:min-h-screen relative flex flex-col justify-center py-16 md:py-24">
          <div class="absolute inset-0 -z-10">
            <video
          poster="/img/gian/cover.webp"
              autoplay
              muted
              loop
              playsinline
              class="w-full h-full object-cover filter brightness-75 contrast-125"
            >
              <source
                src="/video/gian/Reels.mp4"
                type="video/mp4"
              >
            </video>
            <div class="absolute inset-0 bg-black/60 backdrop-blur-[2px]" />
          </div>

          <div class="relative z-10 w-full max-w-5xl mx-auto px-6 md:px-12">
            <!-- Header -->
            <div class="opacity-0 transition-all ease-out transform-gpu scroll-animate -translate-y-10 duration-[700ms] text-center space-y-4 mb-16 md:mb-20">
              <div class="flex justify-center mb-4">
                <i class="mdi mdi-flower-tulip-outline text-4xl text-pink-300 animate-pulse" />
              </div>
              <p class="text-xs md:text-sm tracking-[0.3em] uppercase text-pink-200/90 font-medium">{{ t("journeySub") }}</p>
              <h2 class="text-4xl lg:text-5xl font-light text-white font-serif italic">{{ t("journeyTitle") }}</h2>
            </div>

            <!-- Timeline -->
            <div class="relative">
              <!-- Timeline Center Line -->
              <!-- Center line removed for mobile-only single column -->

              <div class="space-y-8">
                <!-- Event 1 -->
                <div class="relative flex flex-col items-center group">
                  
                  <!-- Left Date/Title for Desktop -->
                  <div class="w-full text-center mb-4 space-y-2">
                    <div
                      class="inline-block px-4 py-1.5 rounded-full bg-pink-300/20 text-pink-200 text-xs font-semibold tracking-widest uppercase mb-2"
                    >{{ t("ch1DateFull") }}</div>
                    
                  </div>
                  <!-- Right Content -->
                  <div class="w-full">
                    <div class="opacity-0 transition-all transform-gpu ease-out scroll-animate translate-y-10 duration-[700ms] bg-white/5 backdrop-blur-md border border-white/10 rounded-2xl p-8 hover:bg-white/15 shadow-xl relative overflow-hidden group-hover:-translate-y-2 text-left"
                    >
                      <div class="absolute -right-6 -top-6 w-24 h-24 bg-pink-500/10 rounded-full blur-2xl" />
                      <div class="mb-4 border-b border-white/10 pb-4">
                        <h3 class="text-xl font-semibold text-white text-center">{{ t("ch1Title") }}</h3>
                      </div>
                      <p class="text-white/80 leading-relaxed text-sm md:text-base font-light">{{ t("ch1Desc") }}</p>
                    </div>
                  </div>
                </div>

                <!-- Event 2 -->
                <div class="relative flex flex-col items-center group">
                  
                  <!-- Right Date/Title for Desktop -->
                  <div class="w-full text-center mb-4 space-y-2">
                    <div
                      class="inline-block px-4 py-1.5 rounded-full bg-pink-300/20 text-pink-200 text-xs font-semibold tracking-widest uppercase mb-2"
                    >{{ t("ch2DateFull") }}</div>
                    
                  </div>
                  <!-- Left Content -->
                  <div class="w-full">
                    <div class="opacity-0 transition-all transform-gpu ease-out scroll-animate translate-y-10 duration-[700ms] bg-white/5 backdrop-blur-md border border-white/10 rounded-2xl p-8 hover:bg-white/15 shadow-xl relative overflow-hidden group-hover:-translate-y-2 text-left"
                    >
                      <div class="absolute -left-6 -bottom-6 w-24 h-24 bg-pink-500/10 rounded-full blur-2xl" />
                      <div class="mb-4 border-b border-white/10 pb-4 text-center">
                        <h3 class="text-xl font-semibold text-white">{{ t("ch2Title") }}</h3>
                      </div>
                      <p class="text-white/80 leading-relaxed text-sm md:text-base font-light">{{ t("ch2Desc") }}</p>
                    </div>
                  </div>
                </div>

                <!-- Event 3 -->
                <div class="relative flex flex-col items-center group">
                  
                  <!-- Left Date/Title for Desktop -->
                  <div class="w-full text-center mb-4 space-y-2">
                    <div
                      class="inline-block px-4 py-1.5 rounded-full bg-pink-300/20 text-pink-200 text-xs font-semibold tracking-widest uppercase mb-2"
                    >{{ t("ch3DateFull") }}</div>
                    
                  </div>
                  <!-- Right Content -->
                  <div class="w-full">
                    <div
                      class="opacity-0 transition-all transform-gpu ease-out scroll-animate translate-y-10 duration-[700ms] bg-gradient-to-br from-pink-500/20 to-white/5 backdrop-blur-md border border-pink-300/30 rounded-2xl p-6 hover:border-pink-300/60 shadow-[0_8px_32px_rgba(249,168,212,0.15)] relative overflow-hidden group-hover:-translate-y-2 text-left"
                    >
                      <div class="absolute -right-10 -bottom-10 w-32 h-32 bg-pink-400/20 rounded-full blur-3xl" />
                      <div class="mb-4 border-b border-pink-300/20 pb-4 text-center">
                        <h3 class="text-xl font-semibold text-white">{{ t("ch3Title") }}</h3>
                      </div>
                      <p class="text-white/90 leading-relaxed text-sm md:text-base font-medium">{{ t("ch3Desc") }}</p>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>

        <!-- SAVE OUR DATE -->
        <section class="min-h-[100dvh] md:min-h-screen relative flex flex-col justify-center py-16 md:py-24">
          <!-- Background Video with elegant overlay -->
          <div class="absolute inset-0 -z-10 bg-[#1a1a1a]">
            <!-- Elegant background alternative if video fails to load, maybe subtle static image or gradient -->
            <div class="absolute inset-0 bg-gradient-to-br from-pink-900/20 to-black z-0" />
            <video
          poster="/img/gian/cover.webp"
              autoplay
              muted
              loop
              playsinline
              class="w-full h-full object-cover opacity-60 z-10 relative mix-blend-screen"
            >
              <source
                src="/video/gian/Reels.mp4"
                type="video/mp4"
              >
            </video>
            <!-- Vignette/Shadow overlay -->
            <div
              class="absolute inset-0 bg-black/40 bg-[radial-gradient(circle_at_center,transparent_0%,rgba(0,0,0,0.8)_100%)] z-20 pointer-events-none"
            />
          </div>

          <div class="relative z-30 max-w-4xl mx-auto text-center px-6 md:px-12 w-full">
            <!-- Main Content Container with Glassmorphism -->
            <div class="opacity-0 transition-all ease-out scroll-animate translate-y-10 duration-[1200ms] bg-white/5 backdrop-blur-xl border border-white/10 rounded-3xl p-8 md:p-10 shadow-[0_8px_32px_rgba(0,0,0,0.4)] relative overflow-hidden group">
              <!-- Decorative elements -->
              <div
                class="absolute top-0 left-0 w-full h-1 bg-gradient-to-r from-transparent via-pink-400/50 to-transparent opacity-50"
              />
              <div
                class="absolute -top-40 -left-40 w-80 h-80 bg-pink-500/10 rounded-full blur-3xl group-hover:bg-pink-500/20 transition-all duration-1000"
              />
              <div
                class="absolute -bottom-40 -right-40 w-80 h-80 bg-pink-500/10 rounded-full blur-3xl group-hover:bg-pink-500/20 transition-all duration-1000"
              />

              <div class="relative z-10 space-y-12">
                <!-- Header Title -->
                <div class="opacity-0 transition-all ease-out scroll-animate -translate-y-10 duration-[1000ms] space-y-4">
                  <div class="flex justify-center mb-6">
                    <div class="w-16 h-px bg-gradient-to-r from-transparent via-pink-300 to-transparent mx-2 my-auto" />
                    <i class="mdi mdi-flower-tulip-outline text-3xl md:text-4xl text-pink-300 mx-4" />
                    <div class="w-16 h-px bg-gradient-to-r from-transparent via-pink-300 to-transparent mx-2 my-auto" />
                  </div>
                  <h2 class="text-xs md:text-sm font-medium tracking-[0.4em] uppercase text-pink-200/80">{{ t("saveOurDate") }}</h2>
                  <p class="text-3xl font-serif italic font-light text-white tracking-wide mt-2">{{ t("dateMain") }}</p>
                </div>

                <!-- Countdown Timer -->
                <div class="py-8 border-y border-white/10 my-10">
                  <div class="grid grid-cols-4 gap-2 md:gap-6 max-w-2xl mx-auto">
                    <!-- Days -->
                    <div
                      class="flex flex-col items-center justify-center p-3 rounded-2xl bg-white/5 border border-white/5 hover:bg-white/10 transition-colors"
                    >
                      <span class="text-3xl font-light text-white font-serif">{{ countdown.days }}</span>
                      <span
                        class="text-[10px] md:text-xs uppercase tracking-widest text-pink-200/70 mt-2 font-medium"
                      >{{ t("days") }}</span>
                    </div>
                    <!-- Hours -->
                    <div
                      class="flex flex-col items-center justify-center p-3 rounded-2xl bg-white/5 border border-white/5 hover:bg-white/10 transition-colors"
                    >
                      <span class="text-3xl font-light text-white font-serif">{{ countdown.hours }}</span>
                      <span
                        class="text-[10px] md:text-xs uppercase tracking-widest text-pink-200/70 mt-2 font-medium"
                      >{{ t("hours") }}</span>
                    </div>
                    <!-- Minutes -->
                    <div
                      class="flex flex-col items-center justify-center p-3 rounded-2xl bg-white/5 border border-white/5 hover:bg-white/10 transition-colors"
                    >
                      <span class="text-3xl font-light text-white font-serif">{{ countdown.minutes }}</span>
                      <span
                        class="text-[10px] md:text-xs uppercase tracking-widest text-pink-200/70 mt-2 font-medium"
                      >{{ t("minutes") }}</span>
                    </div>
                    <!-- Seconds -->
                    <div
                      class="flex flex-col items-center justify-center p-3 rounded-2xl bg-white/5 border border-white/5 hover:bg-white/10 transition-colors"
                    >
                      <span class="text-3xl font-light text-pink-300 font-serif">{{ countdown.seconds
                      }}</span>
                      <span
                        class="text-[10px] md:text-xs uppercase tracking-widest text-pink-200/70 mt-2 font-medium"
                      >{{ t("seconds") }}</span>
                    </div>
                  </div>

                  <div class="mt-8 flex justify-center">
                    <a
                      href="/save-the-date.ics"
                      download
                      class="inline-flex items-center gap-2 px-8 py-3 bg-pink-300 hover:bg-pink-400 text-gray-900 rounded-full text-sm font-medium tracking-wide transition-all duration-300 hover:shadow-[0_0_20px_rgba(249,168,212,0.4)] hover:-translate-y-1"
                    >
                      <UIcon name="mdi:calendar-heart" class="w-5 h-5" /> {{ t("saveToCal") }}
                    </a>
                  </div>
                </div>

                <!-- Event Details -->
                <div class="flex flex-col gap-8 md:gap-10 text-left pt-2 max-w-xl mx-auto">
                  <!-- Pemberkatan -->
                  <div class="relative pl-6 md:pl-8 border-l border-pink-300/30">
                    <div
                      class="absolute -left-[5px] top-1.5 w-2 h-2 rounded-full bg-pink-300 shadow-[0_0_10px_rgba(249,168,212,0.8)]"
                    />
                    <h3 class="font-serif italic text-2xl text-white mb-2">{{ t("pemberkatanTitle") }}</h3>
                    <div class="space-y-3 text-white/80 font-light text-sm md:text-base">
                      <p class="flex items-center gap-3">
                        <UIcon
                          name="mdi:clock-outline"
                          class="w-4 h-4 text-pink-300/70"
                        /> {{ t("pemberkatanTime") }}
                      </p>
                      <p class="flex items-start gap-3">
                        <UIcon
                          name="mdi:map-marker-outline"
                          class="w-4 h-4 text-pink-300/70 mt-1 flex-shrink-0"
                        />
<span class="leading-relaxed">{{ t("pemberkatanLocation") }}</span>
</p>
                    </div>
                  </div>

                  <!-- Youth Party -->
                  <div class="relative pl-6 md:pl-8 border-l border-pink-300/30">
                    <div
                      class="absolute -left-[5px] top-1.5 w-2 h-2 rounded-full bg-pink-300 shadow-[0_0_10px_rgba(249,168,212,0.8)]"
                    />
                    <h3 class="font-serif italic text-2xl text-white mb-2">{{ t("resepsiTitle") }}</h3>
                    <div class="space-y-3 text-white/80 font-light text-sm md:text-base">
                      <p class="flex items-center gap-3">
                        <UIcon
                          name="mdi:clock-outline"
                          class="w-4 h-4 text-pink-300/70"
                        /> {{ t("resepsiTime") }}
                      </p>
                      <p class="flex items-start gap-3">
                        <UIcon
                          name="mdi:map-marker-outline"
                          class="w-4 h-4 text-pink-300/70 mt-1 flex-shrink-0"
                        />
<span class="leading-relaxed">{{ t("resepsiLocation") }}</span>
</p>
                    </div>
                  </div>
                  <!-- Adat -->
                  <div class="relative pl-6 md:pl-8 border-l border-pink-300/30">
                    <div
                      class="absolute -left-[5px] top-1.5 w-2 h-2 rounded-full bg-pink-300 shadow-[0_0_10px_rgba(249,168,212,0.8)]"
                    />
                    <h3 class="font-serif italic text-2xl text-white mb-2">{{ t("adatTitle") }}</h3>
                    <div class="space-y-3 text-white/80 font-light text-sm md:text-base">
                      <p class="flex items-center gap-3">
                        <UIcon
                          name="mdi:clock-outline"
                          class="w-4 h-4 text-pink-300/70"
                        /> {{ t("adatTime") }}
                      </p>
                      <p class="flex items-start gap-3">
                        <UIcon
                          name="mdi:map-marker-outline"
                          class="w-4 h-4 text-pink-300/70 mt-1 flex-shrink-0"
                        />
<span class="leading-relaxed">{{ t("resepsiLocation") }}</span>
</p>
                    </div>
                  </div>
                </div>

                <!-- Maps Button -->
                <div class="pt-6">
                  <a
                    href="https://maps.app.goo.gl/CGjFjVbBF8SQpLMe7?g_st=aw"
                    target="_blank"
                    class="inline-flex items-center gap-2 px-6 py-3 bg-white/10 hover:bg-white/20 border border-white/20 text-white rounded-full text-sm font-medium tracking-wide transition-all duration-300"
                  >
                    <UIcon
                      name="mdi:google-maps"
                      class="w-5 h-5 text-pink-300"
                    /> {{ t("openMap") }}
                  </a>
                </div>
              </div>
            </div>
          </div>
        </section>

        <!-- Wedding Gift -->
        <section class="min-h-[100dvh] md:min-h-screen relative flex flex-col justify-center py-16 md:py-24">
          <!-- Background Video with elegant overlay -->
          <div class="absolute inset-0 -z-10 bg-[#1a1a1a]">
            <!-- Elegant background alternative if video fails to load, maybe subtle static image or gradient -->
            <div class="absolute inset-0 bg-gradient-to-br from-pink-900/20 to-black z-0" />
            <video
          poster="/img/gian/cover.webp"
              autoplay
              muted
              loop
              playsinline
              class="w-full h-full object-cover opacity-60 z-10 relative mix-blend-screen grayscale"
            >
              <source
                src="/video/gian/Reels.mp4"
                type="video/mp4"
              >
            </video>
            <!-- Vignette/Shadow overlay -->
            <div
              class="absolute inset-0 bg-black/40 bg-[radial-gradient(circle_at_center,transparent_0%,rgba(0,0,0,0.8)_100%)] z-20 pointer-events-none"
            />
          </div>

          <!-- Content -->
          <div class="relative z-30 max-w-5xl mx-auto text-center px-6 md:px-12 w-full">
            <div class="opacity-0 transition-all ease-out scroll-animate translate-y-10 duration-[1200ms] bg-white/5 backdrop-blur-xl border border-white/10 rounded-3xl p-8 md:p-10 shadow-[0_8px_32px_rgba(0,0,0,0.4)] relative overflow-hidden group">
              <!-- Decorative elements -->
              <div
                class="absolute top-0 left-0 w-full h-1 bg-gradient-to-r from-transparent via-pink-400/50 to-transparent opacity-50"
              />
              <div class="absolute -top-40 -left-40 w-80 h-80 bg-pink-500/10 rounded-full blur-3xl" />
              <div class="absolute -bottom-40 -right-40 w-80 h-80 bg-pink-500/10 rounded-full blur-3xl" />

              <div class="relative z-10 space-y-12">
                <!-- Heading -->
                <div class="opacity-0 transition-all ease-out scroll-animate -translate-y-10 duration-[1000ms] space-y-4">
                  <div class="flex justify-center mb-6">
                    <div class="w-16 h-px bg-gradient-to-r from-transparent via-pink-300 to-transparent mx-2 my-auto" />
                    <i class="mdi mdi-gift-outline text-3xl md:text-4xl text-pink-300 mx-4" />
                    <div class="w-16 h-px bg-gradient-to-r from-transparent via-pink-300 to-transparent mx-2 my-auto" />
                  </div>
                  <h2 class="text-xs md:text-sm font-medium tracking-[0.4em] uppercase text-pink-200/80">{{ t("giftSub") }}</h2>
                  <p class="text-3xl font-serif italic font-light text-white tracking-wide mt-2">{{ t("giftTitle") }}</p>
                  <p class="text-white/70 text-sm md:text-base leading-relaxed max-w-xl mx-auto pt-4">{{ t("giftDesc") }}</p>
                </div>

                <!-- Cards Container -->
                <div class="flex flex-col gap-6 pt-6 max-w-2xl mx-auto w-full">
                  <!-- Card 1: Nomor Rekening BCA -->
                  <div class="opacity-0 transition-all ease-out scroll-animate translate-y-10 duration-[1000ms] delay-[400ms] bg-white/5 border border-white/10 rounded-2xl p-6 text-white flex flex-col justify-between hover:bg-white/10 hover:-translate-y-1 transition-all duration-300 group/card relative overflow-hidden"
                  >
                    <div
                      class="absolute inset-0 bg-gradient-to-b from-blue-500/5 to-transparent opacity-0 group-hover/card:opacity-100 transition-opacity duration-300"
                    />

                    <div class="space-y-4 relative z-10 flex-1 text-left">
                      <!-- Tambah Icon Bank Asli jika punya, untuk sementara pakai icon bank dummy -->
                      <div class="w-12 h-12 rounded-full bg-blue-400/20 flex items-center justify-center mb-6">
                        <UIcon
                          name="mdi:bank-outline"
                          class="w-6 h-6 text-blue-300"
                        />
                      </div>
                      <h3 class="font-serif italic text-2xl text-white">{{ t("bankTransfer") }}</h3>
                      <div class="space-y-2">
                        <p class="text-xs tracking-widest uppercase text-white/50 font-medium">
                          Mandiri - Gian Felix Sinaga
                        </p>
                        <p class="font-mono text-2xl text-white tracking-wider flex items-center gap-3">
                          1450014144972
                        </p>
                      </div>
                    </div>

                    <button
                      class="w-full mt-6 relative z-10 flex items-center justify-center gap-2 px-5 py-3.5 bg-blue-500 hover:bg-blue-600 text-white rounded-xl text-sm font-medium tracking-wide transition-all shadow-lg"
                      @click="copyText('1450014144972')"
                    >
                      <UIcon name="mdi:content-copy" class="w-5 h-5" /> {{ t("copyAcc") }}
                    </button>
                  </div>

                  <!-- Card 2: Gopay / E-Wallet -->
                  <div class="opacity-0 transition-all ease-out scroll-animate translate-y-10 duration-[1000ms] delay-[600ms] bg-white/5 border border-white/10 rounded-2xl p-6 text-white flex flex-col justify-between hover:bg-white/10 hover:-translate-y-1 transition-all duration-300 group/card relative overflow-hidden md:col-span-2 lg:col-span-1"
                  >
                    <div
                      class="absolute inset-0 bg-gradient-to-b from-green-500/5 to-transparent opacity-0 group-hover/card:opacity-100 transition-opacity duration-300"
                    />

                    <div class="space-y-4 relative z-10 flex-1 text-left">
                      <div class="w-12 h-12 rounded-full bg-green-400/20 flex items-center justify-center mb-6">
                        <UIcon
                          name="mdi:wallet-outline"
                          class="w-6 h-6 text-green-300"
                        />
                      </div>
                      <h3 class="font-serif italic text-2xl text-white">{{ t("digitalWallet") }}</h3>
                      <div class="space-y-2">
                        <p class="text-xs tracking-widest uppercase text-white/50 font-medium">
                          Dana - Kristiani Munthe
                        </p>
                        <p class="font-mono text-xl md:text-2xl text-white tracking-wider">
                          085835306808
                        </p>
                      </div>
                    </div>

                    <button
                      class="w-full mt-6 relative z-10 flex items-center justify-center gap-2 px-5 py-3.5 bg-green-500 hover:bg-green-600 text-white rounded-xl text-sm font-medium tracking-wide transition-all shadow-lg"
                      @click="copyText('085835306808')"
                    >
                      <UIcon name="mdi:content-copy" class="w-5 h-5" /> {{ t("copyNum") }}
                    </button>
                  </div>

                  <!-- Card 3: Kirim Kado / Alamat -->
                  <div class="opacity-0 transition-all ease-out scroll-animate translate-y-10 duration-[1000ms] delay-[200ms] bg-white/5 border border-white/10 rounded-2xl p-6 text-white flex flex-col justify-between hover:bg-white/10 hover:-translate-y-1 transition-all duration-300 group/card relative overflow-hidden"
                  >
                    <div
                      class="absolute inset-0 bg-gradient-to-b from-pink-500/5 to-transparent opacity-0 group-hover/card:opacity-100 transition-opacity duration-300"
                    />

                    <div class="space-y-4 relative z-10 flex-1 text-left">
                      <div class="w-12 h-12 rounded-full bg-pink-300/20 flex items-center justify-center mb-6">
                        <UIcon
                          name="mdi:home-heart"
                          class="w-6 h-6 text-pink-300"
                        />
                      </div>
                      <h3 class="font-serif italic text-2xl text-white">{{ t("physGift") }}</h3>
                      <p class="text-white/70 font-light text-sm leading-relaxed pb-4">
{{ t("physAddress") }}
</p>
                    </div>

                    <a
                      href="https://maps.app.goo.gl/nYpG8PgVewvY1wTT8"
                      target="_blank"
                      class="w-full relative z-10 flex items-center justify-center gap-2 px-5 py-3.5 bg-white/10 hover:bg-white/20 border border-white/10 rounded-xl text-sm font-medium tracking-wide transition-all text-white mt-auto"
                    >
                      <UIcon
                        name="mdi:google-maps"
                        class="w-5 h-5 text-pink-300"
                      /> Google Maps
                    </a>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>

        <!-- RSVP -->
        <section class="min-h-[100dvh] md:min-h-screen relative flex flex-col justify-center py-16 md:py-24">
          <!-- Background Video with elegant overlay -->
          <div class="absolute inset-0 -z-10 bg-[#1a1a1a]">
            <div class="absolute inset-0 bg-gradient-to-br from-pink-900/20 to-black z-0" />
            <video
          poster="/img/gian/cover.webp"
              autoplay
              muted
              loop
              playsinline
              class="w-full h-full object-cover opacity-60 z-10 relative mix-blend-screen"
            >
              <source
                src="/video/gian/Reels.mp4"
                type="video/mp4"
              >
            </video>
            <div
              class="absolute inset-0 bg-black/40 bg-[radial-gradient(circle_at_center,transparent_0%,rgba(0,0,0,0.8)_100%)] z-20 pointer-events-none"
            />
          </div>

          <div class="relative z-30 max-w-4xl mx-auto text-center px-6 md:px-12 w-full">
            <div class="flex flex-col gap-12">
              <!-- Top side: Header & Form -->
              <div class="space-y-8 lg:text-left">
                <!-- Judul + Intro -->
                <div class="opacity-0 transition-all ease-out scroll-animate -translate-x-10 duration-[1000ms] space-y-6 text-center lg:text-left">
                  <div class="flex justify-center lg:justify-start mb-4">
                    <i class="mdi mdi-flower-tulip-outline text-3xl md:text-5xl text-pink-300" />
                  </div>
                  <h2 class="text-xs md:text-sm font-medium tracking-[0.4em] uppercase text-pink-200/80">{{ t("rsvpSub") }}</h2>
                  <p class="text-3xl md:text-5xl font-serif italic font-light text-white tracking-wide mt-2">{{ t("rsvpTitle") }}</p>
                  <p class="text-white/70 text-sm md:text-lg leading-relaxed max-w-2xl mx-auto lg:mx-0">{{ t("rsvpDesc") }}</p>
                </div>

                <!-- Form RSVP -->
                <form class="opacity-0 transition-all ease-out scroll-animate translate-y-10 duration-[1000ms] delay-[200ms] bg-white/5 backdrop-blur-xl border border-white/10 rounded-3xl p-6 md:p-8 shadow-[0_8px_32px_rgba(0,0,0,0.4)] relative overflow-hidden group space-y-6"
                  @submit.prevent="submitRSVP"
                >
                  <div class="absolute -top-40 -right-40 w-80 h-80 bg-pink-500/10 rounded-full blur-3xl" />

                  <div class="relative z-10 space-y-6">
                    <!-- Nama Lengkap -->
                    <div class="flex flex-col text-left space-y-2">
                      <label
                        for="nama"
                        class="text-xs tracking-widest uppercase text-pink-200/80 font-medium ml-1"
                      >{{ t("fullName") }}</label>
                      <input
                        id="nama"
                        v-model="nama"
                        type="text"
                        name="nama"
                        :placeholder="t('fullNamePlaceholder')"
                        class="w-full px-5 py-3.5 rounded-2xl bg-white/5 border border-white/10 text-white placeholder-white/30 focus:outline-none focus:border-pink-300/50 focus:bg-white/10 transition-all font-light"
                        required
                      >
                    </div>

                    <!-- Konfirmasi Kehadiran -->
                    <div class="flex flex-col text-left space-y-3">
                      <p class="text-xs tracking-widest uppercase text-pink-200/80 font-medium ml-1">{{ t("confirmAttendance") }}</p>
                      <div class="flex flex-col sm:flex-row gap-4">
                        <label class="flex-1 cursor-pointer">
                          <input
                            v-model="kehadiran"
                            type="radio"
                            name="kehadiran"
                            value="Hadir"
                            class="peer sr-only"
                            required
                          >
                          <div
                            class="px-5 py-3.5 rounded-2xl bg-white/5 border border-white/10 text-white/70 text-center peer-checked:bg-pink-300/20 peer-checked:border-pink-300/50 peer-checked:text-white transition-all font-light hover:bg-white/10"
                          >{{ t("attendYes") }}</div>
                        </label>
                        <label class="flex-1 cursor-pointer">
                          <input
                            v-model="kehadiran"
                            type="radio"
                            name="kehadiran"
                            value="Tidak Hadir"
                            class="peer sr-only"
                          >
                          <div
                            class="px-5 py-3.5 rounded-2xl bg-white/5 border border-white/10 text-white/70 text-center peer-checked:bg-white/20 peer-checked:border-white/30 peer-checked:text-white transition-all font-light hover:bg-white/10"
                          >{{ t("attendNo") }}</div>
                        </label>
                      </div>
                    </div>

                    <!-- Ucapan & Doa -->
                    <div class="flex flex-col text-left space-y-2">
                      <label
                        for="ucapan"
                        class="text-xs tracking-widest uppercase text-pink-200/80 font-medium ml-1"
                      >{{ t("wishes") }}</label>
                      <textarea
                        id="ucapan"
                        v-model="ucapan"
                        name="ucapan"
                        rows="4"
                        :placeholder="t('wishesPlaceholder')"
                        class="w-full px-5 py-4 rounded-2xl bg-white/5 border border-white/10 text-white placeholder-white/30 focus:outline-none focus:border-pink-300/50 focus:bg-white/10 transition-all font-light resize-none"
                      />
                    </div>

                    <!-- Tombol Kirim -->
                    <button
                      type="submit"
                      class="w-full py-4 bg-pink-300 hover:bg-pink-400 text-gray-900 rounded-2xl text-sm font-medium tracking-wide transition-all duration-300 hover:shadow-[0_0_20px_rgba(249,168,212,0.4)] hover:-translate-y-1 flex justify-center items-center gap-2 mt-4"
                      :disabled="isSubmitting"
                    >
                      <span
                        v-if="isSubmitting"
                        class="animate-spin border-2 border-t-transparent border-gray-900 rounded-full w-5 h-5"
                      />
                      <span
                        v-else-if="submitSuccess === true"
                        class="text-green-700 flex items-center gap-2"
                      >
                        <UIcon
                          name="mdi:check-circle"
                          class="w-5 h-5"
                        /> {{ t("sentSuccess") }}
</span>
                      <span
                        v-else-if="submitSuccess === false"
                        class="text-red-600 flex items-center gap-2"
                      >
                        <UIcon
                          name="mdi:alert-circle"
                          class="w-5 h-5"
                        /> {{ t("sentFailed") }}
</span>
                      <span
                        v-else
                        class="flex items-center gap-2"
                      >
                        <UIcon
                          name="mdi:send-outline"
                          class="w-5 h-5"
                        /> {{ t("sendBtn") }}
</span>
                    </button>
                  </div>
                </form>
              </div>

              <!-- Bottom side: List Ucapan Tamu -->
              <div class="h-full">
                <div class="opacity-0 transition-all ease-out scroll-animate translate-x-10 duration-[1000ms] delay-[400ms] bg-white/5 backdrop-blur-xl border border-white/10 rounded-3xl p-6 h-full min-h-[500px] flex flex-col shadow-[0_8px_32px_rgba(0,0,0,0.4)] relative overflow-hidden group">
                  <div class="absolute -bottom-40 -left-40 w-80 h-80 bg-pink-500/10 rounded-full blur-3xl" />

                  <div class="relative z-10 flex flex-col h-full">
                    <!-- Judul tetap di atas -->
                    <div class="mb-6 border-b border-white/10 pb-4 flex items-center gap-3">
                      <UIcon
                        name="mdi:message-heart-outline"
                        class="w-6 h-6 text-pink-300"
                      />
                      <h3 class="text-xl font-serif italic text-white flex-1 text-left">
{{ t("wishesTitle") }}
</h3>
                      <span class="bg-pink-300/20 text-pink-200 text-xs px-2.5 py-1 rounded-full font-medium">
{{ guestMessages.length }} {{ t("messagesCount") }}
</span>
                    </div>

                    <!-- Container scrollable untuk card -->
                    <div class="flex-1 overflow-y-auto space-y-4 pr-2 max-h-[500px] md:max-h-[600px] scrollbar-hide">
                      <template v-if="guestMessages.length > 0">
                        <div
                          v-for="(entry, index) in guestMessages"
                          :key="index"
                          class="bg-white/5 border border-white/5 p-5 rounded-2xl space-y-3 hover:bg-white/10 transition-colors text-left"
                        >
                          <div class="flex justify-between items-start gap-4">
                            <p class="font-medium text-white text-sm md:text-base">
                              {{ entry.nama }}
                            </p>
                            <span
                              class="text-[10px] uppercase tracking-widest px-2 py-1 rounded-md shrink-0"
                              :class="entry.kehadiran === 'Hadir' ? 'bg-green-500/20 text-green-200' : 'bg-white/10 text-white/60'"
                            >
                              {{ entry.kehadiran === 'Hadir' ? t('attendBadge') : t('absentBadge') }}
                            </span>
                          </div>
                          <p class="text-white/70 text-sm font-light leading-relaxed">
                            "{{ entry.ucapan }}"
                          </p>
                          <p class="text-[10px] text-white/40 font-medium">
                            {{ formatDate(entry.tanggal) }}
                          </p>
                        </div>

                        <!-- Load More Button -->
                        <div v-if="hasMore" class="pt-4 pb-2 flex justify-center w-full">
                          <button
                            @click="loadMoreMessages"
                            :disabled="isLoadingMore"
                            class="px-6 py-2.5 bg-white/5 hover:bg-white/10 border border-white/10 hover:border-pink-300/30 rounded-full text-xs text-white transition-all flex items-center gap-2"
                          >
                            <span v-if="isLoadingMore" class="animate-spin border-2 border-t-transparent border-white rounded-full w-4 h-4"></span>
                            <span v-else>{{ t('loadMore') }}</span>
                          </button>
                        </div>
                      </template>
                      <template v-else>
                        <div
                          class="h-full flex flex-col items-center justify-center text-white/40 space-y-4 py-10 min-h-[300px]"
                        >
                          <UIcon
                            name="mdi:emoticon-happy-outline"
                            class="w-12 h-12 opacity-50"
                          />
                          <p class="text-sm">
{{ t("noWishes") }}
</p>
                        </div>
                      </template>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </section>

        <!-- GALERI -->
        <section class="min-h-[100dvh] md:min-h-screen relative flex flex-col justify-center py-16 md:py-24 overflow-hidden">
          <!-- Background -->
          <div class="absolute inset-0 -z-10 bg-[#1a1a1a]">
            <div class="absolute inset-0 bg-gradient-to-t from-pink-900/20 via-black to-black z-0" />
            <div
              class="absolute inset-0 bg-[radial-gradient(circle_at_center,rgba(249,168,212,0.05)_0%,transparent_100%)] z-10"
            />
          </div>

          <!-- Content -->
          <div class="relative z-30 max-w-6xl mx-auto px-6 md:px-12 w-full h-full flex flex-col">
            <!-- Header Section -->
            <div class="opacity-0 transition-all ease-out scroll-animate -translate-y-10 duration-[1000ms] text-center space-y-4 mb-10 md:mb-16">
              <div class="flex justify-center mb-4">
                <i class="mdi mdi-camera-outline text-3xl md:text-4xl text-pink-300" />
              </div>
              <h2 class="text-xs md:text-sm font-medium tracking-[0.4em] uppercase text-pink-200/80">{{ t("memoriesSub") }}</h2>
              <p class="text-4xl md:text-6xl font-serif italic font-light text-white tracking-wide mt-2">{{ t("memoriesTitle") }}</p>
            </div>

            <!-- Prewedding Video Card -->
            <div class="opacity-0 transition-all ease-out scroll-animate scale-95 duration-[1200ms] relative w-full bg-white/5 backdrop-blur-md border border-white/10 rounded-3xl p-4 md:p-6 shadow-[0_8px_32px_rgba(0,0,0,0.4)] mb-8">
              <div class="relative w-full max-w-[360px] aspect-[9/16] mx-auto">
                <iframe 
                  class="absolute inset-0 w-full h-full"
                  src="https://www.youtube.com/embed/xkNAcFxU6XI?autoplay=1&mute=1&loop=1&playlist=xkNAcFxU6XI"
                  title="Prewedding Video" 
                  frameborder="0" 
                  allow="autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
                  allowfullscreen
                ></iframe>
              </div>
            </div>

            <!-- Gallery Grid / Carousel Card -->
            <div class="opacity-0 transition-all ease-out scroll-animate scale-95 duration-[1200ms] delay-200 relative flex-1 w-full bg-white/5 backdrop-blur-md border border-white/10 rounded-3xl p-4 md:p-6 shadow-[0_8px_32px_rgba(0,0,0,0.4)] mt-4">
              <!-- Decorative ambient glow -->
              <div
                class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 w-[80%] h-[80%] bg-pink-500/10 rounded-full blur-[100px] pointer-events-none"
              />

              <!-- Image Display -->
              <div class="relative w-full h-[65dvh] lg:h-[75vh] rounded-2xl overflow-hidden group">
                <!-- Main Featured Images -->
                <transition-group
                  name="fade"
                  tag="div"
                  class="absolute inset-0 w-full h-full"
                >
                  <div
                    v-for="(img, idx) in images"
                    v-show="current === idx"
                    :key="'main-' + idx"
                    class="absolute inset-0 w-full h-full"
                  >
                    <img
                      :src="img"
                      class="absolute inset-0 w-full h-full object-cover transition-transform duration-[10000ms] ease-linear hover:scale-105 cursor-pointer"
                      @click="openLightbox(img)"
                    >
                    <!-- Vignette Overlay -->
                    <div
                      class="absolute inset-0 bg-gradient-to-t from-black/80 via-transparent to-black/30 pointer-events-none mix-blend-multiply"
                    />
                  </div>
                </transition-group>

                <!-- Navigation Controls (Hover visible on desktop) -->
                <div
                  class="absolute inset-0 flex items-center justify-between px-4 opacity-100 md:opacity-0 group-hover:opacity-100 transition-opacity duration-300 z-20 pointer-events-none"
                >
                  <button
                    class="w-12 h-12 rounded-full bg-black/40 backdrop-blur-md border border-white/20 text-white flex items-center justify-center hover:bg-pink-500/80 hover:border-pink-300 transition-all hover:scale-110 pointer-events-auto"
                    @click.stop="prevSlide"
                  >
                    <UIcon
                      name="mdi:chevron-left"
                      class="w-8 h-8"
                    />
                  </button>
                  <button
                    class="w-12 h-12 rounded-full bg-black/40 backdrop-blur-md border border-white/20 text-white flex items-center justify-center hover:bg-pink-500/80 hover:border-pink-300 transition-all hover:scale-110 pointer-events-auto"
                    @click.stop="nextSlide"
                  >
                    <UIcon
                      name="mdi:chevron-right"
                      class="w-8 h-8"
                    />
                  </button>
                </div>

                <!-- Open Lightbox Hint -->
                <div
                  class="absolute bottom-6 left-1/2 -translate-x-1/2 flex items-center gap-2 px-4 py-2 bg-black/40 backdrop-blur-md rounded-full border border-white/10 z-20 pointer-events-none opacity-100 md:opacity-0 group-hover:opacity-100 transition-opacity duration-500 delay-100"
                >
                  <UIcon
                    name="mdi:magnify-plus-outline"
                    class="w-4 h-4 text-pink-300"
                  />
                  <span class="text-xs text-white uppercase tracking-widest font-medium whitespace-nowrap">{{ t("tapEnlarge") }}</span>
                </div>
              </div>

              <!-- Thumbnails / Pagination -->
              <div
                ref="thumbContainer"
                class="mt-6 md:mt-8 flex justify-start gap-3 overflow-x-auto py-4 custom-scrollbar px-2"
              >
                <button
                  v-for="(img, idx) in images"
                  :key="'thumb-' + idx"
                  :ref="(el: any) => { if (el) thumbs[idx] = el }"
                  class="relative w-16 h-16 md:w-24 md:h-24 flex-shrink-0 rounded-xl overflow-hidden border-2 transition-all duration-300"
                  :class="current === idx ? 'border-pink-400 scale-110 shadow-[0_0_15px_rgba(249,168,212,0.5)] z-10' : 'border-transparent opacity-50 hover:opacity-100 hover:scale-105'"
                  @click="current = idx"
                >
                  <img
                    :src="img"
                    class="w-full h-full object-cover"
                  >
                  <div
                    class="absolute inset-0 bg-black/20"
                    :class="current === idx ? 'opacity-0' : 'opacity-100'"
                  />
                </button>
              </div>
            </div>
          </div>
        </section>

        <!-- FOOTER / THANK YOU -->
        <section class="relative w-full min-h-[100dvh] md:min-h-screen overflow-hidden flex flex-col">
          <!-- Background Gradient Vertikal -->
          <div class="absolute inset-0 -z-10">
            <div class="absolute inset-0 bg-gradient-to-b from-pink-800/30 via-black/70 to-black/95" />
            <div
              class="absolute inset-0 bg-[radial-gradient(circle_at_top,rgba(249,168,212,0.05)_0%,transparent_100%)] z-10"
            />
          </div>

          <!-- Main Content (Centered) -->
          <div class="relative z-20 max-w-4xl mx-auto text-center px-6 md:px-12 flex flex-col justify-center flex-1">
            <!-- Heart / Ornament -->
            <div class="flex justify-center mb-6">
              <i class="mdi mdi-heart text-4xl text-pink-300 animate-pulse" />
            </div>

            <!-- Thank You Text -->
            <p class="opacity-0 transition-all ease-out scroll-animate translate-y-10 duration-[1000ms] text-xl md:text-2xl font-serif italic font-light text-white/90 mb-4">
{{ t("thankYouText") }}
</p>

            <!-- Small Note -->
            <p class="text-sm md:text-base text-white/60 tracking-wide mb-6">
{{ t("thankYouSub") }}
</p>

            <!-- Footer Branding / Couple Name -->
            <p class="text-pink-200 text-sm md:text-base uppercase tracking-[0.25em] font-medium mb-4">
              Gian & Kristiani
            </p>

            <!-- Keevia Label Before Instagram -->
            <p class="text-white/50 text-xs md:text-sm mb-3">
              Keevia.id Digital Invitation
            </p>

            <!-- Instagram Perusahaan -->
            <div class="flex justify-center gap-4">
              <a
                href="https://instagram.com/keevia.id"
                target="_blank"
                rel="noopener noreferrer"
                class="w-10 h-10 rounded-full bg-white/10 backdrop-blur-md border border-white/20 text-white flex items-center justify-center hover:bg-pink-400 hover:border-pink-300 transition-all hover:scale-110"
              >
                <UIcon
                  name="mdi:instagram"
                  class="w-5 h-5"
                />
              </a>
            </div>
          </div>

          <!-- Bottom Rights (Always at Bottom) -->
          <div class="relative z-20 text-center mt-auto py-4 text-white/40 text-xs md:text-sm border-t border-white/10">
            &copy; 2026 Keevia.id. All Rights Reserved.
          </div>
        </section>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">

import { ref, onMounted, computed, inject, watch, nextTick } from 'vue'
import { useRoute } from 'vue-router'
import { useNuxtApp } from '#app'

const isVideoPlaying = ref(false)
const isLoading = ref(true)
const loadingProgress = ref(0)

// Daftar gambar
const images = ref<string[]>([
  '/img/gian/gallery/gallery_1.JPEG',
  '/img/gian/gallery/gallery_2.JPEG',
  '/img/gian/gallery/gallery_3.JPEG',
  '/img/gian/gallery/gallery_4.JPEG',
  '/img/gian/gallery/gallery_5.JPEG',
  '/img/gian/gallery/gallery_6.JPEG',
  '/img/gian/gallery/gallery_7.JPEG',
  '/img/gian/gallery/gallery_8.JPEG',
  '/img/gian/gallery/gallery_9.JPEG',
  '/img/gian/gallery/gallery_10.JPEG',
  '/img/gian/gallery/gallery_11.JPEG',
  '/img/gian/gallery/gallery_12.JPEG',
  '/img/gian/gallery/gallery_13.JPEG',
  '/img/gian/gallery/gallery_14.JPEG',
  '/img/gian/gallery/gallery_15.JPEG',
])

const current = ref(0)
let _interval: number | undefined

const nextSlide = () => {
  current.value = (current.value + 1) % images.value.length
}

const prevSlide = () => {
  current.value
    = (current.value - 1 + images.value.length) % images.value.length
}

// Refs untuk thumbnail container & items
const rightPanel = ref<HTMLElement | null>(null)
const thumbContainer = ref<HTMLElement | null>(null)
const thumbs = ref<HTMLElement[]>([])

// Scroll thumbnail aktif ke tengah
const scrollThumbIntoView = () => {
  nextTick(() => {
    if (!thumbContainer.value || !thumbs.value.length) return
    const container = thumbContainer.value
    const activeThumb = thumbs.value[current.value]
    if (!activeThumb) return

    const containerRect = container.getBoundingClientRect()
    const thumbRect = activeThumb.getBoundingClientRect()

    // Calculate actual center taking into account scroll position
    const scrollLeftTo = activeThumb.offsetLeft - (containerRect.width / 2) + (activeThumb.offsetWidth / 2)
    container.scrollTo({
      left: scrollLeftTo,
      behavior: 'smooth'
    })
  })
}

// Watch current slide
watch(current, () => {
  scrollThumbIntoView()
})


// Simple Lightbox
const openLightbox = (src: string) => {
  const lightbox = document.createElement('div')
  lightbox.className = 'fixed inset-0 bg-black/80 z-50 flex items-center justify-center cursor-pointer'
  lightbox.innerHTML = `<img src="${src}" class="max-h-[90vh] max-w-[90vw] rounded-2xl shadow-lg" />`
  lightbox.onclick = () => lightbox.remove()
  document.body.appendChild(lightbox)
}

// AUDIO CONTROL
const audioControl = inject('audioControl') as {
  isPlaying: Ref<boolean>
  toggleAudio: () => void
  play: () => void
  pause: () => void
} | undefined

const route = useRoute()

const dict = {
  id: {
    weddingOf: "Pernikahan",
    dateFull: "Sabtu, 25 April 2026",
    toYth: "Kepada Yth.",
    openingMsg: "Merupakan suatu kehormatan dan kebahagiaan bagi kami apabila Bapak/Ibu/Saudara/i berkenan hadir untuk memberikan doa restu.",
    openBtn: "BUKA UNDANGAN",
    bibleQuote: "“Sebab itu seorang laki-laki akan meninggalkan ayahnya dan ibunya dan bersatu dengan isterinya, sehingga keduanya menjadi satu daging.”",
    bibleVerse: "Kejadian 2:24",
    theGroom: "Mempelai Pria",
    sonOf: "Putra Pertama dari",
    parentsGroom: "Bapak Ranal Sinaga & Ibu Merianta br Purba",
    theBride: "Mempelai Wanita",
    daughterOf: "Putri Kedua dari",
    parentsBride: "Bapak Manuel Munthe & Ibu Henny br Girsang",
    journeySub: "Kisah Cinta Menuju Pelaminan",
    journeyTitle: "Lembaran Baru Kami",
    ch1DateAbbr: "2018-2019",
    ch1DateFull: "2018-2019",
    ch1Title: "Pertemuan Pertama",
    ch1Desc: "Pada tahun 2018, Gian dan Kristi bertemu di gereja. Tahun 2019 kami melayani bersama di sekolah minggu. Pada awalnya, perbedaan karakter dan latar belakang membuat kami tidak saling tertarik, namun Tuhan perlahan menumbuhkan sesuatu yang indah di antara kami.",
    ch2DateAbbr: "2020-2025",
    ch2DateFull: "2020-2025",
    ch2Title: "Saling Melengkapi",
    ch2Desc: "Kami juga memiliki visi hidup yang berbeda, sehingga perjalanan ini tidak selalu mudah. Namun pada tahun 2021, Tuhan mempersatukan kami dalam visi baru melalui sebuah komunitas. Sejak itu, Kristus menjadi fondasi hubungan kami dan kasih di antara kami semakin bertumbuh dan berwarna.",
    ch3DateAbbr: "April 2026",
    ch3DateFull: "April 2026",
    ch3Title: "Melangkah Bersama",
    ch3Desc: "Enam tahun perjalanan ini dipimpin oleh kasih Kristus hingga kami tiba di bab ini. Dengan berkat dan penyertaan-Nya, kami melangkah ke perjalanan baru yang indah—bersama Dia, selamanya.",
    saveOurDate: "Menuju Hari Bahagia",
    dateMain: "Sabtu, 25 April 2026",
    days: "Hari",
    hours: "Jam",
    minutes: "Menit",
    seconds: "Detik",
    saveToCal: "Simpan Tanggal",
    pemberkatanTitle: "Pemberkatan Pernikahan",
    pemberkatanTime: "09.00 - 11.00 WITA",
    pemberkatanLocation: "Jl. RE Martadinata Jl. Raya Pelabuhan Benoa, Benoa, Denpasar Selatan, Kota Denpasar, Bali 80119",
    resepsiTitle: "Youth Party",
    adatTitle : "Adat",
    resepsiTime: "11.30 - 12.30 WITA",
    adatTime : "12.30 - Selesai",
    resepsiLocation: "Jl. WR Supratman No.302, Kesiman Kertalangu, Kec. Denpasar Tim., Kota Denpasar, Bali 80237",
    openMap: "Buka Google Maps",
    rsvpSub: "Konfirmasi Kehadiran",
    rsvpTitle: "Kehadiran Tanda Kasih",
    rsvpDesc: "Langkah ini tidak akan terasa sempurna tanpa kehadiran serta iringan doa dari seluruh kerabat dan sahabat tercinta.",
    fullName: "Nama Lengkap",
    fullNamePlaceholder: "Tulis nama Anda?",
    confirmAttendance: "Konfirmasi Kehadiran Turut Serta",
    attendYes: "Ya, Saya Akan Hadir",
    attendNo: "Maaf, Berhalangan",
    wishes: "Ruang Tanda Sayang",
    wishesPlaceholder: "Tinggalkan doa dan ucapan hangat untuk pengantin",
    sending: "Sedang Mengirim...",
    sentSuccess: "Pesan Berhasil Terkirim",
    sentFailed: "Gagal Mengirim, Coba Kembali",
    sendBtn: "Kirim Ucapan",
    wishesTitle: "Ucapan & Doa",
    messagesCount: "Pesan",
    attendBadge: "✔️ Hadir",
    absentBadge: "❌ Berhalangan",
    noWishes: "Jadilah yang pertama untuk berbagi ucapan dan doa!",
    loadMore: "Muat Pesan Lainnya",
    giftSub: "Titipan Kasih",
    giftTitle: "Hadiah Pernikahan",
    giftDesc: "Kehadiran dan restu Anda adalah hadiah terbaik bagi kami. Namun, jika Anda ingin memberikan tanda kasih sayang berupa hadiah fisik atau digital, Anda dapat menggunakan opsi di bawah ini.",
    physGift: "Alamat Pengiriman",
    physAddress: "Jl. PB. Sudirman II No. 4, Denpasar Barat, Bali",
    bankTransfer: "Transfer Nomor Rekening",
    copyAcc: "Salin Ke Papan Klip",
    digitalWallet: "Dompet Digital",
    copyNum: "Salin Nomor",
    memoriesSub: "Potret Kasih",
    memoriesTitle: "Galeri",
    tapEnlarge: "Ketuk Untuk Memperbesar",
    thankYouText: "Terima kasih yang sebesar-besarnya atas restu dan ketersediaan waktu untuk menghadiri momen istimewa kami.",
    thankYouSub: "Rahmat dan damai sejahtera senantiasa membersamai langkah kehidupan kita."
  },
  en: {
    weddingOf: "The Wedding Of",
    dateFull: "Saturday, April 25th 2026",
    toYth: "Dear",
    openingMsg: "It is an honor and joy for us if you would be willing to attend and give your blessings.",
    openBtn: "OPEN INVITATION",
    bibleQuote: '“Therefore shall a man leave his father and his mother, and shall cleave unto his wife: and they shall be one flesh.”',
    bibleVerse: "Genesis 2:24",
    theGroom: "The Groom",
    sonOf: "First Son of",
    parentsGroom: "Mr. Ranal Sinaga & Mrs. Merianta br Purba",
    theBride: "The Bride",
    daughterOf: "Second Daughter of",
    parentsBride: "Mr. Manuel Munthe & Mrs. Henny br Girsang",
    journeySub: "A Journey in Love",
    journeyTitle: "The Unfinished Chapter",
    ch1DateAbbr: "2018-2019",
    ch1DateFull: "2018-2019",
    ch1Title: "The Unexpected Comeback",
    ch1Desc: "In 2018, Gian and Kristi met at church. By 2019, we were serving together in Sunday School. At first, our different characters and backgrounds meant there was no mutual attraction, but slowly, God grew something beautiful between us.",
    ch2DateAbbr: "2020-2025",
    ch2DateFull: "2020-2025",
    ch2Title: "The Beautiful Mess",
    ch2Desc: "We also held different visions for our lives, which made this journey far from easy. But in 2021, God united us with a new, shared vision through a community. Since then, Christ has become the foundation of our relationship, and the love between us continues to grow and flourish in vibrant color.",
    ch3DateAbbr: "April 2026",
    ch3DateFull: "April 2026",
    ch3Title: "The Forever Chapter",
    ch3Desc: "This six-year journey has been led by the love of Christ, bringing us to this very chapter. With His blessing and guidance, we are stepping into a beautiful new journey—together with Him, forever.",
    saveOurDate: "Save Our Date",
    dateMain: "Saturday, April 25th 2026",
    days: "Days",
    hours: "Hours",
    minutes: "Mins",
    seconds: "Secs",
    saveToCal: "Save to Calendar",
    pemberkatanTitle: "Holy Matrimony",
    pemberkatanTime: "09.00 - 11.00 WITA",
    pemberkatanLocation: "Jl. RE Martadinata Jl. Raya Pelabuhan Benoa, Benoa, Denpasar Selatan, Kota Denpasar, Bali 80119",
    resepsiTitle: "Youth Party",
    adatTitle : "Cultural Ceremony",
    resepsiTime: "11.30 - 12.30 WITA",
    adatTime : "12.30 - End",
    resepsiLocation: "Jl. WR Supratman No.302, Kesiman Kertalangu, Kec. Denpasar Tim., Kota Denpasar, Bali 80237",
    openMap: "Open in Google Maps",
    rsvpSub: "RSVP & Wishes",
    rsvpTitle: "Your Presence",
    rsvpDesc: "It is an honor and joy for us if you would be willing to attend and give your blessings.",
    fullName: "Full Name",
    fullNamePlaceholder: "Write your name",
    confirmAttendance: "Confirm Attendance",
    attendYes: "Yes, I will attend",
    attendNo: "Sorry, I cannot attend",
    wishes: "Wishes & Prayers",
    wishesPlaceholder: "Give your best wishes for the bride and groom",
    sending: "Sending...",
    sentSuccess: "Successfully Sent",
    sentFailed: "Failed, Try Again",
    sendBtn: "Send RSVP",
    wishesTitle: "Wishes & Prayers",
    messagesCount: "Messages",
    attendBadge: "✔️ Attending",
    absentBadge: "❌ Not Attending",
    noWishes: "No wishes yet. Be the first to send one!",
    loadMore: "Load More",
    giftSub: "Wedding Gift",
    giftTitle: "Token of Love",
    giftDesc: "Your presence and blessings are the best gifts for us. However, if you wish to give a token of love in the form of a physical or digital gift, you can use the options below.",
    physGift: "Send Physical Gift",
    physAddress: "Jl. PB. Sudirman II No. 4, Denpasar Barat, Bali",
    bankTransfer: "Bank Transfer",
    copyAcc: "Copy Account",
    digitalWallet: "Digital Wallet",
    copyNum: "Copy Number",
    memoriesSub: "Portraits of Love",
    memoriesTitle: "Gallery",
    tapEnlarge: "Tap to Enlarge",
    thankYouText: "Thank you for the prayers, love, and your presence on our happy day.",
    thankYouSub: "May happiness and love always be with us all."
  }
}

const lang = computed(() => {
  const l = route.query.lang as string
  return (l === 'en' ? 'en' : 'id')
})

const t = (key: keyof typeof dict.id) => dict[lang.value as 'id'|'en'][key]

const guestName = computed(() => (route.query.to as string) || 'Tamu Undangan')

const isOpen = ref(false)
const openInvitation = () => {
  isOpen.value = true
  document.body.classList.remove('overflow-hidden')

  nextTick(() => {
    initScrollAnimations()
  })

  if (audioControl && !audioControl.isPlaying.value) {
    audioControl.play()
  }

  startCountdown()

  // Force play all background videos upon user interaction
  document.querySelectorAll('video').forEach(vid => {
    const playPromise = vid.play()
    if (playPromise !== undefined) {
      playPromise.catch(() => {})
    }
  })
}

// Start interval if open
watch(isOpen, (val) => {
  if (val) {
    _interval = window.setInterval(nextSlide, 4000)
  } else {
    clearInterval(_interval)
    current.value = 0 // reset ke data pertama
  }
})

const initScrollAnimations = () => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach(entry => {
      if (entry.isIntersecting) {
        entry.target.classList.remove('opacity-0', 'translate-y-10', '-translate-y-10', 'translate-x-10', '-translate-x-10', 'scale-95')
        entry.target.classList.add('opacity-100', 'translate-y-0', 'translate-x-0', 'scale-100')
        observer.unobserve(entry.target)
      }
    })
  }, { threshold: 0.1, rootMargin: '0px 0px -50px 0px' })

  document.querySelectorAll('.scroll-animate').forEach(el => observer.observe(el))
}

onMounted(() => {
  // Simulate loading progress
  const duration = 2000 // 2 seconds minimum loading time
  const intervalTime = 30
  const steps = duration / intervalTime
  let currentStep = 0

  const loadingInterval = setInterval(() => {
    currentStep++
    loadingProgress.value = Math.min(Math.round((currentStep / steps) * 100), 100)
    
    if (currentStep >= steps) {
      clearInterval(loadingInterval)
      setTimeout(() => {
        isLoading.value = false
        // Start scroll animations slightly after preloader starts fading out
        setTimeout(() => {
          initScrollAnimations()
        }, 500)
      }, 500)
    }
  }, intervalTime)

  // Force play videos
  document.querySelectorAll('video').forEach(vid => {
    const playPromise = vid.play()
    if (playPromise !== undefined) {
      playPromise.catch(e => console.warn('Autoplay prevented:', e))
    }
  })

  document.body.classList.add('overflow-hidden') // Require visitor to open invitation to scroll

  // Interval dipindahkan ke watcher / observer
  if (thumbContainer.value) {
    // // Manual select removed // removed manual select
  }
})

// Countdown
const countdown = ref({
  days: '00',
  hours: '00',
  minutes: '00',
  seconds: '00'
})

const saveOurDate = new Date('April 25, 2026 09:00:00').getTime()
let countdownInterval: ReturnType<typeof setInterval>

const startCountdown = () => {
  countdownInterval = setInterval(() => {
    const now = new Date().getTime()
    const distance = saveOurDate - now

    countdown.value.days = String(Math.floor(distance / (1000 * 60 * 60 * 24))).padStart(2, '0')
    countdown.value.hours = String(Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60))).padStart(2, '0')
    countdown.value.minutes = String(Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60))).padStart(2, '0')
    countdown.value.seconds = String(Math.floor((distance % (1000 * 60)) / 1000)).padStart(2, '0')

    if (distance < 0) {
      clearInterval(countdownInterval)
      countdown.value.days = countdown.value.hours = countdown.value.minutes = countdown.value.seconds = '00'
    }
  }, 1000)
}

// Firebase
interface FirebasePlugin {
  db: ReturnType<typeof import('firebase/firestore').getFirestore>
  collection: typeof import('firebase/firestore').collection
  addDoc: typeof import('firebase/firestore').addDoc
  serverTimestamp: typeof import('firebase/firestore').serverTimestamp
}

const firebase = import.meta.client
  ? (useNuxtApp().$firebase as FirebasePlugin)
  : null

// Collection reference
const rsvpCollection = import.meta.client && firebase
  ? firebase.collection(firebase.db, 'rsvp_messages')
  : null

//  Form state
const nama = ref('')
const kehadiran = ref('')
const ucapan = ref('')

// Guest messages type
interface GuestMessage {
  nama: string
  kehadiran: 'Hadir' | 'Tidak Hadir'
  ucapan: string
  tanggal: Date
}

const guestMessages = ref<GuestMessage[]>([])

//  Google Apps Script URL
const GOOGLE_SCRIPT_URL = 'https://script.google.com/macros/s/AKfycby4kUYXnmoRNCgVGHhs9H-uG-yi0LLE3LJFxYNHXX1WRecd4ynUos3Y-6Ou_QiiotXH/exec'

//  Submit RSVP
const isSubmitting = ref(false)
const submitSuccess = ref<boolean | null>(null) // null = idle, true = sukses, false = error

const submitRSVP = async () => {
  if (!import.meta.client) return
  if (!firebase || !rsvpCollection) return
  if (!nama.value || !kehadiran.value) return

  isSubmitting.value = true
  submitSuccess.value = null

  try {
    await firebase.addDoc(rsvpCollection, {
      nama: nama.value,
      kehadiran: kehadiran.value,
      ucapan: ucapan.value,
      tanggal: firebase.serverTimestamp()
    })

    // Update locally so it appears immediately
    guestMessages.value.unshift({
      nama: nama.value,
      kehadiran: kehadiran.value as 'Hadir' | 'Tidak Hadir',
      ucapan: ucapan.value,
      tanggal: new Date()
    })

    // Google Sheet
    const params = new URLSearchParams({
      nama: nama.value,
      kehadiran: kehadiran.value
    })

    await fetch(`${GOOGLE_SCRIPT_URL}?${params.toString()}`)

    submitSuccess.value = true
  } catch (err) {
    console.error(err)
    submitSuccess.value = false
  } finally {
    isSubmitting.value = false

    // reset form & ikon sukses/error setelah 2 detik
    setTimeout(() => {
      submitSuccess.value = null
      nama.value = ''
      kehadiran.value = ''
      ucapan.value = ''
    }, 2000)
  }
}

// Pagination state
const lastVisible = ref<any>(null)
const hasMore = ref(true)
const isLoadingMore = ref(false)

// Fetch initial guest messages
const fetchGuestMessages = async () => {
  if (!import.meta.client || !firebase || !rsvpCollection) return

  const { query, orderBy, limit, getDocs } = await import('firebase/firestore')

  const q = query(rsvpCollection, orderBy('tanggal', 'desc'), limit(10))
  const snapshot = await getDocs(q)

  if (snapshot.empty) {
    hasMore.value = false
    return
  }

  lastVisible.value = snapshot.docs[snapshot.docs.length - 1]
  hasMore.value = snapshot.docs.length === 10

  guestMessages.value = snapshot.docs.map((doc) => {
    const data = doc.data()
    return {
      nama: data.nama,
      kehadiran: data.kehadiran,
      ucapan: data.ucapan,
      tanggal: data.tanggal?.toDate?.() || new Date()
    }
  })
}

// Load more messages
const loadMoreMessages = async () => {
  if (!import.meta.client || !firebase || !rsvpCollection || !lastVisible.value) return
  isLoadingMore.value = true

  try {
    const { query, orderBy, limit, getDocs, startAfter } = await import('firebase/firestore')
    const q = query(rsvpCollection, orderBy('tanggal', 'desc'), startAfter(lastVisible.value), limit(10))
    const snapshot = await getDocs(q)

    if (snapshot.empty) {
      hasMore.value = false
      return
    }

    lastVisible.value = snapshot.docs[snapshot.docs.length - 1]
    hasMore.value = snapshot.docs.length === 10

    const newMessages = snapshot.docs.map((doc) => {
      const data = doc.data()
      return {
        nama: data.nama,
        kehadiran: data.kehadiran,
        ucapan: data.ucapan,
        tanggal: data.tanggal?.toDate?.() || new Date()
      }
    })

    guestMessages.value = [...guestMessages.value, ...newMessages]
  } catch (err) {
    console.error('Error loading more messages:', err)
  } finally {
    isLoadingMore.value = false
  }
}

// Format tanggal
const formatDate = (d: Date) => new Date(d).toLocaleString('id-ID', {
  dateStyle: 'medium',
  timeStyle: 'short'
})

onMounted(() => {
  if (import.meta.client) {
    fetchGuestMessages()
  }
})

const copyText = (text: string) => {
  navigator.clipboard.writeText(text)
    .then(() => {
      showToast(`Berhasil disalin`)
    })
    .catch(() => {
      showToast('Gagal menyalin', true)
    })
}

const showToast = (message: string, _isError = false) => {
  const toast = document.createElement('div')
  toast.textContent = message
  toast.className = `
    fixed top-6 left-1/2 transform -translate-x-1/2
    z-50 px-6 py-3 rounded-2xl text-white backdrop-blur-md bg-white/10
    font-medium text-center
    shadow-lg
    transition-all duration-300
  `
  document.body.appendChild(toast)

  // otomatis fade out dan hilang setelah 2 detik
  setTimeout(() => {
    toast.style.opacity = '0'
    toast.style.transform = 'translate(-50%, -20px)'
    setTimeout(() => toast.remove(), 300)
  }, 2000)
}
</script>

<style>
html, body {
  scroll-behavior: smooth;
  overflow-x: hidden;
  width: 100%;
}

.scroll-animate {
  will-change: opacity, transform;
  transform: translateZ(0); /* Hardware acceleration iOS */
  backface-visibility: hidden;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 1s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
