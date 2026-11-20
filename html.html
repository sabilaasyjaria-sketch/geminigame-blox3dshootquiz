<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>BloxQuest Arena 3D - Shooter & Hidden Gem Quiz</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@500;600;700&family=Inter:wght@400;600;700;800&display=swap" rel="stylesheet">
    <style>
        * {
            box-sizing: border-box;
            user-select: none;
            -webkit-user-select: none;
        }
        body, html {
            margin: 0;
            padding: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            font-family: 'Inter', sans-serif;
            background-color: #0f172a;
        }
        .font-roblox {
            font-family: 'Fredoka', sans-serif;
            letter-spacing: 0.02em;
        }
        /* Custom 3D Roblox-style chunky buttons */
        .btn-blox {
            transition: all 0.12s cubic-bezier(0.4, 0, 0.2, 1);
            box-shadow: 0 5px 0 rgba(0, 0, 0, 0.35);
        }
        .btn-blox:hover {
            transform: translateY(-2px);
            box-shadow: 0 7px 0 rgba(0, 0, 0, 0.35);
        }
        .btn-blox:active {
            transform: translateY(3px);
            box-shadow: 0 2px 0 rgba(0, 0, 0, 0.35);
        }
        /* Custom Scrollbar for Quiz Editor */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: rgba(15, 23, 42, 0.6);
            border-radius: 8px;
        }
        ::-webkit-scrollbar-thumb {
            background: #3b82f6;
            border-radius: 8px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #60a5fa;
        }
        #game-canvas {
            position: fixed;
            inset: 0;
            width: 100%;
            height: 100%;
            display: block;
            z-index: 1;
        }
        #preview-canvas {
            width: 100%;
            height: 100%;
            display: block;
        }
        .crosshair {
            position: fixed;
            top: 50%;
            left: 50%;
            width: 24px;
            height: 24px;
            transform: translate(-50%, -50%);
            pointer-events: none;
            z-index: 20;
        }
        @keyframes pulseGlow {
            0%, 100% { transform: scale(1); filter: drop-shadow(0 0 8px rgba(250, 204, 21, 0.8)); }
            50% { transform: scale(1.08); filter: drop-shadow(0 0 16px rgba(250, 204, 21, 1)); }
        }
        .gem-pulse {
            animation: pulseGlow 1.5s infinite ease-in-out;
        }
        .glass-panel {
            background: rgba(15, 23, 42, 0.82);
            backdrop-filter: blur(12px);
            border: 2px solid rgba(255, 255, 255, 0.14);
        }
    </style>
