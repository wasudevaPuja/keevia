<template>
    <div
        class="flex flex-col w-full min-h-[100dvh] bg-[#fdfaf5] text-[#4a3f35] font-sans selection:bg-amber-100 selection:text-amber-900 overflow-x-hidden">

        <!-- Top Progress Bar -->
        <div class="fixed top-0 left-0 h-1 bg-amber-400/50 z-[60] transition-all duration-300 pointer-events-none"
            :style="{ width: scrollProgress + '%' }" />


        <!-- 1. HERO SECTION -->
        <section class="relative w-full h-[100svh] flex items-center justify-center overflow-hidden bg-[#1a1510] px-4">
            <!-- Cinematic Background -->
            <div class="absolute inset-0 z-0">
                <div
                    class="absolute inset-0 bg-[radial-gradient(circle_at_center,_var(--tw-gradient-stops))] from-amber-900/20 via-black to-black opacity-60">
                </div>
                <div
                    class="absolute inset-0 bg-[url('https://www.transparenttextures.com/patterns/natural-paper.png')] opacity-10 mix-blend-overlay">
                </div>
            </div>

            <!-- Animated Light Leak -->
            <div
                class="absolute -top-[20%] -left-[10%] w-[60%] h-[60%] bg-amber-400/5 blur-[120px] rounded-full animate-pulse-slow">
            </div>
            <div
                class="absolute -bottom-[20%] -right-[10%] w-[60%] h-[60%] bg-amber-600/5 blur-[120px] rounded-full animate-pulse-slow delay-1000">
            </div>

            <!-- Content -->
            <div class="relative z-10 flex flex-col items-center text-center px-6 max-w-5xl">
                <div class="opacity-0 translate-y-8 scale-95 transition-all duration-[1500ms] cubic-bezier(0.2, 0, 0, 1)"
                    :class="{ 'opacity-100 translate-y-0 scale-100': hasMounted }">
                    <!-- Elegant Badge -->
                    <div class="inline-flex items-center gap-4 mb-6 md:mb-12">
                        <div class="w-8 h-px bg-white/20"></div>
                        <span
                            class="text-[9px] md:text-[11px] tracking-[0.6em] uppercase font-medium text-amber-200/80 drop-shadow-sm">
                            {{ t('pawiwahanTitle') }}
                        </span>
                        <div class="w-8 h-px bg-white/20"></div>
                    </div>

                    <!-- Artistic Typography -->
                    <div class="relative mb-8 md:mb-12">
                        <h1
                            class="text-4xl md:text-7xl font-display leading-[1.1] text-white flex flex-col md:flex-row items-center justify-center gap-2 md:gap-8">
                            <span class="relative">
                                {{ groomName }}
                                <div
                                    class="absolute -bottom-2 left-0 w-full h-px bg-gradient-to-r from-transparent via-white/10 to-transparent">
                                </div>
                            </span>
                            <span
                                class="italic text-amber-300/80 font-serif text-3xl md:text-5xl my-2 md:my-0 drop-shadow-lg">&</span>
                            <span class="relative">
                                {{ brideName }}
                                <div
                                    class="absolute -bottom-2 left-0 w-full h-px bg-gradient-to-r from-transparent via-white/10 to-transparent">
                                </div>
                            </span>
                        </h1>
                    </div>

                    <p class="text-[10px] md:text-xs tracking-[0.5em] font-light uppercase text-white/60 mb-12 md:mb-20">
                        {{ weddingDate }}
                    </p>

                    <!-- Decorative Reveal Area -->
                    <div class="relative w-full flex justify-center py-6 md:py-10 min-h-[100px]">
                        <!-- Transition Decoration -->
                        <div class="absolute inset-0 flex justify-center items-center transition-all duration-[2000ms] ease-out-expo"
                            :class="isOpen ? 'scale-100' : 'opacity-0 scale-75 pointer-events-none'">
                            <div class="relative group">
                                <NuxtImg
                                    src="https://res.cloudinary.com/debcjiypk/image/upload/v1773585924/bali_gold_motif-removebg-preview_p8kxmm.png"
                                    class="w-25 md:w-25 relative z-10" />
                            </div>
                        </div>

                        <!-- Premium Invitation Card -->
                        <div class="relative w-full max-w-sm transition-all duration-[1200ms] ease-in-out"
                            :class="isOpen ? 'opacity-0 -translate-y-12 scale-90 pointer-events-none' : 'opacity-100 translate-y-0 scale-100'">
                            <!-- Card Glow -->
                            <div
                                class="absolute -inset-1 bg-gradient-to-b from-amber-400/20 to-transparent opacity-30 blur-2xl rounded-[40px]">
                            </div>

                            <div
                                class="relative p-7 sm:p-10 rounded-[40px] bg-white/[0.04] backdrop-blur-3xl border border-white/10 shadow-[0_40px_100px_-20px_rgba(0,0,0,0.6)] ring-1 ring-white/10 overflow-hidden group">
                                <!-- Geometric Accent -->
                                <div class="absolute top-0 right-0 w-32 h-32 bg-amber-400/5 blur-3xl -tr-10 -te-10">
                                </div>

                                <p class="text-[9px] tracking-[0.5em] uppercase font-bold text-white/30 mb-4">{{
                                    t('guestLabel') }}</p>
                                <h3 class="text-2xl sm:text-3xl font-serif text-white mb-6 md:mb-8 tracking-wide font-light">{{ guestName }}
                                </h3>

                                <p
                                    class="text-xs sm:text-sm md:text-base font-extralight leading-relaxed text-white/50 font-serif italic mb-8 md:mb-10 px-4">
                                    {{ t('inviteText') }}
                                </p>

                                <button @click="openInvitation"
                                    class="relative overflow-hidden w-full px-10 py-4 md:py-5 bg-white text-black rounded-2xl hover:bg-amber-50 transition-all font-bold tracking-[0.3em] text-[9px] group shadow-[0_20px_40px_rgba(255,255,255,0.1)] active:scale-95">
                                    <span class="relative z-10">{{ t('openButton') }}</span>
                                    <!-- Shimmer Effect -->
                                    <div
                                        class="absolute inset-0 bg-gradient-to-r from-transparent via-black/5 to-transparent -translate-x-full group-hover:translate-x-full transition-transform duration-1000" />
                                </button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <div v-if="isOpen" class="w-full relative">
            <!-- 2. OPENING MESSAGE -->
            <section class="w-full py-32 px-6 flex flex-col items-center">
                <div class="max-w-3xl text-center scroll-animate opacity-0 translate-y-10 duration-1000">
                    <h2 class="text-3xl font-bold md:text-4xl font-serif font-light text-[#4a3f35] mb-8 italic">Om
                        Swastiastu</h2>
                    <p class="text-base font-bold md:text-lg font-light leading-relaxed text-[#4a3f35]/80 italic">
                        Atas Asung Kertha Wara Nugraha Ida Sang Hyang Widhi Wasa/Tuhan Yang Maha Esa kami bermaksud
                        mengundang Bapak/Ibu/Saudara/i pada Upacara Manusa Yadnya Pawiwahan (Pernikahan) Putra dan Putri
                        kami.
                    </p>
                </div>
            </section>

            <!-- 3. THE COUPLE -->
            <section class="w-full py-32 px-6 md:px-12 bg-white relative overflow-hidden">
                <div class="max-w-7xl mx-auto relative z-10">
                    <div class="grid md:grid-cols-2 gap-16 md:gap-32 items-start">

                        <!-- Groom -->
                        <div
                            class="scroll-animate opacity-0 -translate-x-10 duration-[1500ms] flex flex-col items-center md:items-end text-center md:text-right">
                            <!-- Symbolic Seal -->
                            <div
                                class="relative w-48 h-48 md:w-64 md:h-64 mb-12 group scroll-animate opacity-0 scale-90 rotate-[-12deg] duration-[1500ms] delay-200">
                                <div
                                    class="absolute inset-0 border border-amber-400/20 rounded-full animate-spin-veryslow">
                                </div>
                                <div class="absolute inset-4 border border-amber-600/10 rounded-full -rotate-45"></div>
                                <div class="absolute inset-0 flex items-center justify-center">
                                    <NuxtImg
                                        src="https://res.cloudinary.com/debcjiypk/image/upload/v1773585924/bali_gold_motif-removebg-preview_p8kxmm.png"
                                        class="w-32 md:w-40 opacity-20 transition-all duration-1000 group-hover:opacity-40 group-hover:scale-110" />
                                </div>
                                <!-- Line Decoration -->
                                <div
                                    class="absolute -right-20 top-1/2 w-20 h-px bg-gradient-to-l from-amber-400/50 to-transparent hidden md:block">
                                </div>
                            </div>

                            <div class="scroll-animate opacity-0 translate-y-8 duration-1000 delay-400">
                                <span
                                    class="text-[10px] md:text-[11px] tracking-[0.6em] uppercase font-bold text-amber-600/40 mb-4 block">
                                    {{ t('groomLabel') }}
                                </span>
                                <h2 class="text-3xl md:text-6xl font-display text-[#4a3f35] mb-6 leading-tight">
                                    {{ groomFullName }}
                                </h2>

                                <div class="w-12 h-px bg-amber-400/30 mb-6 md:ml-auto"></div>

                                <p
                                    class="text-sm md:text-base font-light text-[#4a3f35]/60 max-w-sm md:ml-auto leading-relaxed">
                                    {{ t('sonOf') }} <br />
                                    <strong class="text-[#4a3f35] font-semibold text-lg md:text-xl block mt-2">
                                        {{ groomParents }}
                                    </strong>
                                </p>
                            </div>
                        </div>

                        <!-- Bride -->
                        <div
                            class="scroll-animate opacity-0 translate-x-10 duration-[1500ms] flex flex-col items-center md:items-start text-center md:text-left pt-12 md:pt-48">
                            <!-- Symbolic Seal -->
                            <div
                                class="relative w-48 h-48 md:w-64 md:h-64 mb-12 group order-first md:order-none scroll-animate opacity-0 scale-90 rotate-[12deg] duration-[1500ms] delay-200">
                                <div class="absolute inset-0 border border-amber-400/20 rounded-full animate-spin-veryslow"
                                    style="animation-direction: reverse;"></div>
                                <div class="absolute inset-4 border border-amber-600/10 rounded-full rotate-45"></div>
                                <div class="absolute inset-0 flex items-center justify-center">
                                    <NuxtImg
                                        src="https://res.cloudinary.com/debcjiypk/image/upload/v1773585924/bali_gold_motif-removebg-preview_p8kxmm.png"
                                        class="w-32 md:w-40 opacity-20 transition-all duration-1000 group-hover:opacity-40 group-hover:scale-110" />
                                </div>
                                <!-- Line Decoration -->
                                <div
                                    class="absolute -left-20 top-1/2 w-20 h-px bg-gradient-to-r from-amber-400/50 to-transparent hidden md:block">
                                </div>
                            </div>

                            <div class="scroll-animate opacity-0 translate-y-8 duration-1000 delay-400">
                                <span
                                    class="text-[10px] md:text-[11px] tracking-[0.6em] uppercase font-bold text-amber-600/40 mb-4 block">
                                    {{ t('brideLabel') }}
                                </span>
                                <h2 class="text-3xl md:text-6xl font-display text-[#4a3f35] mb-6 leading-tight">
                                    {{ brideFullName }}
                                </h2>

                                <div class="w-12 h-px bg-amber-400/30 mb-6"></div>

                                <p class="text-sm md:text-base font-light text-[#4a3f35]/60 max-w-sm leading-relaxed">
                                    {{ t('daughterOf') }} <br />
                                    <strong class="text-[#4a3f35] font-semibold text-lg md:text-xl block mt-2">
                                        {{ brideParents }}
                                    </strong>
                                </p>
                            </div>
                        </div>
                    </div>
                </div>
            </section>
            
            <!-- 3.5 OUR STORY -->
            <section class="w-full py-32 px-6 relative overflow-hidden bg-white">
                <!-- Symmetrical Motifs -->
                <NuxtImg
                    src="https://res.cloudinary.com/debcjiypk/image/upload/v1773585924/bali_gold_motif-removebg-preview_p8kxmm.png"
                    class="absolute top-0 right-[-100px] w-64 opacity-[0.03] rotate-12 pointer-events-none" />
                <NuxtImg
                    src="https://res.cloudinary.com/debcjiypk/image/upload/v1773585924/bali_gold_motif-removebg-preview_p8kxmm.png"
                    class="absolute bottom-0 left-[-100px] w-64 opacity-[0.03] -rotate-12 pointer-events-none" />

                <div class="max-w-6xl mx-auto relative z-10">
                    <div class="text-center mb-24 scroll-animate opacity-0 -translate-y-10 duration-[1200ms]">
                        <span class="text-[10px] md:text-[11px] tracking-[0.5em] uppercase font-bold text-amber-600/40 mb-6 block">
                            {{ t('journeySub') }}
                        </span>
                        <h2 class="text-3xl md:text-5xl font-display font-light text-[#4a3f35] mb-8">
                            {{ t('journeyTitle') }}
                        </h2>
                        <div class="w-24 h-px bg-gradient-to-r from-transparent via-amber-400/50 to-transparent mx-auto"></div>
                    </div>

                    <div class="relative">
                        <!-- Vertical Timeline Path -->
                        <div class="absolute left-1/2 top-0 bottom-0 w-px bg-gradient-to-b from-amber-400/0 via-amber-400/20 to-amber-400/0 -translate-x-1/2 hidden md:block"></div>
                        
                        <!-- Mobile Timeline Guide -->
                        <div class="absolute left-4 top-0 bottom-0 w-px bg-amber-400/10 md:hidden"></div>

                        <div class="space-y-32">
                            <!-- Story 1: Left Content, Right Empty (Fade Right) -->
                            <div class="relative grid md:grid-cols-2 gap-12 md:gap-24 items-center">
                                <div class="scroll-animate opacity-0 -translate-x-20 duration-[1500ms] md:text-right">
                                    <div class="inline-block p-10 md:p-12 bg-[#fdfaf5] rounded-[50px] border border-amber-400/10 shadow-[0_30px_60px_-15px_rgba(0,0,0,0.03)] hover:shadow-xl transition-all duration-700 group relative overflow-hidden">
                                        <!-- Card Motif -->
                                        <NuxtImg
                                            src="https://res.cloudinary.com/debcjiypk/image/upload/v1773585924/bali_gold_motif-removebg-preview_p8kxmm.png"
                                            class="absolute top-[-30px] right-[-30px] w-32 opacity-[0.05] rotate-45 pointer-events-none group-hover:rotate-90 transition-transform duration-[2000ms]" />
                                        
                                        <span class="text-4xl md:text-5xl font-display text-amber-600/10 mb-6 block group-hover:text-amber-600/30 transition-colors duration-700">
                                            {{ t('ch1Date') }}
                                        </span>
                                        <h3 class="text-2xl md:text-3xl font-serif text-[#4a3f35] mb-6">{{ t('ch1Title') }}</h3>
                                        <p class="text-sm md:text-base text-[#4a3f35]/60 leading-relaxed font-light italic">
                                            "{{ t('ch1Desc') }}"
                                        </p>
                                    </div>
                                </div>
                                <div class="hidden md:flex justify-start items-center">
                                    <div class="w-5 h-5 rounded-full bg-white border-4 border-amber-400 shadow-[0_0_20px_rgba(251,191,36,0.5)] -ml-[10px] relative z-20"></div>
                                </div>
                            </div>

                            <!-- Story 2: Right Content, Left Empty (Fade Left) -->
                            <div class="relative grid md:grid-cols-2 gap-12 md:gap-24 items-center">
                                <div class="hidden md:flex justify-end items-center">
                                    <div class="w-5 h-5 rounded-full bg-white border-4 border-amber-400 shadow-[0_0_20px_rgba(251,191,36,0.5)] -mr-[10px] relative z-20"></div>
                                </div>
                                <div class="scroll-animate opacity-0 translate-x-20 duration-[1500ms]">
                                    <div class="inline-block p-10 md:p-12 bg-[#fdfaf5] rounded-[50px] border border-amber-400/10 shadow-[0_30px_60px_-15px_rgba(0,0,0,0.03)] hover:shadow-xl transition-all duration-700 group relative overflow-hidden">
                                        <!-- Card Motif -->
                                        <NuxtImg
                                            src="https://res.cloudinary.com/debcjiypk/image/upload/v1773585924/bali_gold_motif-removebg-preview_p8kxmm.png"
                                            class="absolute top-[-30px] left-[-30px] w-32 opacity-[0.05] -rotate-45 pointer-events-none group-hover:-rotate-90 transition-transform duration-[2000ms]" />
                                        
                                        <span class="text-4xl md:text-5xl font-display text-amber-600/10 mb-6 block group-hover:text-amber-600/30 transition-colors duration-700">
                                            {{ t('ch2Date') }}
                                        </span>
                                        <h3 class="text-2xl md:text-3xl font-serif text-[#4a3f35] mb-6">{{ t('ch2Title') }}</h3>
                                        <p class="text-sm md:text-base text-[#4a3f35]/60 leading-relaxed font-light italic">
                                            "{{ t('ch2Desc') }}"
                                        </p>
                                    </div>
                                </div>
                            </div>

                            <!-- Story 3: Left Content, Right Empty (Fade Right) -->
                            <div class="relative grid md:grid-cols-2 gap-12 md:gap-24 items-center">
                                <div class="scroll-animate opacity-0 -translate-x-20 duration-[1500ms] md:text-right">
                                    <div class="inline-block p-10 md:p-12 bg-[#fdfaf5] rounded-[50px] border border-amber-400/10 shadow-[0_30px_60px_-15px_rgba(0,0,0,0.03)] hover:shadow-xl transition-all duration-700 group relative overflow-hidden">
                                        <!-- Card Motif -->
                                        <NuxtImg
                                            src="https://res.cloudinary.com/debcjiypk/image/upload/v1773585924/bali_gold_motif-removebg-preview_p8kxmm.png"
                                            class="absolute top-[-30px] right-[-30px] w-32 opacity-[0.05] rotate-45 pointer-events-none group-hover:rotate-90 transition-transform duration-[2000ms]" />
                                        
                                        <span class="text-4xl md:text-5xl font-display text-amber-600/10 mb-6 block group-hover:text-amber-600/30 transition-colors duration-700">
                                            {{ t('ch3Date') }}
                                        </span>
                                        <h3 class="text-2xl md:text-3xl font-serif text-[#4a3f35] mb-6">{{ t('ch3Title') }}</h3>
                                        <p class="text-sm md:text-base text-[#4a3f35]/60 leading-relaxed font-light italic">
                                            "{{ t('ch3Desc') }}"
                                        </p>
                                    </div>
                                </div>
                                <div class="hidden md:flex justify-start items-center">
                                    <div class="w-5 h-5 rounded-full bg-white border-4 border-amber-400 shadow-[0_0_20px_rgba(251,191,36,0.5)] -ml-[10px] relative z-20"></div>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- 4. QUOTE -->
            <section class="w-full py-32 px-6 flex justify-center bg-[#fdfaf5]">
                <div class="max-w-3xl text-center">
                    <div class="scroll-animate opacity-0 translate-y-10 duration-[1500ms]">
                        <p class="text-xl md:text-2xl font-serif italic text-[#4a3f35]/90 leading-relaxed mb-6">
                            "Ihaiva stam ma vi yaustam, visvam ayur vyasnutam, kridantau putrair naptrbhih, modamanau sve
                            grhe."
                        </p>
                    </div>

                    <div class="scroll-animate opacity-0 translate-y-8 duration-[1500ms] delay-300">
                        <p class="text-base md:text-lg font-serif italic text-[#4a3f35]/60 leading-relaxed mb-10 max-w-2xl mx-auto">
                            Wahai pasangan suami-istri, semoga kalian tetap bersatu dan tidak pernah terpisahkan. Semoga
                            kalian mencapai hidup penuh kebahagiaan, tinggal di rumah yang penuh kegembiraan bersama seluruh
                            keturunanmu.
                        </p>
                    </div>

                    <div class="scroll-animate opacity-0 scale-95 duration-1000 delay-500">
                        <div class="w-12 h-[1px] bg-amber-400 mx-auto mb-6" />
                        <p class="text-[11px] tracking-[0.2em] font-bold uppercase text-amber-600/70">Rg Veda X.85.42</p>
                    </div>
                </div>
            </section>

            <!-- 5. EVENTS -->
            <section class="w-full py-32 px-6 md:px-12 relative overflow-hidden bg-[#fdfaf5]">
                <!-- Symmetrical Decorative Accents -->
                <NuxtImg
                    src="https://res.cloudinary.com/debcjiypk/image/upload/v1773585924/bali_gold_motif-removebg-preview_p8kxmm.png"
                    class="absolute top-0 left-[-150px] w-[500px] opacity-[0.02] -rotate-12 pointer-events-none" />
                <NuxtImg
                    src="https://res.cloudinary.com/debcjiypk/image/upload/v1773585924/bali_gold_motif-removebg-preview_p8kxmm.png"
                    class="absolute bottom-0 right-[-150px] w-[500px] opacity-[0.02] rotate-[165deg] pointer-events-none" />
                
                <div
                    class="absolute inset-0 bg-[url('https://www.transparenttextures.com/patterns/natural-paper.png')] opacity-[0.03] pointer-events-none">
                </div>

                <div class="max-w-6xl mx-auto relative z-10">
                    <div class="text-center mb-24 scroll-animate opacity-0 -translate-y-10 duration-[1200ms]">
                        <span
                            class="text-[12px] md:text-[11px] tracking-[0.5em] uppercase font-bold text-amber-600/40 mb-6 block">{{
                                t('countdownHeading') }}</span>
                        <div
                            class="w-24 h-px bg-gradient-to-r from-transparent via-amber-400/50 to-transparent mx-auto">
                        </div>
                    </div>

                    <!-- Countdown -->
                    <div class="flex flex-col items-center mb-32">
                        <div
                            class="grid grid-cols-4 gap-4 md:gap-8 max-w-4xl w-full scroll-animate opacity-0 scale-95 duration-1000 delay-200">
                            <div v-for="(val, unit) in countdown" :key="unit"
                                class="relative flex flex-col items-center p-6 md:p-10 bg-white rounded-[40px] shadow-[0_30px_60px_-15px_rgba(0,0,0,0.05)] border border-amber-400/10 group hover:shadow-2xl transition-all duration-700">
                                <!-- Unit Decoration -->
                                <div
                                    class="absolute inset-2 border border-amber-400/5 rounded-[32px] pointer-events-none">
                                </div>

                                <span
                                    class="text-4xl md:text-7xl font-display font-light text-[#4a3f35] group-hover:text-amber-600 transition-colors duration-500">{{
                                        val }}</span>
                                <span
                                    class="text-[9px] md:text-[10px] tracking-[0.3em] uppercase font-bold text-amber-600/40 mt-4">{{
                                        t(unit.toLowerCase() as any) }}</span>
                            </div>
                        </div>

                        <!-- Save Date Button -->
                        <a href="/save-the-date-dewi.ics"
                            class="mt-16 group relative flex items-center gap-4 px-12 py-5 bg-[#4a3f35] text-amber-200 rounded-full overflow-hidden transition-all duration-500 hover:shadow-[0_20px_40px_rgba(74,63,53,0.3)] hover:-translate-y-1 active:scale-95 scroll-animate opacity-0 translate-y-8 delay-500">
                            <!-- Shimmer -->
                            <div
                                class="absolute inset-0 bg-gradient-to-r from-transparent via-white/5 to-transparent -translate-x-full group-hover:translate-x-full transition-transform duration-1000">
                            </div>

                            <UIcon name="mdi:calendar-check" class="w-5 h-5 opacity-80" />
                            <span class="text-[11px] font-bold tracking-[0.3em]">{{ t('saveDate') }}</span>
                        </a>
                    </div>

                    <div class="grid md:grid-cols-2 gap-12 md:gap-16 items-stretch">
                        <!-- Event 1 (Pawiwahan) -->
                        <div class="scroll-animate opacity-0 translate-y-16 duration-[1500ms] delay-300 relative group">
                            <!-- Background Card -->
                            <div
                                class="h-full p-10 md:p-16 bg-white rounded-[60px] border border-amber-400/10 shadow-[0_40px_80px_-20px_rgba(0,0,0,0.03)] transition-all duration-700 hover:shadow-2xl hover:-translate-y-2 overflow-hidden flex flex-col relative">
                                <!-- Subtle Motif Accent -->
                                <NuxtImg
                                    src="https://res.cloudinary.com/debcjiypk/image/upload/v1773585924/bali_gold_motif-removebg-preview_p8kxmm.png"
                                    class="absolute top-[-50px] right-[-50px] w-48 opacity-[0.03] rotate-45 pointer-events-none group-hover:rotate-90 transition-transform duration-[2000ms]" />

                                <div class="flex flex-col items-center text-center mb-12 relative z-10">
                                    <div
                                        class="w-16 h-16 flex items-center justify-center rounded-3xl bg-amber-500/5 text-amber-600 mb-8 ring-1 ring-amber-500/20 group-hover:rotate-[360deg] transition-all duration-[1200ms]">
                                        <UIcon name="mdi:calendar-heart" class="w-8 h-8" />
                                    </div>
                                    <h3 class="text-4xl md:text-5xl font-serif font-light text-[#4a3f35] mb-2">Pawiwahan
                                    </h3>
                                    <div class="w-12 h-px bg-amber-400/40"></div>
                                </div>

                                <div class="space-y-10 flex-grow relative z-10 font-serif">
                                    <div class="flex flex-col items-center text-center gap-3">
                                        <UIcon name="mdi:clock-outline" class="w-5 h-5 text-amber-600/30" />
                                        <div>
                                            <p class="text-lg text-[#4a3f35] font-medium">{{ weddingDate }}</p>
                                            <p
                                                class="text-sm tracking-[0.3em] text-amber-600/60 uppercase font-bold mt-2">
                                                {{ weddingTime }}</p>
                                        </div>
                                    </div>

                                    <div class="flex flex-col items-center text-center gap-3">
                                        <UIcon name="mdi:map-marker-outline" class="w-5 h-5 text-amber-600/30" />
                                        <div class="px-4">
                                            <p class="text-xl text-[#4a3f35] mb-3 leading-tight">{{ weddingLocation }}</p>
                                            <p
                                                class="text-sm leading-relaxed text-[#4a3f35]/50 italic max-w-xs mx-auto">
                                                {{ weddingAddress }}</p>
                                        </div>
                                    </div>
                                </div>

                                <a href="https://maps.app.goo.gl/nz4cCZkJwDdba6pF9"
                                    target="_blank"
                                    class="mt-16 inline-flex items-center gap-4 px-10 py-5 bg-[#4a3f35] text-amber-100 rounded-3xl font-bold tracking-[0.2em] text-[10px] hover:bg-[#5a4f45] transition-all w-full justify-center group/btn relative overflow-hidden whitespace-nowrap z-10">

                                    <span class="relative z-10">{{ t('mapDirection') }}</span>

                                    <UIcon name="mdi:arrow-top-right"
                                        class="w-4 h-4 relative z-10 group-hover/btn:translate-x-1 group-hover/btn:-translate-y-1 transition-transform" />
                                </a>
                            </div>
                        </div>

                        <!-- Event 2 (Resepsi) -->
                        <div class="scroll-animate opacity-0 translate-y-16 duration-[1500ms] delay-500 relative group">
                            <!-- Background Card -->
                            <div
                                class="h-full p-10 md:p-16 bg-white rounded-[60px] border border-amber-400/10 shadow-[0_40px_80px_-20px_rgba(0,0,0,0.03)] transition-all duration-700 hover:shadow-2xl hover:-translate-y-2 overflow-hidden flex flex-col relative">
                                <!-- Subtle Motif Accent -->
                                <NuxtImg
                                    src="https://res.cloudinary.com/debcjiypk/image/upload/v1773585924/bali_gold_motif-removebg-preview_p8kxmm.png"
                                    class="absolute top-[-50px] left-[-50px] w-48 opacity-[0.03] -rotate-45 pointer-events-none group-hover:-rotate-90 transition-transform duration-[2000ms]" />

                                <div class="flex flex-col items-center text-center mb-12 relative z-10">
                                    <div
                                        class="w-16 h-16 flex items-center justify-center rounded-3xl bg-amber-500/5 text-amber-600 mb-8 ring-1 ring-amber-500/20 group-hover:rotate-[360deg] transition-all duration-[1200ms]">
                                        <UIcon name="mdi:glass-wine" class="w-8 h-8" />
                                    </div>
                                    <h3 class="text-4xl md:text-5xl font-serif font-light text-[#4a3f35] mb-2">Resepsi
                                    </h3>
                                    <div class="w-12 h-px bg-amber-400/40"></div>
                                </div>

                                <div class="space-y-10 flex-grow relative z-10 font-serif">
                                    <div class="flex flex-col items-center text-center gap-3">
                                        <UIcon name="mdi:clock-outline" class="w-5 h-5 text-amber-600/30" />
                                        <div>
                                            <p class="text-lg text-[#4a3f35] font-medium">{{ weddingDate }}</p>
                                            <p
                                                class="text-sm tracking-[0.3em] text-amber-600/60 uppercase font-bold mt-2">
                                                {{ receptionTime }}</p>
                                        </div>
                                    </div>

                                    <div class="flex flex-col items-center text-center gap-3">
                                        <UIcon name="mdi:map-marker-outline" class="w-5 h-5 text-amber-600/30" />
                                        <div class="px-4">
                                            <p class="text-xl text-[#4a3f35] mb-3 leading-tight">{{ receptionLocation }}
                                            </p>
                                            <p
                                                class="text-sm leading-relaxed text-[#4a3f35]/50 italic max-w-xs mx-auto">
                                                {{ receptionAddress }}</p>
                                        </div>
                                    </div>
                                </div>

                                <a href="https://maps.app.goo.gl/nz4cCZkJwDdba6pF9"
                                    target="_blank"
                                    class="mt-16 inline-flex items-center gap-4 px-10 py-5 bg-[#4a3f35] text-amber-100 rounded-3xl font-bold tracking-[0.2em] text-[10px] hover:bg-[#5a4f45] transition-all w-full justify-center group/btn relative overflow-hidden whitespace-nowrap z-10">

                                    <span class="relative z-10">{{ t('mapDirection') }}</span>

                                    <UIcon name="mdi:arrow-top-right"
                                        class="w-4 h-4 relative z-10 group-hover/btn:translate-x-1 group-hover/btn:-translate-y-1 transition-transform" />
                                </a>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- 6. RSVP FORM -->
            <section class="w-full py-32 px-6 flex justify-center overflow-hidden">
                <div
                    class="w-full max-w-4xl grid md:grid-cols-2 gap-12 items-center bg-white rounded-[60px] p-8 md:p-16 shadow-2xl border border-[#4a3f35]/5">
                    <div class="flex flex-col gap-12">
                        <div class="scroll-animate opacity-0 -translate-x-10 duration-1000">
                            <h2 class="text-3xl font-serif text-[#4a3f35] mb-6">Konfirmasi Kehadiran</h2>
                            <p class="text-sm text-[#4a3f35]/60 leading-relaxed max-w-sm">
                                Mohon konfirmasi kehadiran Bapak/Ibu/Saudara/i dengan mengisi formulir di bawah ini.
                            </p>
                        </div>
                        <div class="scroll-animate opacity-0 translate-y-10 duration-1000 delay-300">
                            <form @submit.prevent="sendRSVP" class="space-y-6">
                                <input v-model="rsvpName" type="text" placeholder="Nama Lengkap"
                                    class="w-full px-6 py-4 rounded-2xl bg-[#fdfaf5] border-none focus:ring-2 focus:ring-amber-400 outline-none text-sm transition-all"
                                    required />
                                <div class="flex gap-4">
                                    <button type="button" @click="rsvpStatus = 'attending'; validationError = false"
                                        :class="[
                                            'flex-1 py-4 px-6 rounded-2xl text-xs font-bold border transition-all',
                                            rsvpStatus === 'attending' ? 'bg-amber-100 text-[#4a3f35] border-amber-300 shadow-inner' : 'bg-amber-100/50 text-[#4a3f35]/50 border-amber-200 hover:bg-amber-100',
                                            validationError && !rsvpStatus ? 'border-red-500 bg-red-50' : ''
                                        ]">
                                        Hadir
                                    </button>
                                    <button type="button" @click="rsvpStatus = 'not_attending'; validationError = false"
                                        :class="[
                                            'flex-1 py-4 px-6 rounded-2xl text-xs font-bold border transition-all',
                                            rsvpStatus === 'not_attending' ? 'bg-[#eee] text-[#4a3f35] border-[#ccc] shadow-inner' : 'bg-[#fdfaf5] text-[#4a3f35]/40 border-[#eee] hover:bg-[#eee]',
                                            validationError && !rsvpStatus ? 'border-red-500 bg-red-50' : ''
                                        ]">
                                        TIDAK HADIR
                                    </button>
                                </div>
                                <p v-if="validationError && !rsvpStatus"
                                    class="text-[10px] text-red-500 font-bold uppercase tracking-wider mt-1 ml-2">Mohon
                                    pilih status kehadiran</p>
                                <textarea v-model="rsvpWishes" placeholder="Ucapan & Doa" rows="4"
                                    class="w-full px-6 py-4 rounded-2xl bg-[#fdfaf5] border-none focus:ring-2 focus:ring-amber-400 outline-none text-sm transition-all resize-none"></textarea>
                                <button type="submit" :disabled="isSending"
                                    class="w-full py-4 rounded-2xl font-bold tracking-[0.2em] text-[10px] shadow-lg hover:shadow-2xl transition-all disabled:opacity-50 flex items-center justify-center gap-2"
                                    :class="[
                                        submitSuccess === true ? 'bg-green-600 text-white' :
                                            submitSuccess === false ? 'bg-red-600 text-white' :
                                                'bg-[#4a3f35] text-white'
                                    ]">
                                    <UIcon v-if="isSending" name="mdi:loading" class="w-4 h-4 animate-spin" />
                                    <UIcon v-else-if="submitSuccess === true" name="mdi:check-circle" class="w-4 h-4" />
                                    <UIcon v-else-if="submitSuccess === false" name="mdi:alert-circle"
                                        class="w-4 h-4" />
                                    {{ isSending ? 'Mengirim...' : submitSuccess === true ? 'TERKIRIM' : submitSuccess
                                        ===
                                        false ? 'GAGAL MENGIRIM' : 'Kirim Ucapan' }}
                                </button>
                            </form>
                        </div>
                    </div>
                    <!-- Guestbook List -->
                    <div
                        class="scroll-animate opacity-0 translate-x-10 duration-[1200ms] h-full flex flex-col pt-8 md:pt-0">
                        <div class="flex items-center justify-between mb-8 border-b border-amber-100 pb-4">
                            <h3 class="text-2xl font-serif text-[#4a3f35]">Ucapan & Doa</h3>
                            <span class="text-[10px] font-bold bg-amber-50 text-amber-700 px-3 py-1 rounded-full">{{
                                guestMessages.length }} UCAPAN</span>
                        </div>

                        <div class="flex-1 overflow-y-auto max-h-[500px] space-y-4 pr-2 scrollbar-hide">
                            <template v-if="guestMessages.length > 0">
                                <div v-for="(msg, i) in guestMessages" :key="i"
                                    class="p-6 rounded-3xl bg-[#fdfaf5]/50 border border-amber-100/50 hover:bg-white hover:shadow-md transition-all group">
                                    <div class="flex justify-between items-start mb-3">
                                        <p class="font-bold text-[#4a3f35] text-sm">{{ msg.nama }}</p>
                                        <span
                                            class="text-[8px] font-bold px-2 py-0.5 rounded-md uppercase tracking-wider"
                                            :class="msg.kehadiran === 'Hadir' ? 'bg-green-100 text-green-700' : 'bg-gray-100 text-gray-500'">
                                            {{ msg.kehadiran === 'Hadir' ? 'Hadir' : 'Tidak Hadir' }}
                                        </span>
                                    </div>
                                    <p class="text-sm text-[#4a3f35]/70 italic leading-relaxed font-serif mb-4">"{{
                                        msg.ucapan }}"</p>
                                    <p class="text-[9px] text-[#4a3f35]/30 font-medium">{{ formatDate(msg.tanggal) }}
                                    </p>
                                </div>

                                <!-- Load More -->
                                <div v-if="hasMore" class="pt-6 flex justify-center">
                                    <button @click="loadMoreMessages" :disabled="isLoadingMore"
                                        class="px-8 py-3 bg-white border border-amber-200 rounded-xl text-[9px] font-bold text-amber-800 hover:bg-amber-50 transition-all flex items-center gap-2 group shadow-sm disabled:opacity-50">
                                        <UIcon v-if="isLoadingMore" name="mdi:loading" class="w-3 h-3 animate-spin" />
                                        {{ isLoadingMore ? 'LOADING...' : 'Muat Pesan Lainnya' }}
                                        <UIcon v-if="!isLoadingMore" name="mdi:chevron-down"
                                            class="w-3 h-3 group-hover:translate-y-0.5 transition-transform" />
                                    </button>
                                </div>
                            </template>
                            <div v-else
                                class="h-full flex flex-col items-center justify-center py-20 text-center opacity-30">
                                <UIcon name="mdi:message-off-outline" class="w-12 h-12 mb-4" />
                                <p class="text-xs font-bold tracking-widest uppercase">Belum Ada Ucapan</p>
                            </div>
                        </div>
                    </div>
                </div>
            </section>

            <!-- 7. GIFT -->
            <section class="w-full py-24 px-6 text-center">
                <div class="max-w-3xl mx-auto scroll-animate opacity-0 translate-y-10 duration-1000">
                    <span class="text-[10px] tracking-[0.4em] uppercase font-bold text-amber-600/60 mb-4 block">Titipan
                        Kasih</span>
                    <h2 class="text-3xl font-display text-[#4a3f35] mb-6">Hadiah Pernikahan</h2>
                    <p class="text-sm text-[#4a3f35]/60 mb-12">Kehadiran dan restu anda sudah merupakan hadiah terindah
                        bagi kami,
                        namun jika kamu ingin memberikan hadiah, kamu dapat melakukannya melalui kartu hadiah di bawah
                        ini.</p>

                    <div class="grid sm:grid-cols-2 gap-6">
                        <div
                            class="p-10 rounded-[40px] bg-white shadow-xl flex flex-col items-center group scroll-animate opacity-0 translate-y-10 duration-[1000ms] delay-200">
                            <UIcon name="mdi:bank-outline"
                                class="w-10 h-10 text-amber-600 mb-6 group-hover:scale-110 transition-transform" />
                            <p class="text-xs font-bold text-[#4a3f35]/40 tracking-widest mb-1">{{ bankInfo.name }}</p>
                            <p class="text-2xl font-mono text-[#4a3f35] mb-8 tracking-tighter">{{ bankInfo.number }}</p>
                            <button @click="copyText('1783208603')"
                                class="px-8 py-3 bg-[#4a3f35]/5 rounded-xl text-[10px] font-bold tracking-widest hover:bg-[#4a3f35] hover:text-white transition-all">SALIN
                                NOMOR</button>
                        </div>
                        <div
                            class="p-10 rounded-[40px] bg-white shadow-xl flex flex-col items-center group scroll-animate opacity-0 translate-y-10 duration-[1000ms] delay-400">
                            <UIcon name="mdi:wallet-outline"
                                class="w-10 h-10 text-amber-600 mb-6 group-hover:scale-110 transition-transform" />
                            <p class="text-xs font-bold text-[#4a3f35]/40 tracking-widest mb-1">{{ walletInfo.name }}
                            </p>
                            <p class="text-2xl font-mono text-[#4a3f35] mb-8 tracking-tighter">{{ walletInfo.number }}
                            </p>
                            <button @click="copyText('082144865542')"
                                class="px-8 py-3 bg-[#4a3f35]/5 rounded-xl text-[10px] font-bold tracking-widest hover:bg-[#4a3f35] hover:text-white transition-all">SALIN
                                NOMOR</button>
                        </div>
                    </div>
                </div>
            </section>

            <!-- 9. FOOTER -->
            <section class="relative w-full pt-40 bg-[#fdfaf5] overflow-hidden flex flex-col items-center">
                <!-- Decorative Background Motif -->
                <NuxtImg
                    src="https://res.cloudinary.com/debcjiypk/image/upload/v1773585924/bali_gold_motif-removebg-preview_p8kxmm.png"
                    class="absolute bottom-[-100px] left-1/2 -translate-x-1/2 w-[600px] opacity-[0.02] pointer-events-none animate-float [animation-duration:20s]" />

                <!-- Main Content -->
                <div
                    class="relative z-10 max-w-4xl mx-auto text-center px-6 md:px-12 flex flex-col items-center flex-1 scroll-animate opacity-0 translate-y-10 duration-1000">
                    <!-- Heart / Ornament -->
                    <div class="flex justify-center mb-8">
                        <UIcon name="mdi:heart" class="text-4xl text-amber-500 animate-pulse" />
                    </div>

                    <!-- Thank You Text -->
                    <p class="text-xl md:text-2xl font-serif italic font-light text-[#4a3f35]/90 mb-4 max-w-2xl">
                        {{ t('thankYouText') }}
                    </p>

                    <!-- Small Note -->
                    <p class="text-sm md:text-base text-[#4a3f35]/60 tracking-wide font-serif mb-16">
                        {{ t('thankYouSub') }}
                    </p>

                    <!-- Couple Name -->
                    <div class="mb-20">
                        <h2 class="text-3xl md:text-7xl font-display text-[#4a3f35] mb-4 tracking-tighter leading-none">
                            {{ groomName }} <span class="italic text-amber-500/40 normal-case font-serif">&</span> {{
                                brideName }}
                        </h2>
                        <div class="w-20 h-px bg-amber-500/20 mx-auto"></div>
                    </div>

                    <!-- Footer Branding / Social -->
                    <div class="flex flex-col items-center gap-6 mb-20">
                        <p class="text-[#4a3f35]/50 text-xs md:text-sm tracking-[0.2em] font-medium uppercase">
                            Keevia.id Digital Invitation
                        </p>

                        <a href="https://instagram.com/keevia.id" target="_blank" rel="noopener noreferrer"
                            class="w-12 h-12 rounded-full bg-[#4a3f35]/5 border border-[#4a3f35]/10 text-[#4a3f35] flex items-center justify-center hover:bg-[#4a3f35] hover:text-white transition-all hover:scale-110 shadow-sm">
                            <UIcon name="mdi:instagram" class="w-6 h-6" />
                        </a>
                    </div>
                </div>

                <!-- Bottom Rights -->
                <div
                    class="relative z-10 w-full text-center py-10 text-[#4a3f35]/40 text-[10px] tracking-[0.3em] uppercase border-t border-[#4a3f35]/5">
                    &copy; 2026 Keevia.id. All Rights Reserved.
                </div>
            </section>
        </div>
    </div>
