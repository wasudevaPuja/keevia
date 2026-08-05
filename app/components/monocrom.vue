<template>
    <div class="flex w-full min-h-[100dvh] text-[#e8e1d8] font-sans selection:bg-[#b59b6b] selection:text-white">
        <!-- PRELOADER SPLASH SCREEN -->
        <transition name="fade">
            <div v-if="isLoading" class="
            fixed inset-0 z-[100]
            bg-[#080808]
            text-[#f5f5f5]
            flex flex-col
            items-center justify-center
            font-sans
            tracking-wide
        ">

                <!-- Center Content -->
                <div class="flex flex-col items-center space-y-8">

                    <!-- Small Label -->
                    <div class="flex items-center gap-4">
                        <div class="w-8 h-px bg-[#c8a96a]/60"></div>

                        <p class="
                    text-[10px]
                    md:text-xs
                    uppercase
                    tracking-[0.45em]
                    text-white/50
                ">
                            {{ t("weddingOf") }}
                        </p>

                        <div class="w-8 h-px bg-[#c8a96a]/60"></div>
                    </div>


                    <!-- Photo Frame -->
                    <div class="
                    relative
                    w-40 h-56
                    md:w-44 md:h-60
                    overflow-hidden
                    bg-black
                    border
                    border-[#c8a96a]/40
                    shadow-[0_20px_20px_rgba(0,0,0,.8)]
                    p-1
                ">

                        <!-- Gold Corner Decoration -->
                        <div class="
                        absolute
                        top-0
                        left-0
                        w-8
                        h-8
                        border-t
                        border-l
                        border-[#c8a96a]
                        z-10
                    "></div>

                        <div class="
                        absolute
                        bottom-0
                        right-0
                        w-8
                        h-8
                        border-b
                        border-r
                        border-[#c8a96a]
                        z-10
                    "></div>


                        <img src="https://assets.keevia.id/wedding-danan/IMG_3801.jpg" alt="Preloading" class="
                        w-full
                        h-full
                        object-cover
                        opacity-90
                        grayscale-[0.15]
                        contrast-[1.1]
                    " />

                        <!-- Cinematic Overlay -->
                        <div class="
                        absolute
                        inset-0
                        bg-gradient-to-t
                        from-black/40
                        via-transparent
                        to-transparent
                    "></div>

                    </div>


                    <!-- Couple Name -->
                    <div class="text-center">

                        <p class="
                        text-lg
                        md:text-xl
                        font-serif
                        tracking-[0.35em]
                        uppercase
                        text-white
                    ">
                            Danan
                            <span class="
                            italic
                            font-light
                            text-[#c8a96a]
                        ">
                                &
                            </span>
                            Ayu
                        </p>


                        <div class="
                        w-10
                        h-px
                        bg-[#c8a96a]/60
                        mx-auto
                        mt-5
                    "></div>

                    </div>

                </div>


                <!-- Progress Text -->
                <div class="
                absolute
                bottom-10
                left-8
                md:bottom-12
                md:left-12
            ">
                    <p class="
                    text-[10px]
                    md:text-xs
                    tracking-[0.3em]
                    uppercase
                    text-white/40
                ">
                        LOADING... {{ loadingProgress }}%
                    </p>
                </div>
            </div>
        </transition>

        <!-- LEFT PANEL (80% on Desktop, hidden on Mobile) -->
        <div
            class="hidden md:block md:w-[75%] flex-1 sticky top-0 self-start h-[100dvh] md:h-screen relative overflow-hidden bg-black">
            <!-- BACKGROUND PHOTO FOR LEFT PANEL (CRISP & SHARP) -->
            <div class="absolute inset-0 z-0 pointer-events-none">
                <img src="https://assets.keevia.id/wedding-danan/IMG_3809.jpg"
                    class="w-full h-full object-cover object-center filter contrast-[1.05] brightness-95"
                    alt="Danan & Ayu Cover" />
                <!-- Elegant Dark Vignette Gradient Overlay (No Blur) -->
                <div class="absolute inset-0 bg-gradient-to-t from-black/85 via-black/30 to-transparent"></div>
                <div class="absolute inset-0 bg-gradient-to-r from-black/50 via-transparent to-transparent"></div>
            </div>

            <!-- Desktop Left Panel Content -->
            <div class="absolute bottom-16 left-16 text-white z-10 max-w-xl select-none">
                <div class="flex items-center gap-4 mb-4">
                    <div class="w-12 h-px bg-white/60" />
                    <p class="tracking-[0.35em] text-xs uppercase text-white/80 font-medium">{{ t("weddingOf") }}</p>
                </div>
                <h1 class="text-6xl lg:text-7xl font-serif leading-tight tracking-wide text-white drop-shadow-md">
                    Danan <span class="italic font-light text-white/90">&amp;</span><br>Ayu
                </h1>
                <p class="mt-6 text-sm tracking-[0.25em] uppercase text-white/70">{{ t("dateFull") }}</p>
            </div>
        </div>

        <!-- RIGHT PANEL (20% on Desktop, 100% on Mobile) -->
        <div :class="[
            'relative shrink-0 w-full md:w-[25%] max-w-full h-[100dvh] md:h-screen transition-all duration-700 z-20 bg-transparent flex flex-col',
            isOpen ? 'overflow-x-hidden overflow-y-auto' : 'overflow-hidden'
        ]">
            <!-- FIXED BACKGROUND VIDEO FOR ENTIRE RIGHT PANEL -->
            <div class="fixed inset-y-0 right-0 w-full md:w-[25%] z-0 pointer-events-none overflow-hidden ">
                <video src="https://assets.keevia.id/wedding-danan/video_prewed.mp4" autoplay loop muted playsinline
                    class="w-full h-full object-cover opacity-80 ">
                </video>
                <!-- Dark Cinematic Overlay -->
                <div class=" absolute  inset-0  bg-black/20"></div>
                <!-- Bottom Fade -->
                <div class="absolute inset-0 bg-gradient-to-t from-black via-black/30to-transparent"></div>
                <!-- Subtle Luxury Tone -->
                <div class="absolute inset-0 bg-gradient-to-br from-[#c8a96a]/10 via-transparent to-transparent"></div>
            </div>



            <!-- HERO / COVER SECTION -->
            <section class="relative z-10 w-full min-h-[100dvh] flex flex-col px-6 pt-20 pb-16 text-center shrink-0">
                <!-- TOP TITLE -->
                <div class="flex flex-col items-center w-full">


                    <p class="text-[10px] tracking-[0.5em] uppercase mb-5 text-white/60 text-halo">
                        {{ t("weddingOf") }}
                    </p>

                    <h1
                        class="text-4xl md:text-5xl font-serif mb-5 text-white leading-tight tracking-[0.12em] select-none text-halo">
                        Danan
                        <span class="italic font-light text-[#c8a96a]">
                            &
                        </span>
                        Ayu
                    </h1>


                    <p class="text-[10px] tracking-[0.45em] uppercase text-white/50 text-halo">
                        {{ t("dateFull") }}
                    </p>
                </div>

                <!-- SPACER -->
                <div class="flex-1"></div>

                <!-- GUEST CARD -->
                <div v-if="!isOpen" class="flex flex-col items-centerw-full">

                    <div
                        class="w-full max-w-sm bg-black/30 backdrop-blur-md border border-[#c8a96a]/30 p-8 rounded-3xl shadow-[0_20px_60px_rgba(0,0,0,.7)]">

                        <!-- Label -->
                        <p class="text-[10px] tracking-[0.4em] uppercase mb-3 text-[#c8a96a]">
                            {{ t("toYth") }}
                        </p>
                        <!-- Guest -->
                        <p class="text-xl font-serif mb-6 text-white tracking-wide">
                            {{ guestName }}
                        </p>


                        <!-- Message -->
                        <p class="text-xs text-white/70 leading-relaxed mb-8 font-light">
                            {{ t("openingMsg") }}
                        </p>

                        <!-- Button -->
                        <button
                            class="w-full py-3 rounded-full text-[10px] tracking-[0.35em] uppercase font-medium bg-white text-black hover:bg-white/80 transition-all duration-300 shadow-[0_8px_30px_rgba(200,169,106,.25)] cursor-pointer"
                            @click="openInvitation">
                            {{ t("openBtn") }}
                        </button>
                    </div>
                </div>

                <!-- SCROLL -->
                <div v-if="isOpen"
                    class="flex flex-col items-center gap-2 text-white/60 animate-bounce text-halo mt-auto">
                    <span class="text-[10px] tracking-[0.5em] uppercase">
                        Scroll
                    </span>

                    <UIcon name="mdi:chevron-down" class="w-5 h-5 text-[#c8a96a]" />
                </div>
            </section>

            <!-- SCROLL CONTENT (WHEN IS OPEN) -->
            <div v-if="isOpen" class="relative z-10 flex-1 flex flex-col w-full">

                <!-- QUOTE SECTION -->
                <section class="relative w-full min-h-[100dvh] overflow-hidden">

                    <!-- FULL BACKGROUND PHOTO -->
                    <img src="https://assets.keevia.id/wedding-danan/IMG_3794.jpg" alt="Wedding Quote"
                        class="absolute inset-0 w-full h-full object-cover" loading="lazy" decoding="async" />


                    <!-- DARK CINEMATIC OVERLAY -->
                    <div class="absolute inset-0 bg-black/45"></div>

                    <!-- TOP & BOTTOM GRADIENT -->
                    <div class="absolute inset-0 bg-gradient-to-b from-black/70 via-transparent to-black/90">
                    </div>


                    <!-- CONTENT -->
                    <div
                        class="relative z-10 min-h-[100dvh] flex flex-col justify-end items-center text-center px-8 pb-24">

                        <!-- Ornament -->
                        <div class="w-16 h-px bg-white/40 mb-10"></div>


                        <!-- Title -->
                        <p class="text-[10px] tracking-[0.5em] uppercase mb-10 text-white/60">
                            The Beginning of Forever
                        </p>


                        <!-- Sloka -->
                        <p
                            class="max-w-md text-sm md:text-base italic leading-loose font-serif text-white tracking-wide">
                            "Ihaiva stam mā vi yaustam,
                            Visvām āyur vyasnutam.
                            Krindantau putrair naptrbhih,
                            Modamānau sve grhe."
                        </p>


                        <!-- Source -->
                        <p class="text-[10px] tracking-[0.4em] uppercase text-white/50 mt-8">
                            (Rgveda : X.85.42)
                        </p>


                        <!-- Divider -->
                        <div class="w-10 h-px bg-white/30 my-10"></div>


                        <!-- Translation -->
                        <p class="max-w-lg text-xs md:text-sm leading-relaxed font-light text-white/80">
                            Wahai pasangan suami-isteri, semoga kalian tetap bersatu
                            dan tidak pernah terpisahkan. Semoga kalian mencapai hidup
                            penuh kebahagiaan, tinggal di rumah yang penuh kegembiraan
                            bersama seluruh keturunanmu.
                        </p>


                        <!-- Bottom Ornament -->
                        <div class="w-16 h-px bg-white/40 mt-10"></div>


                    </div>

                </section>
                <!-- PROFILE SECTION (FULL WIDTH & FULL SCREEN) -->
                <section class="relative w-full">
                    <!-- Header -->
                    <div class="flex flex-col items-center text-center py-24 px-6">
                        <!-- Elegant Divider -->
                        <div class="flex items-center gap-6 mb-8">
                            <div class="w-16 h-px bg-gradient-to-r from-transparent to-white/30"></div>

                            <div class="w-1.5 h-1.5 rounded-full bg-[#c8b08a]"></div>

                            <div class="w-16 h-px bg-gradient-to-l from-transparent to-white/30"></div>
                        </div>


                        <!-- Minimal Ornament -->
                        <div class="w-px h-14 bg-gradient-to-b from-white/40 to-transparent"></div>

                    </div>

                    <!-- Stacked Full Sections -->
                    <div class="flex flex-col w-full text-left">
                        <!-- MEMPELAI PRIA (GROOM) -->
                        <div class="relative w-full min-h-[100dvh] group overflow-hidden">
                            <img src="https://assets.keevia.id/wedding-danan/IMG_3829.jpg" alt="Groom Danan"
                                class="absolute inset-0 w-full h-full object-cover transition-transform duration-[8000ms] ease-linear group-hover:scale-110 filter sepia-[0.15]"
                                loading="lazy" decoding="async">
                            <!-- Elegant Dark Vignette Overlay (same as Left Panel) -->
                            <div class="absolute inset-0 bg-gradient-to-t from-black/85 via-black/30 to-transparent" />
                            <div
                                class="absolute inset-0 bg-gradient-to-r from-black/50 via-transparent to-transparent" />

                            <!-- Content -->
                            <div class="absolute inset-0 flex flex-col justify-end p-8 pb-16 md:p-12 z-10 w-full">
                                <div
                                    class="scroll-animate opacity-0 translate-y-8 transition-all duration-1000 space-y-3 max-w-xs">
                                    <!-- Label -->
                                    <div class="flex items-center gap-3 mb-1">
                                        <div class="w-8 h-px bg-white/50" />
                                        <p class="text-[10px] tracking-[0.35em] uppercase text-white/60 font-medium">{{
                                            t("theGroom") }}</p>
                                    </div>

                                    <!-- Name Block -->
                                    <div class="space-y-0.5">
                                        <h2
                                            class="text-2xl md:text-3xl font-light text-white font-serif tracking-wide leading-snug">
                                            I Kadek Wahyu
                                        </h2>
                                        <h2
                                            class="text-2xl md:text-3xl font-light text-white font-serif tracking-wide leading-snug">
                                            <span class="italic text-white/75">Dananjaya, S.Kom.</span>
                                        </h2>
                                    </div>

                                    <!-- Divider -->
                                    <div class="w-10 h-px bg-white/20 my-1"></div>

                                    <!-- Parents -->
                                    <div class="space-y-0.5">
                                        <p class="text-[11px] text-white/55 font-light tracking-wide">{{ t("sonOf") }}
                                        </p>
                                        <p class="text-xs text-white/90 font-medium leading-relaxed">{{
                                            t("parentsGroom") }}</p>
                                    </div>

                                    <!-- Instagram Link -->
                                    <div class="pt-3">
                                        <a href="https://www.instagram.com/wahyu_dananjayaa" target="_blank"
                                            rel="noopener noreferrer"
                                            class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-white/10 backdrop-blur-md border border-white/20 text-white/80 text-[10px] tracking-widest uppercase hover:bg-white/20 transition-all">
                                            <UIcon name="mdi:instagram" class="w-3.5 h-3.5" />
                                        </a>
                                    </div>
                                </div>
                            </div>
                        </div>

                        <!-- MEMPELAI WANITA (BRIDE) -->
                        <div class="relative w-full min-h-[100dvh] group overflow-hidden">
                            <img src="https://assets.keevia.id/wedding-danan/IMG_3828.jpg" alt="Bride Ayu"
                                class="absolute inset-0 w-full h-full object-cover transition-transform duration-[8000ms] ease-linear group-hover:scale-110 filter sepia-[0.15]"
                                loading="lazy" decoding="async">
                            <!-- Elegant Dark Vignette Overlay (same as Left Panel) -->
                            <div class="absolute inset-0 bg-gradient-to-t from-black/85 via-black/30 to-transparent" />
                            <div
                                class="absolute inset-0 bg-gradient-to-l from-black/50 via-transparent to-transparent" />

                            <!-- Content (Right aligned) -->
                            <div
                                class="absolute inset-0 flex flex-col justify-end p-8 pb-16 md:p-12 z-10 items-end text-right w-full">
                                <div
                                    class="scroll-animate opacity-0 translate-y-8 transition-all duration-1000 space-y-3 max-w-xs flex flex-col items-end">
                                    <!-- Label -->
                                    <div class="flex items-center gap-3 flex-row-reverse mb-1">
                                        <div class="w-8 h-px bg-white/50" />
                                        <p class="text-[10px] tracking-[0.35em] uppercase text-white/60 font-medium">{{
                                            t("theBride") }}</p>
                                    </div>

                                    <!-- Name Block -->
                                    <div class="space-y-0.5 text-right">
                                        <h2
                                            class="text-2xl md:text-3xl font-light text-white font-serif tracking-wide leading-snug">
                                            Ns. Kadek Ayu Krisna
                                        </h2>
                                        <h2
                                            class="text-2xl md:text-3xl font-light text-white font-serif tracking-wide leading-snug">
                                            <span class="italic text-white/75">Dewi, S.Kep.</span>
                                        </h2>
                                    </div>

                                    <!-- Divider -->
                                    <div class="w-10 h-px bg-white/20 my-1"></div>

                                    <!-- Parents -->
                                    <div class="space-y-0.5">
                                        <p class="text-[11px] text-white/55 font-light tracking-wide">{{ t("daughterOf")
                                        }}</p>
                                        <p class="text-xs text-white/90 font-medium leading-relaxed">{{
                                            t("parentsBride") }}</p>
                                    </div>

                                    <!-- Instagram Link -->
                                    <div class="pt-3">
                                        <a href="https://www.instagram.com/ayuk.krisna" target="_blank"
                                            rel="noopener noreferrer"
                                            class="inline-flex items-center gap-2 px-4 py-2 rounded-full bg-white/10 backdrop-blur-md border border-white/20 text-white/80 text-[10px] tracking-widest uppercase hover:bg-white/20 transition-all">
                                            <UIcon name="mdi:instagram" class="w-3.5 h-3.5" />
                                        </a>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </section>

                <!-- COUNTDOWN / SAVE OUR DATE -->
                <section class="py-24 px-6 relative w-full">
                    <!-- Soft dark overlay supaya text tetap terbaca -->
                    <div class="absolute inset-0"></div>

                    <div
                        class="relative z-10 max-w-4xl mx-auto scroll-animate opacity-90 translate-y-8 transition-all duration-1000">

                        <!-- Glass Container -->
                        <div
                            class="bg-black/30 backdrop-blur-md border border-white/10 rounded-3xl p-8 md:p-12 shadow-2xl">
                            <!-- Header -->
                            <div class="flex flex-col items-center mb-12">
                                <!-- Ornament -->
                                <div class="flex items-center gap-5 mb-8">
                                    <div
                                        class="w-14 h-px bg-gradient-to-r from-transparent via-white/40 to-transparent">
                                    </div>
                                    <div class="w-1.5 h-1.5 rounded-full bg-[#c8b08a]"></div>
                                    <div
                                        class="w-14 h-px bg-gradient-to-r from-transparent via-white/40 to-transparent">
                                    </div>
                                </div>
                                <p class="text-[9px] font-medium tracking-[0.5em] uppercase mb-4 text-white/60">
                                    {{ t("saveOurDate") }}
                                </p>

                                <h2
                                    class="text-3xl text-center md:text-4xl font-serif text-white tracking-wide mb-4 drop-shadow-lg">
                                    {{ t("dateMain") }}
                                </h2>
                                <div class="w-12 h-px bg-[#c8b08a]/50"></div>
                            </div>



                            <!-- Countdown -->
                            <div class="grid grid-cols-4 gap-3 max-w-md mx-auto mb-10">
                                <div class="rounded-xl bg-white/10 backdrop-blur-sm border border-white/15 p-4">
                                    <span class="block text-3xl font-serif text-white">
                                        {{ countdown.days }}
                                    </span>
                                    <span class="text-[9px] uppercase tracking-[0.25em] text-white/50">
                                        {{ t("days") }}
                                    </span>
                                </div>


                                <div class="rounded-xl bg-white/10 backdrop-blur-sm border border-white/15 p-4">
                                    <span class="block text-3xl font-serif text-white">
                                        {{ countdown.hours }}
                                    </span>
                                    <span class="text-[9px] uppercase tracking-[0.25em] text-white/50">
                                        {{ t("hours") }}
                                    </span>
                                </div>


                                <div class="rounded-xl bg-white/10 backdrop-blur-sm border border-white/15 p-4">
                                    <span class="block text-3xl font-serif text-white">
                                        {{ countdown.minutes }}
                                    </span>
                                    <span class="text-[9px] uppercase tracking-[0.25em] text-white/50">
                                        {{ t("minutes") }}
                                    </span>
                                </div>

                                <div class="rounded-xl bg-white/10 backdrop-blur-sm border border-white/15 p-4">

                                    <span class="block text-3xl font-serif text-white">
                                        {{ countdown.seconds }}
                                    </span>

                                    <span class="text-[9px] uppercase tracking-[0.25em] text-white/50">
                                        {{ t("seconds") }}
                                    </span>
                                </div>
                            </div>

                            <!-- Button -->
                            <div class="flex justify-center w-full">
                                <a :href="isAndroid ? googleCalendarLink : '/save-the-date-danan.ics'"
                                    :target="isAndroid ? '_blank' : undefined"
                                    :download="!isAndroid ? 'save-the-date-danan.ics' : undefined"
                                    class="inline-flex items-center gap-3 py-3 px-8 bg-white/10 backdrop-blur-md border border-white/30 text-white text-[10px] font-medium tracking-[0.3em] uppercase hover:bg-white hover:text-black transition-all rounded-full">
                                    <UIcon name="mdi:calendar-heart" class="w-4 h-4" />
                                    {{ t("saveToCal") }}
                                </a>
                            </div>
                        </div>
                    </div>
                </section>

                <!-- EVENT -->
                <section class="py-24 px-6 relative w-full">

                    <div class="max-w-5xl mx-auto relative z-10">

                        <!-- SECTION DIVIDER -->
                        <div class="flex flex-col items-center mb-16">
                            <div class="w-px h-20 bg-gradient-to-b from-transparent via-white/30 to-white/50"></div>
                        </div>


                        <!-- HEADER -->
                        <div
                            class="flex flex-col items-center text-center mb-16 scroll-animate opacity-90 translate-y-8 transition-all duration-1000">

                            <p class="text-[9px] font-medium tracking-[0.5em] text-white/50 uppercase mb-5">
                                The best is yet to come
                            </p>

                            <h2 class="text-3xl md:text-4xl font-serif text-white tracking-wide mb-6 drop-shadow-lg">
                                Wedding Event
                            </h2>

                            <div class="w-12 h-px bg-white/30"></div>

                        </div>


                        <!-- EVENT CARD -->
                        <div class="grid grid-cols-1 gap-8">

                            <div
                                class="bg-black/30 backdrop-blur-xl border border-white/15 p-8 rounded-3xl text-center shadow-2xl scroll-animate opacity-0 translate-y-8 transition-all duration-1000 delay-200">
                                <!-- ICON -->
                                <div
                                    class="w-14 h-14 mx-auto rounded-full bg-white/5 border border-white/20 flex items-center justify-center mb-7">

                                    <UIcon name="mdi:glass-flute" class="w-6 h-6 text-white/70" />

                                </div>


                                <!-- TITLE -->
                                <h3 class="text-2xl font-serif text-white mb-5 tracking-wide">
                                    {{ t("resepsiTitle") }}
                                </h3>

                                <!-- DATE -->
                                <p class="text-sm text-white/70 mb-2 tracking-wide">
                                    {{ t("dateFull") }}
                                </p>

                                <!-- TIME -->
                                <p class="text-sm text-white font-medium mb-7 tracking-wide">
                                    Pukul {{ resepsiTime }}
                                </p>
                                <!-- DIVIDER -->
                                <div class="w-10 h-px bg-white/30 mx-auto mb-7"></div>
                                <!-- LOCATION -->
                                <p class="text-xs leading-relaxed text-white/60 font-light mb-10 max-w-sm mx-auto">
                                    {{ t("resepsiLocation") }}
                                </p>
                                <!-- MAP BUTTON -->
                                <a href="https://maps.app.goo.gl/vKRTZ8QVQ2w46BUeA?g_st=ic" target="_blank"
                                    class="inline-flex items-center justify-center py-3 px-8 bg-white/10 backdrop-blur-md border border-white/30 text-white text-[10px] font-medium tracking-[0.3em] uppercase hover:bg-white hover:text-black transition-all duration-500 rounded-full">
                                    {{ t("openMap") }}
                                </a>
                            </div>
                        </div>
                    </div>
                </section>

                <!-- RSVP & UCAPAN -->
                <section class="py-20 px-6 max-w-5xl mx-auto w-full relative">

                    <!-- HEADER -->
                    <div
                        class="flex flex-col items-center text-center mb-16 scroll-animate opacity-90 translate-y-8 transition-all duration-1000">

                        <div class="w-px h-16 bg-gradient-to-b from-transparent to-white/40 mb-6"></div>

                        <p class="text-[9px] font-medium tracking-[0.4em] uppercase mb-4 text-white/50">
                            {{ t("rsvpSub") }}
                        </p>

                        <h2 class="text-3xl md:text-4xl font-serif text-white tracking-wide mb-6">
                            {{ t("rsvpTitle") }}
                        </h2>
                        <div class="w-12 h-px bg-white/30"></div>
                    </div>
                    <div class="grid grid-cols-1 gap-12 items-start">
                        <!-- FORM -->
                        <div
                            class="bg-black/35 backdrop-blur-xl border border-white/20 p-8 rounded-3xl shadow-2xl scroll-animate opacity-90 translate-y-8 transition-all duration-1000 delay-100">

                            <h3 class="text-xl font-serif mb-8 text-white">
                                {{ t("confirmAttendance") }}
                            </h3>

                            <form @submit.prevent="submitRSVP" class="space-y-7">
                                <!-- NAME -->
                                <div>
                                    <input type="text" v-model="nama" :placeholder="t('fullNamePlaceholder')"
                                        class="w-full pb-3 border-b border-white/20 bg-transparent text-sm text-white focus:outline-none focus:border-white transition placeholder:text-white/40 font-light"
                                        required />
                                </div>

                                <!-- ATTENDANCE -->
                                <div>

                                    <p class="text-[10px] tracking-widest text-white/50 uppercase mb-3">
                                        {{ t("confirmAttendance") }}
                                    </p>

                                    <div class="flex gap-4">
                                        <label class="cursor-pointer flex-1">
                                            <input type="radio" v-model="kehadiran" value="Hadir" name="hadir"
                                                class="peer sr-only" required>

                                            <div
                                                class="py-3 text-center border border-white/20 bg-white/5 text-white/70 text-[11px] uppercase tracking-widest peer-checked:bg-white peer-checked:text-black transition-all rounded-full">

                                                {{ t("attendYes") }}
                                            </div>
                                        </label>
                                        <label class="cursor-pointer flex-1">
                                            <input type="radio" v-model="kehadiran" value="Tidak Hadir" name="hadir"
                                                class="peer sr-only">
                                            <div
                                                class="py-3 text-center border border-white/20 bg-white/5 text-white/70 text-[11px] uppercase tracking-widest peer-checked:bg-white/30 peer-checked:text-white transition-all rounded-full">
                                                {{ t("attendNo") }}
                                            </div>
                                        </label>
                                    </div>
                                </div>

                                <!-- MESSAGE -->
                                <div>
                                    <textarea v-model="ucapan" rows="4" :placeholder="t('wishesPlaceholder')"
                                        class="w-full p-4 border border-white/20 bg-white/5 text-sm text-white focus:outline-none focus:border-white placeholder:text-white/40 font-light rounded-xl resize-none"
                                        required></textarea>
                                </div>
                                <!-- BUTTON -->
                                <button :disabled="isSubmitting"
                                    class="w-full py-4 bg-white text-black text-[10px] font-bold tracking-[0.25em] uppercase hover:bg-white/80 transition-all rounded-full cursor-pointer disabled:opacity-50">
                                    <span v-if="isSubmitting">
                                        {{ t("sending") }}
                                    </span>

                                    <span v-else-if="submitSuccess === true">
                                        {{ t("sentSuccess") }}
                                    </span>

                                    <span v-else-if="submitSuccess === false">
                                        {{ t("sentFailed") }}
                                    </span>

                                    <span v-else>
                                        {{ t("sendBtn") }}
                                    </span>

                                </button>
                            </form>
                        </div>

                        <!-- MESSAGE LIST -->
                        <div
                            class="bg-black/30 backdrop-blur-xl border border-white/20 p-8 rounded-3xl shadow-2xl h-full max-h-[550px] scroll-animate opacity-90 translate-y-8 transition-all duration-1000 delay-200">
                            <div class="mb-6 border-b border-white/20 pb-4 flex items-center justify-between">
                                <h3 class="text-xl font-serif text-white">
                                    {{ t("wishesTitle") }}
                                </h3>

                                <span
                                    class="bg-white/10 border border-white/20 text-white/80 text-xs px-3 py-1 rounded-full">
                                    {{ totalMessages }} {{ t("messagesCount") }}
                                </span>

                            </div>
                            <template v-if="guestMessages.length > 0">
                                <div class="space-y-4 max-h-[420px] overflow-y-auto">
                                    <div v-for="(entry, index) in guestMessages" :key="index"
                                        class="bg-white/10 backdrop-blur-md border border-white/10 p-4 rounded-2xl space-y-2 shadow-lg">
                                        <div class="flex justify-between items-start gap-4">
                                            <p class="font-medium text-white text-sm">
                                                {{ entry.nama }}
                                            </p>
                                            <span class="text-[10px] uppercase tracking-widest px-2 py-1 rounded-full"
                                                :class="entry.kehadiran === 'Hadir'
                                                    ? 'bg-white text-black'
                                                    : 'bg-white/10 text-white/60'">

                                                {{ entry.kehadiran === 'Hadir' ? t('attendBadge') : t('absentBadge') }}
                                            </span>
                                        </div>
                                        <p class="text-white/70 text-xs font-light leading-relaxed">
                                            "{{ entry.ucapan }}"
                                        </p>
                                        <p class="text-[9px] text-white/40">
                                            {{ formatDate(entry.tanggal) }}
                                        </p>
                                    </div>
                                    <!-- LOAD MORE DISINI -->
                                    <div v-if="hasMore" class="pt-4 pb-2 flex justify-center w-full">
                                        <button @click="loadMoreMessages" :disabled="isLoadingMore"
                                            class="px-6 py-2 bg-white/10 backdrop-blur-md border border-white/20 text-white text-xs tracking-widest uppercase rounded-full hover:bg-white hover:text-black transition-all flex items-center gap-2 cursor-pointer">
                                            <span v-if="isLoadingMore"
                                                class="animate-spin border-2 border-white border-t-transparent rounded-full w-4 h-4">
                                            </span>
                                            <span v-else>
                                                {{ t('loadMore') }}
                                            </span>
                                        </button>
                                    </div>
                                </div>
                            </template>
                            <template v-else>
                                <div class="flex flex-col items-center justify-center text-white/40 text-sm py-16">
                                    <UIcon name="mdi:message-outline" class="w-8 h-8 mb-4 opacity-50" />
                                    <p class="font-light">
                                        {{ t("noWishes") }}
                                    </p>
                                </div>
                            </template>
                        </div>
                    </div>
                </section>

                <!-- WEDDING GIFT -->
                <section
                    class="py-24 px-6 text-center relative mt-8 bg-black/20 backdrop-blur-sm border-t border-white/10 w-full">

                    <div
                        class="flex flex-col items-center max-w-2xl mx-auto scroll-animate opacity-90 translate-y-8 transition-all duration-1000 bg-black/35 backdrop-blur-xl p-8 md:p-12 rounded-3xl border border-white/20 shadow-2xl relative z-10">

                        <!-- Icon -->
                        <div
                            class="w-14 h-14 rounded-full bg-white/10 border border-white/20 flex items-center justify-center mb-6">
                            <UIcon name="mdi:gift-outline" class="w-7 h-7 text-white/80" />
                        </div>


                        <!-- Subtitle -->
                        <p class="text-[9px] font-medium tracking-[0.4em] text-white/50 uppercase mb-4">
                            {{ t("giftSub") }}
                        </p>


                        <!-- Title -->
                        <h2 class="text-3xl md:text-4xl font-serif text-white tracking-wide mb-6">
                            {{ t("giftTitle") }}
                        </h2>


                        <!-- Divider -->
                        <div class="w-12 h-px bg-white/30 mb-8"></div>


                        <!-- Description -->
                        <p
                            class="text-xs md:text-sm text-white/70 mx-auto mb-8 leading-relaxed font-light text-center max-w-md">
                            {{ t("giftDesc") }}
                        </p>

                        <!-- BANK CARD -->
                        <div class="w-full space-y-4 mb-6">
                            <div
                                class="p-6 rounded-2xl bg-white/10 backdrop-blur-md border border-white/20 shadow-lg flex flex-col items-center">
                                <p class="text-xs font-medium tracking-[0.35em] text-white/50 uppercase mb-3">
                                    BRI
                                </p>
                                <p class="text-xl font-serif tracking-wide text-white mb-2">
                                    012401035788506
                                </p>
                                <p class="text-xs text-white/60 mb-6">
                                    a.n I Kadek Wahyu Dananjaya
                                </p>
                                <button @click="copyText('012401035788506')"
                                    class="py-3 px-8 bg-white/10 backdrop-blur-md border border-white/30 text-white text-[10px] font-medium tracking-[0.3em] uppercase hover:bg-white hover:text-black transition-all rounded-full cursor-pointer">

                                    {{ t("copyAcc") }}
                                </button>
                            </div>
                            <div
                                class="p-6 rounded-2xl bg-white/10 backdrop-blur-md border border-white/20 shadow-lg flex flex-col items-center">
                                <p class="text-xs font-medium tracking-[0.35em] text-white/50 uppercase mb-3">
                                    Seabank
                                </p>
                                <p class="text-xl font-serif tracking-wide text-white mb-2">
                                    901068692029
                                </p>
                                <p class="text-xs text-white/60 mb-6">
                                    a.n Kadek Ayu Krisna Dewi
                                </p>
                                <button @click="copyText('901068692029')"
                                    class="py-3 px-8 bg-white/10 backdrop-blur-md border border-white/30 text-white text-[10px] font-medium tracking-[0.3em] uppercase hover:bg-white hover:text-black transition-all rounded-full cursor-pointer">

                                    {{ t("copyAcc") }}
                                </button>
                            </div>
                        </div>
                    </div>
                </section>

                <!-- GALLERY -->
                <section class="py-24 px-6 relative border-t border-white/10 w-full">

                    <div class="max-w-5xl mx-auto">

                        <!-- HEADER -->
                        <div
                            class="flex flex-col items-center text-center mb-16 scroll-animate opacity-0 translate-y-8 transition-all duration-1000">

                            <!-- Ornament -->
                            <div class="w-px h-16 bg-gradient-to-b from-transparent to-white/40 mb-6"></div>

                            <p class="text-[9px] font-medium tracking-[0.4em] text-white/50 uppercase mb-4">
                                {{ t("memoriesSub") }}
                            </p>

                            <h2 class="text-3xl md:text-4xl font-serif text-white tracking-wide mb-6">
                                {{ t("memoriesTitle") }}
                            </h2>
                            <div class="w-12 h-px bg-white/30"></div>
                        </div>
                        <!-- GALLERY GRID -->
                        <div
                            class="grid grid-cols-2 gap-3 scroll-animate opacity-0 translate-y-8 transition-all duration-1000 delay-100">
                            <div v-for="(img, idx) in images" :key="idx"
                                class="overflow-hidden rounded-2xl cursor-pointer group relative bg-white/5 backdrop-blur-md border border-white/20 p-1"
                                @click="openLightbox(img)">
                                <!-- IMAGE -->
                                <div class="overflow-hidden rounded-xl relative h-44 md:h-64 w-full">
                                    <img :src="img"
                                        class="w-full h-full object-cover transition-transform duration-[1200ms] ease-out group-hover:scale-110"
                                        loading="lazy" decoding="async" />

                                    <!-- Dark cinematic overlay -->
                                    <div
                                        class="absolute inset-0 bg-black/20 group-hover:bg-black/50 transition-all duration-500">
                                    </div>

                                    <!-- Zoom Icon -->
                                    <div
                                        class="absolute inset-0 flex items-center justify-center opacity-0 group-hover:opacity-100 transition-all duration-500">

                                        <div
                                            class="w-12 h-12 rounded-full bg-white/10 backdrop-blur-md border border-white/30 flex items-center justify-center">

                                            <UIcon name="mdi:magnify-plus-outline" class="w-6 h-6 text-white" />

                                        </div>
                                    </div>
                                </div>
                            </div>
                        </div>
                    </div>
                </section>

                <!-- FOOTER -->
                <section class="relative w-full min-h-[100dvh] overflow-hidden flex flex-col text-center select-none">
                    <!-- BACKGROUND PHOTO -->
                    <img src="https://assets.keevia.id/wedding-danan/IMG_3835.jpg" alt="Wedding Footer"
                        class="absolute inset-0 w-full h-full object-cover" loading="lazy" decoding="async" />

                    <!-- CINEMATIC OVERLAY -->
                    <div class="absolute inset-0 bg-black/45"></div>

                    <!-- GRADIENT -->
                    <div class="absolute inset-0 bg-gradient-to-b from-black/70 via-transparent to-black/90"></div>

                    <!-- CONTENT -->
                    <div class="relative z-10 min-h-[100dvh] flex flex-col items-center px-6 py-16">

                        <!-- TOP TEXT -->
                        <div class="flex flex-col items-center">
                            <div class="w-12 h-px bg-white/40 mb-8"></div>
                            <h2 class="text-3xl md:text-5xl font-serif font-light text-white tracking-wide mb-4">
                                Danan
                                <span class="italic text-white/70">&amp;</span>
                                Ayu
                            </h2>
                            <p class="text-[10px] tracking-[0.5em] uppercase text-white/60">
                                {{ t("thankYouSub") }}
                            </p>
                        </div>
                        <!-- EMPTY SPACE FOR PHOTO -->
                        <div class="flex-1"></div>
                        <!-- BOTTOM -->
                        <div class="flex flex-col items-center">
                            <!-- Ornament -->
                            <div class="w-px h-10 bg-gradient-to-b from-transparent to-white/40 mb-8"></div>

                            <!-- Keevia Instagram -->
                            <a href="https://instagram.com/keevia.id" target="_blank" rel="noopener noreferrer"
                                class="w-10 h-10 rounded-full border border-white/30 bg-white/10 backdrop-blur-md flex items-center justify-center text-white/70 hover:text-white hover:border-white transition-all mb-6">

                                <UIcon name="mdi:instagram" class="w-5 h-5" />
                            </a>
                            <p class="text-[10px] tracking-[0.35em] uppercase text-white/50 mb-3">
                                Keevia.id
                            </p>

                            <p class="text-[9px] tracking-widest text-white/30 uppercase">
                                &copy; 2026 Keevia.id. All Rights Reserved.
                            </p>
                        </div>
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

const images = ref<string[]>([
    'https://assets.keevia.id/wedding-danan/IMG_3796.jpg',
    'https://assets.keevia.id/wedding-danan/IMG_3797.jpg',
    'https://assets.keevia.id/wedding-danan/IMG_3802.jpg',
    'https://assets.keevia.id/wedding-danan/IMG_3804.jpg',
    'https://assets.keevia.id/wedding-danan/IMG_3807.jpg',
    'https://assets.keevia.id/wedding-danan/IMG_3830.jpg',
    'https://assets.keevia.id/wedding-danan/IMG_3841.JPG',
    'https://assets.keevia.id/wedding-danan/IMG_3843.JPG',
    'https://assets.keevia.id/wedding-danan/IMG_3846.JPG',
    'https://assets.keevia.id/wedding-danan/IMG_3837.JPG',
    'https://assets.keevia.id/wedding-danan/IMG_3842.JPG',
    'https://assets.keevia.id/wedding-danan/IMG_3844.JPG',
])

const current = ref(0)
let _interval: number | undefined

const nextSlide = () => {
    current.value = (current.value + 1) % images.value.length
}

const prevSlide = () => {
    current.value = (current.value - 1 + images.value.length) % images.value.length
}

const rightPanel = ref<HTMLElement | null>(null)
const thumbContainer = ref<HTMLElement | null>(null)
const thumbs = ref<HTMLElement[]>([])

const scrollThumbIntoView = () => {
    nextTick(() => {
        if (!thumbContainer.value || !thumbs.value.length) return
        const container = thumbContainer.value
        const activeThumb = thumbs.value[current.value]
        if (!activeThumb) return

        const containerRect = container.getBoundingClientRect()
        const scrollLeftTo = activeThumb.offsetLeft - (containerRect.width / 2) + (activeThumb.offsetWidth / 2)
        container.scrollTo({
            left: scrollLeftTo,
            behavior: 'smooth'
        })
    })
}

watch(current, () => {
    scrollThumbIntoView()
})

const openLightbox = (src: string) => {
    const lb = document.createElement('div')
    lb.className = 'fixed inset-0 bg-black/95 z-[9999] flex flex-col items-center justify-center cursor-pointer backdrop-blur-sm opacity-0 transition-opacity duration-300'
    lb.innerHTML = `<img src="${src}" class="max-h-[85vh] max-w-[90vw] rounded-xl shadow-2xl filter sepia-[0.2]" />
                  <p class="text-white/50 text-[10px] tracking-[0.3em] font-medium uppercase mt-6">Ketuk di mana saja untuk menutup</p>`

    document.body.appendChild(lb)
    setTimeout(() => { lb.style.opacity = '1' }, 10)

    lb.onclick = () => {
        lb.style.opacity = '0'
        setTimeout(() => lb.remove(), 300)
    }
}

const audioControl = inject('audioControl') as any

const route = useRoute()

const dict = {
    id: {
        weddingOf: "Pawiwahan",
        dateFull: "Rabu, 30 September 2026",
        toYth: "Kepada Yth.",
        openingMsg: "Merupakan suatu kehormatan dan kebahagiaan bagi kami apabila Bapak/Ibu/Saudara/i berkenan hadir untuk memberikan doa restu.",
        openBtn: "BUKA UNDANGAN",
        bibleQuote: "“Sebab itu seorang laki-laki akan meninggalkan ayahnya dan ibunya dan bersatu dengan isterinya, sehingga keduanya menjadi satu daging.”",
        bibleVerse: "Kejadian 2:24",
        theGroom: "Mempelai Pria",
        sonOf: "Putra Kedua dari",
        parentsGroom: "Bapak Drs. I Made Sugiarta & Ibu Ni Wayan Yoniasih",
        theBride: "Mempelai Wanita",
        daughterOf: "Putri Kedua dari",
        parentsBride: "Bapak Komang Sumada & Ibu Ketut Remiti",
        saveOurDate: "Menuju Hari Bahagia",
        dateMain: "Rabu, 30 September 2026",
        days: "Hari",
        hours: "Jam",
        minutes: "Menit",
        seconds: "Detik",
        saveToCal: "Simpan Tanggal",
        resepsiTitle: "Resepsi",
        resepsiLocation: "Jalan Raya Baturiti, Gang Sahadewa, No. 4, Baturiti Kelod, Tabanan",
        openMap: "Lihat Lokasi",
        rsvpSub: "Your Presence",
        rsvpTitle: "RSVP & Best Wishes",
        rsvpDesc: "Langkah ini tidak akan terasa sempurna tanpa kehadiran serta iringan doa dari seluruh kerabat dan sahabat tercinta.",
        fullName: "Nama Lengkap",
        fullNamePlaceholder: "Tulis nama Anda",
        confirmAttendance: "Sampaikan Kehadiran",
        attendYes: "Hadir",
        attendNo: "Tidak Hadir",
        wishes: "Ucapan & Doa",
        wishesPlaceholder: "Tuliskan ucapan dan doa terbaik Anda...",
        sending: "Sedang Mengirim...",
        sentSuccess: "Pesan Terkirim",
        sentFailed: "Gagal Mengirim",
        sendBtn: "Kirim RSVP",
        wishesTitle: "Doa & Ucapan",
        messagesCount: "Pesan",
        attendBadge: "Hadir",
        absentBadge: "Tidak Hadir",
        noWishes: "Belum ada ucapan terbaru.",
        loadMore: "Muat Pesan Lainnya",
        giftSub: "Tanda Kasih",
        giftTitle: "Wedding Gift",
        giftDesc: "Doa restu Anda merupakan karunia yang sangat berarti bagi kami. Namun jika Bapak/Ibu/Saudara/i bermaksud untuk memberikan tanda kasih, dapat melalui tautan di bawah ini.",
        physGift: "Alamat Pengiriman",
        bankTransfer: "Transfer Nomor Rekening",
        copyAcc: "Salin Nomor",
        digitalWallet: "Dompet Digital",
        copyNum: "Salin Nomor",
        memoriesSub: "Our Memories",
        memoriesTitle: "Gallery",
        tapEnlarge: "Ketuk Untuk Memperbesar",
        thankYouText: "Terima kasih yang sebesar-besarnya atas restu dan ketersediaan waktu untuk menghadiri momen istimewa kami.",
        thankYouSub: "With deepest gratitude for your blessings and presence on our special day. May grace, love, and peace always accompany our journey through life."
    }
}

const t = (key: keyof typeof dict.id) => dict.id[key]

const guestName = computed(() => (route.query.to as string) || 'Nama Tamu')
const resepsiTime = computed(() => (route.query.jam as string) || '12.00 WITA - Selesai')

const isAndroid = computed(() => {
    if (!import.meta.client) return false
    return /Android/i.test(navigator.userAgent)
})

const googleCalendarLink = computed(() => {
    const start = '20260930T120000';
    const end = '20261001T000000';
    const title = encodeURIComponent('Pawiwahan - Danan & Ayu');
    const details = encodeURIComponent('Merupakan suatu kehormatan dan kebahagiaan bagi kami apabila Bapak/Ibu/Saudara/i berkenan hadir untuk memberikan doa restu.');
    const location = encodeURIComponent('Jalan Raya Baturiti, Gang Sahadewa, No. 4, Baturiti Kelod, Tabanan');

    return `https://www.google.com/calendar/render?action=TEMPLATE&text=${title}&dates=${start}/${end}&details=${details}&location=${location}`
})

const isOpen = ref(false)

const openInvitation = () => {
    isOpen.value = true
    document.body.classList.remove('overflow-hidden')
    nextTick(() => {
        setTimeout(initScrollAnimations, 100)
        if (audioControl && typeof audioControl.setMusicId === 'function') {
            audioControl.setMusicId('0cKV8_MKsMw')
        }
        if (audioControl && typeof audioControl.play === 'function') {
            audioControl.play()
        } else if (audioControl?.audio?.value && !audioControl.isPlaying?.value) {
            audioControl.audio.value.play().catch(() => { })
            audioControl.isPlaying.value = true
        }
    })
    startCountdown()
}

watch(isOpen, (val) => {
    if (val) {
        _interval = window.setInterval(nextSlide, 4000)
    } else {
        clearInterval(_interval)
        current.value = 0
    }
})

const initScrollAnimations = () => {
    const observer = new IntersectionObserver((entries) => {
        entries.forEach(entry => {
            if (entry.isIntersecting) {
                entry.target.classList.remove('opacity-0', 'translate-y-8', 'translate-y-10', '-translate-y-10', 'translate-x-10', '-translate-x-10', 'scale-95')
                entry.target.classList.add('opacity-100', 'translate-y-0', 'translate-x-0', 'scale-100')
                observer.unobserve(entry.target)
            }
        })
    }, { threshold: 0.1, rootMargin: '0px 0px -50px 0px' })

    document.querySelectorAll('.scroll-animate').forEach(el => observer.observe(el))
}

onMounted(() => {
    if (audioControl && typeof audioControl.setMusicId === 'function') {
        audioControl.setMusicId('0cKV8_MKsMw')
        audioControl.setTheme?.('monocrom')
    }

    const duration = 2000
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
                setTimeout(() => {
                    initScrollAnimations()
                }, 500)
            }, 500)
        }
    }, intervalTime)

    document.querySelectorAll('video').forEach(vid => {
        const playPromise = vid.play()
        if (playPromise !== undefined) {
            playPromise.catch(e => console.warn('Autoplay prevented:', e))
        }
    })

    document.body.classList.add('overflow-hidden')

    if (import.meta.client) {
        fetchGuestMessages()
    }
})

// Countdown
const countdown = ref({
    days: '00',
    hours: '00',
    minutes: '00',
    seconds: '00'
})

const saveOurDate = new Date('2026-09-30T15:00:00+08:00').getTime()
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

const rsvpCollection = import.meta.client && firebase
    ? firebase.collection(firebase.db, 'rsvp_danan')
    : null

const nama = ref('')
const kehadiran = ref('')
const ucapan = ref('')

interface GuestMessage {
    nama: string
    kehadiran: 'Hadir' | 'Tidak Hadir'
    ucapan: string
    tanggal: Date
}

const guestMessages = ref<GuestMessage[]>([])
const totalMessages = ref(0)

const GOOGLE_SCRIPT_URL = 'https://script.google.com/macros/s/AKfycbwYmsrxHCDegsJ8b_qQujioVIthD-hWFyLywZqbugt2-OAG93LyidG3iDwqTVkQueiQ/exec'

const isSubmitting = ref(false)
const submitSuccess = ref<boolean | null>(null)

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

        guestMessages.value.unshift({
            nama: nama.value,
            kehadiran: kehadiran.value as 'Hadir' | 'Tidak Hadir',
            ucapan: ucapan.value,
            tanggal: new Date()
        })

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

        setTimeout(() => {
            submitSuccess.value = null
            nama.value = ''
            kehadiran.value = ''
            ucapan.value = ''
        }, 2000)
    }
}