</head>
<body class="text-white">

    <!-- Main 3D Game Canvas -->
    <canvas id="game-canvas"></canvas>

    <!-- Toast Notification Banner -->
    <div id="toast-container" class="fixed top-20 left-1/2 -translate-x-1/2 z-50 flex flex-col items-center gap-2 pointer-events-none"></div>

    <!-- ==================== PRE-GAME LOBBY SCREEN ==================== -->
    <div id="lobby-screen" class="fixed inset-0 z-30 flex items-center justify-center p-3 sm:p-6 bg-gradient-to-br from-slate-900/90 via-indigo-950/85 to-slate-900/95 backdrop-blur-sm overflow-y-auto">
        <div class="w-full max-w-6xl glass-panel rounded-3xl shadow-2xl p-4 sm:p-7 border-2 border-indigo-400/30 my-auto">
            
            <!-- Header -->
            <div class="flex flex-wrap items-center justify-between gap-4 pb-4 border-b border-white/15">
                <div class="flex items-center gap-3">
                    <div class="w-12 h-12 rounded-2xl bg-gradient-to-tr from-blue-500 to-cyan-400 flex items-center justify-center shadow-lg transform -rotate-3">
                        <span class="font-roblox text-2xl font-bold text-slate-950">BQ</span>
                    </div>
                    <div>
                        <h1 class="font-roblox text-2xl sm:text-3xl font-bold bg-gradient-to-r from-white via-cyan-200 to-indigo-300 bg-clip-text text-transparent">
                            BLOXQUEST ARENA 3D
                        </h1>
                        <p class="text-xs sm:text-sm text-slate-300">Tembak-Tembakan 3D & Berburu 10 Hidden Gem Kuis (10 Menit)</p>
                    </div>
                </div>
                <div class="flex items-center gap-2">
                    <button id="btn-mute-lobby" onclick="toggleAudio()" class="btn-blox px-3.5 py-2 rounded-xl bg-slate-800 hover:bg-slate-700 border border-white/15 text-sm font-bold flex items-center gap-2">
                        <span id="mute-icon-lobby">🔊</span> <span class="hidden sm:inline">Suara</span>
                    </button>
                    <button onclick="openQuizEditor()" class="btn-blox px-4 py-2 rounded-xl bg-amber-500 hover:bg-amber-400 text-slate-950 font-extrabold text-sm flex items-center gap-2">
                        <span>📝</span> Edit 10 Soal Gem
                    </button>
                </div>
            </div>

            <!-- Main Lobby Grid -->
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-6 mt-5">
                
                <!-- Left Column: 3D Character Preview & Customization (5 cols) -->
                <div class="lg:col-span-5 bg-slate-900/75 rounded-2xl p-4 border border-white/10 flex flex-col justify-between">
                    <div>
                        <div class="flex items-center justify-between mb-2">
                            <span class="font-roblox text-lg font-bold text-cyan-300">🎨 Kustomisasi Karakter</span>
                            <span class="text-xs px-2.5 py-1 rounded-full bg-cyan-500/20 text-cyan-300 font-semibold">3D Live Preview</span>
                        </div>

                        <!-- 3D Preview Box -->
                        <div class="relative w-full h-52 sm:h-60 rounded-2xl overflow-hidden bg-gradient-to-b from-indigo-900/50 to-slate-950 border border-white/10 mb-3">
                            <canvas id="preview-canvas"></canvas>
                            <div class="absolute bottom-2 left-1/2 -translate-x-1/2 text-[11px] text-slate-300 bg-black/50 px-3 py-0.5 rounded-full">
                                Karakter Roblox Kamu
                            </div>
                        </div>

                        <!-- Player Name -->
                        <div class="mb-3">
                            <label class="block text-xs font-bold text-slate-300 uppercase mb-1">Nama Pemain</label>
                            <input id="input-player-name" type="text" maxlength="16" value="BloxHero_ID" oninput="updateCharacterConfig()"
                                class="w-full px-3.5 py-2 rounded-xl bg-slate-800 border border-slate-600 focus:border-cyan-400 focus:outline-none font-bold text-white text-sm" placeholder="Masukkan nama...">
                        </div>

                        <!-- Color Pickers -->
                        <div class="grid grid-cols-3 gap-2.5 mb-3">
                            <div class="bg-slate-800/80 p-2 rounded-xl border border-white/5">
                                <label class="block text-[11px] font-bold text-slate-300 mb-1">Warna Kulit</label>
                                <div class="flex items-center gap-1.5">
                                    <input id="color-skin" type="color" value="#facc15" onchange="updateCharacterConfig()" class="w-8 h-8 rounded cursor-pointer bg-transparent border-0">
                                    <button onclick="setPresetColor('skin', '#facc15')" class="w-5 h-5 rounded-full bg-yellow-400 border border-white/40"></button>
                                    <button onclick="setPresetColor('skin', '#fed7aa')" class="w-5 h-5 rounded-full bg-orange-200 border border-white/40"></button>
                                    <button onclick="setPresetColor('skin', '#8d5524')" class="w-5 h-5 rounded-full bg-amber-800 border border-white/40"></button>
                                </div>
                            </div>
                            <div class="bg-slate-800/80 p-2 rounded-xl border border-white/5">
                                <label class="block text-[11px] font-bold text-slate-300 mb-1">Warna Baju</label>
                                <div class="flex items-center gap-1.5">
                                    <input id="color-shirt" type="color" value="#2563eb" onchange="updateCharacterConfig()" class="w-8 h-8 rounded cursor-pointer bg-transparent border-0">
                                    <button onclick="setPresetColor('shirt', '#2563eb')" class="w-5 h-5 rounded-full bg-blue-600 border border-white/40"></button>
                                    <button onclick="setPresetColor('shirt', '#dc2626')" class="w-5 h-5 rounded-full bg-red-600 border border-white/40"></button>
                                    <button onclick="setPresetColor('shirt', '#16a34a')" class="w-5 h-5 rounded-full bg-green-600 border border-white/40"></button>
                                </div>
                            </div>
                            <div class="bg-slate-800/80 p-2 rounded-xl border border-white/5">
                                <label class="block text-[11px] font-bold text-slate-300 mb-1">Warna Celana</label>
                                <div class="flex items-center gap-1.5">
                                    <input id="color-pants" type="color" value="#1e293b" onchange="updateCharacterConfig()" class="w-8 h-8 rounded cursor-pointer bg-transparent border-0">
                                    <button onclick="setPresetColor('pants', '#1e293b')" class="w-5 h-5 rounded-full bg-slate-800 border border-white/40"></button>
                                    <button onclick="setPresetColor('pants', '#15803d')" class="w-5 h-5 rounded-full bg-green-700 border border-white/40"></button>
                                    <button onclick="setPresetColor('pants', '#7c2d12')" class="w-5 h-5 rounded-full bg-orange-900 border border-white/40"></button>
                                </div>
                            </div>
                        </div>

                        <!-- Hat / Accessory Selector -->
                        <div>
                            <label class="block text-xs font-bold text-slate-300 uppercase mb-1.5">Aksesoris Kepala</label>
                            <div class="grid grid-cols-4 gap-2" id="hat-selector">
                                <button type="button" onclick="selectHat('none')" data-hat="none" class="hat-btn py-2 px-2 rounded-xl bg-cyan-600 border-2 border-cyan-300 text-xs font-bold text-center">Polos</button>
                                <button type="button" onclick="selectHat('cap')" data-hat="cap" class="hat-btn py-2 px-2 rounded-xl bg-slate-800 border-2 border-transparent hover:border-slate-500 text-xs font-bold text-center">🧢 Topi</button>
                                <button type="button" onclick="selectHat('crown')" data-hat="crown" class="hat-btn py-2 px-2 rounded-xl bg-slate-800 border-2 border-transparent hover:border-slate-500 text-xs font-bold text-center">👑 Mahkota</button>
                                <button type="button" onclick="selectHat('visor')" data-hat="visor" class="hat-btn py-2 px-2 rounded-xl bg-slate-800 border-2 border-transparent hover:border-slate-500 text-xs font-bold text-center">🤖 Cyber</button>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- Right Column: World Selection, Game Mode & Rules (7 cols) -->
                <div class="lg:col-span-7 flex flex-col justify-between gap-4">
                    
                    <!-- Step 1: World Selection -->
                    <div class="bg-slate-900/75 rounded-2xl p-4 border border-white/10">
                        <span class="font-roblox text-lg font-bold text-indigo-300 block mb-2.5">🌍 Pilih Latar Dunia Permainan</span>
                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
                            <!-- Map 1: Night City -->
                            <div onclick="selectMap('city')" id="map-card-city" class="cursor-pointer rounded-2xl p-3.5 bg-gradient-to-br from-indigo-950 via-purple-950 to-slate-900 border-2 border-cyan-400 shadow-lg transition-all relative overflow-hidden">
                                <div class="flex items-center justify-between mb-1">
                                    <span class="text-2xl">🌃</span>
                                    <span class="text-[11px] font-extrabold px-2 py-0.5 rounded-full bg-cyan-400 text-slate-950">DIPILIH</span>
                                </div>
                                <h3 class="font-roblox text-base font-bold text-white">Kota Neon Malam Hari</h3>
                                <p class="text-xs text-slate-300 mt-1">Gedung pencakar langit bercahaya, lampu jalan neon, peti kargo, dan gang rahasia.</p>
                            </div>

                            <!-- Map 2: Wilderness Forest -->
                            <div onclick="selectMap('forest')" id="map-card-forest" class="cursor-pointer rounded-2xl p-3.5 bg-gradient-to-br from-emerald-950 via-green-900 to-amber-950 border-2 border-white/15 hover:border-emerald-400/60 transition-all relative overflow-hidden">
                                <div class="flex items-center justify-between mb-1">
                                    <span class="text-2xl">🌲</span>
                                    <span class="text-[11px] font-extrabold px-2 py-0.5 rounded-full bg-white/15 text-slate-200 hidden">DIPILIH</span>
                                </div>
                                <h3 class="font-roblox text-base font-bold text-white">Hutan Belantara Senja</h3>
                                <p class="text-xs text-slate-300 mt-1">Pepohonan rimbun ala blok, bebatuan besar, peti kayu kuno, dan semak persembunyian.</p>
                            </div>
                        </div>
                    </div>

                    <!-- Step 2: Game Mode Selection -->
                    <div class="bg-slate-900/75 rounded-2xl p-4 border border-white/10">
                        <span class="font-roblox text-lg font-bold text-emerald-300 block mb-2.5">⚔️ Mode Permainan</span>
                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
                            <button type="button" onclick="selectMode('solo')" id="mode-btn-solo" class="p-3.5 rounded-2xl bg-emerald-600/30 border-2 border-emerald-400 text-left transition-all">
                                <div class="flex items-center justify-between">
                                    <span class="font-roblox font-bold text-base text-white">🤖 Solo vs Bot AI</span>
                                    <span class="text-xs bg-emerald-400 text-slate-950 font-extrabold px-2 py-0.5 rounded-md">1 vs 5 Bot</span>
                                </div>
                                <p class="text-xs text-slate-300 mt-1">Lawan pasukan Bot AI sambil mengumpulkan 10 Hidden Gem sebelum waktu habis.</p>
                            </button>

                            <button type="button" onclick="selectMode('multiplayer')" id="mode-btn-multiplayer" class="p-3.5 rounded-2xl bg-slate-800/70 border-2 border-white/10 hover:border-purple-400/60 text-left transition-all">
                                <div class="flex items-center justify-between">
                                    <span class="font-roblox font-bold text-base text-white">🌐 Multiplayer Arena</span>
                                    <span class="text-xs bg-purple-500 text-white font-extrabold px-2 py-0.5 rounded-md">8 Pemain Live</span>
                                </div>
                                <p class="text-xs text-slate-300 mt-1">Simulasi room multiplayer kompetitif! Rebutan skor eliminasi & 10 Hidden Gem di papan peringkat.</p>
                            </button>
                        </div>

                        <!-- Simulated Multiplayer Room Preview -->
                        <div id="multiplayer-room-box" class="hidden mt-3 p-3 rounded-xl bg-slate-950/70 border border-purple-500/30">
                            <div class="flex items-center justify-between text-xs mb-2">
                                <span class="font-bold text-purple-300">🟢 Room #ID-8842 (Siap Bertanding)</span>
                                <span class="text-slate-400">Semua pemain berbagi daftar soal yang sama</span>
                            </div>
                            <div id="lobby-players-list" class="flex flex-wrap gap-1.5 text-xs"></div>
                        </div>
                    </div>

                    <!-- Step 3: Quick Guide & Start Button -->
                    <div class="bg-slate-900/75 rounded-2xl p-4 border border-white/10 flex flex-col sm:flex-row items-center justify-between gap-4">
                        <div class="text-xs text-slate-300 space-y-1">
                            <div class="font-bold text-white text-sm">🎮 Kontrol Mudah:</div>
                            <div>• <span class="text-cyan-300 font-bold">W A S D / Panah</span>: Jalan &nbsp;|&nbsp; <span class="text-cyan-300 font-bold">Spasi</span>: Lompat</div>
                            <div>• <span class="text-cyan-300 font-bold">Klik Kiri / Tombol Tembak</span>: Tembak Laser &nbsp;|&nbsp; <span class="text-amber-300 font-bold">E / Dekati Gem</span>: Jawab Kuis</div>
                        </div>
                        <button onclick="startGame()" class="btn-blox w-full sm:w-auto px-8 py-4 rounded-2xl bg-gradient-to-r from-emerald-500 to-green-400 hover:from-emerald-400 hover:to-green-300 text-slate-950 font-roblox text-xl font-bold tracking-wide shadow-xl whitespace-nowrap">
                            🚀 MULAI MAIN!
                        </button>
                    </div>

                </div>
            </div>
        </div>
    </div>

    <!-- ==================== QUIZ EDITOR MODAL (PRE-GAME) ==================== -->
    <div id="quiz-editor-modal" class="hidden fixed inset-0 z-40 flex items-center justify-center p-3 sm:p-6 bg-slate-950/85 backdrop-blur-md">
        <div class="w-full max-w-4xl max-h-[90vh] glass-panel rounded-3xl border-2 border-amber-400/40 flex flex-col overflow-hidden shadow-2xl">
            <div class="p-4 sm:p-5 bg-slate-900/90 border-b border-white/15 flex flex-wrap items-center justify-between gap-3">
                <div>
                    <h2 class="font-roblox text-xl sm:text-2xl font-bold text-amber-300">📝 Editor Soal 10 Hidden Gem</h2>
                    <p class="text-xs text-slate-300">Ubah pertanyaan, pilihan jawaban (A-D), dan kunci jawaban untuk masing-masing dari 10 Hidden Gem.</p>
                </div>
                <div class="flex items-center gap-2">
                    <button onclick="resetDefaultQuestions()" class="btn-blox px-3 py-2 rounded-xl bg-slate-700 hover:bg-slate-600 text-xs font-bold text-white">
                        🔄 Reset Default
                    </button>
                    <button onclick="saveAndCloseQuizEditor()" class="btn-blox px-4 py-2 rounded-xl bg-emerald-500 hover:bg-emerald-400 text-slate-950 text-xs sm:text-sm font-extrabold">
                        ✅ Simpan & Tutup
                    </button>
                </div>
            </div>

            <!-- Scrollable List of 10 Questions -->
            <div id="quiz-editor-list" class="p-4 sm:p-5 overflow-y-auto space-y-4 flex-1">
                <!-- Populated dynamically via JS -->
            </div>
        </div>
    </div>

    <!-- ==================== IN-GAME HUD ==================== -->
    <div id="game-hud" class="hidden fixed inset-0 z-20 pointer-events-none">
        
        <!-- Top Bar: Timer, Gem Counter, Score, Mute -->
        <div class="flex flex-wrap items-start justify-between p-3 sm:p-4 gap-2">
            
            <!-- Left: Player HP & Shield Status -->
            <div class="glass-panel rounded-2xl p-3 min-w-[200px] sm:min-w-[240px] pointer-events-auto">
                <div class="flex items-center justify-between mb-1">
                    <span id="hud-player-name" class="font-roblox font-bold text-sm text-cyan-300 truncate max-w-[140px]">BloxHero_ID</span>
                    <span id="hud-hp-text" class="text-xs font-extrabold text-emerald-400">100 / 100 HP</span>
                </div>
                <div class="w-full h-3.5 bg-slate-800 rounded-full overflow-hidden border border-white/10">
                    <div id="hud-hp-bar" class="h-full bg-gradient-to-r from-emerald-500 to-green-400 transition-all duration-200" style="width: 100%"></div>
                </div>
                <div class="flex items-center justify-between mt-2 text-xs font-bold text-slate-300">
                    <span>🎯 Eliminasi: <span id="hud-kills" class="text-rose-400">0</span></span>
                    <span>⭐ Skor: <span id="hud-score" class="text-amber-300">0</span></span>
                </div>
            </div>

            <!-- Center: 10-Minute Countdown Timer & Gems Progress -->
            <div class="flex flex-col items-center gap-2 mx-auto">
                <div class="glass-panel px-5 py-2 rounded-2xl border-2 border-indigo-400/40 flex items-center gap-4 shadow-lg">
                    <div class="text-center">
                        <div class="text-[10px] uppercase tracking-wider text-slate-400 font-bold">Sisa Waktu</div>
                        <div id="hud-timer" class="font-roblox text-2xl sm:text-3xl font-bold text-white">10:00</div>
                    </div>
                    <div class="h-8 w-[1px] bg-white/15"></div>
                    <div class="text-center">
                        <div class="text-[10px] uppercase tracking-wider text-amber-300 font-bold">Hidden Gem</div>
                        <div class="font-roblox text-2xl sm:text-3xl font-bold text-amber-400 flex items-center gap-1">
                            <span>💎</span><span id="hud-gems">0</span><span class="text-base text-slate-400">/10</span>
                        </div>
                    </div>
                </div>
                <!-- Pointer Lock Hint -->
                <div id="pointer-lock-hint" class="bg-black/60 text-white/90 text-[11px] px-3 py-1 rounded-full backdrop-blur-sm">
                    Klik layar untuk mengunci kamera mouse (ESC untuk kursor bebas)
                </div>
            </div>

            <!-- Right: Leaderboard & Quick Actions -->
            <div class="flex flex-col items-end gap-2 pointer-events-auto">
                <div class="flex items-center gap-2">
                    <button onclick="toggleAudio()" class="btn-blox px-3 py-2 rounded-xl glass-panel text-xs font-bold hover:bg-slate-800">
                        <span id="mute-icon-hud">🔊</span>
                    </button>
                    <button onclick="endGameEarly()" class="btn-blox px-3 py-2 rounded-xl bg-rose-600/90 hover:bg-rose-500 text-xs font-bold text-white">
                        Selesai
                    </button>
                </div>

                <!-- Mini Live Leaderboard -->
                <div class="glass-panel rounded-2xl p-2.5 w-48 sm:w-56 hidden sm:block">
                    <div class="text-[11px] font-extrabold uppercase text-indigo-300 mb-1.5 flex items-center justify-between">
                        <span>🏆 Papan Skor Live</span>
                        <span id="hud-mode-badge" class="text-[10px] bg-indigo-500/30 px-1.5 py-0.5 rounded">SOLO</span>
                    </div>
                    <div id="hud-leaderboard" class="space-y-1 text-xs"></div>
                </div>

                <!-- Gem Radar Indicator -->
                <div class="glass-panel rounded-2xl px-3 py-2 flex items-center gap-2 text-xs">
                    <span class="text-amber-400 text-base">🧭</span>
                    <div>
                        <div class="text-[10px] text-slate-400 font-bold">Gem Terdekat</div>
                        <div id="hud-radar-text" class="font-bold text-amber-300">Mencari...</div>
                    </div>
                </div>
            </div>
        </div>

        <!-- Center Crosshair -->
        <div class="crosshair">
            <svg viewBox="0 0 24 24" class="w-full h-full drop-shadow">
                <circle cx="12" cy="12" r="8" fill="none" stroke="rgba(255,255,255,0.85)" stroke-width="1.8"/>
                <circle cx="12" cy="12" r="2" fill="#38bdf8"/>
                <line x1="12" y1="1" x2="12" y2="5" stroke="white" stroke-width="1.8"/>
                <line x1="12" y1="19" x2="12" y2="23" stroke="white" stroke-width="1.8"/>
                <line x1="1" y1="12" x2="5" y2="12" stroke="white" stroke-width="1.8"/>
                <line x1="19" y1="12" x2="23" y2="12" stroke="white" stroke-width="1.8"/>
            </svg>
        </div>

        <!-- Proximity Hidden Gem Prompt -->
        <div id="gem-proximity-prompt" class="hidden fixed bottom-28 left-1/2 -translate-x-1/2 pointer-events-auto z-30">
            <button onclick="triggerNearbyGemQuiz()" class="gem-pulse btn-blox px-6 py-3 rounded-2xl bg-gradient-to-r from-amber-400 to-yellow-300 text-slate-950 font-roblox font-bold text-base sm:text-lg border-2 border-white shadow-2xl flex items-center gap-2">
                <span>💎</span> Tekan [E] atau Klik untuk Buka Kuis Gem #<span id="nearby-gem-number">1</span>!
            </button>
        </div>

        <!-- Bottom Controls Bar (Touch/Click Friendly + Keyboard Legend) -->
        <div class="fixed bottom-3 left-3 right-3 flex items-end justify-between pointer-events-none">
            
            <!-- On-Screen Touch / Easy Movement Pad (Left) -->
            <div class="pointer-events-auto grid grid-cols-3 gap-1.5 w-36 h-36 sm:opacity-75 hover:opacity-100 transition-opacity">
                <div></div>
                <button id="btn-touch-up" class="glass-panel rounded-xl flex items-center justify-center text-lg font-bold active:bg-cyan-500/50">▲</button>
                <div></div>
                <button id="btn-touch-left" class="glass-panel rounded-xl flex items-center justify-center text-lg font-bold active:bg-cyan-500/50">◀</button>
                <button id="btn-touch-down" class="glass-panel rounded-xl flex items-center justify-center text-lg font-bold active:bg-cyan-500/50">▼</button>
                <button id="btn-touch-right" class="glass-panel rounded-xl flex items-center justify-center text-lg font-bold active:bg-cyan-500/50">▶</button>
            </div>

            <!-- Center Desktop Hint -->
            <div class="hidden md:flex glass-panel px-4 py-1.5 rounded-full text-xs text-slate-300 gap-4">
                <span><b>WASD</b> Gerak</span>
                <span><b>Spasi</b> Lompat</span>
                <span><b>Klik Kiri / F</b> Tembak</span>
                <span><b>E</b> Buka Kuis Gem</span>
            </div>

            <!-- Right Action Buttons (Jump & Shoot) -->
            <div class="pointer-events-auto flex items-center gap-2.5">
                <button onclick="playerJump()" class="btn-blox w-14 h-14 sm:w-16 sm:h-16 rounded-2xl bg-indigo-600/90 hover:bg-indigo-500 border-2 border-indigo-300/40 font-roblox font-bold text-xs sm:text-sm flex flex-col items-center justify-center shadow-lg">
                    <span class="text-lg">⬆️</span>
                    <span>Lompat</span>
                </button>
                <button onmousedown="playerShoot()" ontouchstart="playerShoot()" class="btn-blox w-16 h-16 sm:w-20 sm:h-20 rounded-2xl bg-gradient-to-tr from-rose-600 to-orange-500 hover:from-rose-500 hover:to-orange-400 border-2 border-white/40 font-roblox font-bold text-xs sm:text-sm flex flex-col items-center justify-center shadow-xl">
                    <span class="text-xl">🔫</span>
                    <span>TEMBAK</span>
                </button>
            </div>
        </div>
    </div>

    <!-- ==================== IN-GAME HIDDEN GEM QUIZ MODAL ==================== -->
    <div id="active-quiz-modal" class="hidden fixed inset-0 z-40 flex items-center justify-center p-4 bg-slate-950/80 backdrop-blur-md">
        <div class="w-full max-w-xl glass-panel rounded-3xl border-2 border-amber-400 p-5 sm:p-7 shadow-2xl relative">
            <div class="flex items-center justify-between mb-4">
                <div class="flex items-center gap-2.5">
                    <span class="text-3xl gem-pulse">💎</span>
                    <div>
                        <span class="text-xs font-extrabold uppercase tracking-wider text-amber-300">Hidden Gem Ditemukan!</span>
                        <h3 id="quiz-modal-title" class="font-roblox text-xl font-bold text-white">Tantangan Gem #1</h3>
                    </div>
                </div>
                <button onclick="closeActiveQuizModal()" class="px-3 py-1.5 rounded-xl bg-slate-800 hover:bg-slate-700 text-xs font-bold text-slate-300">
                    Tutup (Nanti)
                </button>
            </div>

            <div class="bg-slate-900/90 rounded-2xl p-4 border border-white/10 mb-4">
                <p id="quiz-modal-question" class="text-base sm:text-lg font-bold text-white leading-relaxed">
                    Pertanyaan akan muncul di sini...
                </p>
            </div>

            <div id="quiz-modal-options" class="grid grid-cols-1 gap-2.5">
                <!-- Answer buttons injected here -->
            </div>

            <div id="quiz-modal-feedback" class="hidden mt-4 p-3 rounded-xl text-center font-bold text-sm"></div>
        </div>
    </div>

    <!-- ==================== GAME OVER / VICTORY MODAL ==================== -->
    <div id="gameover-modal" class="hidden fixed inset-0 z-50 flex items-center justify-center p-4 bg-slate-950/90 backdrop-blur-md">
        <div class="w-full max-w-2xl glass-panel rounded-3xl border-2 border-cyan-400/50 p-6 sm:p-8 text-center shadow-2xl">
            <div class="text-5xl mb-2">🏆</div>
            <h2 id="gameover-title" class="font-roblox text-3xl sm:text-4xl font-bold bg-gradient-to-r from-amber-300 via-yellow-200 to-cyan-300 bg-clip-text text-transparent">
                PERTANDINGAN SELESAI!
            </h2>
            <p id="gameover-subtitle" class="text-sm text-slate-300 mt-1 mb-5">Waktu 10 menit telah berakhir!</p>

            <!-- Summary Stats -->
            <div class="grid grid-cols-3 gap-3 mb-5">
                <div class="bg-slate-900/80 p-3 rounded-2xl border border-white/10">
                    <div class="text-xs text-slate-400 font-bold">Total Skor</div>
                    <div id="final-score" class="font-roblox text-2xl font-bold text-amber-400">0</div>
                </div>
                <div class="bg-slate-900/80 p-3 rounded-2xl border border-white/10">
                    <div class="text-xs text-slate-400 font-bold">Hidden Gem</div>
                    <div id="final-gems" class="font-roblox text-2xl font-bold text-cyan-400">0 / 10</div>
                </div>
                <div class="bg-slate-900/80 p-3 rounded-2xl border border-white/10">
                    <div class="text-xs text-slate-400 font-bold">Eliminasi</div>
                    <div id="final-kills" class="font-roblox text-2xl font-bold text-rose-400">0</div>
                </div>
            </div>

            <!-- Final Leaderboard -->
            <div class="bg-slate-900/80 rounded-2xl p-4 border border-white/10 mb-6 text-left">
                <div class="text-xs font-extrabold uppercase text-indigo-300 mb-2">Klasemen Akhir Arena</div>
                <div id="final-leaderboard" class="space-y-1.5 text-sm max-h-44 overflow-y-auto"></div>
            </div>

            <div class="flex flex-wrap items-center justify-center gap-3">
                <button onclick="returnToLobby()" class="btn-blox px-6 py-3.5 rounded-2xl bg-slate-700 hover:bg-slate-600 font-roblox font-bold text-base text-white">
                    🏠 Kembali ke Lobby
                </button>
                <button onclick="restartMatchDirectly()" class="btn-blox px-7 py-3.5 rounded-2xl bg-gradient-to-r from-emerald-500 to-cyan-400 hover:from-emerald-400 hover:to-cyan-300 font-roblox font-bold text-base text-slate-950">
                    🔄 Main Lagi Sekarang
                </button>
            </div>
        </div>
    </div>

