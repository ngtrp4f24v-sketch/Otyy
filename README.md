<!DOCTYPE html>
<html lang="lo">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ລອຍກະທົງອອນໄລນ໌ ສຳລັບຄູ່ຮັກ - Romantic Loy Krathong for Couples</title>
    
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Google Fonts for Lao Language -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+Lao:wght@300;400;600;700;800&family=Phetsarath&family=Great+Vibes&display=swap" rel="stylesheet">
    
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <!-- Canvas Confetti -->
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>

    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        laoGold: '#F39C12',
                        laoDarkGold: '#B7950B',
                        laoDeepPurple: '#1A0B2E',
                        laoNightBlue: '#0D1117',
                        laoWaterDark: '#091C32',
                        laoWaterLight: '#1B4F72',
                    },
                    fontFamily: {
                        lao: ['Noto Sans Lao', 'Phetsarath', 'sans-serif'],
                        romantic: ['Great Vibes', 'cursive'],
                    }
                }
            }
        }
    </script>

    <style>
        body {
            font-family: 'Noto Sans Lao', sans-serif;
            background-color: #0B0E14;
            color: #E2E8F0;
            overflow-x: hidden;
            user-select: none;
        }

        /* Animated Star Field & River */
        .stars-container {
            background: radial-gradient(ellipse at bottom, #1B2735 0%, #090A0F 100%);
        }

        /* Moon Glow Effect */
        .moon-glow {
            box-shadow: 0 0 50px #FFF3D1, 0 0 100px #FAD7A0, 0 0 150px rgba(243, 156, 18, 0.4);
        }

        /* River Waves Gradient and Animation */
        .river-bg {
            background: linear-gradient(180deg, rgba(13,27,42,0.2) 0%, rgba(9,28,50,0.85) 40%, rgba(5,15,30,0.98) 100%);
        }

        .wave-layer {
            position: absolute;
            width: 200%;
            height: 100%;
            background-repeat: repeat-x;
            transform: translate3d(0, 0, 0);
        }

        @keyframes waveAnim {
            0% { transform: translateX(0); }
            50% { transform: translateX(-25%); }
            100% { transform: translateX(-50%); }
        }

        .wave1 {
            animation: waveAnim 18s linear infinite;
            opacity: 0.3;
        }
        .wave2 {
            animation: waveAnim 12s linear infinite reverse;
            opacity: 0.5;
        }

        /* Floating Flame Animation */
        @keyframes candleFlicker {
            0%, 100% { transform: scale(1) rotate(-1deg); opacity: 0.9; box-shadow: 0 0 12px #FF9800, 0 0 25px #FF5722; }
            50% { transform: scale(1.15) rotate(2deg); opacity: 1; box-shadow: 0 0 18px #FFC107, 0 0 35px #FF9800; }
        }

        .candle-flame {
            animation: candleFlicker 1.2s ease-in-out infinite alternate;
            border-radius: 50% 50% 20% 20%;
        }

        /* Incense Smoke Animation */
        @keyframes smokeRise {
            0% { transform: translateY(0) scaleX(1); opacity: 0.7; }
            50% { transform: translateY(-15px) scaleX(1.8) rotate(10deg); opacity: 0.4; }
            100% { transform: translateY(-35px) scaleX(2.5) rotate(-15deg); opacity: 0; }
        }

        .smoke-particle {
            animation: smokeRise 2.5s infinite ease-out;
        }

        /* Floating Krathong Gentle Bobbing */
        @keyframes floatBob {
            0%, 100% { transform: translateY(0px) rotate(0deg); }
            50% { transform: translateY(-8px) rotate(1.5deg); }
        }

        .krathong-bob {
            animation: floatBob 4s ease-in-out infinite;
        }

        /* Floating Lanterns Rising */
        @keyframes lanternFly {
            0% { transform: translateY(105vh) translateX(0) scale(0.6); opacity: 0; }
            10% { opacity: 0.8; }
            90% { opacity: 0.9; }
            100% { transform: translateY(-10vh) translateX(60px) scale(1.1); opacity: 0; }
        }

        .sky-lantern {
            position: absolute;
            animation: lanternFly linear infinite;
            pointer-events: none;
        }

        /* Custom Scrollbar for Modal */
        ::-webkit-scrollbar {
            width: 6px;
        }
        ::-webkit-scrollbar-track {
            background: rgba(15, 23, 42, 0.6);
        }
        ::-webkit-scrollbar-thumb {
            background: #D97706;
            border-radius: 3px;
        }

        /* Glowing Border Animation */
        @keyframes pulseGlow {
            0%, 100% { border-color: rgba(243, 156, 18, 0.4); box-shadow: 0 0 10px rgba(243, 156, 18, 0.2); }
            50% { border-color: rgba(243, 156, 18, 0.9); box-shadow: 0 0 20px rgba(243, 156, 18, 0.6); }
        }
        .glow-box {
            animation: pulseGlow 3s infinite;
        }
    </style>
</head>
<body class="min-h-screen relative overflow-hidden flex flex-col justify-between">

    <!-- TOP HEADER / NAV BAR -->
    <header class="relative z-30 px-4 py-3 flex justify-between items-center bg-black/40 backdrop-blur-md border-b border-amber-500/30">
        <div class="flex items-center gap-3">
            <div class="w-10 h-10 rounded-full bg-gradient-to-tr from-amber-600 to-yellow-300 flex items-center justify-center shadow-lg shadow-amber-500/30 text-slate-900 font-bold text-xl">
                🌸
            </div>
            <div>
                <h1 class="text-lg md:text-xl font-bold bg-gradient-to-r from-amber-200 via-yellow-400 to-amber-500 bg-clip-text text-transparent">
                    ລອຍກະທົງອອນໄລນ໌ ສຳລັບຄູ່ຮັກ 💖
                </h1>
                <p class="text-xs text-amber-200/70 font-light hidden sm:block">ສ້າງຄວາມຊົງຈຳທີ່ງົດງາມ ແລະ ຂໍພອນນຳກັນໃນຄືນວັນເພັງ</p>
            </div>
        </div>

        <!-- Controls / Buttons -->
        <div class="flex items-center gap-2 sm:gap-3">
            <!-- Audio Toggle Button -->
            <button id="bgmToggleBtn" onclick="toggleBGM()" class="p-2.5 rounded-full bg-slate-800/80 hover:bg-slate-700 text-amber-300 border border-amber-500/30 transition-all flex items-center gap-2 text-xs sm:text-sm">
                <i id="bgmIcon" class="fas fa-music text-amber-400"></i>
                <span class="hidden md:inline" id="bgmStatusText">ເປີດເພງ</span>
            </button>

            <!-- Realtime Sync Badge -->
            <div id="syncBadge" class="hidden sm:flex items-center gap-1.5 px-3 py-1 rounded-full bg-emerald-950/80 border border-emerald-500/40 text-emerald-300 text-xs shadow-inner">
                <span class="w-2 h-2 rounded-full bg-emerald-400 animate-ping"></span>
                <span>ເຊື່ອມຕໍ່ສົດ</span>
            </div>

            <!-- Edit Krathong Trigger Button -->
            <button onclick="openCustomizerModal()" class="px-4 py-2 rounded-full bg-gradient-to-r from-amber-500 to-yellow-600 hover:from-amber-600 hover:to-yellow-700 text-slate-950 font-bold text-xs sm:text-sm shadow-lg shadow-amber-500/20 transition-all transform hover:scale-105 flex items-center gap-2">
                <i class="fas fa-edit"></i>
                <span>ແຕ່ງກະທົງ</span>
            </button>
        </div>
    </header>

    <!-- NIGHT SKY & FULL MOON BACKGROUND SECTION -->
    <div class="absolute inset-0 z-0 stars-container">
        <!-- Floating Sky Lanterns Container -->
        <div id="skyLanternsContainer" class="absolute inset-0 overflow-hidden pointer-events-none z-10"></div>

        <!-- Full Moon -->
        <div class="absolute top-12 right-8 sm:right-24 w-28 h-28 sm:w-44 sm:h-44 rounded-full bg-gradient-to-br from-amber-100 via-amber-200 to-yellow-100 moon-glow z-0 flex items-center justify-center opacity-90 transition-all">
            <div class="w-full h-full rounded-full opacity-20 bg-[radial-gradient(#854d0e_1px,transparent_1px)] [background-size:16px_16px]"></div>
        </div>

        <!-- Night Clouds -->
        <div class="absolute top-20 right-0 w-96 h-24 bg-gradient-to-l from-slate-900/60 to-transparent blur-xl pointer-events-none"></div>
        <div class="absolute top-36 left-10 w-80 h-20 bg-gradient-to-r from-purple-950/40 to-transparent blur-2xl pointer-events-none"></div>
        
        <!-- Subtle Star Sparkles -->
        <div class="absolute inset-0 bg-[radial-gradient(white_1px,transparent_1px)] [background-size:40px_40px] opacity-25"></div>
    </div>

    <!-- MAIN INTERACTIVE WATER / RIVER AREA -->
    <main id="mainRiverView" class="relative z-10 flex-grow flex flex-col justify-end min-h-[550px] w-full overflow-hidden select-none">
        
        <!-- River Waves Layer -->
        <div class="absolute bottom-0 left-0 right-0 h-3/5 river-bg z-0 pointer-events-none">
            <!-- Animated SVG Water Ripples -->
            <div class="wave-layer wave1 bottom-0">
                <svg viewBox="0 0 1200 120" preserveAspectRatio="none" class="w-full h-24 fill-amber-300/10">
                    <path d="M0,0 C150,90 350,-40 500,60 C650,160 900,10 1200,40 L1200,120 L0,120 Z"></path>
                </svg>
            </div>
            <div class="wave-layer wave2 bottom-0">
                <svg viewBox="0 0 1200 120" preserveAspectRatio="none" class="w-full h-28 fill-blue-400/10">
                    <path d="M0,40 C300,100 500,0 800,70 C1000,130 1100,20 1200,60 L1200,120 L0,120 Z"></path>
                </svg>
            </div>
        </div>

        <!-- Released Floating Krathongs Stream (Other floating couple krathongs) -->
        <div id="releasedStream" class="absolute inset-0 z-10 pointer-events-none overflow-hidden"></div>

        <!-- MAIN COUPLE KRATHONG CONTAINER (CENTRAL HERO) -->
        <div id="heroKrathongWrapper" class="relative z-20 mx-auto mb-16 sm:mb-20 transition-all duration-1000 ease-in-out cursor-pointer group" onclick="toggleWishBubble()">
            
            <!-- Wish Scroll Banner Floating above Krathong -->
            <div id="wishDisplayBubble" class="absolute -top-36 left-1/2 -translate-x-1/2 w-72 sm:w-96 bg-slate-900/90 backdrop-blur-md border border-amber-500/50 rounded-2xl p-3.5 shadow-2xl shadow-amber-500/20 text-center transition-all duration-500 scale-100 opacity-100 pointer-events-auto">
                <div class="text-amber-400 text-xs font-semibold uppercase tracking-wider mb-1 flex items-center justify-center gap-1">
                    <i class="fas fa-heart text-red-400"></i>
                    <span>ຄຳອະທິຖານຄູ່ຮັກ</span>
                    <i class="fas fa-heart text-red-400"></i>
                </div>
                <!-- Wishes Content -->
                <div class="space-y-1.5 text-xs sm:text-sm text-slate-200 font-light italic">
                    <p id="displayWishP1" class="line-clamp-2"><span class="text-amber-300 font-semibold" id="displayNameP1 font-normal">ຄົນທີ 1</span>: "ຂໍໃຫ້ຄວາມຮັກຂອງເຮົາຍືນຍາວດັ່ງສາຍນ້ຳ..."</p>
                    <div class="w-full h-px bg-amber-500/20 my-1"></div>
                    <p id="displayWishP2" class="line-clamp-2"><span class="text-pink-300 font-semibold" id="displayNameP2 font-normal">ຄົນທີ 2</span>: "ຂໍໃຫ້ມີຄວາມສຸກ ແລະ ຮັກກັນຕະຫຼອດໄປ..."</p>
                </div>
                <!-- Decorative Arrow Pointer -->
                <div class="absolute -bottom-2 left-1/2 -translate-x-1/2 w-4 h-4 bg-slate-900/90 border-r border-b border-amber-500/50 rotate-45"></div>
            </div>

            <!-- THE KRATHONG CANVAS / DESIGN -->
            <div id="heroKrathongBody" class="krathong-bob relative w-64 h-64 sm:w-80 sm:h-80 mx-auto flex items-center justify-center">
                
                <!-- Water Glow aura around bottom -->
                <div class="absolute bottom-2 w-full h-1/3 bg-amber-500/20 rounded-full blur-2xl animate-pulse"></div>

                <!-- 1. LIGHT CANDLES & INCENSE EFFECT -->
                <div class="absolute top-10 z-30 flex items-center justify-center gap-6">
                    <!-- Candle Flame 1 -->
                    <div class="relative flex flex-col items-center">
                        <div class="w-3 h-5 bg-gradient-to-t from-orange-500 via-amber-300 to-white candle-flame"></div>
                        <div class="w-1.5 h-12 bg-amber-100 rounded-sm shadow-md"></div>
                    </div>
                    <!-- Incense Smoke 1 -->
                    <div class="relative flex flex-col items-center top-2">
                        <div class="w-1 h-3 bg-red-400/50 rounded-full smoke-particle"></div>
                        <div class="w-0.5 h-14 bg-amber-800"></div>
                    </div>
                    <!-- Incense Smoke 2 -->
                    <div class="relative flex flex-col items-center top-3 -ml-4">
                        <div class="w-1 h-3 bg-red-400/50 rounded-full smoke-particle" style="animation-delay: 0.8s"></div>
                        <div class="w-0.5 h-12 bg-amber-900"></div>
                    </div>
                </div>

                <!-- 2. COUPLE PHOTOS IN KRATHONG CENTER -->
                <div class="absolute z-20 top-24 flex items-center justify-center -space-x-3 bg-amber-950/60 p-2 rounded-full border border-amber-400/40 shadow-xl backdrop-blur-sm">
                    <!-- Person 1 Face -->
                    <div class="relative group/p1">
                        <div class="w-14 h-14 sm:w-16 sm:h-16 rounded-full border-2 border-amber-300 overflow-hidden bg-slate-800 shadow-md transform hover:scale-110 transition-all">
                            <img id="imgP1" src="https://images.unsplash.com/photo-1534528741775-53994a69daeb?w=150&auto=format&fit=crop&q=80" alt="Person 1" class="w-full h-full object-cover">
                        </div>
                        <span id="badgeP1" class="absolute -bottom-1 left-1/2 -translate-x-1/2 bg-amber-500 text-slate-950 text-[10px] font-bold px-1.5 py-0.2 rounded-full whitespace-nowrap shadow">
                            ເຈົ້າ
                        </span>
                    </div>

                    <!-- Heart Icon Connector -->
                    <div class="z-10 text-red-500 text-lg sm:text-xl animate-bounce drop-shadow">
                        💖
                    </div>

                    <!-- Person 2 Face -->
                    <div class="relative group/p2">
                        <div class="w-14 h-14 sm:w-16 sm:h-16 rounded-full border-2 border-pink-300 overflow-hidden bg-slate-800 shadow-md transform hover:scale-110 transition-all">
                            <img id="imgP2" src="https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=150&auto=format&fit=crop&q=80" alt="Person 2" class="w-full h-full object-cover">
                        </div>
                        <span id="badgeP2" class="absolute -bottom-1 left-1/2 -translate-x-1/2 bg-pink-500 text-white text-[10px] font-bold px-1.5 py-0.2 rounded-full whitespace-nowrap shadow">
                            ຄູ່ຮັກ
                        </span>
                    </div>
                </div>

                <!-- 3. DYNAMIC KRATHONG BASE GRAPHIC (Lotus / Banana Leaf / Royal Flowers) -->
                <div id="krathongBaseSVG" class="absolute inset-0 flex items-center justify-center z-10 transform scale-110">
                    <!-- Default Lotus Krathong SVG -->
                    <svg viewBox="0 0 200 200" class="w-full h-full drop-shadow-2xl">
                        <!-- Bottom Banana Trunk Base -->
                        <ellipse cx="100" cy="145" rx="70" ry="25" fill="#2d5a27" stroke="#1b3818" stroke-width="3" />
                        <ellipse cx="100" cy="140" rx="68" ry="22" fill="#3a7233" />
                        
                        <!-- Lotus Outer Petals Layer 1 -->
                        <g fill="#e91e63" opacity="0.95">
                            <path d="M 30,135 Q 10,100 50,115 C 60,130 40,140 30,135 Z" />
                            <path d="M 170,135 Q 190,100 150,115 C 140,130 160,140 170,135 Z" />
                            <path d="M 50,150 Q 20,125 70,130 C 75,145 60,155 50,150 Z" />
                            <path d="M 150,150 Q 180,125 130,130 C 125,145 140,155 150,150 Z" />
                        </g>
                        <!-- Inner Pink Lotus Petals -->
                        <g fill="#f48fb1">
                            <path d="M 40,125 Q 30,90 70,105 C 75,120 55,130 40,125 Z" />
                            <path d="M 160,125 Q 170,90 130,105 C 125,120 145,130 160,125 Z" />
                            <path d="M 70,158 Q 50,140 90,138 C 95,150 80,160 70,158 Z" />
                            <path d="M 130,158 Q 150,140 110,138 C 105,150 120,160 130,158 Z" />
                        </g>
                        <!-- Yellow Flower Crown Trim -->
                        <circle cx="100" cy="140" r="45" fill="none" stroke="#fbc02d" stroke-width="6" stroke-dasharray="8 4" />
                        <circle cx="100" cy="140" r="48" fill="none" stroke="#f57f17" stroke-width="2" />
                    </svg>
                </div>

            </div>
        </div>

        <!-- ACTION BUTTONS TOOLBAR AT BOTTOM -->
        <div class="relative z-30 max-w-lg mx-auto w-full px-4 mb-6 flex flex-col sm:flex-row items-center justify-center gap-3">
            
            <!-- Save Changes Button -->
            <button id="saveBtn" onclick="saveKrathongData()" class="w-full sm:w-1/2 py-3.5 px-5 rounded-2xl bg-slate-800/90 hover:bg-slate-700 border border-amber-500/40 text-amber-300 font-semibold text-sm shadow-xl flex items-center justify-center gap-2 transition-all active:scale-95">
                <i class="fas fa-cloud-arrow-up text-amber-400"></i>
                <span>ບັນທຶກການປ່ຽນແປງ</span>
            </button>

            <!-- Release Krathong Button -->
            <button id="releaseBtn" onclick="releaseKrathong()" class="w-full sm:w-1/2 py-3.5 px-5 rounded-2xl bg-gradient-to-r from-amber-500 via-yellow-500 to-amber-600 hover:from-amber-400 hover:to-yellow-500 text-slate-950 font-bold text-sm shadow-xl shadow-amber-500/25 flex items-center justify-center gap-2 transition-all transform hover:scale-105 active:scale-95">
                <i class="fas fa-paper-plane text-slate-900"></i>
                <span>ປ່ອຍກະທົງ 🌸</span>
            </button>
            
        </div>

    </main>

    <!-- FOOTER / CREDIT -->
    <footer class="relative z-30 py-2.5 text-center text-xs text-amber-200/50 bg-black/60 backdrop-blur-sm border-t border-amber-500/10">
        <p>🎉 ສຸກສັນວັນລອຍກະທົງ | ລອຍຄວາມທຸກໂສກ ຕ້ອນຮັບຄວາມຮັກ ແລະ ຄວາມສຸກ 💛</p>
    </footer>

    <!-- ========================================================= -->
    <!-- CUSTOMIZATION & EDIT MODAL (POPUP) -->
    <!-- ========================================================= -->
    <div id="customizerModal" class="fixed inset-0 z-50 flex items-center justify-center bg-black/80 backdrop-blur-md p-4 opacity-0 pointer-events-none transition-all duration-300">
        <div class="relative w-full max-w-xl bg-slate-900 border border-amber-500/40 rounded-3xl p-5 sm:p-7 shadow-2xl overflow-y-auto max-h-[90vh] glow-box">
            
            <!-- Close Modal Button -->
            <button onclick="closeCustomizerModal()" class="absolute top-4 right-4 w-9 h-9 rounded-full bg-slate-800 text-amber-400 hover:bg-amber-500 hover:text-slate-950 transition-all flex items-center justify-center">
                <i class="fas fa-times text-lg"></i>
            </button>

            <h2 class="text-xl sm:text-2xl font-bold text-amber-300 mb-1 flex items-center gap-2">
                <span>🌸 ແຕ່ງກະທົງ & ໃສ່ຄຳອະທິຖານ</span>
            </h2>
            <p class="text-xs text-slate-400 mb-6">ປັບແຕ່ງຮູບພາບ, ຂໍ້ຄວາມອະທິຖານ ແລະ ຮູບແບບກະທົງຂອງທ່ານ</p>

            <form id="krathongForm" onsubmit="event.preventDefault(); applyCustomizations();" class="space-y-6">
                
                <!-- 1. PHOTOS & NAMES SECTION -->
                <div class="bg-slate-800/60 p-4 rounded-2xl border border-slate-700 space-y-4">
                    <h3 class="text-sm font-semibold text-amber-400 flex items-center gap-2">
                        <i class="fas fa-user-friends"></i> ຂໍ້ມູນຄູ່ຮັກ (ຮູບ ແລະ ຊື່)
                    </h3>
                    
                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                        <!-- Person 1 Inputs -->
                        <div class="space-y-2 bg-slate-900/50 p-3 rounded-xl border border-slate-700/60">
                            <label class="block text-xs text-amber-200 font-medium">ຄົນທີ 1 (ເຈົ້າ)</label>
                            <input type="text" id="inputNameP1" value="ເຈົ້າ" placeholder="ໃສ່ຊື່..." class="w-full px-3 py-2 bg-slate-800 border border-slate-600 rounded-lg text-xs text-white focus:outline-none focus:border-amber-400">
                            
                            <!-- Image Upload / Choice -->
                            <div class="flex items-center gap-2 pt-1">
                                <label class="cursor-pointer px-3 py-1.5 bg-slate-700 hover:bg-slate-600 rounded-lg text-xs text-amber-300 font-medium flex items-center gap-1.5">
                                    <i class="fas fa-camera"></i>
                                    <span>ເລືອກຮູບ</span>
                                    <input type="file" accept="image/*" class="hidden" onchange="handleImageUpload(event, 'P1')">
                                </label>
                                <span class="text-[10px] text-slate-400">ຫຼື ຮູບເລີ່ມຕົ້ນ</span>
                            </div>
                        </div>

                        <!-- Person 2 Inputs -->
                        <div class="space-y-2 bg-slate-900/50 p-3 rounded-xl border border-slate-700/60">
                            <label class="block text-xs text-pink-300 font-medium">ຄົນທີ 2 (ຄູ່ຮັກ)</label>
                            <input type="text" id="inputNameP2" value="ຄູ່ຮັກ" placeholder="ໃສ່ຊື່..." class="w-full px-3 py-2 bg-slate-800 border border-slate-600 rounded-lg text-xs text-white focus:outline-none focus:border-pink-400">
                            
                            <!-- Image Upload / Choice -->
                            <div class="flex items-center gap-2 pt-1">
                                <label class="cursor-pointer px-3 py-1.5 bg-slate-700 hover:bg-slate-600 rounded-lg text-xs text-pink-300 font-medium flex items-center gap-1.5">
                                    <i class="fas fa-camera"></i>
                                    <span>ເລືອກຮູບ</span>
                                    <input type="file" accept="image/*" class="hidden" onchange="handleImageUpload(event, 'P2')">
                                </label>
                                <span class="text-[10px] text-slate-400">ຫຼື ຮູບເລີ່ມຕົ້ນ</span>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- 2. WISHES / VOWS SECTION -->
                <div class="bg-slate-800/60 p-4 rounded-2xl border border-slate-700 space-y-3">
                    <h3 class="text-sm font-semibold text-amber-400 flex items-center gap-2">
                        <i class="fas fa-scroll"></i> ຂໍ້ຄວາມອະທິຖານ (Wish / Vows)
                    </h3>

                    <div>
                        <label class="block text-xs text-amber-300 mb-1">ຄຳອະທິຖານຈາກ ຄົນທີ 1:</label>
                        <textarea id="inputWishP1" rows="2" class="w-full px-3 py-2 bg-slate-900 border border-slate-700 rounded-xl text-xs text-slate-100 focus:outline-none focus:border-amber-400" placeholder="ພິມຄຳອະທິຖານຂອງທ່ານ..."></textarea>
                    </div>

                    <div>
                        <label class="block text-xs text-pink-300 mb-1">ຄຳອະທິຖານຈາກ ຄົນທີ 2:</label>
                        <textarea id="inputWishP2" rows="2" class="w-full px-3 py-2 bg-slate-900 border border-slate-700 rounded-xl text-xs text-slate-100 focus:outline-none focus:border-pink-400" placeholder="ພິມຄຳອະທິຖານຂອງຄູ່ຮັກ..."></textarea>
                    </div>
                </div>

                <!-- 3. KRATHONG STYLE SELECTION -->
                <div class="bg-slate-800/60 p-4 rounded-2xl border border-slate-700 space-y-3">
                    <h3 class="text-sm font-semibold text-amber-400 flex items-center gap-2">
                        <i class="fas fa-palette"></i> ເລືອກຮູບແບບກະທົງ
                    </h3>

                    <div class="grid grid-cols-3 gap-3">
                        <!-- Option 1: Lotus -->
                        <label class="cursor-pointer border-2 border-amber-500 bg-slate-900 p-2.5 rounded-xl text-center space-y-1 hover:border-amber-400 transition-all style-option" id="styleOpt-lotus">
                            <input type="radio" name="krathongStyle" value="lotus" checked class="hidden" onchange="selectKrathongStyle('lotus')">
                            <div class="text-2xl">🪷</div>
                            <div class="text-xs font-semibold text-amber-200">ກະທົງດອກບົວ</div>
                        </label>

                        <!-- Option 2: Banana Leaf -->
                        <label class="cursor-pointer border-2 border-slate-700 bg-slate-900 p-2.5 rounded-xl text-center space-y-1 hover:border-amber-400 transition-all style-option" id="styleOpt-banana">
                            <input type="radio" name="krathongStyle" value="banana" class="hidden" onchange="selectKrathongStyle('banana')">
                            <div class="text-2xl">🍃</div>
                            <div class="text-xs font-semibold text-slate-300">ກະທົງໃບຕອງ</div>
                        </label>

                        <!-- Option 3: Royal Floral -->
                        <label class="cursor-pointer border-2 border-slate-700 bg-slate-900 p-2.5 rounded-xl text-center space-y-1 hover:border-amber-400 transition-all style-option" id="styleOpt-royal">
                            <input type="radio" name="krathongStyle" value="royal" class="hidden" onchange="selectKrathongStyle('royal')">
                            <div class="text-2xl">🌺</div>
                            <div class="text-xs font-semibold text-slate-300">ກະທົງມາໄລດອກໄມ້</div>
                        </label>
                    </div>
                </div>

                <!-- Submit Button -->
                <button type="submit" class="w-full py-3.5 bg-gradient-to-r from-amber-500 to-yellow-500 text-slate-950 font-bold rounded-2xl shadow-xl hover:from-amber-400 hover:to-yellow-400 transition-all text-sm">
                    ຕົກລົງ / ນຳໃຊ້ຂໍ້ມູນ 
                </button>
            </form>
        </div>
    </div>

    <!-- TOAST NOTIFICATION MESSAGE -->
    <div id="toastMessage" class="fixed top-20 left-1/2 -translate-x-1/2 z-50 bg-slate-900/95 border border-amber-500/60 text-amber-200 px-5 py-2.5 rounded-full shadow-2xl text-xs sm:text-sm font-medium flex items-center gap-2 transition-all duration-300 opacity-0 pointer-events-none transform -translate-y-4">
        <i class="fas fa-check-circle text-emerald-400"></i>
        <span id="toastText">ບັນທຶກຂໍ້ມູນສຳເລັດ!</span>
    </div>

    <!-- FIREBASE INITIALIZATION & LOGIC SCRIPT -->
    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
        import { getAuth, signInAnonymously, signInWithCustomToken, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
        import { getFirestore, doc, setDoc, onSnapshot } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";

        // APP STATE & CONFIG
        const appId = typeof __app_id !== 'undefined' ? __app_id : 'loy-krathong-couples-app';
        let db = null;
        let auth = null;
        let currentUser = null;

        // Default State Data
        window.krathongData = {
            p1Name: "ເຈົ້າ",
            p1Wish: "ຂໍໃຫ້ຄວາມຮັກຂອງເຮົາຍືນຍາວດັ່ງສາຍນ້ຳ ແລະ ມີຄວາມສຸກຕະຫຼອດໄປ...",
            p1Img: "https://images.unsplash.com/photo-1534528741775-53994a69daeb?w=150&auto=format&fit=crop&q=80",
            p2Name: "ຄູ່ຮັກ",
            p2Wish: "ຂໍໃຫ້ເຮົາຢູ່ຄຽງຂ້າງກັນຕະຫຼອດໄປ ບໍ່ມີອຸປະສັກໃດໆມາຂັດຂວາງ...",
            p2Img: "https://images.unsplash.com/photo-1507003211169-0a1dd7228f2d?w=150&auto=format&fit=crop&q=80",
            style: "lotus",
            released: false,
            updatedAt: Date.now()
        };

        // Firebase Setup & Auth Flow
        async function initFirebase() {
            try {
                if (typeof __firebase_config !== 'undefined') {
                    const firebaseConfig = JSON.parse(__firebase_config);
                    const app = initializeApp(firebaseConfig);
                    auth = getAuth(app);
                    db = getFirestore(app);

                    // Auth Handling
                    if (typeof __initial_auth_token !== 'undefined' && __initial_auth_token) {
                        await signInWithCustomToken(auth, __initial_auth_token);
                    } else {
                        await signInAnonymously(auth);
                    }

                    onAuthStateChanged(auth, (user) => {
                        if (user) {
                            currentUser = user;
                            document.getElementById('syncBadge').classList.remove('hidden');
                            setupRealtimeSync();
                        }
                    });
                }
            } catch (err) {
                console.log("Running in offline mode without Firebase sync:", err);
            }
        }

        // Realtime Listener
        function setupRealtimeSync() {
            if (!db || !currentUser) return;
            const docRef = doc(db, 'artifacts', appId, 'public', 'data', 'shared_krathong');

            onSnapshot(docRef, (docSnap) => {
                if (docSnap.exists()) {
                    const data = docSnap.data();
                    if (data) {
                        window.krathongData = { ...window.krathongData, ...data };
                        updateUIFromData();
                    }
                }
            }, (error) => {
                console.warn("Firestore Snapshot error:", error);
            });
        }

        // Save Function
        window.saveKrathongDataToCloud = async function() {
            if (!db || !currentUser) {
                showToast("ບັນທຶກໄວ້ໃນເຄື່ອງສຳເລັດ! (ອອບໄລນ໌)");
                return;
            }

            try {
                const docRef = doc(db, 'artifacts', appId, 'public', 'data', 'shared_krathong');
                window.krathongData.updatedAt = Date.now();
                await setDoc(docRef, window.krathongData, { merge: true });
                showToast("ບັນທຶກການປ່ຽນແປງໄປຍັງຄູ່ຮັກສຳເລັດ! ✨");
            } catch (err) {
                console.error("Error saving data:", err);
                showToast("ເກີດຂໍ້ຜິດພາດໃນການບັນທຶກ");
            }
        };

        // Initialize Firebase on window load
        window.addEventListener('DOMContentLoaded', () => {
            initFirebase();
            updateUIFromData();
            spawnLanterns();
        });
    </script>

    <!-- CORE JS INTERACTION & ANIMATION SCRIPT -->
    <script>
        let isBgmPlaying = false;
        let audioCtx = null;
        let bgmOsc = null;

        // Toggle Wish Scroll Visibility
        function toggleWishBubble() {
            const bubble = document.getElementById('wishDisplayBubble');
            if (bubble.classList.contains('opacity-0')) {
                bubble.classList.remove('opacity-0', 'scale-90', 'pointer-events-none');
                bubble.classList.add('opacity-100', 'scale-100', 'pointer-events-auto');
            } else {
                bubble.classList.add('opacity-0', 'scale-90', 'pointer-events-none');
                bubble.classList.remove('opacity-100', 'scale-100', 'pointer-events-auto');
            }
        }

        // Toast Helper
        function showToast(text) {
            const toast = document.getElementById('toastMessage');
            document.getElementById('toastText').innerText = text;
            toast.classList.remove('opacity-0', '-translate-y-4', 'pointer-events-none');
            toast.classList.add('opacity-100', 'translate-y-0');

            setTimeout(() => {
                toast.classList.add('opacity-0', '-translate-y-4', 'pointer-events-none');
                toast.classList.remove('opacity-100', 'translate-y-0');
            }, 3000);
        }

        // Modal Controls
        function openCustomizerModal() {
            const modal = document.getElementById('customizerModal');
            
            // Populate form inputs
            document.getElementById('inputNameP1').value = window.krathongData.p1Name;
            document.getElementById('inputNameP2').value = window.krathongData.p2Name;
            document.getElementById('inputWishP1').value = window.krathongData.p1Wish;
            document.getElementById('inputWishP2').value = window.krathongData.p2Wish;
            selectKrathongStyle(window.krathongData.style);

            modal.classList.remove('opacity-0', 'pointer-events-none');
            modal.classList.add('opacity-100', 'pointer-events-auto');
        }

        function closeCustomizerModal() {
            const modal = document.getElementById('customizerModal');
            modal.classList.add('opacity-0', 'pointer-events-none');
            modal.classList.remove('opacity-100', 'pointer-events-auto');
        }

        // Handle Image Upload
        function handleImageUpload(event, person) {
            const file = event.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    if (person === 'P1') window.krathongData.p1Img = e.target.result;
                    if (person === 'P2') window.krathongData.p2Img = e.target.result;
                    updateUIFromData();
                };
                reader.readAsDataURL(file);
            }
        }

        // Select Style Radio Handler
        function selectKrathongStyle(styleName) {
            window.krathongData.style = styleName;
            ['lotus', 'banana', 'royal'].forEach(s => {
                const opt = document.getElementById(`styleOpt-${s}`);
                if (opt) {
                    if (s === styleName) {
                        opt.classList.add('border-amber-500', 'bg-slate-800');
                        opt.classList.remove('border-slate-700', 'bg-slate-900');
                    } else {
                        opt.classList.remove('border-amber-500', 'bg-slate-800');
                        opt.classList.add('border-slate-700', 'bg-slate-900');
                    }
                }
            });
        }

        // Apply Customizations from Modal
        function applyCustomizations() {
            window.krathongData.p1Name = document.getElementById('inputNameP1').value || "ເຈົ້າ";
            window.krathongData.p2Name = document.getElementById('inputNameP2').value || "ຄູ່ຮັກ";
            window.krathongData.p1Wish = document.getElementById('inputWishP1').value || "...";
            window.krathongData.p2Wish = document.getElementById('inputWishP2').value || "...";

            updateUIFromData();
            closeCustomizerModal();
            showToast("ອັບເດດຮູບແບບກະທົງແລ້ວ!");
        }

        // Update UI Elements with State Data
        function updateUIFromData() {
            const data = window.krathongData;

            // Photos
            document.getElementById('imgP1').src = data.p1Img;
            document.getElementById('imgP2').src = data.p2Img;

            // Badges & Names
            document.getElementById('badgeP1').innerText = data.p1Name;
            document.getElementById('badgeP2').innerText = data.p2Name;

            // Wishes Text
            document.getElementById('displayWishP1').innerHTML = `<span class="text-amber-300 font-semibold">${data.p1Name}:</span> "${data.p1Wish}"`;
            document.getElementById('displayWishP2').innerHTML = `<span class="text-pink-300 font-semibold">${data.p2Name}:</span> "${data.p2Wish}"`;

            // Render Krathong SVG Style
            renderKrathongSVG(data.style);
        }

        // Render Krathong Base SVG
        function renderKrathongSVG(style) {
            const svgContainer = document.getElementById('krathongBaseSVG');

            if (style === 'banana') {
                // Banana Leaf Traditional
                svgContainer.innerHTML = `
                <svg viewBox="0 0 200 200" class="w-full h-full drop-shadow-2xl">
                    <ellipse cx="100" cy="145" rx="72" ry="26" fill="#1b3818" />
                    <ellipse cx="100" cy="140" rx="70" ry="24" fill="#2d5a27" />
                    <!-- Folded Banana Leaves -->
                    <g fill="#43a047" stroke="#1b5e20" stroke-width="1.5">
                        <polygon points="30,135 15,110 45,120" />
                        <polygon points="170,135 185,110 155,120" />
                        <polygon points="50,150 30,130 65,135" />
                        <polygon points="150,150 170,130 135,135" />
                        <polygon points="80,162 60,145 95,148" />
                        <polygon points="120,162 140,145 105,148" />
                    </g>
                    <!-- Yellow Marigold Trim -->
                    <circle cx="100" cy="140" r="46" fill="none" stroke="#fbc02d" stroke-width="8" stroke-dasharray="10 5" />
                </svg>`;
            } else if (style === 'royal') {
                // Royal Floral Garland Style
                svgContainer.innerHTML = `
                <svg viewBox="0 0 200 200" class="w-full h-full drop-shadow-2xl">
                    <ellipse cx="100" cy="145" rx="72" ry="26" fill="#4a148c" />
                    <ellipse cx="100" cy="140" rx="70" ry="24" fill="#6a1b9a" />
                    <!-- Orchid/Floral Layer -->
                    <g fill="#ab47bc" opacity="0.9">
                        <circle cx="35" cy="130" r="14" />
                        <circle cx="165" cy="130" r="14" />
                        <circle cx="55" cy="150" r="15" />
                        <circle cx="145" cy="150" r="15" />
                        <circle cx="85" cy="160" r="16" />
                        <circle cx="115" cy="160" r="16" />
                    </g>
                    <g fill="#e1bee7">
                        <circle cx="35" cy="130" r="7" />
                        <circle cx="165" cy="130" r="7" />
                        <circle cx="55" cy="150" r="8" />
                        <circle cx="145" cy="150" r="8" />
                        <circle cx="85" cy="160" r="8" />
                        <circle cx="115" cy="160" r="8" />
                    </g>
                    <!-- Golden Crown Trim -->
                    <circle cx="100" cy="140" r="45" fill="none" stroke="#ffd54f" stroke-width="6" stroke-dasharray="6 3" />
                </svg>`;
            } else {
                // Default Pink Lotus
                svgContainer.innerHTML = `
                <svg viewBox="0 0 200 200" class="w-full h-full drop-shadow-2xl">
                    <ellipse cx="100" cy="145" rx="70" ry="25" fill="#2d5a27" stroke="#1b3818" stroke-width="3" />
                    <ellipse cx="100" cy="140" rx="68" ry="22" fill="#3a7233" />
                    <g fill="#e91e63" opacity="0.95">
                        <path d="M 30,135 Q 10,100 50,115 C 60,130 40,140 30,135 Z" />
                        <path d="M 170,135 Q 190,100 150,115 C 140,130 160,140 170,135 Z" />
                        <path d="M 50,150 Q 20,125 70,130 C 75,145 60,155 50,150 Z" />
                        <path d="M 150,150 Q 180,125 130,130 C 125,145 140,155 150,150 Z" />
                    </g>
                    <g fill="#f48fb1">
                        <path d="M 40,125 Q 30,90 70,105 C 75,120 55,130 40,125 Z" />
                        <path d="M 160,125 Q 170,90 130,105 C 125,120 145,130 160,125 Z" />
                        <path d="M 70,158 Q 50,140 90,138 C 95,150 80,160 70,158 Z" />
                        <path d="M 130,158 Q 150,140 110,138 C 105,150 120,160 130,158 Z" />
                    </g>
                    <circle cx="100" cy="140" r="45" fill="none" stroke="#fbc02d" stroke-width="6" stroke-dasharray="8 4" />
                </svg>`;
            }
        }

        // Save Button Click Handler
        function saveKrathongData() {
            if (window.saveKrathongDataToCloud) {
                window.saveKrathongDataToCloud();
            } else {
                showToast("ບັນທຶກຂໍ້ມູນສຳເລັດ!");
            }
        }

        // RELEASE KRATHONG ANIMATION
        function releaseKrathong() {
            const heroWrapper = document.getElementById('heroKrathongWrapper');
            const releaseBtn = document.getElementById('releaseBtn');

            // Disable button during animation
            releaseBtn.disabled = true;
            releaseBtn.classList.add('opacity-50');

            // Confetti effect
            if (window.confetti) {
                confetti({
                    particleCount: 70,
                    spread: 60,
                    origin: { y: 0.7 },
                    colors: ['#F39C12', '#E91E63', '#FFD54F', '#4CAF50']
                });
            }

            // Animate Hero Krathong Drifting Away
            heroWrapper.style.transition = 'all 7s cubic-bezier(0.25, 1, 0.5, 1)';
            heroWrapper.style.transform = 'translateY(-220px) scale(0.35)';
            heroWrapper.style.opacity = '0.35';

            showToast("ກະທົງຂອງທ່ານຖືກປ່ອຍລອຍໄປຕາມສາຍນ້ຳແລ້ວ! 🌸✨");

            // Add floating clone copy to released stream
            setTimeout(() => {
                addReleasedCloneToStream();

                // Reset Hero Krathong position slowly
                setTimeout(() => {
                    heroWrapper.style.transition = 'none';
                    heroWrapper.style.transform = 'translateY(0px) scale(1)';
                    heroWrapper.style.opacity = '1';

                    releaseBtn.disabled = false;
                    releaseBtn.classList.remove('opacity-50');
                }, 1000);
            }, 6500);
        }

        // Add Floating Background Krathong Clones
        function addReleasedCloneToStream() {
            const stream = document.getElementById('releasedStream');
            const clone = document.createElement('div');
            
            const startLeft = Math.random() * 70 + 10;
            const size = Math.random() * 40 + 40;

            clone.className = 'absolute bottom-10 transition-all duration-[25s] linear opacity-80';
            clone.style.left = `${startLeft}%`;
            clone.style.width = `${size}px`;
            clone.style.height = `${size}px`;

            clone.innerHTML = `
                <div class="relative w-full h-full flex flex-col items-center justify-center">
                    <div class="w-1.5 h-3 bg-amber-300 rounded-full animate-ping"></div>
                    <span class="text-2xl">🪷</span>
                </div>
            `;

            stream.appendChild(clone);

            // Animate drifting down & shrinking
            requestAnimationFrame(() => {
                clone.style.transform = `translateY(-350px) translateX(${Math.random() * 100 - 50}px) scale(0.2)`;
                clone.style.opacity = '0.1';
            });

            setTimeout(() => {
                clone.remove();
            }, 25000);
        }

        // SPAWN SKY LANTERNS IN BACKGROUND
        function spawnLanterns() {
            const container = document.getElementById('skyLanternsContainer');
            const lanternCount = 12;

            for (let i = 0; i < lanternCount; i++) {
                const lantern = document.createElement('div');
                lantern.className = 'sky-lantern flex flex-col items-center';
                
                const leftPos = Math.random() * 100;
                const duration = Math.random() * 15 + 15;
                const delay = Math.random() * 12;

                lantern.style.left = `${leftPos}%`;
                lantern.style.animationDuration = `${duration}s`;
                lantern.style.animationDelay = `${delay}s`;

                lantern.innerHTML = `
                    <div class="w-4 h-6 sm:w-6 sm:h-8 bg-gradient-to-t from-amber-500 via-yellow-300 to-amber-200 rounded-t-lg rounded-b-sm shadow-lg shadow-amber-400/50 opacity-90 flex items-end justify-center pb-0.5">
                        <div class="w-1.5 h-1.5 bg-white rounded-full animate-pulse"></div>
                    </div>
                `;

                container.appendChild(lantern);
            }
        }

        // SYNTHESIZED ROMANTIC AMBIENT SOUND (Web Audio API)
        function toggleBGM() {
            const statusText = document.getElementById('bgmStatusText');
            const icon = document.getElementById('bgmIcon');

            if (!isBgmPlaying) {
                playAmbientSynth();
                isBgmPlaying = true;
                statusText.innerText = "ປິດເພງ";
                icon.className = "fas fa-volume-up text-amber-400 animate-pulse";
            } else {
                stopAmbientSynth();
                isBgmPlaying = false;
                statusText.innerText = "ເປີດເພງ";
                icon.className = "fas fa-music text-amber-400";
            }
        }

        function playAmbientSynth() {
            try {
                if (!audioCtx) {
                    audioCtx = new (window.AudioContext || window.webkitAudioContext)();
                }

                bgmOsc = audioCtx.createOscillator();
                const gainNode = audioCtx.createGain();

                bgmOsc.type = 'sine';
                bgmOsc.frequency.setValueAtTime(220, audioCtx.currentTime); // Soft A3 pitch
                
                // Low volume gentle chime/drone
                gainNode.gain.setValueAtTime(0.03, audioCtx.currentTime);

                bgmOsc.connect(gainNode);
                gainNode.connect(audioCtx.destination);
                bgmOsc.start();
            } catch (e) {
                console.log("Audio play blocked or unsupported", e);
            }
        }

        function stopAmbientSynth() {
            if (bgmOsc) {
                bgmOsc.stop();
                bgmOsc.disconnect();
            }
        }
    </script>
</body>
</html>