const lastVisible = ref<any>(null)
const hasMore = ref(true)
const isLoadingMore = ref(false)

const fetchGuestMessages = async () => {
    if (!import.meta.client || !firebase || !rsvpCollection) return

    const { query, orderBy, limit, getDocs, onSnapshot } = await import('firebase/firestore')

    onSnapshot(rsvpCollection, (snapshot) => {
        totalMessages.value = snapshot.size
    })

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

const formatDate = (d: Date) => new Date(d).toLocaleString('id-ID', {
    dateStyle: 'medium',
    timeStyle: 'short'
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
    z-50 px-6 py-3 rounded-2xl text-white backdrop-blur-md bg-black/70
    font-medium text-center
    shadow-lg
    transition-all duration-300
  `
    document.body.appendChild(toast)

    setTimeout(() => {
        toast.style.opacity = '0'
        toast.style.transform = 'translate(-50%, -20px)'
        setTimeout(() => toast.remove(), 300)
    }, 2000)
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,600;1,400&family=Inter:wght@300;400;500&display=swap');

.font-serif {
    font-family: 'Playfair Display', serif;
}

.font-sans {
    font-family: 'Inter', sans-serif;
}

.text-halo {
    text-shadow: 0 0 15px rgba(250, 248, 245, 0.9), 0 0 30px rgba(250, 248, 245, 1), 0 0 45px rgba(250, 248, 245, 1);
}

.line-halo {
    box-shadow: 0 0 10px rgba(250, 248, 245, 0.9), 0 0 20px rgba(250, 248, 245, 1);
    background-color: rgba(138, 129, 124, 0.7) !important;
}

.fade-enter-active,
.fade-leave-active {
    transition: opacity 1.5s ease;
}

.fade-enter-from,
.fade-leave-to {
    opacity: 0;
}
</style>