</template>

<script setup lang="ts">
import { ref, onMounted, computed, inject, nextTick, onUnmounted } from 'vue'
import { useRoute } from 'vue-router'

const props = defineProps({
    groomName: { type: String, default: 'Darma' },
    brideName: { type: String, default: 'Dewi' },
    groomFullName: { type: String, default: 'I Putu Sedana Darma Putra' },
    brideFullName: { type: String, default: 'Ni Putu Dewi Susinta' },
    groomParents: { type: String, default: 'Bpk. ⁠I Made Wiranata & Ibu.  ⁠Ni Made Dwi Hudiani' },
    brideParents: { type: String, default: 'Bpk. ⁠I Made Sukerta & Ibu. ⁠Ni Wayan Sutami' },
    weddingDate: { type: String, default: 'Rabu, 25 Maret 2026' },
    weddingTime: { type: String, default: '08.00 AM - 11.00 AM WITA' },
    receptionTime: { type: String, default: '13.00 PM - Selesai' },
    weddingLocation: { type: String, default: 'Rumah Mempelai' },
    weddingAddress: { type: String, default: '⁠Br. Dinas Bun, Desa Sangketan, Kecamatan Penebel, Kabupaten tabanan' },
    receptionLocation: { type: String, default: 'Rumah Mempelai' },
    receptionAddress: { type: String, default: '⁠Br. Dinas Bun, Desa Sangketan, Kecamatan Penebel, Kabupaten tabanan' },
    musicId: { type: String, default: 'GAf2DQPYvGE' },
    firebaseCollection: { type: String, default: 'rsvp_dewi' },
    bankInfo: {
        type: Object,
        default: () => ({ name: 'BNI - NI PUTU DEWI SUSINTA', number: '1783208603' })
    },
    walletInfo: {
        type: Object,
        default: () => ({ name: 'OVO - NI PUTU DEWI SUSINTA', number: '082144865542' })
    },
    shippingAddress: { type: String, default: "Romeo's Home, Jimbaran, South Kuta, Bali" },
    galleryImages: {
        type: Array,
        default: () => [
            'https://res.cloudinary.com/debcjiypk/image/upload/v1773580561/bali_motif_uvtos5.png',
            'https://res.cloudinary.com/debcjiypk/image/upload/v1773580561/bali_motif_uvtos5.png',
        ]
    }
})