<script>
/**
 * ============================================================================
 * 1. WEB AUDIO API SYNTHESIZER (Efek Suara Retro/Arcade Tanpa File Eksternal)
 * ============================================================================
 */
const SoundFX = {
    ctx: null,
    muted: false,

    init() {
        if (!this.ctx) {
            const AudioContext = window.AudioContext || window.webkitAudioContext;
            this.ctx = new AudioContext();
        }
        if (this.ctx.state === 'suspended') {
            this.ctx.resume();
        }
    },

    playTone(freq, type, duration, vol = 0.15, slideFreq = null) {
        if (this.muted) return;
        this.init();
        const now = this.ctx.currentTime;
        const osc = this.ctx.createOscillator();
        const gain = this.ctx.createGain();
        osc.type = type;
        osc.frequency.setValueAtTime(freq, now);
        if (slideFreq) {
            osc.frequency.exponentialRampToValueAtTime(slideFreq, now + duration);
        }
        gain.gain.setValueAtTime(vol, now);
        gain.gain.exponentialRampToValueAtTime(0.001, now + duration);
        osc.connect(gain);
        gain.connect(this.ctx.destination);
        osc.start(now);
        osc.stop(now + duration);
    },

    shoot() {
        this.playTone(680, 'sawtooth', 0.14, 0.12, 160);
    },

    hit() {
        this.playTone(190, 'square', 0.12, 0.15, 70);
    },

    elim() {
        this.playTone(300, 'triangle', 0.1, 0.18, 600);
        setTimeout(() => this.playTone(600, 'sine', 0.22, 0.18, 900), 90);
    },

    jump() {
        this.playTone(220, 'sine', 0.16, 0.12, 480);
    },

    gemOpen() {
        this.playTone(523.25, 'sine', 0.12, 0.15); // C5
        setTimeout(() => this.playTone(659.25, 'sine', 0.15, 0.15), 80); // E5
    },

    correct() {
        const notes = [523.25, 659.25, 783.99, 1046.50]; // C5 E5 G5 C6
        notes.forEach((n, idx) => {
            setTimeout(() => this.playTone(n, 'triangle', 0.22, 0.18), idx * 85);
        });
    },

    wrong() {
        this.playTone(180, 'sawtooth', 0.18, 0.16, 130);
        setTimeout(() => this.playTone(140, 'sawtooth', 0.25, 0.16, 95), 140);
    },

    click() {
        this.playTone(440, 'sine', 0.06, 0.08);
    }
};

function toggleAudio() {
    SoundFX.muted = !SoundFX.muted;
    const icon = SoundFX.muted ? '🔇' : '🔊';
    document.getElementById('mute-icon-lobby').textContent = icon;
    document.getElementById('mute-icon-hud').textContent = icon;
    if (!SoundFX.muted) SoundFX.click();
}

/**
 * ============================================================================
 * 2. DATA SOAL HIDDEN GEM (10 Soal Default + Dapat Diedit Pemain)
 * ============================================================================
 */
const DEFAULT_QUESTIONS = [
    {
        q: "Planet manakah yang dikenal sebagai Planet Merah di tata surya kita?",
        options: ["Venus", "Mars", "Jupiter", "Saturnus"],
        answer: 1
    },
    {
        q: "Berapakah hasil dari 15 × 6 + 10?",
        options: ["90", "100", "110", "85"],
        answer: 1
    },
    {
        q: "Apa nama ibu kota negara Jepang?",
        options: ["Seoul", "Beijing", "Tokyo", "Osaka"],
        answer: 2
    },
    {
        q: "Gas apakah yang paling banyak dibutuhkan tumbuhan untuk melakukan fotosintesis?",
        options: ["Oksigen", "Nitrogen", "Karbon Dioksida", "Helium"],
        answer: 2
    },
    {
        q: "Berapa jumlah sisi pada bangun ruang kubus?",
        options: ["4 sisi", "6 sisi", "8 sisi", "12 sisi"],
        answer: 1
    },
    {
        q: "Gunung tertinggi di dunia adalah...",
        options: ["Gunung Kilimanjaro", "Gunung Fuji", "Gunung Everest", "Gunung Jayawijaya"],
        answer: 2
    },
    {
        q: "Simbol kimia untuk air murni adalah...",
        options: ["CO2", "H2O", "O2", "NaCl"],
        answer: 1
    },
    {
        q: "Hewan mamalia tercepat di darat adalah...",
        options: ["Singa", "Cheetah", "Kuda", "Serigala"],
        answer: 1
    },
    {
        q: "Benua terluas di permukaan Bumi adalah...",
        options: ["Afrika", "Amerika", "Eropa", "Asia"],
        answer: 3
    },
    {
        q: "Jika sebuah jam menunjukkan pukul 14:30, berarti pukul berapa itu pada sore hari?",
        options: ["Pukul 2.30 siang/sore", "Pukul 4.30 sore", "Pukul 3.30 sore", "Pukul 12.30 siang"],
        answer: 0
    }
];

let quizQuestions = JSON.parse(JSON.stringify(DEFAULT_QUESTIONS));

function openQuizEditor() {
    SoundFX.click();
    const listContainer = document.getElementById('quiz-editor-list');
    listContainer.innerHTML = '';

    quizQuestions.forEach((item, index) => {
        const card = document.createElement('div');
        card.className = 'bg-slate-900/90 border border-white/15 rounded-2xl p-4 space-y-3';
        card.innerHTML = `
            <div class="flex items-center justify-between">
                <span class="font-roblox font-bold text-amber-300 text-base">💎 Hidden Gem #${index + 1}</span>
                <span class="text-xs text-slate-400">Pilih radio button untuk kunci jawaban benar</span>
            </div>
            <div>
                <label class="block text-xs font-bold text-slate-300 mb-1">Pertanyaan:</label>
                <input type="text" id="edit-q-${index}" value="${escapeHtml(item.q)}" 
                    class="w-full px-3 py-2 rounded-xl bg-slate-800 border border-slate-600 focus:border-amber-400 focus:outline-none text-sm text-white font-semibold">
            </div>
            <div class="grid grid-cols-1 sm:grid-cols-2 gap-2.5">
                ${['A', 'B', 'C', 'D'].map((letter, optIdx) => `
                    <div class="flex items-center gap-2 bg-slate-800/80 p-2 rounded-xl border border-white/5">
                        <input type="radio" name="correct-${index}" value="${optIdx}" ${item.answer === optIdx ? 'checked' : ''} 
                            class="w-4 h-4 accent-emerald-400 cursor-pointer">
                        <span class="font-bold text-xs text-cyan-300 w-4">${letter}.</span>
                        <input type="text" id="edit-opt-${index}-${optIdx}" value="${escapeHtml(item.options[optIdx])}" 
                            class="w-full bg-transparent text-xs sm:text-sm text-white focus:outline-none">
                    </div>
                `).join('')}
            </div>
        `;
        listContainer.appendChild(card);
    });

    document.getElementById('quiz-editor-modal').classList.remove('hidden');
}

