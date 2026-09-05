<template>
    <div
        class="flex w-full min-h-[100dvh] bg-[#FAF6EE] text-[#6B5328] font-sans selection:bg-[#B38E46] selection:text-white">
        <!-- PRELOADER SPLASH SCREEN -->
        <transition name="fade">
            <div v-if="isLoading" class="
            fixed inset-0 z-[100]
            bg-[#FAF6EE]
            text-[#6B5328]
            flex flex-col
            items-center justify-center
            font-mepandes-sans
            tracking-wide
            overflow-hidden
        ">

                <!-- Subtle Background Glow -->
                <div class="
                absolute
                inset-0
                pointer-events-none
                bg-gradient-to-br
                from-[#B38E46]/[0.04]
                via-transparent
                to-[#E8DFD1]/30
            "></div>


                <!-- Center Content -->
                <div class="
                relative
                z-10
                flex
                flex-col
                items-center
                space-y-7
                px-6
            ">

                    <!-- Top Ornament -->
                    <div class="flex items-center gap-4">

                        <div class="
                        w-10
                        md:w-14
                        h-px
                        bg-gradient-to-r
                        from-transparent
                        to-[#B38E46]/60
                    "></div>

                        <div class="
                        w-1.5
                        h-1.5
                        rotate-45
                        border
                        border-[#B38E46]/80
                    "></div>

                        <div class="
                        w-10
                        md:w-14
                        h-px
                        bg-gradient-to-l
                        from-transparent
                        to-[#B38E46]/60
                    "></div>

                    </div>


                    <!-- Small Label -->
                    <p class="
                    text-[9px]
                    md:text-[10px]
                    uppercase
                    tracking-[0.45em]
                    text-[#B38E46]
                    font-semibold
                ">
                        Upacara Manusa Yadnya
                    </p>


                    <!-- Logo Frame -->
                    <div class="
                    relative
                    w-52
                    h-52
                    md:w-60
                    md:h-60
                    p-3
                    bg-white/40
                    border
                    border-[#B38E46]/35
                    shadow-[0_15px_45px_rgba(107,83,40,0.08)]
                ">

                        <!-- Inner Border -->
                        <div class="
                        absolute
                        inset-2
                        border
                        border-[#B38E46]/15
                        pointer-events-none
                    "></div>


                        <!-- Gold Corner Decoration -->
                        <div class="
                        absolute
                        top-0
                        left-0
                        w-7
                        h-7
                        border-t
                        border-l
                        border-[#B38E46]
                        z-10
                    "></div>

                        <div class="
                        absolute
                        top-0
                        right-0
                        w-7
                        h-7
                        border-t
                        border-r
                        border-[#B38E46]
                        z-10
                    "></div>

                        <div class="
                        absolute
                        bottom-0
                        left-0
                        w-7
                        h-7
                        border-b
                        border-l
                        border-[#B38E46]
                        z-10
                    "></div>

                        <div class="
                        absolute
                        bottom-0
                        right-0
                        w-7
                        h-7
                        border-b
                        border-r
                        border-[#B38E46]
                        z-10
                    "></div>


                        <!-- Logo Utama -->
                        <div class="
                        w-full
                        h-full
                        flex
                        items-center
                        justify-center
                    ">
                            <img src="https://assets.keevia.id/mepandes/logo_jeroan_no_bg.png" alt="Logo Mepandes"
                                class="
                            w-full
                            h-full
                            object-contain
                        " />
                        </div>

                    </div>


                    <!-- Mepandes Title -->
                    <div class="text-center">

                        <h1 class="
                        font-mepandes
                        text-3xl
                        md:text-4xl
                        font-medium
                        tracking-[0.16em]
                        text-[#6B5328]
                        leading-tight
                    ">
                            MEPANDES
                        </h1>

                        <div class="flex items-center justify-center gap-3 mt-4">

                            <div class="
                            w-8
                            h-px
                            bg-[#B38E46]/50
                        "></div>

                            <div class="
                            w-1
                            h-1
                            rotate-45
                            bg-[#B38E46]/70
                        "></div>

                            <div class="
                            w-8
                            h-px
                            bg-[#B38E46]/50
                        "></div>

                        </div>

                    </div>

                </div>


                <!-- Loading Progress -->
                <div class="
                absolute
                bottom-8
                left-1/2
                -translate-x-1/2
                z-10
            ">
                    <p class="
                    text-[9px]
                    md:text-[10px]
                    tracking-[0.3em]
                    uppercase
                    text-[#B38E46]/70
                    whitespace-nowrap
                    font-mepandes-sans
                ">
                        LOADING... {{ loadingProgress }}%
                    </p>
                </div>


                <!-- Bottom Decorative Line -->
                <div class="
                absolute
                bottom-0
                left-1/2
                -translate-x-1/2
                w-24
                h-px
                bg-[#B38E46]/40
            "></div>

            </div>
        </transition>

        <!-- LEFT PANEL (75% on Desktop, hidden on Mobile) -->
        <div class="
        hidden md:flex
        md:w-[75%]
        flex-1
        sticky top-0
        self-start
        h-[100dvh]
        relative
        overflow-hidden
        bg-[#FAF6EE]
        items-center
        justify-center
    ">

            <!-- Watermark Logo -->
            <div class="
            absolute
            inset-0
            flex
            items-center
            justify-center
            pointer-events-none
        ">
                <img src="https://assets.keevia.id/mepandes/logo_jeroan_no_bg.png" alt="" class="
                w-[65%]
                max-w-3xl
                object-contain
                opacity-[0.10]
            " />
            </div>


            <!-- Decorative Border -->
            <div class="
            absolute
            inset-8
            border
            border-[#B38E46]/20
            pointer-events-none
        "></div>


            <!-- Center Content -->
            <div class="
            relative
            z-10
            flex
            flex-col
            items-center
            text-center
            px-12
            max-w-5xl
        ">

                <!-- Top Ornament -->
                <div class="flex items-center gap-5 mb-8">

                    <div class="
                    w-20
                    h-px
                    bg-gradient-to-r
                    from-transparent
                    to-[#B38E46]/60
                "></div>

                    <div class="
                    w-2
                    h-2
                    rotate-45
                    border
                    border-[#B38E46]
                "></div>

                    <div class="
                    w-20
                    h-px
                    bg-gradient-to-l
                    from-transparent
                    to-[#B38E46]/60
                "></div>

                </div>


                <!-- Label -->
                <p class="
                font-mepandes-sans
                text-[9px]
                md:text-[10px]
                tracking-[0.45em]
                uppercase
                text-[#B38E46]
                font-semibold
                mb-4
            ">
                    Upacara Manusa Yadnya
                </p>


                <!-- Main Title -->
                <h2 class="
                font-mepandes
                text-3xl
                lg:text-4xl
                text-[#6B5328]
                font-medium
                tracking-wide
                leading-tight
                mb-7
            ">
                    Mepandes
                </h2>


                <!-- Names -->
                <div class="text-center">

                    <!-- Name 1 -->
                    <h1 class="
                    font-mepandes
                    text-2xl
                    lg:text-3xl
                    text-[#6B5328]
                    font-medium
                    tracking-wide
                    leading-relaxed
                ">
                        I Gusti A. Ayu Galuh Parwati
                    </h1>


                    <!-- Separator -->
                    <div class="flex items-center justify-center gap-3 my-3">

                        <div class="
                        w-8
                        h-px
                        bg-[#B38E46]/40
                    "></div>

                        <div class="
                        w-1
                        h-1
                        rotate-45
                        bg-[#B38E46]/70
                    "></div>

                        <div class="
                        w-8
                        h-px
                        bg-[#B38E46]/40
                    "></div>

                    </div>


                    <!-- Name 2 -->
                    <h1 class="
                    font-mepandes
                    text-2xl
                    lg:text-3xl
                    text-[#6B5328]
                    font-medium
                    tracking-wide
                    leading-relaxed
                ">
                        I Gusti Ayu Cahya Pratiwi
                    </h1>


                    <!-- Separator -->
                    <div class="flex items-center justify-center gap-3 my-3">

                        <div class="
                        w-8
                        h-px
                        bg-[#B38E46]/40
                    "></div>

                        <div class="
                        w-1
                        h-1
                        rotate-45
                        bg-[#B38E46]/70
                    "></div>

                        <div class="
                        w-8
                        h-px
                        bg-[#B38E46]/40
                    "></div>

                    </div>


                    <!-- Name 3 -->
                    <h1 class="
                    font-mepandes
                    text-2xl
                    lg:text-3xl
                    text-[#6B5328]
                    font-medium
                    tracking-wide
                    leading-relaxed
                ">
                        I Gusti Ngurah Agung Alit Arya Wibawa
                    </h1>


                    <!-- Separator -->
                    <div class="flex items-center justify-center gap-3 my-3">

                        <div class="
                        w-8
                        h-px
                        bg-[#B38E46]/40
                    "></div>

                        <div class="
                        w-1
                        h-1
                        rotate-45
                        bg-[#B38E46]/70
                    "></div>

                        <div class="
                        w-8
                        h-px
                        bg-[#B38E46]/40
                    "></div>

                    </div>


                    <!-- Name 4 -->
                    <h1 class="
                    font-mepandes
                    text-2xl
                    lg:text-3xl
                    text-[#6B5328]
                    font-medium
                    tracking-wide
                    leading-relaxed
                ">
                        I Gusti Agung Ngurah Bratha Prasetya
                    </h1>

                </div>


                <!-- Bottom Ornament -->
                <div class="flex items-center gap-3 my-7">

                    <div class="
                    w-10
                    h-px
                    bg-[#B38E46]/50
                "></div>

                    <div class="
                    w-1.5
                    h-1.5
                    rotate-45
                    border
                    border-[#B38E46]/70
                "></div>

                    <div class="
                    w-10
                    h-px
                    bg-[#B38E46]/50
                "></div>

                </div>


                <!-- Date -->
                <p class="
                font-mepandes-sans
                text-[12px]
                md:text-sm
                tracking-[0.2em]
                uppercase
                text-[#6B5328]
                font-semibold
            ">
                    {{ t("dateFull") }}
                </p>

            </div>

        </div>

        <!-- RIGHT PANEL (20% on Desktop, 100% on Mobile) -->
        <div :class="[
            'relative shrink-0 w-full md:w-[25%] max-w-full h-[100dvh] md:h-screen transition-all duration-700 z-20 bg-transparent flex flex-col',
            isOpen ? 'overflow-x-hidden overflow-y-auto' : 'overflow-hidden'
        ]">

            <!-- FIXED BACKGROUND FOR ENTIRE RIGHT PANEL -->
            <div class="
        fixed
        inset-y-0
        right-0
        w-full
        md:w-[25%]
        z-0
        pointer-events-none
        overflow-hidden
        bg-[#FAF6EE]
    ">

                <!-- Subtle Logo Watermark -->
                <div class="
            absolute
            inset-0
            flex
            items-center
            justify-center
        ">
                    <img src="https://assets.keevia.id/mepandes/logo_jeroan_no_bg.png" alt="" class="
                w-[85%]
                max-w-md
                object-contain
                opacity-[0.12]
                [image-rendering:auto]
            " />
                </div>


                <!-- Very Soft Warm Gradient -->
                <div class="
            absolute
            inset-0
            bg-gradient-to-br
            from-[#B38E46]/[0.03]
            via-transparent
            to-[#E8DFD1]/30
        "></div>


                <!-- Side Decoration -->
                <div class="
            absolute
            inset-y-0
            left-0
            w-px
            bg-[#B38E46]/20
        "></div>

            </div>

            <!-- HERO / COVER SECTION -->
            <section :class="[
                'relative z-10 w-full min-h-[100dvh] flex flex-col px-6 pt-10 pb-8 text-center shrink-0 overflow-x-hidden',
                !isOpen
                    ? 'max-h-[100dvh] overflow-y-auto overscroll-contain'
                    : 'overflow-visible'
            ]">

                <!-- TOP CONTENT -->
                <div class="flex flex-col items-center w-full shrink-0">

                    <!-- TOP ORNAMENT -->
                    <div class="flex items-center gap-4 mb-5">

                        <div class="
                    w-8
                    h-px
                    bg-gradient-to-r
                    from-transparent
                    to-[#B38E46]/45
                "></div>

                        <div class="
                    w-1.5
                    h-1.5
                    rotate-45
                    border
                    border-[#B38E46]/65
                "></div>

                        <div class="
                    w-8
                    h-px
                    bg-gradient-to-l
                    from-transparent
                    to-[#B38E46]/45
                "></div>

                    </div>


                    <!-- CEREMONY LABEL -->
                    <p class="
                font-mepandes-sans
                text-[8px]
                md:text-[9px]
                tracking-[0.45em]
                uppercase
                text-[#B38E46]
                font-semibold
                mb-2
            ">
                        Upacara Manusa Yadnya
                    </p>


                    <!-- MAIN HEADING -->
                    <h2 class="
                font-mepandes
                text-2xl
                md:text-4xl
                text-[#6B5328]
                font-medium
                tracking-wide
                leading-tight
                mb-2
            ">
                        Mepandes
                    </h2>


                    <!-- DECORATIVE DIVIDER -->
                    <div class="flex items-center gap-3 mb-5">

                        <div class="
                    w-10
                    h-px
                    bg-[#B38E46]/25
                "></div>

                        <div class="
                    w-1
                    h-1
                    rounded-full
                    bg-[#B38E46]/50
                "></div>

                        <div class="
                    w-10
                    h-px
                    bg-[#B38E46]/25
                "></div>

                    </div>


                    <!-- NAMES -->
                    <div class="text-center w-full max-w-xl shrink-0">

                        <!-- NAME 1 -->
                        <h1 class="
                    font-mepandes
                    text-lg
                    md:text-2xl
                    text-[#6B5328]
                    font-medium
                    tracking-wide
                    leading-relaxed
                ">
                            I Gusti A. Ayu Galuh Parwati
                        </h1>

                        <p class="
                    font-mepandes-sans
                    text-[7px]
                    uppercase
                    tracking-[0.35em]
                    text-[#B38E46]/65
                    mt-0.5
                ">
                            Putri
                        </p>


                        <!-- SEPARATOR -->
                        <div class="flex items-center justify-center gap-3 my-2.5">

                            <div class="w-5 h-px bg-[#B38E46]/25"></div>

                            <div class="
                        w-1
                        h-1
                        rotate-45
                        bg-[#B38E46]/50
                    "></div>

                            <div class="w-5 h-px bg-[#B38E46]/25"></div>

                        </div>


                        <!-- NAME 2 -->
                        <h1 class="
                    font-mepandes
                    text-lg
                    md:text-2xl
                    text-[#6B5328]
                    font-medium
                    tracking-wide
                    leading-relaxed
                ">
                            I Gusti Ayu Cahya Pratiwi
                        </h1>

                        <p class="
                    font-mepandes-sans
                    text-[7px]
                    uppercase
                    tracking-[0.35em]
                    text-[#B38E46]/65
                    mt-0.5
                ">
                            Putri
                        </p>


                        <!-- SEPARATOR -->
                        <div class="flex items-center justify-center gap-3 my-2.5">

                            <div class="w-5 h-px bg-[#B38E46]/25"></div>

                            <div class="
                        w-1
                        h-1
                        rotate-45
                        bg-[#B38E46]/50
                    "></div>

                            <div class="w-5 h-px bg-[#B38E46]/25"></div>

                        </div>


                        <!-- NAME 3 -->
                        <h1 class="
                    font-mepandes
                    text-lg
                    md:text-2xl
                    text-[#6B5328]
                    font-medium
                    tracking-wide
                    leading-relaxed
                ">
                            I Gusti Ngurah Agung Alit Arya Wibawa
                        </h1>

                        <p class="
                    font-mepandes-sans
                    text-[7px]
                    uppercase
                    tracking-[0.35em]
                    text-[#B38E46]/65
                    mt-0.5
                ">
                            Putra
                        </p>


                        <!-- SEPARATOR -->
                        <div class="flex items-center justify-center gap-3 my-2.5">

                            <div class="w-5 h-px bg-[#B38E46]/25"></div>

                            <div class="
                        w-1
                        h-1
                        rotate-45
                        bg-[#B38E46]/50
                    "></div>

                            <div class="w-5 h-px bg-[#B38E46]/25"></div>

                        </div>


                        <!-- NAME 4 -->
                        <h1 class="
                    font-mepandes
                    text-lg
                    md:text-2xl
                    text-[#6B5328]
                    font-medium
                    tracking-wide
                    leading-relaxed
                ">
                            I Gusti Agung Ngurah Bratha Prasetya
                        </h1>

                        <p class="
                    font-mepandes-sans
                    text-[7px]
                    uppercase
                    tracking-[0.35em]
                    text-[#B38E46]/65
                    mt-0.5
                ">
                            Putra
                        </p>

                    </div>


                    <!-- DATE -->
                    <div class="flex flex-col items-center mt-5 shrink-0">

                        <div class="flex items-center gap-3 mb-3">

                            <div class="
                        w-7
                        h-px
                        bg-[#B38E46]/25
                    "></div>

                            <div class="
                        w-1
                        h-1
                        rounded-full
                        bg-[#B38E46]/50
                    "></div>

                            <div class="
                        w-7
                        h-px
                        bg-[#B38E46]/25
                    "></div>

                        </div>

                        <p class="
                    font-mepandes-sans
                    text-[12px]
                    md:text-sm
                    tracking-[0.2em]
                    uppercase
                    text-[#6B5328]
                    font-semibold
                ">
                            {{ t("dateFull") }}
                        </p>

                    </div>

                </div>


                <!-- FLEXIBLE SPACER -->
                <div class="flex-1 min-h-4"></div>


                <!-- GUEST CARD -->
                <div v-if="!isOpen" class="
            flex
            flex-col
            items-center
            w-full
            shrink-0
            pb-2
        ">

                    <div class="
                w-full
                max-w-sm
                bg-white/80
                backdrop-blur-md
                border
                border-[#B38E46]/20
                px-6
                py-5
                md:p-8
                rounded-2xl
                shadow-[0_20px_60px_rgba(107,83,40,.08)]
            ">

                        <!-- Recipient -->
                        <p class="
                    font-mepandes-sans
                    text-[8px]
                    tracking-[0.4em]
                    uppercase
                    mb-2
                    text-[#B38E46]
                    font-semibold
                ">
                            {{ t("toYth") }}
                        </p>


                        <!-- Guest Name -->
                        <p class="
                    font-mepandes
                    text-xl
                    md:text-2xl
                    mb-3
                    text-[#6B5328]
                    tracking-wide
                    font-medium
                    leading-relaxed
                ">
                            {{ guestName }}
                        </p>


                        <!-- Opening Message -->
                        <p class="
                    font-mepandes-sans
                    text-[10px]
                    md:text-xs
                    text-[#6B5328]/65
                    leading-relaxed
                    mb-5
                    font-light
                ">
                            {{ t("openingMsg") }}
                        </p>


                        <!-- Open Button -->
                        <button type="button" class="
                    w-full
                    py-3.5
                    rounded-full
                    text-[9px]
                    tracking-[0.35em]
                    uppercase
                    font-mepandes-sans
                    font-semibold
                    bg-[#B38E46]
                    text-white
                    hover:bg-[#6B5328]
                    active:scale-[0.98]
                    transition-all
                    duration-300
                    shadow-[0_8px_30px_rgba(179,142,70,.18)]
                    cursor-pointer
                " @click="openInvitation">
                            {{ t("openBtn") }}
                        </button>

                    </div>

                </div>


                <!-- SCROLL INDICATOR -->
                <div v-if="isOpen" class="
            flex
            flex-col
            items-center
            gap-2
            text-[#6B5328]/45
            animate-bounce
            mt-auto
            pt-6
            shrink-0
        ">

                    <span class="
                font-mepandes-sans
                text-[8px]
                tracking-[0.5em]
                uppercase
                font-medium
            ">
                        Scroll
                    </span>

                    <UIcon name="mdi:chevron-down" class="
                w-5
                h-5
                text-[#B38E46]
            " />

                </div>

            </section>
            <!-- SCROLL CONTENT (WHEN IS OPEN) -->
            <div v-if="isOpen" class="relative z-10 flex-1 flex flex-col w-full">

                <!-- QUOTE SECTION -->
                <section class="relative w-full min-h-[100dvh] overflow-hidden bg-[#FAF6EE]">

                    <!-- SUBTLE WATERMARK -->
                    <div class="absolute inset-0 flex items-center justify-center pointer-events-none">
                        <img src="https://assets.keevia.id/mepandes/logo_jeroan_no_bg.png" alt=""
                            class="w-[75%] max-w-md object-contain opacity-[0.12]" />
                    </div>

                    <!-- SOFT GOLD GRADIENT -->
                    <div
                        class="absolute inset-0 bg-gradient-to-b from-[#B38E46]/[0.03] via-transparent to-[#E8DFD1]/30">
                    </div>

                    <!-- DECORATIVE BORDER -->
                    <div class="absolute inset-6 border border-[#B38E46]/15 pointer-events-none"></div>

                    <!-- CONTENT -->
                    <div
                        class="relative z-10 min-h-[100dvh] flex flex-col justify-center items-center text-center px-8 py-24">

                        <!-- Top Ornament -->
                        <div class="flex items-center justify-center gap-4 mb-12">
                            <div class="w-12 h-px bg-[#B38E46]/40"></div>

                            <div class="w-2 h-2 rotate-45 border border-[#B38E46]/60"></div>

                            <div class="w-12 h-px bg-[#B38E46]/40"></div>
                        </div>

                        <!-- Om Swastyastu -->
                        <p class="font-serif text-lg md:text-xl text-[#6B5328] tracking-wide mb-12">
                            Om Swastyastu
                        </p>

                        <!-- Main Text -->
                        <div class="max-w-lg space-y-6">

                            <p class="text-[10px] md:text-xs tracking-[0.35em] uppercase text-[#B38E46] font-semibold">
                                Upacara Manusa Yadnya
                            </p>

                            <p class="font-mepandes-sans text-xs md:text-sm leading-loose text-[#6B5328]/80">
                                Atas asung kertha wara nugraha Ida Sang Hyang Widhi Wasa /
                                Tuhan Yang Maha Esa, kami bermaksud mengundang
                                Bapak/Ibu/Saudara/i untuk hadir pada
                                <span class="font-semibold text-[#6B5328]">
                                    Upacara Mepandes
                                </span>
                                putra dan putri kami.
                            </p>

                        </div>

                        <!-- Divider -->
                        <div class="flex items-center justify-center gap-3 mt-10">
                            <div class="w-10 h-px bg-[#B38E46]/30"></div>

                            <div class="w-1 h-1 rotate-45 bg-[#B38E46]/60"></div>

                            <div class="w-10 h-px bg-[#B38E46]/30"></div>
                        </div>

                        <!-- Flower Ornament -->
                        <div class="mt-7 flex items-center justify-center">
                            <UIcon name="ph:flower-lotus" class="w-7 h-7 text-[#B38E46]/55" />
                        </div>

                        <!-- Bottom Ornament -->
                        <div class="flex items-center justify-center gap-3 mt-7">
                            <div class="w-10 h-px bg-[#B38E46]/30"></div>

                            <div class="w-1 h-1 rotate-45 bg-[#B38E46]/60"></div>

                            <div class="w-10 h-px bg-[#B38E46]/30"></div>
                        </div>
                    </div>

                </section>
                <!-- PROFILE SECTION -->
                <section class="relative w-full bg-[#FAF6EE]">

                    <!-- Header Ornament -->
                    <div class="flex flex-col items-center text-center py-20 px-6">

                        <!-- Elegant Divider -->
                        <div class="flex items-center gap-5 mb-7">
                            <div class="w-14 h-px bg-gradient-to-r from-transparent to-[#B38E46]/40"></div>

                            <!-- Diamond -->
                            <div class="w-2 h-2 rotate-45 border border-[#B38E46]/60"></div>

                            <div class="w-14 h-px bg-gradient-to-l from-transparent to-[#B38E46]/40"></div>
                        </div>

                        <!-- Small Vertical Ornament -->
                        <div class="flex flex-col items-center gap-2">
                            <div class="w-px h-8 bg-gradient-to-b from-[#B38E46]/50 to-transparent"></div>

                            <div class="w-1 h-1 rounded-full bg-[#B38E46]/50"></div>
                        </div>

                    </div>

                </section>


                <!-- COUNTDOWN / SAVE OUR DATE -->
                <section class="relative w-full px-6 py-20 md:py-24 bg-[#FAF6EE]">

                    <!-- Subtle Background Decoration -->
                    <div class="absolute inset-0 pointer-events-none overflow-hidden">

                        <!-- Watermark -->
                        <div class="absolute inset-0 flex items-center justify-center">
                            <img src="https://assets.keevia.id/mepandes/logo_jeroan_no_bg.png" alt=""
                                class="w-[70%] max-w-sm object-contain opacity-[0.035]" />
                        </div>

                        <!-- Soft Gold Glow -->
                        <div
                            class="absolute inset-0 bg-gradient-to-b from-[#B38E46]/[0.025] via-transparent to-[#E8DFD1]/25">
                        </div>

                    </div>


                    <div
                        class="relative z-10 max-w-3xl mx-auto scroll-animate opacity-90 translate-y-8 transition-all duration-1000">

                        <!-- Main Container -->
                        <div class="
                relative
                bg-white/60
                backdrop-blur-sm
                border border-[#B38E46]/20
                rounded-2xl
                p-7 md:p-12
                shadow-[0_15px_45px_rgba(107,83,40,0.06)]
            ">

                            <!-- Inner Border -->
                            <div
                                class="absolute inset-3 md:inset-4 border border-[#B38E46]/[0.08] rounded-xl pointer-events-none">
                            </div>


                            <!-- Header -->
                            <div class="relative flex flex-col items-center text-center mb-10">

                                <!-- Top Ornament -->
                                <div class="flex items-center gap-4 mb-7">

                                    <div class="w-12 h-px bg-gradient-to-r from-transparent to-[#B38E46]/35"></div>

                                    <!-- Diamond -->
                                    <div class="w-1.5 h-1.5 rotate-45 bg-[#B38E46]/60"></div>

                                    <div class="w-12 h-px bg-gradient-to-l from-transparent to-[#B38E46]/35"></div>

                                </div>


                                <!-- Label -->
                                <p class="
                        text-[9px]
                        md:text-[10px]
                        font-semibold
                        tracking-[0.45em]
                        uppercase
                        text-[#B38E46]
                        mb-4
                    ">
                                    {{ t("saveOurDate") }}
                                </p>


                                <!-- Date -->
                                <h2 class="
                        font-mepandes
                        text-2xl
                        md:text-4xl
                        text-[#6B5328]
                        tracking-wide
                        leading-relaxed
                        mb-5
                    ">
                                    {{ t("dateMain") }}
                                </h2>


                                <!-- Minimal Divider -->
                                <div class="flex items-center gap-3">
                                    <div class="w-8 h-px bg-[#B38E46]/30"></div>

                                    <div class="w-1 h-1 rounded-full bg-[#B38E46]/50"></div>

                                    <div class="w-8 h-px bg-[#B38E46]/30"></div>
                                </div>

                            </div>


                            <!-- Countdown -->
                            <div class="
                    grid grid-cols-4
                    gap-2 md:gap-4
                    max-w-lg
                    mx-auto
                    mb-10
                ">

                                <!-- Days -->
                                <div class="
                        flex flex-col items-center justify-center
                        rounded-xl
                        bg-[#FAF6EE]/80
                        border border-[#B38E46]/15
                        py-4 px-2
                        min-h-[82px]
                    ">
                                    <span
                                        class="block font-mepandes text-2xl md:text-3xl text-[#6B5328] leading-none mb-2">
                                        {{ countdown.days }}
                                    </span>

                                    <span class="text-[8px] md:text-[9px] uppercase tracking-[0.2em] text-[#6B5328]/50">
                                        {{ t("days") }}
                                    </span>
                                </div>


                                <!-- Hours -->
                                <div class="
                        flex flex-col items-center justify-center
                        rounded-xl
                        bg-[#FAF6EE]/80
                        border border-[#B38E46]/15
                        py-4 px-2
                        min-h-[82px]
                    ">
                                    <span
                                        class="block font-mepandes text-2xl md:text-3xl text-[#6B5328] leading-none mb-2">
                                        {{ countdown.hours }}
                                    </span>

                                    <span class="text-[8px] md:text-[9px] uppercase tracking-[0.2em] text-[#6B5328]/50">
                                        {{ t("hours") }}
                                    </span>
                                </div>


                                <!-- Minutes -->
                                <div class="
                        flex flex-col items-center justify-center
                        rounded-xl
                        bg-[#FAF6EE]/80
                        border border-[#B38E46]/15
                        py-4 px-2
                        min-h-[82px]
                    ">
                                    <span
                                        class="block font-mepandes text-2xl md:text-3xl text-[#6B5328] leading-none mb-2">
                                        {{ countdown.minutes }}
                                    </span>

                                    <span class="text-[8px] md:text-[9px] uppercase tracking-[0.2em] text-[#6B5328]/50">
                                        {{ t("minutes") }}
                                    </span>
                                </div>


                                <!-- Seconds -->
                                <div class="
                        flex flex-col items-center justify-center
                        rounded-xl
                        bg-[#FAF6EE]/80
                        border border-[#B38E46]/15
                        py-4 px-2
                        min-h-[82px]
                    ">
                                    <span
                                        class="block font-mepandes text-2xl md:text-3xl text-[#6B5328] leading-none mb-2">
                                        {{ countdown.seconds }}
                                    </span>

                                    <span class="text-[8px] md:text-[9px] uppercase tracking-[0.2em] text-[#6B5328]/50">
                                        {{ t("seconds") }}
                                    </span>
                                </div>

                            </div>


                            <!-- Save To Calendar -->
                            <div class="flex justify-center w-full">

                                <a :href="isAndroid ? googleCalendarLink : '/save-the-date-mepandes.ics'"
                                    :target="isAndroid ? '_blank' : undefined"
                                    :download="!isAndroid ? 'save-the-date-mepandes.ics' : undefined" class="
                        inline-flex
                        items-center
                        justify-center
                        gap-3
                        py-3
                        px-7
                        md:px-8
                        bg-[#B38E46]
                        text-white
                        text-[9px]
                        md:text-[10px]
                        font-semibold
                        tracking-[0.25em]
                        uppercase
                        rounded-full
                        shadow-sm
                        hover:bg-[#6B5328]
                        transition-all
                        duration-300
                    ">
                                    <UIcon name="mdi:calendar-heart" class="w-4 h-4" />

                                    {{ t("saveToCal") }}
                                </a>

                            </div>


                            <!-- Bottom Ornament -->
                            <div class="flex items-center justify-center mt-10">

                                <div class="flex items-center gap-3">

                                    <div class="w-8 h-px bg-[#B38E46]/25"></div>

                                    <!-- Center Diamond -->
                                    <div class="w-1.5 h-1.5 rotate-45 border border-[#B38E46]/50"></div>

                                    <div class="w-8 h-px bg-[#B38E46]/25"></div>

                                </div>

                            </div>

                        </div>

                    </div>

                </section>

                <!-- EVENT -->
                <section class="py-24 px-6 relative w-full bg-[#FAF6EE]">

                    <!-- Background Decoration -->
                    <div class="absolute inset-0 pointer-events-none overflow-hidden">

                        <!-- Subtle Watermark -->
                        <div class="absolute inset-0 flex items-center justify-center">
                            <img src="https://assets.keevia.id/mepandes/logo_jeroan_no_bg.png" alt=""
                                class="w-[65%] max-w-sm object-contain opacity-[0.025]" />
                        </div>

                        <!-- Soft Gold Gradient -->
                        <div
                            class="absolute inset-0 bg-gradient-to-b from-transparent via-[#B38E46]/[0.02] to-[#E8DFD1]/20">
                        </div>

                    </div>


                    <div class="max-w-5xl mx-auto relative z-10">

                        <!-- SECTION DIVIDER -->
                        <div class="flex flex-col items-center mb-16">

                            <div class="w-px h-16 bg-gradient-to-b from-transparent via-[#B38E46]/30 to-[#B38E46]/50">
                            </div>

                            <div class="w-1.5 h-1.5 rotate-45 bg-[#B38E46]/55 mt-2"></div>

                        </div>


                        <!-- HEADER -->
                        <div class="
                flex flex-col items-center text-center
                mb-14
                scroll-animate
                opacity-90
                translate-y-8
                transition-all
                duration-1000
            ">

                            <!-- Ornament -->
                            <div class="flex items-center gap-4 mb-7">

                                <div class="w-12 h-px bg-gradient-to-r from-transparent to-[#B38E46]/35">
                                </div>

                                <div class="w-1.5 h-1.5 rotate-45 border border-[#B38E46]/60"></div>

                                <div class="w-12 h-px bg-gradient-to-l from-transparent to-[#B38E46]/35">
                                </div>

                            </div>


                            <!-- Label -->
                            <p class="
                    text-[9px]
                    md:text-[10px]
                    font-semibold
                    tracking-[0.45em]
                    text-[#B38E46]
                    uppercase
                    mb-4
                ">
                                Upacara
                            </p>


                            <!-- Title -->
                            <h2 class="
                    font-mepandes
                    text-3xl
                    md:text-4xl
                    text-[#6B5328]
                    tracking-wide
                    leading-relaxed
                    mb-5
                ">
                                {{ t("resepsiTitle") }}
                            </h2>


                            <!-- Divider -->
                            <div class="flex items-center gap-3">

                                <div class="w-8 h-px bg-[#B38E46]/30"></div>

                                <div class="w-1 h-1 rounded-full bg-[#B38E46]/50"></div>

                                <div class="w-8 h-px bg-[#B38E46]/30"></div>

                            </div>

                        </div>


                        <!-- EVENT CARD -->
                        <div class="grid grid-cols-1 gap-8">

                            <div class="
                    relative
                    max-w-2xl
                    mx-auto
                    w-full
                    bg-white/65
                    backdrop-blur-sm
                    border border-[#B38E46]/20
                    rounded-2xl
                    p-8
                    md:p-12
                    text-center
                    shadow-[0_15px_45px_rgba(107,83,40,0.06)]
                    scroll-animate
                    opacity-0
                    translate-y-8
                    transition-all
                    duration-1000
                    delay-200
                ">

                                <!-- Inner Border -->
                                <div class="
                        absolute
                        inset-3
                        md:inset-4
                        border
                        border-[#B38E46]/[0.08]
                        rounded-xl
                        pointer-events-none
                    "></div>


                                <!-- ICON -->
                                <div class="
                        relative
                        w-14
                        h-14
                        mx-auto
                        rounded-full
                        bg-[#FAF6EE]
                        border
                        border-[#B38E46]/20
                        flex
                        items-center
                        justify-center
                        mb-7
                    ">

                                    <UIcon name="mdi:temple-hindu-outline" class="w-6 h-6 text-[#B38E46]/70" />

                                </div>


                                <!-- TITLE -->
                                <h3 class="
                        relative
                        font-mepandes
                        text-2xl
                        md:text-3xl
                        text-[#6B5328]
                        mb-5
                        tracking-wide
                    ">
                                    {{ t("resepsiTitle") }}
                                </h3>


                                <!-- DATE -->
                                <p class="
                        text-xs
                        md:text-sm
                        text-[#6B5328]/65
                        mb-2
                        tracking-wide
                    ">
                                    {{ t("dateFull") }}
                                </p>


                                <!-- TIME -->
                                <p class="
                        text-xs
                        md:text-sm
                        text-[#6B5328]
                        font-semibold
                        mb-7
                        tracking-wide
                    ">
                                    Pukul {{ resepsiTime }}
                                </p>


                                <!-- DIVIDER -->
                                <div class="flex items-center justify-center gap-3 mb-7">

                                    <div class="w-8 h-px bg-[#B38E46]/25"></div>

                                    <div class="w-1 h-1 rotate-45 bg-[#B38E46]/50"></div>

                                    <div class="w-8 h-px bg-[#B38E46]/25"></div>

                                </div>


                                <!-- LOCATION -->
                                <p class="
                        text-xs
                        md:text-sm
                        leading-relaxed
                        text-[#6B5328]/60
                        font-light
                        mb-9
                        max-w-sm
                        mx-auto
                    ">
                                    {{ t("resepsiLocation") }}
                                </p>


                                <!-- MAP BUTTON -->
                                <a href="https://maps.app.goo.gl/ZEBBtygPWA8bNZxZ7" target="_blank"
                                    rel="noopener noreferrer" class="
                        inline-flex
                        items-center
                        justify-center
                        gap-2
                        py-3
                        px-7
                        bg-[#B38E46]
                        text-white
                        text-[9px]
                        md:text-[10px]
                        font-semibold
                        tracking-[0.25em]
                        uppercase
                        hover:bg-[#6B5328]
                        transition-all
                        duration-300
                        rounded-full
                        shadow-sm
                    ">

                                    <UIcon name="mdi:map-marker-outline" class="w-4 h-4" />

                                    {{ t("openMap") }}

                                </a>

                            </div>

                        </div>

                    </div>

                </section>

                <!-- RSVP & UCAPAN -->
                <section class="py-20 px-6 max-w-5xl mx-auto w-full relative bg-[#FAF6EE]">

                    <!-- BACKGROUND DECORATION -->
                    <div class="absolute inset-0 pointer-events-none overflow-hidden">

                        <!-- Watermark -->
                        <div class="absolute inset-0 flex items-center justify-center">
                            <img src="https://assets.keevia.id/mepandes/logo_jeroan_no_bg.png" alt=""
                                class="w-[70%] max-w-md object-contain opacity-[0.025]" />
                        </div>

                        <!-- Soft Gold Gradient -->
                        <div
                            class="absolute inset-0 bg-gradient-to-b from-transparent via-[#B38E46]/[0.02] to-[#E8DFD1]/20">
                        </div>

                    </div>


                    <div class="relative z-10">

                        <!-- HEADER -->
                        <div class="
                flex flex-col items-center text-center
                mb-16
                scroll-animate
                opacity-90
                translate-y-8
                transition-all
                duration-1000
            ">

                            <!-- Top Ornament -->
                            <div class="flex items-center gap-4 mb-7">
                                <div class="w-12 h-px bg-gradient-to-r from-transparent to-[#B38E46]/35">
                                </div>

                                <div class="w-1.5 h-1.5 rotate-45 border border-[#B38E46]/60"></div>

                                <div class="w-12 h-px bg-gradient-to-l from-transparent to-[#B38E46]/35">
                                </div>
                            </div>

                            <!-- Label -->
                            <p class="
                    text-[9px]
                    md:text-[10px]
                    font-semibold
                    tracking-[0.45em]
                    uppercase
                    mb-4
                    text-[#B38E46]
                ">
                                {{ t("rsvpSub") }}
                            </p>

                            <!-- Title -->
                            <h2 class="
                    font-mepandes
                    text-3xl
                    md:text-4xl
                    text-[#6B5328]
                    tracking-wide
                    leading-relaxed
                    mb-5
                ">
                                {{ t("rsvpTitle") }}
                            </h2>

                            <!-- Divider -->
                            <div class="flex items-center gap-3">
                                <div class="w-8 h-px bg-[#B38E46]/30"></div>
                                <div class="w-1 h-1 rounded-full bg-[#B38E46]/50"></div>
                                <div class="w-8 h-px bg-[#B38E46]/30"></div>
                            </div>

                        </div>


                        <!-- CONTENT -->
                        <div class="grid grid-cols-1 gap-10 items-start">

                            <!-- FORM -->
                            <div class="
                    relative
                    bg-white/65
                    backdrop-blur-sm
                    border border-[#B38E46]/20
                    p-8
                    md:p-10
                    rounded-2xl
                    shadow-[0_15px_45px_rgba(107,83,40,0.06)]
                    scroll-animate
                    opacity-90
                    translate-y-8
                    transition-all
                    duration-1000
                    delay-100
                ">

                                <!-- Inner Border -->
                                <div class="
                        absolute
                        inset-3
                        md:inset-4
                        border
                        border-[#B38E46]/[0.08]
                        rounded-xl
                        pointer-events-none
                    "></div>


                                <!-- FORM CONTENT -->
                                <div class="relative">

                                    <h3 class="
                            font-mepandes
                            text-2xl
                            md:text-3xl
                            mb-8
                            text-[#6B5328]
                            tracking-wide
                        ">
                                        {{ t("confirmAttendance") }}
                                    </h3>


                                    <form @submit.prevent="submitRSVP" class="space-y-7">

                                        <!-- NAME -->
                                        <div>
                                            <input type="text" v-model="nama" :placeholder="t('fullNamePlaceholder')"
                                                class="
                                    w-full
                                    pb-3
                                    border-b
                                    border-[#B38E46]/20
                                    bg-transparent
                                    text-sm
                                    text-[#6B5328]
                                    focus:outline-none
                                    focus:border-[#B38E46]
                                    transition
                                    placeholder:text-[#6B5328]/35
                                    font-light
                                " required />
                                        </div>


                                        <!-- ATTENDANCE -->
                                        <div>

                                            <p class="
                                    text-[9px]
                                    md:text-[10px]
                                    tracking-[0.35em]
                                    text-[#B38E46]
                                    uppercase
                                    font-semibold
                                    mb-3
                                ">
                                                {{ t("confirmAttendance") }}
                                            </p>


                                            <div class="flex gap-3">

                                                <!-- HADIR -->
                                                <label class="cursor-pointer flex-1">

                                                    <input type="radio" v-model="kehadiran" value="Hadir" name="hadir"
                                                        class="peer sr-only" required>

                                                    <div class="
                                            py-3
                                            text-center
                                            border
                                            border-[#B38E46]/20
                                            bg-[#FAF6EE]/70
                                            text-[#6B5328]/60
                                            text-[10px]
                                            uppercase
                                            tracking-[0.2em]
                                            peer-checked:bg-[#B38E46]
                                            peer-checked:text-white
                                            peer-checked:border-[#B38E46]
                                            transition-all
                                            rounded-full
                                        ">
                                                        {{ t("attendYes") }}
                                                    </div>

                                                </label>


                                                <!-- TIDAK HADIR -->
                                                <label class="cursor-pointer flex-1">

                                                    <input type="radio" v-model="kehadiran" value="Tidak Hadir"
                                                        name="hadir" class="peer sr-only">

                                                    <div class="
                                            py-3
                                            text-center
                                            border
                                            border-[#B38E46]/20
                                            bg-[#FAF6EE]/70
                                            text-[#6B5328]/60
                                            text-[10px]
                                            uppercase
                                            tracking-[0.2em]
                                            peer-checked:bg-[#E8DFD1]
                                            peer-checked:text-[#6B5328]
                                            peer-checked:border-[#B38E46]/30
                                            transition-all
                                            rounded-full
                                        ">
                                                        {{ t("attendNo") }}
                                                    </div>

                                                </label>

                                            </div>

                                        </div>


                                        <!-- MESSAGE -->
                                        <div>

                                            <textarea v-model="ucapan" rows="4" :placeholder="t('wishesPlaceholder')"
                                                class="
                                    w-full
                                    p-4
                                    border
                                    border-[#B38E46]/20
                                    bg-[#FAF6EE]/60
                                    text-sm
                                    text-[#6B5328]
                                    focus:outline-none
                                    focus:border-[#B38E46]/60
                                    placeholder:text-[#6B5328]/35
                                    font-light
                                    rounded-xl
                                    resize-none
                                    transition
                                " required></textarea>

                                        </div>


                                        <!-- BUTTON -->
                                        <button :disabled="isSubmitting" class="
                                w-full
                                py-4
                                bg-[#B38E46]
                                text-white
                                text-[10px]
                                font-semibold
                                tracking-[0.25em]
                                uppercase
                                hover:bg-[#6B5328]
                                transition-all
                                rounded-full
                                cursor-pointer
                                disabled:opacity-50
                            ">

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

                            </div>


                            <!-- MESSAGE LIST -->
                            <div class="
                    relative
                    bg-white/65
                    backdrop-blur-sm
                    border border-[#B38E46]/20
                    p-8
                    md:p-10
                    rounded-2xl
                    shadow-[0_15px_45px_rgba(107,83,40,0.06)]
                    h-full
                    max-h-[550px]
                    scroll-animate
                    opacity-90
                    translate-y-8
                    transition-all
                    duration-1000
                    delay-200
                ">

                                <!-- Inner Border -->
                                <div class="
                        absolute
                        inset-3
                        md:inset-4
                        border
                        border-[#B38E46]/[0.08]
                        rounded-xl
                        pointer-events-none
                    "></div>


                                <div class="relative">

                                    <!-- HEADER -->
                                    <div class="
                            mb-6
                            border-b
                            border-[#B38E46]/15
                            pb-4
                            flex
                            items-center
                            justify-between
                            gap-4
                        ">

                                        <h3 class="
                                font-mepandes
                                text-2xl
                                text-[#6B5328]
                                tracking-wide
                            ">
                                            {{ t("wishesTitle") }}
                                        </h3>


                                        <span class="
                                bg-[#FAF6EE]
                                border
                                border-[#B38E46]/15
                                text-[#6B5328]/60
                                text-[10px]
                                px-3
                                py-1
                                rounded-full
                                whitespace-nowrap
                            ">
                                            {{ totalMessages }} {{ t("messagesCount") }}
                                        </span>

                                    </div>


                                    <!-- MESSAGES -->
                                    <template v-if="guestMessages.length > 0">

                                        <div class="space-y-4 max-h-[420px] overflow-y-auto pr-1">

                                            <div v-for="(entry, index) in guestMessages" :key="index" class="
                                    bg-[#FAF6EE]/70
                                    backdrop-blur-sm
                                    border
                                    border-[#B38E46]/10
                                    p-4
                                    rounded-xl
                                    space-y-2
                                    shadow-sm
                                ">

                                                <div class="flex justify-between items-start gap-4">

                                                    <p class="
                                            font-medium
                                            text-[#6B5328]
                                            text-sm
                                        ">
                                                        {{ entry.nama }}
                                                    </p>


                                                    <span class="
                                            text-[9px]
                                            uppercase
                                            tracking-[0.15em]
                                            px-2
                                            py-1
                                            rounded-full
                                        " :class="entry.kehadiran === 'Hadir'
                                            ? 'bg-[#B38E46] text-white'
                                            : 'bg-[#E8DFD1] text-[#6B5328]/60'">
                                                        {{ entry.kehadiran === 'Hadir' ? t('attendBadge') :
                                                            t('absentBadge') }}
                                                    </span>

                                                </div>


                                                <p class="
                                        text-[#6B5328]/65
                                        text-xs
                                        font-light
                                        leading-relaxed
                                    ">
                                                    "{{ entry.ucapan }}"
                                                </p>


                                                <p class="
                                        text-[9px]
                                        text-[#6B5328]/40
                                    ">
                                                    {{ formatDate(entry.tanggal) }}
                                                </p>

                                            </div>


                                            <!-- LOAD MORE -->
                                            <div v-if="hasMore" class="pt-4 pb-2 flex justify-center w-full">

                                                <button @click="loadMoreMessages" :disabled="isLoadingMore" class="
                                        px-6
                                        py-2
                                        bg-[#FAF6EE]
                                        border
                                        border-[#B38E46]/20
                                        text-[#6B5328]/70
                                        text-[10px]
                                        tracking-[0.2em]
                                        uppercase
                                        rounded-full
                                        hover:bg-[#B38E46]
                                        hover:text-white
                                        transition-all
                                        flex
                                        items-center
                                        gap-2
                                        cursor-pointer
                                    ">

                                                    <span v-if="isLoadingMore" class="
                                            animate-spin
                                            border-2
                                            border-[#B38E46]
                                            border-t-transparent
                                            rounded-full
                                            w-4
                                            h-4
                                        ">
                                                    </span>

                                                    <span v-else>
                                                        {{ t('loadMore') }}
                                                    </span>

                                                </button>

                                            </div>

                                        </div>

                                    </template>


                                    <!-- EMPTY -->
                                    <template v-else>

                                        <div class="
                                flex
                                flex-col
                                items-center
                                justify-center
                                text-[#6B5328]/40
                                text-sm
                                py-16
                            ">

                                            <UIcon name="mdi:message-outline"
                                                class="w-8 h-8 mb-4 opacity-40 text-[#B38E46]" />

                                            <p class="font-light">
                                                {{ t("noWishes") }}
                                            </p>

                                        </div>

                                    </template>

                                </div>

                            </div>

                        </div>

                    </div>

                </section>

                <!-- FOOTER -->
                <section class="
        relative
        w-full
        min-h-[100dvh]
        overflow-hidden
        flex
        flex-col
        text-center
        select-none
        bg-[#FAF6EE]
    ">

                    <!-- BACKGROUND DECORATION -->
                    <div class="absolute inset-0 pointer-events-none overflow-hidden">

                        <!-- Watermark -->
                        <div class="absolute inset-0 flex items-center justify-center">
                            <img src="https://assets.keevia.id/mepandes/logo_jeroan_no_bg.png" alt="" class="
                    w-[75%]
                    max-w-lg
                    object-contain
                    opacity-[0.20]
                " />
                        </div>

                        <!-- Soft Gold Glow -->
                        <div class="
                absolute
                inset-0
                bg-gradient-to-b
                from-[#B38E46]/[0.02]
                via-transparent
                to-[#E8DFD1]/35
            "></div>

                    </div>


                    <!-- CONTENT -->
                    <div class="
            relative
            z-10
            min-h-[100dvh]
            flex
            flex-col
            items-center
            px-6
            py-16
        ">

                        <!-- TOP -->
                        <div class="flex flex-col items-center">

                            <!-- Ornament -->
                            <div class="flex items-center gap-4 mb-8">

                                <div class="
                        w-12
                        h-px
                        bg-gradient-to-r
                        from-transparent
                        to-[#B38E46]/40
                    "></div>

                                <div class="
                        w-1.5
                        h-1.5
                        rotate-45
                        border
                        border-[#B38E46]/60
                    "></div>

                                <div class="
                        w-12
                        h-px
                        bg-gradient-to-l
                        from-transparent
                        to-[#B38E46]/40
                    "></div>

                            </div>


                            <!-- Closing Title -->
                            <h2 class="
        font-mepandes
        text-3xl
        md:text-5xl
        font-medium
        text-[#6B5328]
        tracking-wide
        leading-relaxed
        mb-5
    ">
                                Matur Suksma
                            </h2>

                            <!-- Subtitle -->
                            <p class="
        max-w-md
        text-[10px]
        md:text-xs
        leading-relaxed
        tracking-wide
        text-[#6B5328]/60
        font-light
    ">
                                {{ t("thankYouSub") }}
                            </p>

                        </div>


                        <!-- FLEXIBLE SPACE -->
                        <div class="flex-1"></div>


                        <!-- BOTTOM -->
                        <div class="flex flex-col items-center">

                            <!-- Vertical Ornament -->
                            <div class="flex flex-col items-center mb-8">

                                <div class="
                        w-px
                        h-10
                        bg-gradient-to-b
                        from-transparent
                        to-[#B38E46]/40
                    "></div>

                                <div class="
                        w-1
                        h-1
                        rounded-full
                        bg-[#B38E46]/50
                        mt-2
                    "></div>

                            </div>


                            <!-- Keevia Instagram -->
                            <a href="https://instagram.com/keevia.id" target="_blank" rel="noopener noreferrer" class="
                    w-10
                    h-10
                    rounded-full
                    border
                    border-[#B38E46]/25
                    bg-white/50
                    backdrop-blur-sm
                    flex
                    items-center
                    justify-center
                    text-[#B38E46]/70
                    hover:text-[#6B5328]
                    hover:border-[#B38E46]/50
                    hover:bg-white
                    transition-all
                    mb-5
                ">
                                <UIcon name="mdi:instagram" class="w-5 h-5" />
                            </a>


                            <!-- Brand -->
                            <p class="
                    text-[10px]
                    tracking-[0.35em]
                    uppercase
                    text-[#6B5328]/55
                    mb-3
                ">
                                Keevia.id
                            </p>


                            <!-- Copyright -->
                            <p class="
                    text-[9px]
                    tracking-widest
                    text-[#6B5328]/35
                    uppercase
                ">
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
        weddingOf: "Mepandes",
        dateFull: "Jumat, 16 Oktober 2026",
        toYth: "Kepada Yth.",
        openingMsg: "Merupakan suatu kehormatan dan kebahagiaan bagi kami apabila Bapak/Ibu/Saudara/i berkenan hadir untuk memberikan doa restu dalam rangkaian upacara Manusa Yadnya Mepandes kami.",
        openBtn: "BUKA UNDANGAN",
        bibleQuote: "“Sebab itu seorang laki-laki akan meninggalkan ayahnya dan ibunya dan bersatu dengan isterinya, sehingga keduanya menjadi satu daging.”",
        bibleVerse: "Kejadian 2:24",
        theGroom: "Mempelai Pria",
        sonOf: "Putra Kedua dari",
        parentsGroom: "Bapak Drs. I Made Sugiarta & Ibu Ni Wayan Yoniasih",
        theBride: "Mempelai Wanita",
        daughterOf: "Putri Kedua dari",
        parentsBride: "Bapak Komang Sumada & Ibu Ketut Remiti",
        saveOurDate: "Upacara Mepandes",
        dateMain: "Jumat, 16 Oktober 2026",
        days: "Hari",
        hours: "Jam",
        minutes: "Menit",
        seconds: "Detik",
        saveToCal: "Simpan Tanggal",
        resepsiTitle: "Resepsi",
        resepsiLocation: "Puri Agung Marga - Saren Kelod, Tabanan, Bali",
        openMap: "Lihat Lokasi",
        rsvpSub: "Your Presence",
        rsvpTitle: "Konfirmasi Kehadiran & Ucapan",
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
        sendBtn: "Kirim Doa",
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
        thankYouSub: "Dengan penuh rasa syukur, kami mengucapkan terima kasih atas kehadiran dan doa restu Bapak/Ibu/Saudara/i dalam rangkaian Upacara Manusa Yadnya Mepandes kami."
    }
}

const t = (key: keyof typeof dict.id) => dict.id[key]

const guestName = computed(() => (route.query.to as string) || 'Nama Tamu')
const resepsiTime = computed(() => (route.query.jam as string) || '09.00 WITA - Selesai')

const isAndroid = computed(() => {
    if (!import.meta.client) return false
    return /Android/i.test(navigator.userAgent)
})

const googleCalendarLink = computed(() => {
    const start = '20261016T090000';
    const end = '20261017T160000';
    const title = encodeURIComponent('Mepandes - I Gusti A. Ayu Galuh Parwati, I Gusti Ayu Cahya Pratiwi, I Gusti Ngurah Agung Alit Arya Wibawa, I Gusti Agung Ngurah Bratha Prasetya');
    const details = encodeURIComponent('Merupakan suatu kehormatan dan kebahagiaan bagi kami apabila Bapak/Ibu/Saudara/i berkenan hadir untuk memberikan doa restu pada upacara Manusa Yadnya Mepandes kami.');
    const location = encodeURIComponent('Puri Agung Marga - Saren Kelod, Tabanan, Bali');

    return `https://www.google.com/calendar/render?action=TEMPLATE&text=${title}&dates=${start}/${end}&details=${details}&location=${location}`
})

const isOpen = ref(false)

const openInvitation = () => {
    isOpen.value = true
    document.body.classList.remove('overflow-hidden')
    nextTick(() => {
        setTimeout(initScrollAnimations, 100)
        if (audioControl && typeof audioControl.setMusicId === 'function') {
            audioControl.setMusicId('-BR872_MnuQ')
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
        audioControl.setMusicId('-BR872_MnuQ')
        audioControl.setTheme?.('gold-elegan')
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

const saveOurDate = new Date('2026-10-16T08:00:00+08:00').getTime()
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
    ? firebase.collection(firebase.db, 'rsvp_mepandes_keluarga_intan')
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
    font-family: 'Cormorant Garamond', serif;
}

.font-sans {
    font-family: 'DM Sans', sans-serif;
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