const dict = {
    id: {
        pawiwahanTitle: 'PAWIWAHAN',
        guestLabel: 'Kepada Yth.',
        openButton: 'BUKA UNDANGAN',
        inviteText: '"Atas doa restu Anda, kami mengundang Bapak/Ibu/Saudara/i untuk merayakan hari istimewa kami."',
        groomLabel: 'Mempelai Pria',
        brideLabel: 'Mempelai Wanita',
        sonOf: 'Putra pertama dari',
        daughterOf: 'Putri pertama dari',
        saveDate: 'SIMPAN TANGGAL',
        mapDirection: 'PETUNJUK LOKASI',
        countdownHeading: 'Menuju Hari Bahagia',
        days: 'HARI',
        hours: 'JAM',
        minutes: 'MENIT',
        seconds: 'DETIK',
        thankYouText: 'Terima kasih yang sebesar-besarnya atas restu dan ketersediaan waktu untuk menghadiri momen istimewa kami.',
        thankYouSub: 'Rahmat dan damai sejahtera senantiasa membersamai langkah kehidupan kita.',
        journeySub: 'Kisah Cinta Menuju Pelaminan',
        journeyTitle: 'Lembaran Baru Kami',
        ch1Title: 'Pertemuan Pertama',
        ch1Desc: 'Pada Februari 2023, kami tidak sengaja berkenalan melalui media sosial. Seiring bejalan waktu kamu memulai hubungan ini yang menjadi titik awal kami bisa bersama sampai saat ini, berawal dari iseng berujung ke hubungan yang serius.',
        ch1Date: '2023',
        ch2Title: 'Menjalin Kedekatan',
        ch2Desc: 'Kami sebagai dua orang yang memiliki kepribadian yang berbeda, dimana selama beberapa tahun hubungan kami banyak dihiasi dengan tawa, tangis, banyak kenangan manis yang tercipta dan banyak kejadian-kejadian yang membuat kami lebih kuat dan berfikir lebih dewasa.',
        ch2Date: '2023-2025',
        ch3Title: 'Menuju Pelaminan',
        ch3Desc: 'Akhirnya setelah sekian banyak drama kehidupan yang kami alami bersama, suka maupun duka, kami memutuskan untuk melanjutkan hubungan ke tahap yang lebih serius yaitu melangsungkan pernikahan, dengan adanya restu dari kedua orang tua kami dan keluarga, kami akan memulai lembaran baru sebagai keluarga, menjalani kehidupan bersama dalam suka maupun duka selamanya.',
        ch3Date: 'Maret 2026'
    },
    en: {
        pawiwahanTitle: 'THE WEDDING',
        guestLabel: 'Dear Honored Guest',
        openButton: 'OPEN INVITATION',
        inviteText: '"With great joy, we invite you to celebrate our special day and bless our union."',
        groomLabel: 'The Groom',
        brideLabel: 'The Bride',
        sonOf: 'The beloved son of',
        daughterOf: 'The beloved daughter of',
        saveDate: 'SAVE THE DATE',
        mapDirection: 'MAP DIRECTION',
        countdownHeading: 'Countdown to the Big Day',
        days: 'DAYS',
        hours: 'HOURS',
        minutes: 'MINUTES',
        seconds: 'SECONDS',
        thankYouText: 'Thank you for the prayers, love, and your presence on our happy day.',
        thankYouSub: 'May happiness and love always be with us all.',
        journeySub: 'A Journey in Love',
        journeyTitle: 'Our Story',
        ch1Title: 'First Meeting',
        ch1Desc: 'Our humble yet memorable first meeting, where every small moment began to plant the seeds of sincere love in our hearts.',
        ch1Date: '2023',
        ch1DateFull: 'January 2018',
        ch2Title: 'Growing Together',
        ch2Desc: 'Through every laugh and shared moment, we found a connection that made us even more confident to walk together and face every challenge.',
        ch2Date: '2021',
        ch2DateFull: 'June 2021',
        ch3Title: 'The Future Home',
        ch3Desc: 'With the blessing of our parents and faith in our hearts, we decided to make a sacred promise on this special day, stepping into a new chapter of life.',
        ch3Date: '2026',
        ch3DateFull: 'March 2026'
    }
}