function saveAndCloseQuizEditor() {
    SoundFX.click();
    for (let i = 0; i < 10; i++) {
        const qVal = document.getElementById(`edit-q-${i}`).value.trim();
        const opts = [0, 1, 2, 3].map(optIdx => {
            const val = document.getElementById(`edit-opt-${i}-${optIdx}`).value.trim();
            return val || `Pilihan ${['A','B','C','D'][optIdx]}`;
        });
        const checkedRadio = document.querySelector(`input[name="correct-${i}"]:checked`);
        const ansIdx = checkedRadio ? parseInt(checkedRadio.value, 10) : 0;

        quizQuestions[i] = {
            q: qVal || DEFAULT_QUESTIONS[i].q,
            options: opts,
            answer: ansIdx
        };
    }
    document.getElementById('quiz-editor-modal').classList.add('hidden');
    showToast('✅ 10 Soal Hidden Gem berhasil disimpan!', 'bg-emerald-500 text-slate-950');
}

function resetDefaultQuestions() {
    SoundFX.click();
    quizQuestions = JSON.parse(JSON.stringify(DEFAULT_QUESTIONS));
    openQuizEditor();
    showToast('🔄 Soal dikembalikan ke pengaturan awal.', 'bg-amber-400 text-slate-950');
}

function escapeHtml(text) {
    return text.replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;").replace(/"/g, "&quot;");
}

function showToast(msg, colorClass = 'bg-cyan-400 text-slate-950') {
    const container = document.getElementById('toast-container');
    const el = document.createElement('div');
    el.className = `${colorClass} px-4 py-2 rounded-2xl font-bold text-xs sm:text-sm shadow-xl transition-all duration-300 transform translate-y-0 opacity-100`;
    el.textContent = msg;
    container.appendChild(el);
    setTimeout(() => {
        el.style.opacity = '0';
        el.style.transform = 'translateY(-10px)';
        setTimeout(() => el.remove(), 300);
    }, 2600);
}

/**
 * ============================================================================
 * 3. STATE & KUSTOMISASI KARAKTER + LOBBY 3D PREVIEW
 * ============================================================================
 */
const gameConfig = {
    playerName: 'BloxHero_ID',
    skinColor: '#facc15',
    shirtColor: '#2563eb',
    pantsColor: '#1e293b',
    hat: 'none',
    map: 'city',      // 'city' | 'forest'
    mode: 'solo'      // 'solo' | 'multiplayer'
};

const MULTIPLAYER_BOT_NAMES = [
    'RakaPro_99', 'NadiaBlox', 'SultanIndo', 'CyberZaki',
    'PutriGem', 'GarudaX', 'BimaSakti', 'KiraNeon'
];

// Builder untuk Karakter Roblox 3D yang Artikulatif
function createRobloxCharacter(options) {
    const {
        skinColor = '#facc15',
        shirtColor = '#2563eb',
        pantsColor = '#1e293b',
        hat = 'none',
        isBot = false
    } = options;

    const group = new THREE.Group();

    const matSkin = new THREE.MeshLambertMaterial({ color: skinColor });
    const matShirt = new THREE.MeshLambertMaterial({ color: shirtColor });
    const matPants = new THREE.MeshLambertMaterial({ color: pantsColor });
    const matDark = new THREE.MeshLambertMaterial({ color: 0x111827 });

    // Torso (Badan)
    const torso = new THREE.Mesh(new THREE.BoxGeometry(1.1, 1.2, 0.6), matShirt);
    torso.position.y = 1.65;
    torso.castShadow = true;
    torso.receiveShadow = true;
    group.add(torso);

    // Head (Kepala ala Roblox dengan sudut membulat/bevel visual)
    const headGroup = new THREE.Group();
    headGroup.position.y = 2.65;
    const head = new THREE.Mesh(new THREE.BoxGeometry(0.85, 0.85, 0.85), matSkin);
    head.castShadow = true;
    headGroup.add(head);

    // Wajah (Mata & Senyum Blok)
    const eyeGeo = new THREE.BoxGeometry(0.11, 0.14, 0.05);
    const leftEye = new THREE.Mesh(eyeGeo, matDark);
    leftEye.position.set(-0.18, 0.08, 0.43);
    const rightEye = new THREE.Mesh(eyeGeo, matDark);
    rightEye.position.set(0.18, 0.08, 0.43);

    const mouth = new THREE.Mesh(new THREE.BoxGeometry(0.28, 0.07, 0.05), matDark);
    mouth.position.set(0, -0.16, 0.43);
    headGroup.add(leftEye, rightEye, mouth);

    // Aksesoris Kepala (Topi / Mahkota / Cyber Visor)
    if (hat === 'cap') {
        const capBase = new THREE.Mesh(new THREE.BoxGeometry(0.9, 0.28, 0.9), new THREE.MeshLambertMaterial({ color: 0xef4444 }));
        capBase.position.y = 0.48;
        const capBrim = new THREE.Mesh(new THREE.BoxGeometry(0.88, 0.08, 0.45), new THREE.MeshLambertMaterial({ color: 0xdc2626 }));
        capBrim.position.set(0, 0.38, 0.55);
        headGroup.add(capBase, capBrim);
    } else if (hat === 'crown') {
        const crownMat = new THREE.MeshStandardMaterial({ color: 0xfacc15, metalness: 0.6, roughness: 0.2 });
        const crownBase = new THREE.Mesh(new THREE.CylinderGeometry(0.45, 0.42, 0.3, 8), crownMat);
        crownBase.position.y = 0.55;
        headGroup.add(crownBase);
        for (let i = 0; i < 4; i++) {
            const spike = new THREE.Mesh(new THREE.ConeGeometry(0.1, 0.22, 4), crownMat);
            const ang = (i * Math.PI) / 2;
            spike.position.set(Math.cos(ang) * 0.32, 0.75, Math.sin(ang) * 0.32);
            headGroup.add(spike);
        }
    } else if (hat === 'visor') {
        const helmet = new THREE.Mesh(new THREE.BoxGeometry(0.94, 0.92, 0.94), new THREE.MeshLambertMaterial({ color: 0x334155 }));
        helmet.position.y = 0.05;
        const visor = new THREE.Mesh(new THREE.BoxGeometry(0.82, 0.24, 0.12), new THREE.MeshBasicMaterial({ color: 0x22d3ee }));
        visor.position.set(0, 0.1, 0.46);
        headGroup.add(helmet, visor);
    }
    group.add(headGroup);

    // Left Arm
    const leftArmPivot = new THREE.Group();
    leftArmPivot.position.set(-0.8, 2.15, 0);
    const leftArm = new THREE.Mesh(new THREE.BoxGeometry(0.45, 1.15, 0.48), matSkin);
    leftArm.position.y = -0.45;
    leftArm.castShadow = true;
    leftArmPivot.add(leftArm);
    group.add(leftArmPivot);

    // Right Arm + 3D Blaster Gun
    const rightArmPivot = new THREE.Group();
    rightArmPivot.position.set(0.8, 2.15, 0);
    const rightArm = new THREE.Mesh(new THREE.BoxGeometry(0.45, 1.15, 0.48), matSkin);
    rightArm.position.y = -0.45;
    rightArm.castShadow = true;
    rightArmPivot.add(rightArm);

    // Blaster Weapon
    const gunGroup = new THREE.Group();
    gunGroup.position.set(0, -0.85, 0.45);
    const gunBody = new THREE.Mesh(
        new THREE.BoxGeometry(0.24, 0.28, 0.85),
        new THREE.MeshLambertMaterial({ color: isBot ? 0xef4444 : 0x0ea5e9 })
    );
    const gunBarrel = new THREE.Mesh(
        new THREE.BoxGeometry(0.14, 0.14, 0.35),
        new THREE.MeshBasicMaterial({ color: isBot ? 0xfca5a5 : 0x67e8f9 })
    );
    gunBarrel.position.z = 0.5;
    gunGroup.add(gunBody, gunBarrel);
    rightArmPivot.add(gunGroup);
    rightArmPivot.rotation.x = -Math.PI / 2.4; // Pose memegang senjata ke depan
    group.add(rightArmPivot);

    // Left Leg
    const leftLegPivot = new THREE.Group();
    leftLegPivot.position.set(-0.28, 1.05, 0);
    const leftLeg = new THREE.Mesh(new THREE.BoxGeometry(0.5, 1.05, 0.54), matPants);
    leftLeg.position.y = -0.52;
    leftLeg.castShadow = true;
    leftLegPivot.add(leftLeg);
    group.add(leftLegPivot);

    // Right Leg
    const rightLegPivot = new THREE.Group();
    rightLegPivot.position.set(0.28, 1.05, 0);
    const rightLeg = new THREE.Mesh(new THREE.BoxGeometry(0.5, 1.05, 0.54), matPants);
    rightLeg.position.y = -0.52;
    rightLeg.castShadow = true;
    rightLegPivot.add(rightLeg);
    group.add(rightLegPivot);

    return {
        mesh: group,
        leftArmPivot,
        rightArmPivot,
        leftLegPivot,
        rightLegPivot,
        headGroup
    };
}

// 3D Live Preview di Lobby
let previewScene, previewCamera, previewRenderer, previewCharObj, previewAnimId;

function initLobbyPreview() {
    const canvas = document.getElementById('preview-canvas');
    previewScene = new THREE.Scene();
    previewCamera = new THREE.PerspectiveCamera(42, canvas.clientWidth / canvas.clientHeight, 0.1, 100);
    previewCamera.position.set(0, 2.2, 5.2);
    previewCamera.lookAt(0, 1.6, 0);

    previewRenderer = new THREE.WebGLRenderer({ canvas, alpha: true, antialias: true });
    previewRenderer.setSize(canvas.clientWidth, canvas.clientHeight);
    previewRenderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));

    const amb = new THREE.AmbientLight(0xffffff, 0.75);
    const dir = new THREE.DirectionalLight(0xffffff, 0.9);
    dir.position.set(4, 8, 5);
    previewScene.add(amb, dir);

    // Pedestal platform
    const pedestal = new THREE.Mesh(
        new THREE.CylinderGeometry(1.4, 1.6, 0.25, 24),
        new THREE.MeshLambertMaterial({ color: 0x1e293b })
    );
    pedestal.position.y = -0.12;
    previewScene.add(pedestal);

    rebuildPreviewCharacter();

    function animatePreview() {
        previewAnimId = requestAnimationFrame(animatePreview);
        if (previewCharObj && !document.getElementById('lobby-screen').classList.contains('hidden')) {
            previewCharObj.mesh.rotation.y += 0.015;
            const t = performance.now() * 0.004;
            previewCharObj.leftArmPivot.rotation.x = Math.sin(t) * 0.2;
            previewCharObj.leftLegPivot.rotation.x = -Math.sin(t) * 0.15;
            previewCharObj.rightLegPivot.rotation.x = Math.sin(t) * 0.15;
            previewRenderer.render(previewScene, previewCamera);
        }
    }
    animatePreview();
}

function rebuildPreviewCharacter() {
    if (previewCharObj) {
        previewScene.remove(previewCharObj.mesh);
    }
    previewCharObj = createRobloxCharacter({
        skinColor: gameConfig.skinColor,
        shirtColor: gameConfig.shirtColor,
        pantsColor: gameConfig.pantsColor,
        hat: gameConfig.hat,
        isBot: false
    });
    previewScene.add(previewCharObj.mesh);
}

function updateCharacterConfig() {
    const nameInput = document.getElementById('input-player-name').value.trim();
    gameConfig.playerName = nameInput || 'BloxHero_ID';
    gameConfig.skinColor = document.getElementById('color-skin').value;
    gameConfig.shirtColor = document.getElementById('color-shirt').value;
    gameConfig.pantsColor = document.getElementById('color-pants').value;
    rebuildPreviewCharacter();
}

function setPresetColor(part, hex) {
    SoundFX.click();
    document.getElementById(`color-${part}`).value = hex;
    updateCharacterConfig();
}

