
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Smart WiFi Optimization System - Live Prototype</title>
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @keyframes scan {
            0% { transform: translateY(0); }
            50% { transform: translateY(180px); }
            100% { transform: translateY(0); }
        }
        .animate-scan {
            animation: scan 4s linear infinite;
        }
        .pulse-slow {
            animation: pulse 3s cubic-bezier(0.4, 0, 0.6, 1) infinite;
        }
    </style>
</head>
<body class="bg-[#070a13] text-slate-100 font-sans antialiased min-h-screen flex flex-col justify-center items-center p-4">

    <div class="w-full max-w-4xl bg-[#111827] rounded-3xl p-6 md:p-8 border border-slate-800 shadow-2xl">
        <div class="grid md:grid-cols-12 gap-8 items-center">
            
            <div class="md:col-span-5 flex justify-center">
                <div class="w-[290px] h-[570px] bg-[#030712] rounded-[42px] border-[6px] border-slate-800 shadow-[0_0_40px_rgba(37,99,235,0.15)] relative p-3 flex flex-col justify-between overflow-hidden group">
                    
                    <div class="absolute top-0 inset-x-0 h-6 bg-[#030712] z-40 flex justify-between items-center px-6 text-[9px] font-mono text-slate-400 pointer-events-none">
                        <span>9:41</span>
                        <div class="w-24 h-4 bg-black rounded-b-xl absolute left-1/2 -translate-x-1/2 top-0"></div>
                        <div class="flex items-center space-x-1">
                            <i class="fa-solid fa-signal"></i>
                            <i class="fa-solid fa-wifi text-blue-400"></i>
                            <i class="fa-solid fa-battery-three-quarters"></i>
                        </div>
                    </div>
                    
                    <div id="phone-screen" class="h-full flex flex-col justify-between pt-6 pb-8 transition-all duration-300">
                        <div id="screen-content" class="flex flex-col justify-between h-full">
                            
                            <div class="text-center mt-3">
                                <h4 class="font-bold text-xs tracking-wider text-slate-200">WiFi Optimizer</h4>
                                <p class="text-[9px] font-semibold text-blue-400 tracking-wider uppercase mt-0.5">
                                    <i class="fa-solid fa-building-columns mr-1"></i> Kolej Pendeta Za'ba (KPZ)
                                </p>
                            </div>
                            
                            <div class="flex flex-col items-center justify-center my-auto relative">
                                <div id="radial-container" class="relative w-36 h-36 flex items-center justify-center cursor-pointer active:scale-95 transition-transform duration-150" onclick="triggerOptimization()">
                                    <svg class="w-full h-full transform -rotate-90" viewBox="0 0 100 100">
                                        <circle cx="50" cy="50" r="42" stroke="#1f2937" stroke-width="6" fill="transparent" />
                                        <circle id="progress-bar" cx="50" cy="50" r="42" stroke="#10b981" stroke-width="6" fill="transparent" stroke-dasharray="230 264" stroke-linecap="round" class="transition-all duration-1000" />
                                    </svg>
                                    <div class="absolute text-center select-none">
                                        <span id="gauge-percent" class="text-3xl font-black block text-white tracking-tighter">95%</span>
                                        <span id="gauge-status" class="text-[8px] text-emerald-400 font-bold tracking-widest uppercase">OPTIMIZED</span>
                                    </div>
                                </div>
                                <p class="text-[9px] text-slate-500 mt-2 pointer-events-none animate-pulse">👇 Tap circle to recalibrate</p>
                            </div>

                            <div class="space-y-2">
                                <div id="log-card" class="bg-slate-900/90 p-3 rounded-xl text-[11px] border border-slate-800 shadow-inner min-h-[75px] flex flex-col justify-center">
                                    <div class="flex justify-between items-center mb-0.5">
                                        <span class="font-bold text-slate-300">Channel Monitor</span>
                                        <span id="log-status-dot" class="inline-block w-1.5 h-1.5 rounded-full bg-emerald-500"></span>
                                    </div>
                                    <p id="log-text" class="text-slate-400 text-[10px] leading-tight">System managing micro-channels dynamically. Line clear.</p>
                                </div>
                                
                                <div class="grid grid-cols-2 gap-1.5 pt-1">
                                    <button onclick="changeAppTab('ar')" class="bg-slate-900 border border-slate-800 hover:bg-slate-800 active:scale-95 transition text-[10px] py-1.5 rounded-lg text-slate-300 font-medium">
                                        <i class="fa-solid fa-camera mr-1 text-purple-400"></i> AR View
                                    </button>
                                    <button onclick="changeAppTab('map')" class="bg-slate-900 border border-slate-800 hover:bg-slate-800 active:scale-95 transition text-[10px] py-1.5 rounded-lg text-slate-300 font-medium">
                                        <i class="fa-solid fa-map-location-dot mr-1 text-emerald-400"></i> Density Map
                                    </button>
                                </div>
                            </div>

                        </div>
                    </div>
                </div>
            </div>

            <div class="md:col-span-7 space-y-4">
                <div class="mb-2">
                    <span class="text-[10px] font-bold tracking-widest text-blue-500 bg-blue-500/10 px-2.5 py-1 rounded-md border border-blue-500/20 uppercase">Interactive Pitch Module</span>
                    <h2 class="text-xl font-bold text-white tracking-wide mt-2">UKM WiFi Optimization Deck</h2>
                    <p class="text-xs text-slate-400 mt-0.5">Test real-time operations directly on the viewport device profile container framework layout.</p>
                </div>

                <button onclick="changeAppTab('dashboard')" id="deck-tab-dashboard" class="w-full text-left p-4 rounded-xl bg-slate-800/80 border border-blue-500/40 transition-all flex items-center space-x-4 shadow-md">
                    <div class="w-9 h-9 rounded-lg bg-blue-600/10 flex items-center justify-center text-blue-400 font-bold text-sm"><i class="fa-solid fa-gauge-high"></i></div>
                    <div>
                        <h4 class="font-bold text-xs text-white">Module 1: Channel Calibration Dashboard</h4>
                        <p class="text-[11px] text-slate-400 mt-0.5">Simulates automatic hardware configuration background actions inside dormitory environments.</p>
                    </div>
                </button>

                <button onclick="changeAppTab('ar')" id="deck-tab-ar" class="w-full text-left p-4 rounded-xl bg-slate-900/40 border border-slate-800 hover:border-slate-700/50 transition-all flex items-center space-x-4">
                    <div class="w-9 h-9 rounded-lg bg-purple-600/10 flex items-center justify-center text-purple-400 font-bold text-sm"><i class="fa-solid fa-vr-cardboard"></i></div>
                    <div>
                        <h4 class="font-bold text-xs text-slate-400">Module 2: AR Signal Boundary Layout</h4>
                        <p class="text-[11px] text-slate-400 mt-0.5">Triggers simulated smartphone camera tracking lines over spatial unit vectors to avoid dead zones.</p>
                    </div>
                </button>

                <button onclick="changeAppTab('map')" id="deck-tab-map" class="w-full text-left p-4 rounded-xl bg-slate-900/40 border border-slate-800 hover:border-slate-700/50 transition-all flex items-center space-x-4">
                    <div class="w-9 h-9 rounded-lg bg-emerald-600/10 flex items-center justify-center text-emerald-400 font-bold text-sm"><i class="fa-solid fa-network-wired"></i></div>
                    <div>
                        <h4 class="font-bold text-xs text-slate-400">Module 3: Real-Time Grid Crowd-Map</h4>
                        <p class="text-[11px] text-slate-400 mt-0.5">Exhibits internal crowdsourced metrics framework across academic library blocks and community centers.</p>
                    </div>
                </button>
            </div>

        </div>
    </div>

    <script>
        let isOptimizing = false;

        function updateDeckControls(activeType) {
            ['dashboard', 'ar', 'map'].forEach(type => {
                const button = document.getElementById(`deck-tab-${type}`);
                button.className = "w-full text-left p-4 rounded-xl bg-slate-900/40 border border-slate-800 hover:border-slate-700/50 transition-all flex items-center space-x-4";
                button.querySelector('h4').className = "font-bold text-xs text-slate-400";
            });

            const currentActive = document.getElementById(`deck-tab-${activeType}`);
            if (activeType === 'dashboard') {
                currentActive.className = "w-full text-left p-4 rounded-xl bg-slate-800/80 border border-blue-500/40 transition-all flex items-center space-x-4 shadow-md";
            } else if (activeType === 'ar') {
                currentActive.className = "w-full text-left p-4 rounded-xl bg-slate-800/80 border border-purple-500/40 transition-all flex items-center space-x-4 shadow-md";
            } else if (activeType === 'map') {
                currentActive.className = "w-full text-left p-4 rounded-xl bg-slate-800/80 border border-emerald-500/40 transition-all flex items-center space-x-4 shadow-md";
            }
            currentActive.querySelector('h4').className = "font-bold text-xs text-white";
        }

        function changeAppTab(targetView) {
            const viewport = document.getElementById('phone-screen');
            updateDeckControls(targetView);

            if (targetView === 'dashboard') {
                viewport.innerHTML = `
                    <div id="screen-content" class="flex flex-col justify-between h-full">
                        <div class="text-center mt-3">
                            <h4 class="font-bold text-xs tracking-wider text-slate-200">WiFi Optimizer</h4>
                            <p class="text-[9px] font-semibold text-blue-400 tracking-wider uppercase mt-0.5"><i class="fa-solid fa-building-columns mr-1"></i> Kolej Pendeta Za'ba (KPZ)</p>
                        </div>
                        <div class="flex flex-col items-center justify-center my-auto relative">
                            <div id="radial-container" class="relative w-36 h-36 flex items-center justify-center cursor-pointer active:scale-95 transition-transform duration-150" onclick="triggerOptimization()">
                                <svg class="w-full h-full transform -rotate-90" viewBox="0 0 100 100">
                                    <circle cx="50" cy="50" r="42" stroke="#1f2937" stroke-width="6" fill="transparent" />
                                    <circle id="progress-bar" cx="50" cy="50" r="42" stroke="#10b981" stroke-width="6" fill="transparent" stroke-dasharray="230 264" stroke-linecap="round" />
                                </svg>
                                <div class="absolute text-center select-none">
                                    <span id="gauge-percent" class="text-3xl font-black block text-white tracking-tighter">95%</span>
                                    <span id="gauge-status" class="text-[8px] text-emerald-400 font-bold tracking-widest uppercase">OPTIMIZED</span>
                                </div>
                            </div>
                            <p class="text-[9px] text-slate-500 mt-2 pointer-events-none animate-pulse">👇 Tap circle to recalibrate</p>
                        </div>
                        <div class="space-y-2">
                            <div id="log-card" class="bg-slate-900/90 p-3 rounded-xl text-[11px] border border-slate-800 shadow-inner min-h-[75px] flex flex-col justify-center">
                                <div class="flex justify-between items-center mb-0.5">
                                    <span class="font-bold text-slate-300">Channel Monitor</span>
                                    <span id="log-status-dot" class="inline-block w-1.5 h-1.5 rounded-full bg-emerald-500"></span>
                                </div>
                                <p id="log-text" class="text-slate-400 text-[10px] leading-tight">System managing micro-channels dynamically. Line clear.</p>
                            </div>
                            <div class="grid grid-cols-2 gap-1.5 pt-1">
                                <button onclick="changeAppTab('ar')" class="bg-slate-900 border border-slate-800 text-[10px] py-1.5 rounded-lg text-slate-300 font-medium"><i class="fa-solid fa-camera mr-1 text-purple-400"></i> AR View</button>
                                <button onclick="changeAppTab('map')" class="bg-slate-900 border border-slate-800 text-[10px] py-1.5 rounded-lg text-slate-300 font-medium"><i class="fa-solid fa-map-location-dot mr-1 text-emerald-400"></i> Density Map</button>
                            </div>
                        </div>
                    </div>
                `;
            } else if (targetView === 'ar') {
                viewport.innerHTML = `
                    <div class="flex flex-col justify-between h-full relative bg-slate-950 rounded-2xl overflow-hidden p-2 border border-slate-800">
                        <div class="absolute inset-0 opacity-10 bg-[linear-gradient(to_right,#f1f5f9_1px,transparent_1px),linear-gradient(to_bottom,#f1f5f9_1px,transparent_1px)] bg-[size:14px_14px]"></div>
                        <div class="absolute inset-x-0 top-12 h-0.5 bg-purple-500/30 animate-scan z-20 shadow-md"></div>
                        
                        <div class="relative z-10 bg-black/70 p-1.5 rounded-lg text-center border border-purple-500/20 text-[8px] tracking-wider">
                            <p class="text-purple-400 font-bold"><i class="fa-solid fa-expand mr-1"></i> AR CALIBRATION HOUSING SENSOR</p>
                        </div>

                        <div onclick="toggleZoneDesc('red')" class="absolute bottom-28 left-6 z-30 flex flex-col items-center cursor-pointer group/node">
                            <div class="w-14 h-14 rounded-full bg-red-500/20 border border-red-500/80 flex items-center justify-center relative text-center active:scale-90 transition shadow-lg">
                                <span class="text-[8px] font-bold text-white tracking-wide">RED ZONE</span>
                            </div>
                        </div>

                        <div onclick="toggleZoneDesc('green')" class="absolute top-24 right-6 z-30 flex flex-col items-center cursor-pointer group/node">
                            <div class="w-16 h-16 rounded-full bg-emerald-500/20 border border-emerald-500/80 flex items-center justify-center text-center relative active:scale-90 transition shadow-lg">
                                <span class="text-[8px] font-bold text-white tracking-wide leading-tight">GREEN ZONE<br><span class="text-emerald-300 text-[7px] font-semibold">Clear Area</span></span>
                                <div class="absolute -inset-1 rounded-full border border-emerald-400/30 animate-ping"></div>
                            </div>
                        </div>

                        <div class="relative z-10 bg-black/90 p-2 rounded-xl text-center text-[9px] border border-slate-800 min-h-[42px] flex items-center justify-center">
                            <p id="ar-descriptor" class="text-slate-300 transition-all duration-150">Point device camera at room corners. Tap zones to filter.</p>
                        </div>
                    </div>
                `;
            } else if (targetView === 'map') {
                viewport.innerHTML = `
                    <div class="flex flex-col justify-between h-full">
                        <div class="text-center mt-3">
                            <h4 class="font-bold text-xs tracking-wider text-slate-200">UKM Density Grid</h4>
                            <p class="text-[8px] font-bold text-emerald-400 tracking-wider uppercase mt-0.5">Crowdsourced Channel Map</p>
                        </div>
                        
                        <div class="space-y-2 my-auto px-1">
                            <div onclick="showGridLog('ptsl')" class="bg-slate-900/90 p-2 rounded-xl border border-slate-800 hover:border-red-500/30 cursor-pointer active:scale-[0.99] transition flex justify-between items-center text-[10px]">
                                <div>
                                    <p class="font-bold text-slate-200">Perpustakaan PTSL</p>
                                    <p class="text-[8px] text-slate-500">Saturation high index</p>
                                </div>
                                <span class="px-1.5 py-0.5 rounded bg-red-500/10 text-red-400 font-mono text-[8px] border border-red-500/20 font-bold">SESAK 🔴</span>
                            </div>

                            <div onclick="showGridLog('pusanika')" class="bg-slate-900/90 p-2 rounded-xl border border-slate-800 hover:border-yellow-500/30 cursor-pointer active:scale-[0.99] transition flex justify-between items-center text-[10px]">
                                <div>
                                    <p class="font-bold text-slate-200">Pusanika Hub</p>
                                    <p class="text-[8px] text-slate-500">Balanced dynamic load</p>
                                </div>
                                <span class="px-1.5 py-0.5 rounded bg-yellow-500/10 text-yellow-400 font-mono text-[8px] border border-yellow-500/20 font-bold">SEDERHANA 🟡</span>
                            </div>

                            <div onclick="showGridLog('ftsm')" class="bg-slate-900/90 p-2 rounded-xl border border-slate-800 hover:border-emerald-500/30 cursor-pointer active:scale-[0.99] transition flex justify-between items-center text-[10px]">
                                <div>
                                    <p class="font-bold text-slate-200">Fakulti FTSM / FST</p>
                                    <p class="text-[8px] text-slate-500">Channel structural nodes open</p>
                                </div>
                                <span class="px-1.5 py-0.5 rounded bg-emerald-500/10 text-emerald-400 font-mono text-[8px] border border-emerald-500/20 font-bold">LAPANG 🟢</span>
                            </div>
                        </div>

                        <div class="bg-slate-900 p-2 rounded-xl text-center text-[9px] text-slate-400 border border-slate-800/60 min-h-[38px] flex items-center justify-center">
                            <p id="map-descriptor">Select any campus hub location node above to parse real-time data logs.</p>
                        </div>
                    </div>
                `;
            }
        }

        // Action Function: Screen 1 Recalibration Process Trigger
        function triggerOptimization() {
            if (isOptimizing) return;
            isOptimizing = true;

            const progressBar = document.getElementById('progress-bar');
            const percentText = document.getElementById('gauge-percent');
            const statusText = document.getElementById('gauge-status');
            const logText = document.getElementById('log-text');
            const logDot = document.getElementById('log-status-dot');
            const container = document.getElementById('radial-container');

            container.classList.add('pulse-slow');
            logDot.className = "inline-block w-1.5 h-1.5 rounded-full bg-yellow-500 animate-ping";
            statusText.innerText = "TUNING...";
            statusText.className = "text-[8px] text-yellow-400 font-bold tracking-widest uppercase";

            let current = 95;
            let counter = 0;
            
            // Artificial drop to simulate scan
            percentText.innerText = "42%";
            progressBar.style.strokeDasharray = "100 264";
            progressBar.style.stroke = "#ef233c";
            logText.innerText = "Analyzing interference vectors on current access point profile...";

            setTimeout(() => {
                // Return smoothly to optimized state
                percentText.innerText = "100%";
                progressBar.style.strokeDasharray = "264 264";
                progressBar.style.stroke = "#10b981";
                statusText.innerText = "FULLY OPTIMIZED";
                statusText.className = "text-[7px] text-emerald-400 font-bold tracking-wider uppercase";
                logText.innerHTML = "<strong>Recalibration successful!</strong> All active clients shifted to cleared physical channel nodes safely.";
                logDot.className = "inline-block w-1.5 h-1.5 rounded-full bg-emerald-500";
                container.classList.remove('pulse-slow');
                isOptimizing = false;
            }, 1800);
        }

        // Action Function: Screen 2 AR Zone Detail Viewer Toggle
        function toggleZoneDesc(zone) {
            const desc = document.getElementById('ar-descriptor');
            if (zone === 'red') {
                desc.innerHTML = "<span class='text-red-400 font-semibold'>Red Zone:</span> High wave damping from adjacent structures. Avoid router setups here.";
            } else if (zone === 'green') {
                desc.innerHTML = "<span class='text-emerald-400 font-semibold'>Green Zone:</span> Open line-of-sight tracking. Best position for stable UKMFolio sessions.";
            }
        }

        // Action Function: Screen 3 Map Hub Log Parser
        function showGridLog(hub) {
            const desc = document.getElementById('map-descriptor');
            if (hub === 'ptsl') {
                desc.innerHTML = "<strong>PTSL Library:</strong> 142 devices connected. Suggesting structural reallocation to local auxiliary channels.";
            } else if (hub === 'pusanika') {
                desc.innerHTML = "<strong>Pusanika Square:</strong> 64 devices connected. Signal bandwidth balancing operating efficiently.";
            } else if (hub === 'ftsm') {
                desc.innerHTML = "<strong>FTSM / FST:</strong> 18 devices connected. Maximum link speed variables achieved effortlessly.";
            }
        }
    </script>
</body>
</html>