const lang = computed(() => {
    const l = route.query.lang as string
    return (l === 'en' ? 'en' : 'id')
})

const t = (key: keyof typeof dict.id) => dict[lang.value as 'id' | 'en'][key]

const route = useRoute()
const guestName = computed(() => (route.query.to as string) || 'Tamu Undangan')
const audioControl = inject('audioControl') as any
const nuxtApp = useNuxtApp()
const firebase = nuxtApp.$firebase as any

const hasMounted = ref(false)
const isOpening = ref(false)
const isOpen = ref(false)
const scrollProgress = ref(0)
const activeImage = ref<string | null>(null)

const openLightbox = (imgPath: string) => {
    activeImage.value = imgPath
}

const countdown = ref({
    DAYS: '00',
    HOURS: '00',
    MINUTES: '00',
    SECONDS: '00'
})

const targetDate = new Date('2026-03-25T08:00:00+08:00').getTime()
let timerInterval: any

const startTimer = () => {
    timerInterval = setInterval(() => {
        const now = new Date().getTime()
        const dist = targetDate - now
        if (dist < 0) {
            clearInterval(timerInterval)
            return
        }
        countdown.value.DAYS = String(Math.floor(dist / (1000 * 60 * 60 * 24))).padStart(2, '0')
        countdown.value.HOURS = String(Math.floor((dist % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60))).padStart(2, '0')
        countdown.value.MINUTES = String(Math.floor((dist % (1000 * 60 * 60)) / (1000 * 60))).padStart(2, '0')
        countdown.value.SECONDS = String(Math.floor((dist % (1000 * 60)) / 1000)).padStart(2, '0')
    }, 1000)
}
const openInvitation = () => {
    isOpening.value = true
    setTimeout(() => {
        isOpen.value = true
        startTimer()
        if (audioControl && !audioControl.isPlaying.value) {
            audioControl.toggleAudio()
        }
        nextTick(() => {
            initScrollAnimations()
        })
    }, 100)
}