function selectHat(hatId) {
    SoundFX.click();
    gameConfig.hat = hatId;
    document.querySelectorAll('.hat-btn').forEach(btn => {
        if (btn.dataset.hat === hatId) {
            btn.className = 'hat-btn py-2 px-2 rounded-xl bg-cyan-600 border-2 border-cyan-300 text-xs font-bold text-center';
        } else {
            btn.className = 'hat-btn py-2 px-2 rounded-xl bg-slate-800 border-2 border-transparent hover:border-slate-500 text-xs font-bold text-center';
        }
    });
    rebuildPreviewCharacter();
}

function selectMap(mapId) {
    SoundFX.click();
    gameConfig.map = mapId;
    const cityCard = document.getElementById('map-card-city');
    const forestCard = document.getElementById('map-card-forest');

    if (mapId === 'city') {
        cityCard.classList.replace('border-white/15', 'border-cyan-400');
        cityCard.querySelector('span:last-child').classList.remove('hidden');
        forestCard.classList.replace('border-emerald-400', 'border-white/15');
        forestCard.querySelector('span:last-child').classList.add('hidden');
    } else {
        forestCard.classList.replace('border-white/15', 'border-emerald-400');
        forestCard.querySelector('span:last-child').classList.remove('hidden');
        cityCard.classList.replace('border-cyan-400', 'border-white/15');
        cityCard.querySelector('span:last-child').classList.add('hidden');
    }
}

function selectMode(modeId) {
    SoundFX.click();
    gameConfig.mode = modeId;
    const soloBtn = document.getElementById('mode-btn-solo');
    const mpBtn = document.getElementById('mode-btn-multiplayer');
    const mpRoom = document.getElementById('multiplayer-room-box');

    if (modeId === 'solo') {
        soloBtn.className = 'p-3.5 rounded-2xl bg-emerald-600/30 border-2 border-emerald-400 text-left transition-all';
        mpBtn.className = 'p-3.5 rounded-2xl bg-slate-800/70 border-2 border-white/10 hover:border-purple-400/60 text-left transition-all';
        mpRoom.classList.add('hidden');
    } else {
        mpBtn.className = 'p-3.5 rounded-2xl bg-purple-600/30 border-2 border-purple-400 text-left transition-all';
        soloBtn.className = 'p-3.5 rounded-2xl bg-slate-800/70 border-2 border-white/10 hover:border-emerald-400/60 text-left transition-all';
        mpRoom.classList.remove('hidden');
        renderMultiplayerLobbyList();
    }
}

function renderMultiplayerLobbyList() {
    const list = document.getElementById('lobby-players-list');
    const players = [gameConfig.playerName + ' (Kamu)', ...MULTIPLAYER_BOT_NAMES.slice(0, 7)];
    list.innerHTML = players.map(p => `
        <span class="px-2.5 py-1 rounded-lg bg-purple-900/60 border border-purple-400/30 text-purple-100 font-semibold">
            👤 ${escapeHtml(p)}
        </span>
    `).join('');
}

/**
 * ============================================================================
 * 4. ENGINE GAME 3D UTAMA (THREE.JS)
 * ============================================================================
 */
let scene, camera, renderer;
let gameActive = false;
let isQuizModalOpen = false;
let matchTimeRemaining = 600; // 10 menit = 600 detik
let timerInterval = null;
let lastFrameTime = 0;

// Arena & Collision Objects
const ARENA_SIZE = 130;
let obstacles = [];      // { minX, maxX, minZ, maxZ, height }
let environmentGroup = null;

// Player State
let playerObj = null;
const playerState = {
    pos: new THREE.Vector3(0, 0, 0),
    velY: 0,
    onGround: true,
    yaw: 0,
    pitch: 0.22,
    hp: 100,
    maxHp: 100,
    score: 0,
    kills: 0,
    gemsCollected: 0,
    shootCooldown: 0,
    walkCycle: 0
};

// Entities
let bots = [];
let projectiles = [];
let particles = [];
let hiddenGems = [];
let nearbyGem = null;

// Input State
const keys = {};
let isPointerLocked = false;
let isDraggingLook = false;
let prevMouseX = 0, prevMouseY = 0;

function initThreeEngine() {
    const canvas = document.getElementById('game-canvas');
    scene = new THREE.Scene();

    camera = new THREE.PerspectiveCamera(65, window.innerWidth / window.innerHeight, 0.1, 350);

    renderer = new THREE.WebGLRenderer({ canvas, antialias: true });
    renderer.setSize(window.innerWidth, window.innerHeight);
    renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
    renderer.shadowMap.enabled = true;
    renderer.shadowMap.type = THREE.PCFSoftShadowMap;

    setupControls();
    window.addEventListener('resize', onWindowResize);
}

function onWindowResize() {
    if (camera && renderer) {
        camera.aspect = window.innerWidth / window.innerHeight;
        camera.updateProjectionMatrix();
        renderer.setSize(window.innerWidth, window.innerHeight);
    }
    const pCanvas = document.getElementById('preview-canvas');
    if (pCanvas && previewRenderer && previewCamera && pCanvas.clientWidth > 0) {
        previewCamera.aspect = pCanvas.clientWidth / pCanvas.clientHeight;
        previewCamera.updateProjectionMatrix();
        previewRenderer.setSize(pCanvas.clientWidth, pCanvas.clientHeight);
    }
}

/**
 * ============================================================================
 * 5. PEMBANGUN DUNIA 3D (KOTA NEON MALAM HARI & HUTAN BELANTARA)
 * ============================================================================
 */
function buildWorldEnvironment(mapType) {
    if (environmentGroup) {
        scene.remove(environmentGroup);
    }
    environmentGroup = new THREE.Group();
    obstacles = [];

    // Bersihkan lampu lama
    scene.children.filter(c => c.isLight).forEach(l => scene.remove(l));

    if (mapType === 'city') {
        // --- LATAR 1: KOTA NEON MALAM HARI ---
        scene.background = new THREE.Color(0x060918);
        scene.fog = new THREE.FogExp2(0x060918, 0.0085);

        const hemiLight = new THREE.HemisphereLight(0x6366f1, 0x0f172a, 0.85);
        scene.add(hemiLight);

        const moonLight = new THREE.DirectionalLight(0x93c5fd, 0.9);
        moonLight.position.set(45, 75, 35);
        moonLight.castShadow = true;
        moonLight.shadow.mapSize.width = 2048;
        moonLight.shadow.mapSize.height = 2048;
        moonLight.shadow.camera.left = -80;
        moonLight.shadow.camera.right = 80;
        moonLight.shadow.camera.top = 80;
        moonLight.shadow.camera.bottom = -80;
        scene.add(moonLight);

        // Lantai Jalan Aspal Kota dengan Garis Grid Neon
        const ground = new THREE.Mesh(
            new THREE.PlaneGeometry(ARENA_SIZE, ARENA_SIZE),
            new THREE.MeshLambertMaterial({ color: 0x111827 })
        );
        ground.rotation.x = -Math.PI / 2;
        ground.receiveShadow = true;
        environmentGroup.add(ground);

        const gridHelper = new THREE.GridHelper(ARENA_SIZE, 26, 0x38bdf8, 0x1e293b);
        gridHelper.position.y = 0.02;
        environmentGroup.add(gridHelper);

        // Bintang di langit malam
        const starGeo = new THREE.BufferGeometry();
        const starVerts = [];
        for (let i = 0; i < 400; i++) {
            starVerts.push((Math.random() - 0.5) * 300, 35 + Math.random() * 80, (Math.random() - 0.5) * 300);
        }
        starGeo.setAttribute('position', new THREE.Float32BufferAttribute(starVerts, 3));
        const stars = new THREE.Points(starGeo, new THREE.PointsMaterial({ color: 0xe0f2fe, size: 0.7 }));
        environmentGroup.add(stars);

        // Gedung-gedung Kota Neon (Cover & Sudut Persembunyian)
        const buildingPositions = [
            { x: -35, z: -35, w: 12, d: 12, h: 24, neon: 0x22d3ee },
            { x: 35, z: -35, w: 14, d: 10, h: 28, neon: 0xf472b6 },
            { x: -35, z: 35, w: 11, d: 13, h: 22, neon: 0xa855f7 },
            { x: 35, z: 35, w: 13, d: 13, h: 26, neon: 0x34d399 },
            { x: 0, z: -42, w: 16, d: 9, h: 20, neon: 0xfacc15 },
            { x: 0, z: 42, w: 16, d: 9, h: 20, neon: 0x38bdf8 },
            { x: -45, z: 0, w: 9, d: 16, h: 19, neon: 0xfb7185 },
            { x: 45, z: 0, w: 9, d: 16, h: 19, neon: 0x60a5fa },
            { x: -18, z: -18, w: 7, d: 7, h: 12, neon: 0x22d3ee },
            { x: 18, z: 18, w: 7, d: 7, h: 12, neon: 0xf472b6 }
        ];

        buildingPositions.forEach(b => {
            const bMesh = new THREE.Mesh(
                new THREE.BoxGeometry(b.w, b.h, b.d),
                new THREE.MeshLambertMaterial({ color: 0x1e293b })
            );
            bMesh.position.set(b.x, b.h / 2, b.z);
            bMesh.castShadow = true;
            bMesh.receiveShadow = true;
            environmentGroup.add(bMesh);

            // Strip Lampu Neon di Gedung
            const trim = new THREE.Mesh(
                new THREE.BoxGeometry(b.w + 0.3, 0.5, b.d + 0.3),
                new THREE.MeshBasicMaterial({ color: b.neon })
            );
            trim.position.set(b.x, b.h - 1.5, b.z);
            environmentGroup.add(trim);

            const trimLow = new THREE.Mesh(
                new THREE.BoxGeometry(b.w + 0.25, 0.35, b.d + 0.25),
                new THREE.MeshBasicMaterial({ color: b.neon })
            );
            trimLow.position.set(b.x, 3.5, b.z);
            environmentGroup.add(trimLow);

            addObstacleBox(b.x, b.z, b.w, b.d, b.h);
        });

        // Peti Kontainer & Barikade Jalanan untuk Tempat Sembunyi
        const crateCoords = [
            [-14, 15], [15, -14], [-26, -12], [26, 12],
            [-10, -32], [12, 32], [-50, -25], [50, 25],
            [-28, 48], [28, -48], [0, 14], [0, -14]
        ];
        crateCoords.forEach(([cx, cz], idx) => {
            const crate = new THREE.Mesh(
                new THREE.BoxGeometry(3.4, 2.8, 3.4),
                new THREE.MeshLambertMaterial({ color: idx % 2 === 0 ? 0x0284c7 : 0x7c3aed })
            );
            crate.position.set(cx, 1.4, cz);
            crate.castShadow = true;
            crate.receiveShadow = true;
            environmentGroup.add(crate);
            addObstacleBox(cx, cz, 3.4, 3.4, 2.8);
        });

    } else {
        // --- LATAR 2: HUTAN BELANTARA SENJA ---
        scene.background = new THREE.Color(0x1b4332);
        scene.fog = new THREE.FogExp2(0x1b4332, 0.008);

        const hemiLight = new THREE.HemisphereLight(0xfde68a, 0x14532d, 0.95);
        scene.add(hemiLight);

        const sunLight = new THREE.DirectionalLight(0xfef08a, 1.15);
        sunLight.position.set(50, 80, 40);
        sunLight.castShadow = true;
        sunLight.shadow.mapSize.width = 2048;
        sunLight.shadow.mapSize.height = 2048;
        sunLight.shadow.camera.left = -80;
        sunLight.shadow.camera.right = 80;
        sunLight.shadow.camera.top = 80;
        sunLight.shadow.camera.bottom = -80;
        scene.add(sunLight);

        // Tanah Rumput Hutan
        const ground = new THREE.Mesh(
            new THREE.PlaneGeometry(ARENA_SIZE, ARENA_SIZE),
            new THREE.MeshLambertMaterial({ color: 0x2d6a4f })
        );
        ground.rotation.x = -Math.PI / 2;
        ground.receiveShadow = true;
        environmentGroup.add(ground);

        // Jalan Setapak Tanah di Tengah
        const path1 = new THREE.Mesh(
            new THREE.PlaneGeometry(8, ARENA_SIZE),
            new THREE.MeshLambertMaterial({ color: 0x78350f })
        );
        path1.rotation.x = -Math.PI / 2;
        path1.position.y = 0.02;
        const path2 = new THREE.Mesh(
            new THREE.PlaneGeometry(ARENA_SIZE, 8),
            new THREE.MeshLambertMaterial({ color: 0x78350f })
        );
        path2.rotation.x = -Math.PI / 2;
        path2.position.y = 0.02;
        environmentGroup.add(path1, path2);

        // Pohon-Pohon Blok Raksasa ala Roblox (Hidden Gem bisa bersembunyi di belakang pohon!)
        const treeCoords = [
            [-22, -22], [22, -22], [-22, 22], [22, 22],
            [-40, -15], [40, -15], [-40, 15], [40, 15],
            [-15, -42], [15, -42], [-15, 42], [15, 42],
            [-46, -42], [46, -42], [-46, 42], [46, 42],
            [-32, 0], [32, 0], [0, -30], [0, 30]
        ];

        treeCoords.forEach(([tx, tz]) => {
            const treeGroup = new THREE.Group();
            treeGroup.position.set(tx, 0, tz);

            // Batang Pohon
            const trunk = new THREE.Mesh(
                new THREE.BoxGeometry(2.2, 7.5, 2.2),
                new THREE.MeshLambertMaterial({ color: 0x5c3a21 })
            );
            trunk.position.y = 3.75;
            trunk.castShadow = true;
            trunk.receiveShadow = true;
            treeGroup.add(trunk);

            // Daun Bertingkat ala Roblox
            const leaves1 = new THREE.Mesh(
                new THREE.BoxGeometry(7.5, 3.5, 7.5),
                new THREE.MeshLambertMaterial({ color: 0x15803d })
            );
            leaves1.position.y = 8.2;
            leaves1.castShadow = true;

            const leaves2 = new THREE.Mesh(
                new THREE.BoxGeometry(5.2, 3.0, 5.2),
                new THREE.MeshLambertMaterial({ color: 0x22c55e })
            );
            leaves2.position.y = 11.0;
            leaves2.castShadow = true;

            treeGroup.add(leaves1, leaves2);
            environmentGroup.add(treeGroup);

            addObstacleBox(tx, tz, 2.4, 2.4, 8);
        });

        // Bebatuan Besar & Peti Kayu Hutan
        const rockCoords = [
            [-12, 12], [12, -12], [-28, -32], [28, 32],
            [-50, 0], [50, 0], [0, -50], [0, 50],
            [-18, 34], [18, -34]
        ];
        rockCoords.forEach(([rx, rz], idx) => {
            const isCrate = idx % 2 === 0;
            const mesh = new THREE.Mesh(
                new THREE.BoxGeometry(isCrate ? 3.2 : 4.2, isCrate ? 2.6 : 3.0, isCrate ? 3.2 : 3.8),
                new THREE.MeshLambertMaterial({ color: isCrate ? 0xb45309 : 0x64748b })
            );
            mesh.position.set(rx, isCrate ? 1.3 : 1.5, rz);
            mesh.castShadow = true;
            mesh.receiveShadow = true;
            environmentGroup.add(mesh);
            addObstacleBox(rx, rz, isCrate ? 3.2 : 4.2, isCrate ? 3.2 : 3.8, 3.0);
        });
    }

    // Dinding Pembatas Arena (4 Sisi)
    const wallMat = new THREE.MeshLambertMaterial({ color: mapType === 'city' ? 0x0f172a : 0x3f2e1d });
    const half = ARENA_SIZE / 2;
    const walls = [
        { x: 0, z: -half, w: ARENA_SIZE, d: 2 },
        { x: 0, z: half, w: ARENA_SIZE, d: 2 },
        { x: -half, z: 0, w: 2, d: ARENA_SIZE },
        { x: half, z: 0, w: 2, d: ARENA_SIZE }
    ];
    walls.forEach(w => {
        const wallMesh = new THREE.Mesh(new THREE.BoxGeometry(w.w, 6, w.d), wallMat);
        wallMesh.position.set(w.x, 3, w.z);
        wallMesh.receiveShadow = true;
        environmentGroup.add(wallMesh);
    });

    scene.add(environmentGroup);
}

