
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Smart WiFi Optimization System - Interface Prototype</title>
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
</head>
<body class="bg-[#0b0f19] text-slate-100 font-sans antialiased min-h-screen flex flex-col justify-center items-center p-4 md:p-8">

    <!-- Interactive Workspace Container -->
    <div class="w-full max-w-4xl bg-[#131a2e] rounded-3xl p-6 md:p-8 border border-slate-800 shadow-2xl">
        <div class="grid md:grid-cols-12 gap-8 items-center">
            
            <!-- COLUMN 1: SMARTPHONE MOCKUP SCREEN DISPLAY (5 Columns) -->
            <div class="md:col-span-5 flex justify-center">
                <!-- Outer Phone Frame -->
                <div class="w-[290px] h-[570px] bg-[#070a13] rounded-[40px] border-[6px] border-blue-600 shadow-[0_0_35px_rgba(37,99,235,0.25)] relative p-3 flex flex-col justify-between overflow-hidden">
                    
                    <!-- Dynamic Top Status Bar & Notch -->
                    <div class="absolute top-0 inset-x-0 h-6 bg-[#070a13] z-30 flex justify-between items-center px-6 text-[10px] font-mono text-slate-400">
                        <span>9:41</span>
                        <div class="w-20 h-4 bg-black rounded-b-xl absolute left-1/2 -translate-x-1/2 top-0"></div>
                        <div class="flex items-center space-x-1">
                            <i class="fa-solid fa-signal"></i>
                            <i class="fa-solid fa-wifi text-blue-400"></i>
                            <i class="fa-solid fa-battery-three-quarters"></i>
                        </div>
                    </div>
                    
                    <!-- App Interactive Interface Port -->
                    <div id="interface-viewport" class="h-full flex flex-col justify-between pt-6 pb-1 transition-all duration-200">
                        
                        <!-- DEFAULT INTERFACE: SCREEN 1 (Automated Optimization) -->
                        <div class="flex flex-col justify-between h-full animate-fadeIn">
                            <div class="text-center mt-3">
                                <h4 class="font-bold text-sm tracking-wide text-slate-200"> Smart WiFi Optimization System</h4>
                                <p class="text-[9px] font-semibold text-blue-400 tracking-wider uppercase mt-0.5">
                                    <i class="fa-solid fa-building-columns mr-1"></i> Kolej Pendeta Za'ba (KPZ)
                                </p>
                            </div>
                            
                            <!-- Optimization Radial Progress Gauge -->
                            <div class="flex flex-col items-center justify-center my-auto">
                                <div class="relative w-36 h-36 flex items-center justify-center">
                                    <svg class="w-full h-full transform -rotate-90" viewBox="0 0 100 100">
                                        <circle cx="50" cy="50" r="42" stroke="#161f38" stroke-width="7" fill="transparent" />
                                        <circle cx="50" cy="50" r="42" stroke="#10b981" stroke-width="7" fill="transparent" stroke-dasharray="230 264" stroke-linecap="round" />
                                    </svg>
                                    <div class="absolute text-center">
                                        <span class="text-3xl font-black block text-white tracking-tighter">95%</span>
                                        <span class="text-[8px] text-emerald-400 font-bold tracking-widest uppercase">OPTIMIZED</span>
                                    </div>
                                </div>
                            </div>

                            <!-- Real-time Event Logger Card -->
                            <div class="space-y-3">
                                <div class="bg-[#161f38] p-3 rounded-xl text-[11px] border border-slate-800/60 shadow-inner">
                                    <div class="flex justify-between items-center mb-1">
                                        <span class="font-bold text-slate-300">Congestion Engine</span>
                                        <span class="inline-block w-2 h-2 rounded-full bg-emerald-500 animate-pulse"></span>
                                    </div>
                                    <p class="text-slate-400 leading-tight">Channel 11 interference detected from adjacent dorm rooms.</p>
                                    <div class="text-emerald-400 font-bold mt-1.5 flex items-center">
                                        <i class="fa-solid fa-shuffle mr-1.5 text-[10px]"></i> Auto-switched to Channel 1 (Clear)
                                    </div>
                                </div>
                                <button class="w-full bg-blue-600 active:scale-[0.98] text-white font-bold text-xs py-2.5 rounded-xl transition shadow-md tracking-wide">
                                    Force Recalibration
                                </button>
                            </div>
                        </div>

                    </div>
                </div>
            </div>

            <!-- COLUMN 2: INTERACTIVE BACKEND CONTROLLERS (7 Columns) -->
            <div class="md:col-span-7 space-y-4">
                <div class="mb-4">
                    <h2 class="text-xl font-bold text-white tracking-wide">System Mockup Controls</h2>
                    <p class="text-xs text-slate-400 mt-0.5">Click the functions below to change the application layout simulation live inside the smartphone view frame.</p>
                </div>

                <!-- Controller Button 1 -->
                <button onclick="renderMockup('screen1')" id="tab-screen1" class="w-full text-left p-4 rounded-xl bg-[#1c2641] border border-blue-500/60 transition-all flex items-center space-x-4 shadow-md">
                    <div class="w-10 h-10 rounded-lg bg-blue-600/10 flex items-center justify-center text-blue-400 font-bold"><i class="fa-solid fa-gauge-high"></i></div>
                    <div>
                        <h4 class="font-bold text-sm text-white">Screen 1: Automated Optimization</h4>
                        <p class="text-xs text-slate-400 mt-0.5">Simulates background detection and micro-channel switching tasks on student devices.</p>
                    </div>
                </button>

                <!-- Controller Button 2 -->
                <button onclick="renderMockup('screen2')" id="tab-screen2" class="w-full text-left p-4 rounded-xl bg-slate-900/30 border border-slate-800 hover:border-slate-700/60 transition-all flex items-center space-x-4">
                    <div class="w-10 h-10 rounded-lg bg-purple-600/10 flex items-center justify-center text-purple-400 font-bold"><i class="fa-solid fa-vr-cardboard"></i></div>
                    <div>
                        <h4 class="font-bold text-sm text-slate-400">Screen 2: AR Signal Boundary Guide</h4>
                        <p class="text-xs text-slate-400 mt-0.5">Demonstrates camera overlay scanning to pinpoint physical dead zones vs clear zones inside a hostel unit.</p>
                    </div>
                </button>

                <!-- Controller Button 3 -->
                <button onclick="renderMockup('screen3')" id="tab-screen3" class="w-full text-left p-4 rounded-xl bg-slate-900/30 border border-slate-800 hover:border-slate-700/60 transition-all flex items-center space-x-4">
                    <div class="w-10 h-10 rounded-lg bg-emerald-600/10 flex items-center justify-center text-emerald-400 font-bold"><i class="fa-solid fa-network-wired"></i></div>
                    <div>
                        <h4 class="font-bold text-sm text-slate-400">Screen 3: Campus Density Traffic Grid</h4>
                        <p class="text-xs text-slate-400 mt-0.5">Exhibits real-time crowdsourced congestion status maps across major student focal hubs (PTSL, Pusanika).</p>
                    </div>
                </button>
            </div>

        </div>
    </div>

    <!-- JavaScript to Handle Dynamic Mockup Rendering -->
    <script>
        function renderMockup(screenType) {
            const viewport = document.getElementById('interface-viewport');
            
            // Clean up all controller states
            ['screen1', 'screen2', 'screen3'].forEach(s => {
                const button = document.getElementById(`tab-${s}`);
                button.className = "w-full text-left p-4 rounded-xl bg-slate-900/30 border border-slate-800 hover:border-slate-700/60 transition-all flex items-center space-x-4";
                button.querySelector('h4').className = "font-bold text-sm text-slate-400";
            });

            // Apply selected controller styling
            const targetButton = document.getElementById(`tab-${screenType}`);
            if (screenType === 'screen1') {
                targetButton.className = "w-full text-left p-4 rounded-xl bg-[#1c2641] border border-blue-500/60 transition-all flex items-center space-x-4 shadow-md";
            } else if (screenType === 'screen2') {
                targetButton.className = "w-full text-left p-4 rounded-xl bg-[#1c2641] border border-purple-500/60 transition-all flex items-center space-x-4 shadow-md";
            } else if (screenType === 'screen3') {
                targetButton.className = "w-full text-left p-4 rounded-xl bg-[#1c2641] border border-emerald-500/60 transition-all flex items-center space-x-4 shadow-md";
            }
            targetButton.querySelector('h4').className = "font-bold text-sm text-white";

            // Inject Interface layouts directly without standard prose text wrappers
            if (screenType === 'screen1') {
                viewport.innerHTML = `
                    <div class="flex flex-col justify-between h-full animate-fadeIn">
                        <div class="text-center mt-3">
                            <h4 class="font-bold text-sm tracking-wide text-slate-200">WiFi Optimization System</h4>
                            <p class="text-[9px] font-semibold text-blue-400 tracking-wider uppercase mt-0.5">
                                <i class="fa-solid fa-building-columns mr-1"></i> Kolej Keris Mas (KKM)
                            </p>
                        </div>
                        <div class="flex flex-col items-center justify-center my-auto">
                            <div class="relative w-36 h-36 flex items-center justify-center">
                                <svg class="w-full h-full transform -rotate-90" viewBox="0 0 100 100">
                                    <circle cx="50" cy="50" r="42" stroke="#161f38" stroke-width="7" fill="transparent" />
                                    <circle cx="50" cy="50" r="42" stroke="#10b981" stroke-width="7" fill="transparent" stroke-dasharray="230 264" stroke-linecap="round" />
                                </svg>
                                <div class="absolute text-center">
                                    <span class="text-3xl font-black block text-white tracking-tighter">95%</span>
                                    <span class="text-[8px] text-emerald-400 font-bold tracking-widest uppercase">OPTIMIZED</span>
                                </div>
                            </div>
                        </div>
                        <div class="space-y-3">
                            <div class="bg-[#161f38] p-3 rounded-xl text-[11px] border border-slate-800/60 shadow-inner">
                                <div class="flex justify-between items-center mb-1">
                                    <span class="font-bold text-slate-300">Congestion Engine</span>
                                    <span class="inline-block w-2 h-2 rounded-full bg-emerald-500 animate-pulse"></span>
                                </div>
                                <p class="text-slate-400 leading-tight">Channel 11 interference detected from adjacent dorm rooms.</p>
                                <div class="text-emerald-400 font-bold mt-1.5 flex items-center">
                                    <i class="fa-solid fa-shuffle mr-1.5 text-[10px]"></i> Auto-switched to Channel 1 (Clear)
                                </div>
                            </div>
                            <button class="w-full bg-blue-600 text-white font-bold text-xs py-2.5 rounded-xl shadow-md tracking-wide">Force Recalibration</button>
                        </div>
                    </div>
                `;
            } else if (screenType === 'screen2') {
                viewport.innerHTML = `
                    <div class="flex flex-col justify-between h-full relative animate-fadeIn bg-slate-900 rounded-2xl overflow-hidden p-2 border border-slate-800">
                        <!-- Camera Viewport Guideline Mesh Overlay -->
                        <div class="absolute inset-0 opacity-10 bg-[linear-gradient(to_right,#f1f5f9_1px,transparent_1px),linear-gradient(to_bottom,#f1f5f9_1px,transparent_1px)] bg-[size:16px_16px]"></div>
                        
                        <div class="relative z-10 bg-black/60 backdrop-blur-sm p-1.5 rounded-lg text-center border border-purple-500/20 text-[9px]">
                            <p class="text-purple-400 font-bold"><i class="fa-solid fa-camera mr-1"></i> AR CALIBRATION HOUSING MODE</p>
                        </div>

                        <!-- AR Entity 1: Weak Zone Placement -->
                        <div class="absolute bottom-24 left-4 z-10 flex flex-col items-center">
                            <div class="w-16 h-16 rounded-full bg-red-500/20 border border-red-500/80 flex items-center justify-center relative text-center">
                                <span class="text-[8px] font-bold text-white tracking-wide leading-tight">RED ZONE<br><span class="text-red-300 text-[7px] font-normal">Blocked</span></span>
                            </div>
                        </div>

                        <!-- AR Entity 2: Optimal Zone Suggestion Placement -->
                        <div class="absolute top-24 right-4 z-10 flex flex-col items-center">
                            <div class="w-20 h-20 rounded-full bg-emerald-500/20 border border-emerald-500/80 flex items-center justify-center text-center px-1 relative">
                                <span class="text-[9px] font-bold text-white tracking-wide leading-tight">GREEN ZONE<br><span class="text-emerald-300 text-[7px] font-semibold">Optimal desk placement</span></span>
                                <div class="absolute -inset-1 rounded-full border border-emerald-400/40 animate-ping"></div>
                            </div>
                        </div>

                        <div class="relative z-10 bg-black/80 p-2 rounded-xl text-center text-[9px] border border-slate-800">
                            <p class="text-slate-300">Point at room structures to calibrate signal lines</p>
                        </div>
                    </div>
                `;
            } else if (screenType === 'screen3') {
                viewport.innerHTML = `
                    <div class="flex flex-col justify-between h-full animate-fadeIn">
                        <div class="text-center mt-3">
                            <h4 class="font-bold text-sm tracking-wide text-slate-200">Campus Density Index</h4>
                            <p class="text-[9px] font-bold text-emerald-400 tracking-wider uppercase mt-0.5">UKM INTERNAL WiFi SYNC</p>
                        </div>
                        
                        <!-- Simulated Real-time Metrics Stack -->
                        <div class="space-y-2 my-auto px-0.5">
                            <div class="bg-slate-900/90 p-2 rounded-xl border border-red-500/20 flex justify-between items-center text-[11px]">
                                <div>
                                    <p class="font-bold text-slate-200">Perpustakaan PTSL</p>
                                    <p class="text-[8px] text-slate-400">High node count saturated</p>
                                </div>
                                <span class="px-2 py-0.5 rounded bg-red-500/10 text-red-400 font-mono text-[8px] border border-red-500/20 font-bold">CONGESTED</span>
                            </div>

                            <div class="bg-slate-900/90 p-2 rounded-xl border border-yellow-500/20 flex justify-between items-center text-[11px]">
                                <div>
                                    <p class="font-bold text-slate-200">Pusanika Hub</p>
                                    <p class="text-[8px] text-slate-400">Moderate system loads</p>
                                </div>
                                <span class="px-2 py-0.5 rounded bg-yellow-500/10 text-yellow-400 font-mono text-[8px] border border-yellow-500/20 font-bold">MODERATE</span>
                            </div>

                            <div class="bg-slate-900/90 p-2 rounded-xl border border-emerald-500/20 flex justify-between items-center text-[11px]">
                                <div>
                                    <p class="font-bold text-slate-200">Fakulti (FTSM / FST)</p>
                                    <p class="text-[8px] text-slate-400">Clear channel bandwidth</p>
                                </div>
                                <span class="px-2 py-0.5 rounded bg-emerald-500/10 text-emerald-400 font-mono text-[8px] border border-emerald-500/20 font-bold">STABLE</span>
                            </div>
                        </div>

                        <div class="bg-[#161f38] p-2 rounded-xl text-center text-[9px] text-slate-400 border border-slate-800/60">
                            Metrics sourced directly via local active client nodes
                        </div>
                    </div>
                `;
            }
        }
    </script>

    <!-- UI Smooth Element Transition Injector Styles -->
    <style>
        @keyframes fadeIn {
            from { opacity: 0; transform: scale(0.98) translateY(2px); }
            to { opacity: 1; transform: scale(1) translateY(0); }
        }
        .animate-fadeIn {
            animation: fadeIn 0.2s ease-out forwards;
        }
    </style>
</body>
</html>