const initScrollAnimations = () => {
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.remove('opacity-0', 'translate-y-10', '-translate-y-10', 'translate-y-16', 'translate-y-8', 'translate-x-20', '-translate-x-20', 'translate-x-10', '-translate-x-10', 'scale-95', 'scale-90', 'rotate-[-12deg]', 'rotate-[12deg]')
                entry.target.classList.add('opacity-100', 'translate-y-0', 'translate-x-0', 'scale-100', 'rotate-0')
            }
        })
    }, { threshold: 0.1, rootMargin: '0px 0px -50px 0px' })

    document.querySelectorAll('.scroll-animate').forEach(el => observer.observe(el))
}

const updateScroll = () => {
    const winScroll = document.body.scrollTop || document.documentElement.scrollTop
    const height = document.documentElement.scrollHeight - document.documentElement.clientHeight
    scrollProgress.value = (winScroll / height) * 100
}

const rsvpName = ref('')
const rsvpStatus = ref<string | null>(null)
const rsvpWishes = ref('')
const isSending = ref(false)
const submitSuccess = ref<boolean | null>(null)

// Guest messages state
interface GuestMessage {
    nama: string
    kehadiran: 'Hadir' | 'Tidak Hadir'
    ucapan: string
    tanggal: Date
}

const guestMessages = ref<GuestMessage[]>([])
const lastVisible = ref<any>(null)
const hasMore = ref(true)
const isLoadingMore = ref(false)