function addObstacleBox(cx, cz, width, depth, height) {
    obstacles.push({
        minX: cx - width / 2,
        maxX: cx + width / 2,
        minZ: cz - depth / 2,
        maxZ: cz + depth / 2,
        height
    });
}

/**
 * ============================================================================
 * 6. PENEMPATAN 10 HIDDEN GEM DI SUDUT, BELAKANG POHON, & PETI
 * ============================================================================
 */
function spawnHiddenGems() {
    hiddenGems.forEach(g => scene.remove(g.mesh));
    hiddenGems = [];

    // 10 titik persembunyian strategis (di belakang gedung, pohon, peti, dan sudut map)
    const hidingSpots = [
        { x: -42, z: -42 }, // Sudut Barat Laut (belakang gedung/pohon)
        { x: 42, z: -42 },  // Sudut Timur Laut
        { x: -42, z: 42 },  // Sudut Barat Daya
        { x: 42, z: 42 },   // Sudut Timur Daya
        { x: -25, z: -15 }, // Belakang peti/pohon kiri
        { x: 25, z: 15 },   // Belakang peti/pohon kanan
        { x: 0, z: -53 },   // Belakang bangunan/batu utara
        { x: 0, z: 53 },    // Belakang bangunan/batu selatan
        { x: -53, z: 0 },   // Sudut barat tengah
        { x: 53, z: 0 }     // Sudut timur tengah
    ];

    hidingSpots.forEach((spot, index) => {
        const gemGroup = new THREE.Group();
        gemGroup.position.set(spot.x, 1.3, spot.z);

        // Peti Harta Karun Kecil di Bawah Gem
        const chest = new THREE.Mesh(
            new THREE.BoxGeometry(1.5, 0.9, 1.1),
            new THREE.MeshLambertMaterial({ color: 0x92400e })
        );
        chest.position.y = -0.8;
        chest.castShadow = true;
        gemGroup.add(chest);

        const chestTrim = new THREE.Mesh(
            new THREE.BoxGeometry(1.56, 0.18, 1.16),
            new THREE.MeshBasicMaterial({ color: 0xfacc15 })
        );
        chestTrim.position.y = -0.45;
        gemGroup.add(chestTrim);

        // Kristal Permata Bercahaya (Octahedron)
        const crystal = new THREE.Mesh(
            new THREE.OctahedronGeometry(0.75, 0),
            new THREE.MeshStandardMaterial({
                color: 0x38bdf8,
                emissive: 0x0284c7,
                emissiveIntensity: 0.7,
                roughness: 0.15,
                metalness: 0.3
            })
        );
        crystal.position.y = 0.45;
        gemGroup.add(crystal);

        // Cincin Cahaya Bawah
        const ring = new THREE.Mesh(
            new THREE.RingGeometry(0.9, 1.25, 24),
            new THREE.MeshBasicMaterial({ color: 0xfacc15, side: THREE.DoubleSide })
        );
        ring.rotation.x = -Math.PI / 2;
        ring.position.y = -1.25;
        gemGroup.add(ring);

        scene.add(gemGroup);

        hiddenGems.push({
            id: index,
            x: spot.x,
            z: spot.z,
            mesh: gemGroup,
            crystal,
            collected: false,
            collectedBy: null
        });
    });
}

/**
 * ============================================================================
 * 7. PEMAIN UTAMA & BOT / MULTIPLAYER AI
 * ============================================================================
 */
function spawnPlayerAndBots() {
    if (playerObj) scene.remove(playerObj.mesh);
    bots.forEach(b => scene.remove(b.charObj.mesh));
    bots = [];
    projectiles.forEach(p => scene.remove(p.mesh));
    projectiles = [];

    // Reset Player State
    playerState.pos.set(0, 0, 0);
    playerState.velY = 0;
    playerState.onGround = true;
    playerState.yaw = 0;
    playerState.pitch = 0.22;
    playerState.hp = 100;
    playerState.score = 0;
    playerState.kills = 0;
    playerState.gemsCollected = 0;

    playerObj = createRobloxCharacter({
        skinColor: gameConfig.skinColor,
        shirtColor: gameConfig.shirtColor,
        pantsColor: gameConfig.pantsColor,
        hat: gameConfig.hat,
        isBot: false
    });
    scene.add(playerObj.mesh);

    // Spawn Bots / Simulated Multiplayer Opponents
    const botCount = gameConfig.mode === 'solo' ? 5 : 7;
    const spawnCoords = [
        [-30, -28], [30, -28], [-30, 28], [30, 28],
        [0, -36], [0, 36], [-38, 0]
    ];
    const botShirtColors = ['#ef4444', '#a855f7', '#f97316', '#ec4899', '#14b8a6', '#eab308', '#6366f1'];
    const botHats = ['cap', 'visor', 'none', 'crown', 'cap', 'none', 'visor'];

    for (let i = 0; i < botCount; i++) {
        const sp = spawnCoords[i % spawnCoords.length];
        const botName = gameConfig.mode === 'solo'
            ? `Bot_Guard_${i + 1}`
            : MULTIPLAYER_BOT_NAMES[i % MULTIPLAYER_BOT_NAMES.length];

        const charObj = createRobloxCharacter({
            skinColor: i % 2 === 0 ? '#facc15' : '#fed7aa',
            shirtColor: botShirtColors[i % botShirtColors.length],
            pantsColor: '#0f172a',
            hat: botHats[i % botHats.length],
            isBot: true
        });
        charObj.mesh.position.set(sp[0], 0, sp[1]);
        scene.add(charObj.mesh);

        bots.push({
            id: `bot-${i}`,
            name: botName,
            charObj,
            pos: new THREE.Vector3(sp[0], 0, sp[1]),
            yaw: Math.random() * Math.PI * 2,
            hp: 100,
            maxHp: 100,
            score: 0,
            kills: 0,
            gems: 0,
            shootTimer: 1.5 + Math.random() * 2,
            wanderTimer: 0,
            walkCycle: Math.random() * 5,
            gemFindTimer: 22 + Math.random() * 25 // Untuk simulasi kompetisi multiplayer
        });
    }
}

/**
 * ============================================================================
 * 8. KONTROL PEMAIN (KEYBOARD, MOUSE LOCK, DRAG, DAN TOUCH)
 * ============================================================================
 */
function setupControls() {
    window.addEventListener('keydown', e => {
        keys[e.code] = true;
        if (!gameActive || isQuizModalOpen) return;

        if (e.code === 'Space') {
            e.preventDefault();
            playerJump();
        } else if (e.code === 'KeyF') {
            playerShoot();
        } else if (e.code === 'KeyE') {
            triggerNearbyGemQuiz();
        }
    });

    window.addEventListener('keyup', e => {
        keys[e.code] = false;
    });

    const canvas = document.getElementById('game-canvas');

    // Pointer lock & Left click shoot
    canvas.addEventListener('mousedown', e => {
        if (!gameActive || isQuizModalOpen) return;
        SoundFX.init();

        if (e.button === 0) {
            if (!isPointerLocked && document.pointerLockElement !== canvas) {
                // Coba kunci pointer pada desktop, tetap izinkan tembak
                try { canvas.requestPointerLock(); } catch (err) {}
            }
            playerShoot();
            isDraggingLook = true;
            prevMouseX = e.clientX;
            prevMouseY = e.clientY;
        }
    });

    window.addEventListener('mouseup', () => {
        isDraggingLook = false;
    });

    document.addEventListener('pointerlockchange', () => {
        isPointerLocked = document.pointerLockElement === canvas;
        const hint = document.getElementById('pointer-lock-hint');
        if (hint) {
            hint.style.display = isPointerLocked ? 'none' : 'block';
        }
    });

    window.addEventListener('mousemove', e => {
        if (!gameActive || isQuizModalOpen) return;
        if (isPointerLocked) {
            playerState.yaw -= e.movementX * 0.0028;
            playerState.pitch = Math.max(-0.25, Math.min(0.85, playerState.pitch + e.movementY * 0.0025));
        } else if (isDraggingLook) {
            const dx = e.clientX - prevMouseX;
            const dy = e.clientY - prevMouseY;
            prevMouseX = e.clientX;
            prevMouseY = e.clientY;
            playerState.yaw -= dx * 0.005;
            playerState.pitch = Math.max(-0.25, Math.min(0.85, playerState.pitch + dy * 0.004));
        }
    });

    // Touch camera look on right side of screen
    let touchLookId = null;
    let lastTouchX = 0, lastTouchY = 0;

    canvas.addEventListener('touchstart', e => {
        if (!gameActive || isQuizModalOpen) return;
        SoundFX.init();
        for (let t of e.changedTouches) {
            if (t.clientX > window.innerWidth * 0.35 && touchLookId === null) {
                touchLookId = t.identifier;
                lastTouchX = t.clientX;
                lastTouchY = t.clientY;
            }
        }
    }, { passive: true });

    canvas.addEventListener('touchmove', e => {
        if (!gameActive || isQuizModalOpen) return;
        for (let t of e.changedTouches) {
            if (t.identifier === touchLookId) {
                const dx = t.clientX - lastTouchX;
                const dy = t.clientY - lastTouchY;
                lastTouchX = t.clientX;
                lastTouchY = t.clientY;
                playerState.yaw -= dx * 0.006;
                playerState.pitch = Math.max(-0.2, Math.min(0.85, playerState.pitch + dy * 0.005));
            }
        }
    }, { passive: true });

    canvas.addEventListener('touchend', e => {
        for (let t of e.changedTouches) {
            if (t.identifier === touchLookId) {
                touchLookId = null;
            }
        }
    });

    // On-screen D-Pad Buttons
    const bindDpad = (btnId, code) => {
        const btn = document.getElementById(btnId);
        const start = e => { e.preventDefault(); keys[code] = true; };
        const end = e => { e.preventDefault(); keys[code] = false; };
        btn.addEventListener('mousedown', start);
        btn.addEventListener('mouseup', end);
        btn.addEventListener('mouseleave', end);
        btn.addEventListener('touchstart', start);
        btn.addEventListener('touchend', end);
    };
    bindDpad('btn-touch-up', 'KeyW');
    bindDpad('btn-touch-down', 'KeyS');
    bindDpad('btn-touch-left', 'KeyA');
    bindDpad('btn-touch-right', 'KeyD');
}

