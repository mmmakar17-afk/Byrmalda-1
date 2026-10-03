<!DOCTYPE html>
<html lang="uk">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RESURRECTION METAL FEST 2027 - Найбільший рок-фестиваль історії</title>

    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>

    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <!-- Google Fonts: Permanent Marker & Montserrat -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,400;0,700;0,900;1,900&family=Permanent+Marker&family=Metal+Mania&display=swap" rel="stylesheet">

    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        metal: {
                            900: '#0a0a0c',
                            800: '#121216',
                            700: '#1e1e24',
                            600: '#2d2d36',
                            accent: '#ff1e00',
                            gold: '#ffb703',
                            chrome: '#e2e8f0'
                        }
                    },
                    fontFamily: {
                        metal: ['"Metal Mania"', 'cursive'],
                        rock: ['"Permanent Marker"', 'cursive'],
                        sans: ['Montserrat', 'sans-serif']
                    }
                }
            }
        }
    </script>

    <style>
        /* Custom Metallic Styles & Animations */
        body {
            background-color: #358736
        ;
            color: #e2e8f0;
            font-family: 'Montserrat', sans-serif;
            overflow-x: hidden;
        }

        .metal-text-gradient {
            background: linear-gradient(180deg, #ffffff 0%, #a1a1aa 50%, #4b5563 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            filter: drop-shadow(0 2px 8px rgba(255, 30, 0, 0.4));
        }

        .fire-text-gradient {
            background: linear-gradient(180deg, #fff7ed 0%, #f97316 40%, #dc2626 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            filter: drop-shadow(0 0 12px rgba(239, 68, 68, 0.8));
        }

        .metal-border {
            border: 2px solid #3f3f46;
            box-shadow: inset 0 0 10px rgba(0,0,0,0.8), 0 0 15px rgba(255, 30, 0, 0.2);
            background: linear-gradient(135deg, #18181b 0%, #09090b 100%);
        }

        .metal-btn {
            background: linear-gradient(180deg, #b91c1c 0%, #7f1d1d 100%);
            border: 2px solid #ef4444;
            box-shadow: 0 4px 15px rgba(220, 38, 38, 0.4), inset 0 1px 0 rgba(255,255,255,0.3);
            transition: all 0.15s ease-in-out;
            position: relative;
            overflow: hidden;
        }

        .metal-btn:hover {
            transform: translateY(-2px) scale(1.02);
            background: linear-gradient(180deg, #dc2626 0%, #991b1b 100%);
            box-shadow: 0 6px 25px rgba(239, 68, 68, 0.7), inset 0 1px 0 rgba(255,255,255,0.5);
        }

        .metal-btn:active {
            transform: translateY(1px) scale(0.98);
        }

        .metal-btn-silver {
            background: linear-gradient(180deg, #52525b 0%, #27272a 100%);
            border: 2px solid #71717a;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.5);
        }

        .metal-btn-silver:hover {
            background: linear-gradient(180deg, #71717a 0%, #3f3f46 100%);
            box-shadow: 0 0 20px rgba(255, 255, 255, 0.3);
        }

        .custom-scrollbar::-webkit-scrollbar {
            width: 8px;
        }
        .custom-scrollbar::-webkit-scrollbar-track {
            background: #09090b;
        }
        .custom-scrollbar::-webkit-scrollbar-thumb {
            background: #dc2626;
            border-radius: 4px;
        }

        /* Lightning pulse effect */
        @keyframes thunder {
            0%, 100% { opacity: 0.1; }
            50% { opacity: 0.35; }
            52% { opacity: 0.8; }
            54% { opacity: 0.2; }
        }
        .thunder-bg {
            animation: thunder 6s infinite;
        }
    </style>
</head>
<body class="custom-scrollbar">

    <!-- Custom Metal Notification Modal (Replaces Browser Alerts) -->
    <div id="metalModal" class="fixed inset-0 bg-black/80 backdrop-blur-md z-50 flex items-center justify-center p-4 hidden">
        <div class="metal-border p-6 rounded-2xl bg-zinc-950 max-w-md w-full text-center space-y-4 shadow-2xl relative border-red-600">
            <div class="w-16 h-16 rounded-full bg-red-950 border border-red-500 flex items-center justify-center text-red-500 text-3xl mx-auto">
                <i id="modalIcon" class="fa-solid fa-skull"></i>
            </div>
            <h3 id="modalTitle" class="font-metal text-2xl text-white uppercase tracking-wider">ПОВІДОМЛЕННЯ</h3>
            <p id="modalMessage" class="text-sm text-zinc-300 leading-relaxed"></p>
            <button onclick="closeMetalModal()" class="metal-btn text-white font-bold px-6 py-2 rounded-lg text-xs uppercase tracking-wider w-full">
                Зрозуміло! 🤘
            </button>
        </div>
    </div>

    <!-- Sound Effect Toggle Floating Banner -->
    <div id="soundBanner" class="fixed top-0 left-0 w-full bg-red-950/90 border-b border-red-600 text-red-200 text-xs md:text-sm py-2 px-4 z-50 flex justify-between items-center backdrop-blur-md">
        <div class="flex items-center gap-2">
            <i class="fa-solid fa-volume-high text-red-500 animate-pulse"></i>
            <span><strong>АУДІО-РЕЖИМ АКТИВОВАНО:</strong> Клікай на будь-які кнопки для важкого металевого звуку!</span>
        </div>
        <button onclick="toggleAudioEngine()" id="audioToggleBtn" class="bg-red-800 hover:bg-red-700 text-white font-bold px-3 py-1 rounded text-xs transition uppercase border border-red-500">
            <i class="fa-solid fa-volume-xmark mr-1"></i> Вимкнути Звук
        </button>
    </div>

    <!-- Navigation Header -->
    <header class="sticky top-10 z-40 bg-metal-900/90 border-b border-zinc-800 backdrop-blur-md shadow-2xl">
        <div class="max-w-7xl mx-auto px-4 py-3 flex justify-between items-center">
            <!-- Logo -->
            <a href="#" class="flex items-center gap-3 group" onclick="playMetalSound('chord')">
                <div class="w-10 h-10 rounded-full bg-red-600/20 border border-red-500 flex items-center justify-center text-red-500 text-2xl group-hover:rotate-12 transition-transform">
                    <i class="fa-solid fa-skull"></i>
                </div>
                <div>
                    <h1 class="font-metal text-2xl md:text-3xl text-red-600 tracking-wider leading-none">RESURRECTION</h1>
                    <p class="text-[10px] tracking-widest text-zinc-400 uppercase font-bold">METAL FEST 2027 • FREE ADMISSION</p>
                </div>
            </a>

            <!-- Nav Links -->
            <nav class="hidden md:flex items-center gap-6 font-semibold text-sm">
                <a href="#lineup" onclick="playMetalSound('click')" class="hover:text-red-500 transition">ЛАЙН-АП</a>
                <a href="#soundboard" onclick="playMetalSound('click')" class="hover:text-red-500 transition"><i class="fa-solid fa-guitar text-red-500 mr-1"></i> РИФ-ПАНЕЛЬ</a>
                <a href="#location" onclick="playMetalSound('click')" class="hover:text-red-500 transition">ЛОКАЦІЯ</a>
                <a href="#ticket" onclick="playMetalSound('click')" class="hover:text-red-500 transition">КВИРОК</a>
                <a href="#decibel" onclick="playMetalSound('click')" class="hover:text-red-500 transition text-yellow-500"><i class="fa-solid fa-bolt mr-1"></i>140 dB</a>
            </nav>

            <!-- CTA Header Button -->
            <a href="#ticket" onclick="playMetalSound('slam')" class="metal-btn text-white font-bold px-5 py-2 rounded-lg text-xs md:text-sm uppercase tracking-wider flex items-center gap-2">
                <i class="fa-solid fa-ticket"></i> Отримати Квиток
            </a>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="relative min-h-[90vh] flex items-center justify-center pt-16 pb-12 overflow-hidden border-b border-zinc-800">
        <!-- Background Overlay / Canvas Effect -->
        <div class="absolute inset-0 bg-gradient-to-b from-red-950/20 via-metal-900 to-metal-900 z-10 pointer-events-none"></div>
        <div class="absolute inset-0 thunder-bg bg-[radial-gradient(ellipse_at_top,_var(--tw-gradient-stops))] from-red-900/40 via-transparent to-transparent pointer-events-none"></div>

        <!-- Flame Particles Canvas Background -->
        <canvas id="flameCanvas" class="absolute inset-0 z-0 opacity-40 pointer-events-none"></canvas>

        <div class="relative z-20 max-w-5xl mx-auto text-center px-4">
            <!-- Badge -->
            <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full bg-red-950/80 border border-red-600/50 text-red-400 font-bold text-xs uppercase tracking-widest mb-6 shadow-lg animate-bounce">
                <i class="fa-solid fa-fire text-yellow-500"></i> НАЙБІЛЬШИЙ І НАЙГУЧНІШИЙ ФЕСТИВАЛЬ В ІСТОРІЇ ЛЮДСТВА <i class="fa-solid fa-fire text-yellow-500"></i>
            </div>

            <!-- Main Title -->
            <h1 class="font-metal text-5xl sm:text-7xl md:text-9xl tracking-wider text-white mb-2 leading-none uppercase drop-shadow-[0_10px_20px_rgba(255,0,0,0.5)]">
                <span class="fire-text-gradient">RESURRECTION</span>
            </h1>
            <p class="font-rock text-2xl md:text-4xl text-zinc-300 mb-6 tracking-widest uppercase">
                ВСІ ЛЕГЕНДИ ВАЖКОГО МЕТАЛУ ВОСКРЕСНУТЬ НА ОДНІЙ СЦЕНІ
            </p>

            <p class="max-w-3xl mx-auto text-zinc-400 text-sm md:text-lg mb-8 leading-relaxed">
                Black Sabbath, Ozzy, Pantera, Metallica, AC/DC, Slipknot, Dio, Dimebag Darrell та десятки інших грандів важкої музики зберуться разом. <span class="text-red-500 font-bold underline">Вхід 100% безкоштовний</span> для кожного металіста світу на злітно-посадковій смузі найбільшого аеропорту планети!
            </p>

            <!-- Countdown Timer -->
            <div class="grid grid-cols-2 sm:grid-cols-4 gap-3 max-w-2xl mx-auto mb-10">
                <div class="metal-border p-3 rounded-lg text-center">
                    <span id="cd-days" class="font-metal text-3xl md:text-5xl text-red-500 block">365</span>
                    <span class="text-[10px] md:text-xs text-zinc-400 font-bold tracking-widest uppercase">Днів</span>
                </div>
                <div class="metal-border p-3 rounded-lg text-center">
                    <span id="cd-hours" class="font-metal text-3xl md:text-5xl text-red-500 block">18</span>
                    <span class="text-[10px] md:text-xs text-zinc-400 font-bold tracking-widest uppercase">Годин</span>
                </div>
                <div class="metal-border p-3 rounded-lg text-center">
                    <span id="cd-mins" class="font-metal text-3xl md:text-5xl text-red-500 block">42</span>
                    <span class="text-[10px] md:text-xs text-zinc-400 font-bold tracking-widest uppercase">Хвилин</span>
                </div>
                <div class="metal-border p-3 rounded-lg text-center">
                    <span id="cd-secs" class="font-metal text-3xl md:text-5xl text-red-500 block">09</span>
                    <span class="text-[10px] md:text-xs text-zinc-400 font-bold tracking-widest uppercase">Секунд</span>
                </div>
            </div>

            <!-- CTA Action Buttons -->
            <div class="flex flex-col sm:flex-row justify-center items-center gap-4">
                <a href="#ticket" onclick="playMetalSound('slam')" class="w-full sm:w-auto metal-btn text-white font-black text-lg px-8 py-4 rounded-xl shadow-2xl flex items-center justify-center gap-3 uppercase tracking-wider">
                    <i class="fa-solid fa-skull-crossbones text-2xl"></i> Зареєструватись Задарма
                </a>
                <button onclick="triggerOverdriveEffect()" class="w-full sm:w-auto metal-btn-silver text-white font-bold text-lg px-8 py-4 rounded-xl flex items-center justify-center gap-3 uppercase tracking-wider">
                    <i class="fa-solid fa-bolt text-yellow-500"></i> Врубати Перегруз!
                </button>
            </div>
        </div>
    </section>

    <!-- Metal Soundboard & Interactive Guitar Synth -->
    <section id="soundboard" class="py-16 bg-metal-800/80 border-b border-zinc-800 relative">
        <div class="max-w-7xl mx-auto px-4">
            <div class="text-center mb-10">
                <h2 class="font-metal text-4xl md:text-6xl text-red-500 tracking-wide uppercase">ІНТЕРАКТИВНА МЕТАЛ-СУМ'ЯТТЯ</h2>
                <p class="text-zinc-400 text-sm md:text-base">Тисни на семпли або на клавіші [A, S, D, F, G, H, J], щоб видавати важкі дисторшн-акорди!</p>
            </div>

            <!-- Guitar & Drum Riff Pad -->
            <div class="grid grid-cols-2 sm:grid-cols-4 md:grid-cols-7 gap-3 mb-8">
                <button onclick="playGuitarChord('E5')" class="metal-border hover:border-red-500 p-4 rounded-xl text-center transition group active:scale-95">
                    <span class="text-xs text-red-500 font-bold block mb-1">КЛАВІША [A]</span>
                    <i class="fa-solid fa-guitar text-2xl text-zinc-300 group-hover:text-red-500 transition mb-2 block"></i>
                    <span class="font-bold text-sm block">E5 POWER CHORD</span>
                </button>
                <button onclick="playGuitarChord('G5')" class="metal-border hover:border-red-500 p-4 rounded-xl text-center transition group active:scale-95">
                    <span class="text-xs text-red-500 font-bold block mb-1">КЛАВІША [S]</span>
                    <i class="fa-solid fa-guitar text-2xl text-zinc-300 group-hover:text-red-500 transition mb-2 block"></i>
                    <span class="font-bold text-sm block">G5 CHORD</span>
                </button>
                <button onclick="playGuitarChord('A5')" class="metal-border hover:border-red-500 p-4 rounded-xl text-center transition group active:scale-95">
                    <span class="text-xs text-red-500 font-bold block mb-1">КЛАВІША [D]</span>
                    <i class="fa-solid fa-guitar text-2xl text-zinc-300 group-hover:text-red-500 transition mb-2 block"></i>
                    <span class="font-bold text-sm block">A5 DROP-D</span>
                </button>
                <button onclick="playGuitarChord('C5')" class="metal-border hover:border-red-500 p-4 rounded-xl text-center transition group active:scale-95">
                    <span class="text-xs text-red-500 font-bold block mb-1">КЛАВІША [F]</span>
                    <i class="fa-solid fa-guitar text-2xl text-zinc-300 group-hover:text-red-500 transition mb-2 block"></i>
                    <span class="font-bold text-sm block">C5 RIFF</span>
                </button>
                <button onclick="playMetalSound('drumBass')" class="metal-border hover:border-yellow-500 p-4 rounded-xl text-center transition group active:scale-95">
                    <span class="text-xs text-yellow-500 font-bold block mb-1">КЛАВІША [G]</span>
                    <i class="fa-solid fa-drum text-2xl text-zinc-300 group-hover:text-yellow-500 transition mb-2 block"></i>
                    <span class="font-bold text-sm block">DOUBLE BASS</span>
                </button>
                <button onclick="playMetalSound('drumSnare')" class="metal-border hover:border-yellow-500 p-4 rounded-xl text-center transition group active:scale-95">
                    <span class="text-xs text-yellow-500 font-bold block mb-1">КЛАВІША [H]</span>
                    <i class="fa-solid fa-drum-steelpan text-2xl text-zinc-300 group-hover:text-yellow-500 transition mb-2 block"></i>
                    <span class="font-bold text-sm block">BLAST BEAT</span>
                </button>
                <button onclick="playMetalSound('metalCrash')" class="metal-border hover:border-red-500 p-4 rounded-xl text-center transition group active:scale-95 col-span-2 sm:col-span-1">
                    <span class="text-xs text-red-500 font-bold block mb-1">КЛАВІША [J]</span>
                    <i class="fa-solid fa-compact-disc text-2xl text-zinc-300 group-hover:text-red-500 transition mb-2 block"></i>
                    <span class="font-bold text-sm block">HEAVY CRASH</span>
                </button>
            </div>

            <!-- Simulated Audio Sampler Deck -->
            <div class="metal-border p-6 rounded-2xl bg-zinc-950 flex flex-col gap-6">
                <div class="flex flex-col md:flex-row items-center justify-between gap-6">
                    <div class="flex items-center gap-4 w-full md:w-auto">
                        <div class="w-16 h-16 rounded-xl bg-red-900/50 border border-red-500 flex items-center justify-center text-3xl text-red-500 shrink-0">
                            <i id="playerDiscIcon" class="fa-solid fa-record-vinyl"></i>
                        </div>
                        <div>
                            <span id="trackBand" class="text-red-500 font-bold text-xs uppercase tracking-widest block">ПЛЕЄР ФЕСТИВАЛЮ</span>
                            <h4 id="trackTitle" class="text-lg md:text-xl font-bold text-white">Black Sabbath - "Iron Man" (Riff Preview)</h4>
                            <p id="trackStatus" class="text-xs text-zinc-400">Натисніть "Слухати Уривок" на будь-якій групі нижче або виберіть трек</p>
                        </div>
                    </div>

                    <!-- Visual Equalizer Bars -->
                    <div class="flex items-end gap-1.5 h-12 px-4 py-2 bg-black rounded-lg border border-zinc-800" id="eqContainer">
                        <div class="eq-bar w-2 bg-red-600 h-3"></div>
                        <div class="eq-bar w-2 bg-red-600 h-6"></div>
                        <div class="eq-bar w-2 bg-red-500 h-4"></div>
                        <div class="eq-bar w-2 bg-yellow-500 h-8"></div>
                        <div class="eq-bar w-2 bg-red-600 h-5"></div>
                        <div class="eq-bar w-2 bg-red-500 h-7"></div>
                        <div class="eq-bar w-2 bg-red-600 h-3"></div>
                        <div class="eq-bar w-2 bg-yellow-500 h-9"></div>
                    </div>

                    <!-- Main Player Control Buttons -->
                    <div class="flex items-center gap-3 w-full md:w-auto justify-center">
                        <button id="mainPlayBtn" onclick="togglePlayCurrentSnippet()" class="metal-btn text-white font-bold px-6 py-3 rounded-xl text-sm uppercase tracking-wider flex items-center gap-2">
                            <i id="mainPlayIcon" class="fa-solid fa-play"></i>
                            <span id="mainPlayText">Грати Уривок</span>
                        </button>
                        <button onclick="stopSnippet()" class="metal-btn-silver text-white font-bold p-3 rounded-xl text-sm">
                            <i class="fa-solid fa-stop"></i>
                        </button>
                    </div>
                </div>

                <!-- Song Progress Bar & Selection Quick Tabs -->
                <div class="space-y-3 border-t border-zinc-800 pt-4">
                    <div class="flex justify-between text-xs text-zinc-400 font-mono">
                        <span id="trackCurrentTime">00:00</span>
                        <span id="trackBandLabel" class="text-red-400 font-bold uppercase">СЕМПЛЕР ВАЖКОГО МЕТАЛУ</span>
                        <span id="trackTotalTime">00:12</span>
          