const GOOGLE_SCRIPT_URL = 'https://script.google.com/macros/s/AKfycbw8T5EBkKe4pNHGexqv-g9V4YdUgC0uBdcUCdA9mFHDu38o0IFzECZRHkzV_uojubQE5g/exec'

const formatDate = (date: Date) => {
    return new Intl.DateTimeFormat('id-ID', {
        day: 'numeric',
        month: 'long',
        year: 'numeric',
        hour: '2-digit',
        minute: '2-digit'
    }).format(date)
}

const fetchGuestMessages = async () => {
    if (!import.meta.client || !firebase) return

    const { query, orderBy, limit, getDocs } = await import('firebase/firestore')
    const collectionRef = firebase.collection(firebase.db, props.firebaseCollection)

    const q = query(collectionRef, orderBy('tanggal', 'desc'), limit(10))
    const snapshot = await getDocs(q)

    if (snapshot.empty) {
        hasMore.value = false
        return
    }

    lastVisible.value = snapshot.docs[snapshot.docs.length - 1]
    hasMore.value = snapshot.docs.length === 10

    guestMessages.value = snapshot.docs.map((doc: any) => {
        const data = doc.data()
        return {
            nama: data.nama,
            kehadiran: data.kehadiran,
            ucapan: data.ucapan,
            tanggal: data.tanggal?.toDate?.() || new Date()
        }
    })
}