function playerJump() {
    if (!gameActive || isQuizModalOpen) return;
    if (playerState.onGround) {
        playerState.velY = 12.5;
        playerState.onGround = false;
        SoundFX.jump();
    }
}

function playerShoot() {
    if (!gameActive || isQuizModalOpen) return;
    if (playerState.shootCooldown > 0) return;

    playerState.shootCooldown = 0.24;
    SoundFX.shoot();

    const dir = new THREE.Vector3(-Math.sin(playerState.yaw), 0, -Math.cos(playerState.yaw)).normalize();
    const spawnPos = playerState.pos.clone().add(new THREE.Vector3(0, 1.75, 0)).addScaledVector(dir, 1.1);

    spawnProjectile(spawnPos, dir, 'player', gameConfig.playerName, 0x38bdf8);
}

function spawnProjectile(origin, dir, ownerType, ownerName, colorHex) {
    const bulletMesh = new THREE.Mesh(
        new THREE.SphereGeometry(0.24, 8, 8),
        new THREE.MeshBasicMaterial({ color: colorHex })
    );
    bulletMesh.position.copy(origin);
    scene.add(bulletMesh);

    projectiles.push({
        mesh: bulletMesh,
        vel: dir.clone().multiplyScalar(54),
        ownerType,
        ownerName,
        life: 1.8
    });
}

function spawnHitParticles(pos, colorHex) {
    for (let i = 0; i < 8; i++) {
        const pMesh = new THREE.Mesh(
            new THREE.BoxGeometry(0.22, 0.22, 0.22),
            new THREE.MeshBasicMaterial({ color: colorHex })
        );
        pMesh.position.copy(pos);
        scene.add(pMesh);
        particles.push({
            mesh: pMesh,
            vel: new THREE.Vector3(
                (Math.random() - 0.5) * 12,
                2 + Math.random() * 8,
                (Math.random() - 0.5) * 12
            ),
            life: 0.45
        });
    }
}

/**
 * ============================================================================
 * 9. LOGIKA PERGERAKAN, TABRAKAN, AI BOT, & HIDDEN GEM QUIZ
 * ============================================================================
 */
function resolveCircleObstacleCollision(pos, radius = 0.85) {
    const limit = ARENA_SIZE / 2 - 1.8;
    pos.x = Math.max(-limit, Math.min(limit, pos.x));
    pos.z = Math.max(-limit, Math.min(limit, pos.z));

    for (const obs of obstacles) {
        const closestX = Math.max(obs.minX, Math.min(pos.x, obs.maxX));
        const closestZ = Math.max(obs.minZ, Math.min(pos.z, obs.maxZ));
        const dx = pos.x - closestX;
        const dz = pos.z - closestZ;
        const distSq = dx * dx + dz * dz;

        if (distSq < radius * radius) {
            const dist = Math.sqrt(distSq) || 0.001;
            const overlap = radius - dist;
            pos.x += (dx / dist) * overlap;
            pos.z += (dz / dist) * overlap;
        }
    }
}

function pointHitsObstacle(pos) {
    const limit = ARENA_SIZE / 2 - 1;
    if (Math.abs(pos.x) > limit || Math.abs(pos.z) > limit) return true;
    for (const obs of obstacles) {
        if (pos.x >= obs.minX && pos.x <= obs.maxX && pos.z >= obs.minZ && pos.z <= obs.maxZ && pos.y <= obs.height) {
            return true;
        }
    }
    return false;
}

function updatePlayer(dt) {
    if (playerState.shootCooldown > 0) playerState.shootCooldown -= dt;

    let moveForward = 0;
    let moveRight = 0;
    if (keys['KeyW'] || keys['ArrowUp']) moveForward += 1;
    if (keys['KeyS'] || keys['ArrowDown']) moveForward -= 1;
    if (keys['KeyD'] || keys['ArrowRight']) moveRight += 1;
    if (keys['KeyA'] || keys['ArrowLeft']) moveRight -= 1;

    const forwardVec = new THREE.Vector3(-Math.sin(playerState.yaw), 0, -Math.cos(playerState.yaw));
    const rightVec = new THREE.Vector3(Math.cos(playerState.yaw), 0, -Math.sin(playerState.yaw));

    const moveDir = new THREE.Vector3()
        .addScaledVector(forwardVec, moveForward)
        .addScaledVector(rightVec, moveRight);

    const isMoving = moveDir.lengthSq() > 0.001;
    if (isMoving) {
        moveDir.normalize();
        const speed = 13.5;
        playerState.pos.addScaledVector(moveDir, speed * dt);

        // Karakter menghadap arah kamera agar membidik selalu akurat
        playerObj.mesh.rotation.y = playerState.yaw + Math.PI;

        // Animasi lari ala Roblox
        playerState.walkCycle += dt * 13;
        const swing = Math.sin(playerState.walkCycle) * 0.65;
        playerObj.leftLegPivot.rotation.x = swing;
        playerObj.rightLegPivot.rotation.x = -swing;
        playerObj.leftArmPivot.rotation.x = -swing * 0.7;
    } else {
        playerObj.mesh.rotation.y = playerState.yaw + Math.PI;
        playerObj.leftLegPivot.rotation.x *= 0.85;
        playerObj.rightLegPivot.rotation.x *= 0.85;
        playerObj.leftArmPivot.rotation.x *= 0.85;
    }

    // Gravitasi & Lompat
    playerState.velY -= 32 * dt;
    playerState.pos.y += playerState.velY * dt;
    if (playerState.pos.y <= 0) {
        playerState.pos.y = 0;
        playerState.velY = 0;
        playerState.onGround = true;
    }

    resolveCircleObstacleCollision(playerState.pos, 0.85);
    playerObj.mesh.position.copy(playerState.pos);

    // Kamera Third-Person Over-the-Shoulder
    const camDist = 7.2;
    const camHeight = 3.2 + Math.sin(playerState.pitch) * 3.5;
    const horizDist = Math.cos(playerState.pitch) * camDist;

    const targetCamPos = new THREE.Vector3(
        playerState.pos.x + Math.sin(playerState.yaw) * horizDist,
        playerState.pos.y + camHeight,
        playerState.pos.z + Math.cos(playerState.yaw) * horizDist
    );

    camera.position.lerp(targetCamPos, 0.25);
    const lookTarget = new THREE.Vector3(
        playerState.pos.x - Math.sin(playerState.yaw) * 6,
        playerState.pos.y + 2.1 - Math.sin(playerState.pitch) * 2.5,
        playerState.pos.z - Math.cos(playerState.yaw) * 6
    );
    camera.lookAt(lookTarget);
}

function updateBots(dt) {
    bots.forEach(bot => {
        const toPlayer = new THREE.Vector3().subVectors(playerState.pos, bot.pos);
        const distToPlayer = toPlayer.length();

        // AI Behavior: Kejar pemain jika dalam jarak 34 unit, atau patroli keliling arena
        if (distToPlayer < 34 && distToPlayer > 7.5) {
            bot.yaw = Math.atan2(-toPlayer.x, -toPlayer.z);
        } else {
            bot.wanderTimer -= dt;
            if (bot.wanderTimer <= 0) {
                bot.yaw += (Math.random() - 0.5) * 2.4;
                bot.wanderTimer = 1.5 + Math.random() * 2.5;
            }
        }

        const forward = new THREE.Vector3(-Math.sin(bot.yaw), 0, -Math.cos(bot.yaw));
        bot.pos.addScaledVector(forward, 7.2 * dt);
        resolveCircleObstacleCollision(bot.pos, 0.85);

        bot.charObj.mesh.position.copy(bot.pos);
        bot.charObj.mesh.rotation.y = bot.yaw + Math.PI;

        // Animasi berjalan bot
        bot.walkCycle += dt * 10;
        const swing = Math.sin(bot.walkCycle) * 0.55;
        bot.charObj.leftLegPivot.rotation.x = swing;
        bot.charObj.rightLegPivot.rotation.x = -swing;

        // Bot menembak pemain jika terlihat dekat
        bot.shootTimer -= dt;
        if (distToPlayer < 28 && bot.shootTimer <= 0) {
            bot.shootTimer = 1.6 + Math.random() * 1.4;
            const aimDir = toPlayer.clone().normalize();
            const origin = bot.pos.clone().add(new THREE.Vector3(0, 1.7, 0)).addScaledVector(aimDir, 1.1);
            spawnProjectile(origin, aimDir, 'bot', bot.name, 0xf87171);
        }

        // Simulasi mode Multiplayer: Bot sesekali mendapat poin eliminasi sesama bot atau menemukan gem
        if (gameConfig.mode === 'multiplayer') {
            bot.gemFindTimer -= dt;
            if (bot.gemFindTimer <= 0) {
                bot.gemFindTimer = 35 + Math.random() * 35;
                bot.score += 50;
                bot.kills += 1;
            }
        }
    });
}

function updateProjectiles(dt) {
    for (let i = projectiles.length - 1; i >= 0; i--) {
        const p = projectiles[i];
        p.life -= dt;
        p.mesh.position.addScaledVector(p.vel, dt);

        if (p.life <= 0 || pointHitsObstacle(p.mesh.position)) {
            spawnHitParticles(p.mesh.position, p.ownerType === 'player' ? 0x38bdf8 : 0xf87171);
            scene.remove(p.mesh);
            projectiles.splice(i, 1);
            continue;
        }

        if (p.ownerType === 'player') {
            // Cek kena bot
            let hitBot = false;
            for (const bot of bots) {
                const dx = p.mesh.position.x - bot.pos.x;
                const dz = p.mesh.position.z - bot.pos.z;
                if (dx * dx + dz * dz < 1.35 && p.mesh.position.y < 3.1) {
                    hitBot = true;
                    bot.hp -= 35;
                    SoundFX.hit();
                    spawnHitParticles(p.mesh.position, 0xfacc15);

                    if (bot.hp <= 0) {
                        // Bot Tereliminasi!
                        SoundFX.elim();
                        playerState.kills += 1;
                        playerState.score += 50;
                        showToast(`💥 Mengeliminasi ${bot.name}! (+50 Skor)`, 'bg-rose-500 text-white');

                        // Respawn bot di titik acak
                        bot.hp = 100;
                        const angle = Math.random() * Math.PI * 2;
                        bot.pos.set(Math.cos(angle) * 44, 0, Math.sin(angle) * 44);
                    }
                    break;
                }
            }
            if (hitBot) {
                scene.remove(p.mesh);
                projectiles.splice(i, 1);
            }
        } else {
            // Peluru Bot kena Pemain
            const dx = p.mesh.position.x - playerState.pos.x;
            const dz = p.mesh.position.z - playerState.pos.z;
            if (dx * dx + dz * dz < 1.1 && p.mesh.position.y < 3.0) {
                playerState.hp = Math.max(0, playerState.hp - 10);
                SoundFX.hit();
                spawnHitParticles(p.mesh.position, 0xef4444);
                scene.remove(p.mesh);
                projectiles.splice(i, 1);

                if (playerState.hp <= 0) {
                    // Respawn pemain cepat tanpa kehilangan Gem
                    playerState.hp = 100;
                    playerState.pos.set(0, 0, 0);
                    showToast('💫 Kamu tereliminasi! Respawn di titik tengah...', 'bg-amber-500 text-slate-950');
                }
            }
        }
    }
}