const loadMoreMessages = async () => {
    if (!import.meta.client || !firebase || !lastVisible.value) return
    isLoadingMore.value = true

    try {
        const { query, orderBy, limit, getDocs, startAfter } = await import('firebase/firestore')
        const collectionRef = firebase.collection(firebase.db, props.firebaseCollection)
        const q = query(collectionRef, orderBy('tanggal', 'desc'), startAfter(lastVisible.value), limit(10))
        const snapshot = await getDocs(q)

        if (snapshot.empty) {
            hasMore.value = false
            return
        }

        lastVisible.value = snapshot.docs[snapshot.docs.length - 1]
        hasMore.value = snapshot.docs.length === 10

        const newMessages = snapshot.docs.map((doc: any) => {
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

const validationError = ref(false)

const sendRSVP = async () => {
    if (!import.meta.client) return
    if (!rsvpName.value || !rsvpStatus.value) {
        validationError.value = true
        return
    }
    validationError.value = false
    isSending.value = true
    submitSuccess.value = null
    try {
        const collectionRef = firebase.collection(firebase.db, props.firebaseCollection)
        await firebase.addDoc(collectionRef, {
            nama: rsvpName.value,
            kehadiran: rsvpStatus.value === 'attending' ? 'Hadir' : 'Tidak Hadir',
            ucapan: rsvpWishes.value,
            tanggal: firebase.serverTimestamp()
        })

        // Local update
        guestMessages.value.unshift({
            nama: rsvpName.value,
            kehadiran: (rsvpStatus.value === 'attending' ? 'Hadir' : 'Tidak Hadir') as 'Hadir' | 'Tidak Hadir',
            ucapan: rsvpWishes.value,
            tanggal: new Date()
        })

        // Google Sheet integration fallback
        try {
            const params = new URLSearchParams({
                nama: rsvpName.value,
                kehadiran: rsvpStatus.value === 'attending' ? 'Hadir' : 'Tidak Hadir'
            })
            await fetch(`${GOOGLE_SCRIPT_URL}?${params.toString()}`)
        } catch (sheetErr) {
            console.warn('Google Sheet sync failed:', sheetErr)
        }

        submitSuccess.value = true

        // Reset form after success
        setTimeout(() => {
            rsvpName.value = ''
            rsvpStatus.value = null
            rsvpWishes.value = ''
            submitSuccess.value = null
        }, 2000)
    } catch (e) {
        console.error(e)
        submitSuccess.value = false
    } finally {
        isSending.value = false
    }
}

onMounted(() => {
    if (audioControl?.currentTheme) audioControl.currentTheme.value = 'bali'
    hasMounted.value = true
    window.addEventListener('scroll', updateScroll)
    if (audioControl && audioControl.setMusicId) {
        audioControl.setMusicId(props.musicId)
    }
    fetchGuestMessages()
})

onUnmounted(() => {
    window.removeEventListener('scroll', updateScroll)
    if (timerInterval) clearInterval(timerInterval)
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

const showToast = (message: string, isError = false) => {
    const toast = document.createElement('div')
    toast.className = `
    fixed top-12 left-1/2 transform -translate-x-1/2 -translate-y-4
    z-[100] px-8 py-4 rounded-[20px] 
    backdrop-blur-xl bg-[#1a1510]/95
    border border-amber-500/30
    shadow-[0_20px_50px_-10px_rgba(0,0,0,0.5),0_0_20px_rgba(251,191,36,0.1)]
    flex items-center gap-4
    transition-all duration-500 ease-out-expo
    opacity-0
  `

    toast.innerHTML = `
    <div class="w-2 h-2 rounded-full ${isError ? 'bg-red-400' : 'bg-amber-400'} animate-pulse"></div>
    <span class="text-[11px] font-bold tracking-[0.2em] text-amber-50/90 uppercase">${message}</span>
  `

    document.body.appendChild(toast)

    // Trigger entering animation
    requestAnimationFrame(() => {
        toast.style.opacity = '1'
        toast.style.transform = 'translate(-50%, 0)'
    })

    // otomatis fade out dan hilang setelah 3 detik
    setTimeout(() => {
        toast.style.opacity = '0'
        toast.style.transform = 'translate(-50%, -20px)'
        setTimeout(() => toast.remove(), 500)
    }, 3000)
}
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;1,300;1,400&family=Montserrat:wght@100;300;400;500;600;700&family=Marcellus&family=Playfair+Display:ital,wght@0,400;0,700;1,400&display=swap');

.font-serif {
    font-family: 'Cormorant Garamond', serif;
}

.font-sans {
    font-family: 'Montserrat', sans-serif;
}

.font-display {
    font-family: 'Marcellus', serif;
    letter-spacing: 0.15em;
    text-transform: uppercase;
}

.scroll-animate {
    will-change: transform, opacity;
    transition-property: transform, opacity;
    transition-timing-function: cubic-bezier(0.16, 1, 0.3, 1);
}

.animate-pulse-slow {
    animation: pulse-slow 8s cubic-bezier(0.4, 0, 0.6, 1) infinite;
}

@keyframes pulse-slow {

    0%,
    100% {
        opacity: 0.1;
        transform: scale(1);
    }

    50% {
        opacity: 0.3;
        transform: scale(1.1);
    }
}

.ease-out-expo {
    transition-timing-function: cubic-bezier(0.19, 1, 0.22, 1);
}

.animate-spin-veryslow {
    animation: spin-slow 60s linear infinite;
}

@keyframes spin-slow {
    from {
        transform: rotate(0deg);
    }

    to {
        transform: rotate(360deg);
    }
}

.animate-float {
    animation: float 10s ease-in-out infinite;
}

@keyframes float {

    0%,
    100% {
        transform: translateY(0) rotate(var(--tw-rotate, 0deg));
    }

    50% {
        transform: translateY(-20px) rotate(calc(var(--tw-rotate, 0deg) + 2deg));
    }
}

/* Simulated opening animation */
@keyframes kenburns {
    0% {
        transform: scale(1.1);
    }

    100% {
        transform: scale(1.2);
    }
}
</style>