function updateParticles(dt) {
    for (let i = particles.length - 1; i >= 0; i--) {
        const pt = particles[i];
        pt.life -= dt;
        pt.vel.y -= 24 * dt;
        pt.mesh.position.addScaledVector(pt.vel, dt);
        pt.mesh.scale.setScalar(Math.max(0.01, pt.life * 2));
        if (pt.life <= 0) {
            scene.remove(pt.mesh);
            particles.splice(i, 1);
        }
    }
}

function updateHiddenGems(dt) {
    let closestUncollected = null;
    let closestDist = Infinity;

    hiddenGems.forEach(gem => {
        if (gem.collected) return;

        // Animasi kristal berputar & melayang
        gem.crystal.rotation.y += dt * 2.2;
        gem.crystal.position.y = 0.45 + Math.sin(performance.now() * 0.004 + gem.id) * 0.18;

        const dx = playerState.pos.x - gem.x;
        const dz = playerState.pos.z - gem.z;
        const dist = Math.sqrt(dx * dx + dz * dz);

        if (dist < closestDist) {
            closestDist = dist;
            closestUncollected = gem;
        }
    });

    // Update Radar HUD
    const radarEl = document.getElementById('hud-radar-text');
    if (closestUncollected) {
        radarEl.textContent = `Gem #${closestUncollected.id + 1} (${Math.round(closestDist)}m)`;
    } else {
        radarEl.textContent = 'Semua Gem Terkumpul!';
    }

    // Proximity Prompt
    const promptEl = document.getElementById('gem-proximity-prompt');
    if (closestUncollected && closestDist < 3.4) {
        nearbyGem = closestUncollected;
        document.getElementById('nearby-gem-number').textContent = closestUncollected.id + 1;
        promptEl.classList.remove('hidden');
    } else {
        nearbyGem = null;
        promptEl.classList.add('hidden');
    }
}

/**
 * ============================================================================
 * 10. SISTEM KUIS INTERAKTIF SAAT MENEMUKAN HIDDEN GEM
 * ============================================================================
 */
let currentActiveGem = null;

function triggerNearbyGemQuiz() {
    if (!nearbyGem || nearbyGem.collected || isQuizModalOpen) return;

    currentActiveGem = nearbyGem;
    isQuizModalOpen = true;
    SoundFX.gemOpen();

    // Bebaskan kursor mouse agar mudah mengklik pilihan jawaban
    if (document.pointerLockElement) {
        try { document.exitPointerLock(); } catch (e) {}
    }

    const qData = quizQuestions[currentActiveGem.id];
    document.getElementById('quiz-modal-title').textContent = `Tantangan Hidden Gem #${currentActiveGem.id + 1}`;
    document.getElementById('quiz-modal-question').textContent = qData.q;

    const feedbackEl = document.getElementById('quiz-modal-feedback');
    feedbackEl.classList.add('hidden');

    const optionsContainer = document.getElementById('quiz-modal-options');
    optionsContainer.innerHTML = '';

    const letters = ['A', 'B', 'C', 'D'];
    qData.options.forEach((optText, idx) => {
        const btn = document.createElement('button');
        btn.className = 'btn-blox w-full p-3.5 rounded-2xl bg-slate-800 hover:bg-indigo-600 border border-white/15 text-left font-bold text-sm sm:text-base flex items-center gap-3 transition-colors';
        btn.innerHTML = `
            <span class="w-8 h-8 rounded-xl bg-amber-400 text-slate-950 font-roblox font-bold flex items-center justify-center shrink-0">${letters[idx]}</span>
            <span>${escapeHtml(optText)}</span>
        `;
        btn.onclick = () => submitGemAnswer(idx, btn);
        optionsContainer.appendChild(btn);
    });

    document.getElementById('active-quiz-modal').classList.remove('hidden');
}

function submitGemAnswer(selectedIdx, btnElement) {
    if (!currentActiveGem) return;
    const qData = quizQuestions[currentActiveGem.id];
    const feedbackEl = document.getElementById('quiz-modal-feedback');

    if (selectedIdx === qData.answer) {
        // JAWABAN BENAR!
        SoundFX.correct();
        btnElement.classList.remove('bg-slate-800', 'hover:bg-indigo-600');
        btnElement.classList.add('bg-emerald-500', 'text-slate-950');

        feedbackEl.textContent = '🎉 BENAR! +100 Skor & Pemulihan +30 HP!';
        feedbackEl.className = 'mt-4 p-3 rounded-xl text-center font-bold text-sm bg-emerald-500/20 border border-emerald-400 text-emerald-300';
        feedbackEl.classList.remove('hidden');

        // Tandai Gem sebagai terkumpul
        currentActiveGem.collected = true;
        scene.remove(currentActiveGem.mesh);
        playerState.gemsCollected += 1;
        playerState.score += 100;
        playerState.hp = Math.min(playerState.maxHp, playerState.hp + 30);

        setTimeout(() => {
            closeActiveQuizModal();
            showToast(`💎 Hidden Gem #${currentActiveGem.id + 1} Berhasil Dikumpulkan! (${playerState.gemsCollected}/10)`, 'bg-amber-400 text-slate-950');

            // Cek jika semua 10 Gem sudah ditemukan
            if (playerState.gemsCollected >= 10) {
                finishMatch('Selamat! Semua 10 Hidden Gem Berhasil Ditemukan!');
            }
        }, 1050);

    } else {
        // JAWABAN SALAH
        SoundFX.wrong();
        btnElement.classList.remove('bg-slate-800');
        btnElement.classList.add('bg-rose-600');
        feedbackEl.textContent = '❌ Kurang tepat! Coba pilih jawaban yang lain.';
        feedbackEl.className = 'mt-4 p-3 rounded-xl text-center font-bold text-sm bg-rose-500/20 border border-rose-400 text-rose-300';
        feedbackEl.classList.remove('hidden');
    }
}

function closeActiveQuizModal() {
    document.getElementById('active-quiz-modal').classList.add('hidden');
    isQuizModalOpen = false;
    currentActiveGem = null;
}

/**
 * ============================================================================
 * 11. UPDATE HUD, TIMER 10 MENIT, DAN SIKLUS PERTANDINGAN
 * ============================================================================
 */
function updateHUD() {
    document.getElementById('hud-player-name').textContent = gameConfig.playerName;
    document.getElementById('hud-hp-text').textContent = `${playerState.hp} / ${playerState.maxHp} HP`;
    document.getElementById('hud-hp-bar').style.width = `${(playerState.hp / playerState.maxHp) * 100}%`;
    document.getElementById('hud-kills').textContent = playerState.kills;
    document.getElementById('hud-score').textContent = playerState.score;
    document.getElementById('hud-gems').textContent = playerState.gemsCollected;

    // Update Mini Leaderboard
    const allEntries = [
        { name: `${gameConfig.playerName} (Kamu)`, score: playerState.score, isMe: true },
        ...bots.map(b => ({ name: b.name, score: b.score, isMe: false }))
    ].sort((a, b) => b.score - a.score).slice(0, 5);

    const lbEl = document.getElementById('hud-leaderboard');
    lbEl.innerHTML = allEntries.map((entry, idx) => `
        <div class="flex items-center justify-between px-2 py-1 rounded-lg ${entry.isMe ? 'bg-cyan-500/25 text-cyan-200 font-bold' : 'text-slate-300'}">
            <span class="truncate max-w-[130px]">${idx + 1}. ${escapeHtml(entry.name)}</span>
            <span class="font-bold text-amber-300">${entry.score}</span>
        </div>
    `).join('');
}

function formatTime(sec) {
    const m = Math.floor(sec / 60);
    const s = sec % 60;
    return `${String(m).padStart(2, '0')}:${String(s).padStart(2, '0')}`;
}

function startGame() {
    SoundFX.init();
    SoundFX.click();

    document.getElementById('lobby-screen').classList.add('hidden');
    document.getElementById('gameover-modal').classList.add('hidden');
    document.getElementById('game-hud').classList.remove('hidden');
    document.getElementById('hud-mode-badge').textContent = gameConfig.mode === 'solo' ? 'SOLO VS BOT' : 'MULTIPLAYER';

    buildWorldEnvironment(gameConfig.map);
    spawnHiddenGems();
    spawnPlayerAndBots();

    matchTimeRemaining = 600; // 10 Menit
    document.getElementById('hud-timer').textContent = formatTime(matchTimeRemaining);

    if (timerInterval) clearInterval(timerInterval);
    timerInterval = setInterval(() => {
        if (!gameActive || isQuizModalOpen) return;
        matchTimeRemaining -= 1;
        document.getElementById('hud-timer').textContent = formatTime(matchTimeRemaining);

        if (matchTimeRemaining <= 0) {
            finishMatch('Waktu 10 Menit Telah Habis!');
        }
    }, 1000);

    gameActive = true;
    isQuizModalOpen = false;
    lastFrameTime = performance.now();
    showToast('🚀 Pertandingan Dimulai! Cari 10 Hidden Gem & Kalahkan Lawan!', 'bg-cyan-400 text-slate-950');
}

function endGameEarly() {
    SoundFX.click();
    finishMatch('Pertandingan Diakhiri oleh Pemain');
}

function finishMatch(reasonText) {
    gameActive = false;
    isQuizModalOpen = false;
    if (timerInterval) clearInterval(timerInterval);
    if (document.pointerLockElement) {
        try { document.exitPointerLock(); } catch (e) {}
    }

    document.getElementById('active-quiz-modal').classList.add('hidden');
    document.getElementById('game-hud').classList.add('hidden');

    document.getElementById('gameover-subtitle').textContent = reasonText;
    document.getElementById('final-score').textContent = playerState.score;
    document.getElementById('final-gems').textContent = `${playerState.gemsCollected} / 10`;
    document.getElementById('final-kills').textContent = playerState.kills;

    const rankings = [
        { name: `${gameConfig.playerName} (Kamu)`, score: playerState.score, kills: playerState.kills, isMe: true },
        ...bots.map(b => ({ name: b.name, score: b.score, kills: b.kills, isMe: false }))
    ].sort((a, b) => b.score - a.score);

    document.getElementById('final-leaderboard').innerHTML = rankings.map((r, i) => `
        <div class="flex items-center justify-between px-3 py-2 rounded-xl ${r.isMe ? 'bg-cyan-500/25 border border-cyan-400/50 font-bold text-white' : 'bg-slate-800/60 text-slate-300'}">
            <span>#${i + 1} ${escapeHtml(r.name)}</span>
            <span class="text-amber-300 font-bold">${r.score} Poin (${r.kills} KO)</span>
        </div>
    `).join('');

    SoundFX.correct();
    document.getElementById('gameover-modal').classList.remove('hidden');
}

function returnToLobby() {
    SoundFX.click();
    document.getElementById('gameover-modal').classList.add('hidden');
    document.getElementById('lobby-screen').classList.remove('hidden');
}

function restartMatchDirectly() {
    startGame();
}

/**
 * ============================================================================
 * 12. LOOP ANIMASI UTAMA (60 FPS)
 * ============================================================================
 */
function gameLoop(now) {
    requestAnimationFrame(gameLoop);

    const dt = Math.min((now - lastFrameTime) / 1000, 0.05);
    lastFrameTime = now;

    if (gameActive && !isQuizModalOpen) {
        updatePlayer(dt);
        updateBots(dt);
        updateProjectiles(dt);
        updateParticles(dt);
        updateHiddenGems(dt);
        updateHUD();
    }

    if (renderer && scene && camera) {
        renderer.render(scene, camera);
    }
}

window.onload = function () {
    initLobbyPreview();
    initThreeEngine();
    // Render latar awal di belakang lobby
    buildWorldEnvironment('city');
    camera.position.set(0, 22, 42);
    camera.lookAt(0, 4, 0);
    lastFrameTime = performance.now();
    requestAnimationFrame(gameLoop);
};
</script>
</body>
</html>