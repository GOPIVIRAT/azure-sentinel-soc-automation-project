
[portfolio.html](https://github.com/user-attachments/files/25247893/portfolio.html)
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gopi Siddamsetty | Interactive SOC Portfolio</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&display=swap" rel="stylesheet">
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f8fafc;
            color: #1e293b;
            scroll-behavior: smooth;
        }
        
        .tab-btn {
            transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
        }
        .tab-btn.active {
            background-color: #2563eb;
            color: white;
            border-color: #2563eb;
            transform: translateY(-2px);
            box-shadow: 0 10px 15px -3px rgba(37, 99, 235, 0.3);
        }

        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: #f1f5f9;
        }
        ::-webkit-scrollbar-thumb {
            background: #cbd5e1;
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: #94a3b8;
        }

        .proof-badge {
            transition: all 0.2s cubic-bezier(0.4, 0, 0.2, 1);
            display: flex;
            align-items: center;
            gap: 6px;
            font-size: 10px;
            font-weight: 800;
            text-transform: uppercase;
            letter-spacing: 0.05em;
            padding: 6px 10px;
            background: #eff6ff;
            border: 1.5px solid #60a5fa;
            border-radius: 6px;
            color: #1d4ed8;
            text-decoration: none;
        }
        .proof-badge:hover {
            border-color: #2563eb;
            background: #dbeafe;
            transform: scale(1.05);
        }

        .ai-explain-btn {
            transition: all 0.2s ease;
            font-size: 10px;
            font-weight: 700;
            padding: 6px 10px;
            border-radius: 6px;
            background: #fdf2f8;
            border: 1.5px solid #f472b6;
            color: #be185d;
        }

        .query-btn {
            font-size: 10px;
            font-weight: 800;
            padding: 6px 10px;
            border-radius: 6px;
            background: #f1f5f9;
            border: 1.5px solid #cbd5e1;
            color: #475569;
            text-transform: uppercase;
            transition: all 0.2s;
        }
        .query-btn:hover {
            background: #e2e8f0;
            border-color: #94a3b8;
        }

        .skill-card-bento {
            background: white;
            border: 1px solid #e2e8f0;
            border-radius: 1.5rem;
            padding: 1.5rem;
            transition: all 0.3s ease;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }
        .skill-card-bento:hover {
            border-color: #3b82f6;
            box-shadow: 0 10px 20px -5px rgba(0, 0, 0, 0.05);
        }
        .tool-tag {
            background: #f1f5f9;
            color: #475569;
            font-size: 11px;
            font-weight: 700;
            padding: 4px 10px;
            border-radius: 6px;
            border: 1px solid #e2e8f0;
        }

        .spinner {
            border: 2px solid #f3f3f3;
            border-top: 2px solid #2563eb;
            border-radius: 50%;
            width: 12px; height: 12px;
            animation: spin 1s linear infinite;
            display: inline-block;
        }
        @keyframes spin { 0% { transform: rotate(0deg); } 100% { transform: rotate(360deg); } }

        .mitre-tag {
            background: #1e293b;
            color: #94a3b8;
            padding: 2px 6px;
            border-radius: 4px;
            font-family: monospace;
            font-size: 10px;
            font-weight: bold;
        }

        /* Ticket Report Styling */
        .ticket-summary {
            background: #ffffff;
            border: 1px solid #e2e8f0;
            border-top: 5px solid #ef4444;
            border-radius: 12px;
            padding: 24px;
            position: relative;
            box-shadow: 0 4px 15px rgba(0,0,0,0.05);
        }
        .ticket-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 2px solid #f1f5f9;
            padding-bottom: 12px;
            margin-bottom: 20px;
        }
        .ticket-label {
            font-size: 10px;
            font-weight: 800;
            color: #64748b;
            text-transform: uppercase;
            letter-spacing: 0.1em;
        }
        .query-block {
            background: #1e293b;
            color: #38bdf8;
            font-family: 'Courier New', Courier, monospace;
            padding: 16px;
            border-radius: 8px;
            font-size: 12px;
            line-height: 1.5;
            margin-top: 12px;
            display: none;
            overflow-x: auto;
            border: 1px solid #334155;
        }
        .analysis-box {
            background: #0f172a;
            color: #38bdf8;
            font-family: 'Courier New', Courier, monospace;
            padding: 16px;
            border-radius: 8px;
            font-size: 11px;
            border-left: 4px solid #3b82f6;
            margin-top: 12px;
        }
    </style>
</head>
<body class="antialiased">

    <header class="bg-white border-b border-slate-200 sticky top-0 z-50">
        <div class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 flex justify-between h-16 items-center">
            <div class="flex flex-col">
                <h1 class="text-2xl font-bold text-slate-900 tracking-tight">Gopi Siddamsetty</h1>
                <span class="text-xs font-semibold text-blue-600 uppercase tracking-wider">SOC Analyst (L1) | MCA Cyber Security</span>
            </div>
            <nav class="hidden md:flex space-x-6">
                <a href="#summary" class="text-slate-500 hover:text-blue-600 px-2 py-2 text-sm font-medium transition-colors">Summary</a>
                <a href="#project-sentinel" class="text-slate-500 hover:text-blue-600 px-2 py-2 text-sm font-medium transition-colors">Microsoft Sentinel</a>
                <a href="#project-splunk" class="text-slate-500 hover:text-blue-600 px-2 py-2 text-sm font-medium transition-colors">Splunk</a>
                <a href="#project-phishing" class="text-slate-500 hover:text-blue-600 px-2 py-2 text-sm font-medium transition-colors">Email</a>
                <a href="#skills" class="text-slate-500 hover:text-blue-600 px-2 py-2 text-sm font-medium transition-colors">Skills</a>
            </nav>
            <div class="flex items-center space-x-4">
                 <a href="#verification" class="bg-slate-900 text-white px-4 py-2 rounded-lg text-sm font-semibold hover:bg-slate-800 transition-colors shadow-sm">View Proof</a>
            </div>
        </div>
    </header>

    <main class="max-w-6xl mx-auto px-4 sm:px-6 lg:px-8 py-8 space-y-16">

        <!-- Section 1: Professional Summary -->
        <section id="summary" class="bg-white rounded-2xl p-8 shadow-sm border border-slate-100">
            <div class="flex flex-col md:flex-row gap-8 items-center">
                <div class="flex-1 space-y-4">
                    <div class="flex items-center justify-between">
                        <h2 class="text-3xl font-bold text-slate-900 uppercase tracking-tighter">SOC Analyst Profile</h2>
                        <button onclick="playProfileAudio()" id="audio-btn" class="flex items-center gap-2 px-4 py-2 rounded-full bg-blue-50 text-blue-700 text-xs font-bold hover:bg-blue-100 transition-colors border border-blue-200">
                            <span id="audio-icon">✨</span> Listen to Briefing
                        </button>
                    </div>
                    <p id="summary-text" class="text-lg text-slate-600 leading-relaxed border-l-4 border-blue-600 pl-6 py-4 bg-blue-50/30 rounded-r-xl shadow-inner">
                        <strong>SOC Analyst</strong> with hands-on project experience in SIEM monitoring, log correlation, and L1 alert triage across endpoint, network, and email environments. Skilled in distinguishing false positives from confirmed incidents and documenting findings aligned to SOPs. Familiar with MITRE ATT&CK–mapped detections, SOAR automation, and Azure cloud security fundamentals.
                    </p>
                </div>
                
                <div class="w-full md:w-1/3 text-center space-y-6">
                    <div class="relative mx-auto w-64 h-64 md:w-72 md:h-72">
                        <div class="absolute inset-0 bg-blue-600 rounded-full blur-xl opacity-10 animate-pulse"></div>
                        <div class="relative group rounded-full overflow-hidden border-8 border-white shadow-2xl aspect-square bg-slate-100 flex items-center justify-center">
                            <img src="https://github.com/user-attachments/assets/6e1aa245-37ed-4e9f-9a07-c3f6df03819e" alt="Gopi Siddamsetty Profile Image" class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110">
                        </div>
                    </div>
                    <a href="https://github.com/user-attachments/files/24908434/Gopi_Siddamsetty.pdf" target="_blank" download class="inline-flex items-center gap-2 px-8 py-3 bg-blue-600 text-white rounded-xl font-black uppercase tracking-widest text-xs hover:bg-blue-700 transition-all shadow-lg hover:shadow-blue-200">
                        Download Resume PDF
                    </a>
                </div>
            </div>
        </section>

        <!-- Section 2: Microsoft Sentinel -->
        <section id="project-sentinel">
            <div class="mb-8">
                <div class="flex items-center space-x-2 mb-2">
                    <span class="px-2 py-1 bg-blue-100 text-blue-800 text-xs font-bold uppercase rounded">Core Project</span>
                    <span class="text-slate-400 text-sm">|</span>
                    <span class="text-slate-500 text-sm font-medium italic">End-to-End Security Implementation</span>
                </div>
                <h2 class="text-3xl font-bold text-slate-900 uppercase tracking-tight">SOC Alert Monitoring & Investigation</h2>
            </div>

            <div class="mb-12 rounded-3xl overflow-hidden border border-slate-200 shadow-2xl bg-white relative group">
                <img src="https://github.com/user-attachments/assets/b78e867b-b68f-408b-9432-2af7cd7be4b5" alt="Microsoft Sentinel Project Image" class="w-full h-auto opacity-95 group-hover:opacity-100 transition-opacity duration-700">
            </div>

            <div class="bg-white rounded-3xl border border-slate-200 shadow-sm p-8">
                <div class="flex flex-col md:flex-row gap-4 mb-8">
                    <button id="sentinel-tab-endpoint" onclick="updateSentinelTab('endpoint')" class="tab-btn active flex-1 py-4 rounded-2xl font-bold uppercase tracking-widest text-sm border-2 border-blue-600 bg-blue-600 text-white transition-all shadow-lg shadow-blue-200/50">
                        1. Endpoint Investigation
                    </button>
                    <button id="sentinel-tab-soar" onclick="updateSentinelTab('soar')" class="tab-btn flex-1 py-4 rounded-2xl font-bold uppercase tracking-widest text-sm border-2 border-slate-200 bg-white text-slate-600 hover:border-blue-400 transition-all">
                        2. SOAR Playbooks
                    </button>
                </div>

                <div id="sentinel-investigation-content" class="relative bg-slate-50 rounded-2xl p-8 border border-slate-100 min-h-[350px] transition-all duration-300">
                    <!-- Content injected via JS -->
                </div>
            </div>
        </section>

        <!-- Section 3: Splunk Project -->
        <section id="project-splunk">
            <div class="mb-8">
                <div class="flex items-center space-x-2 mb-2">
                    <span class="px-2 py-1 bg-green-100 text-green-800 text-xs font-bold uppercase rounded">SIEM Project</span>
                    <span class="text-slate-400 text-sm">|</span>
                    <span class="text-slate-500 text-sm font-medium italic">Splunk Security Analytics</span>
                </div>
                <h2 class="text-3xl font-bold text-slate-900 uppercase tracking-tight">Network Threat Detection & Investigation</h2>
            </div>
            <div class="bg-white rounded-3xl border border-slate-200 shadow-sm p-8">
                <div class="flex flex-col md:flex-row gap-4 mb-8">
                    <button id="splunk-tab-investigation" onclick="updateSplunkTab('investigation')" class="tab-btn active flex-1 py-4 rounded-2xl font-bold uppercase tracking-widest text-sm border-2 border-blue-600 bg-blue-600 text-white transition-all shadow-lg shadow-blue-200/50">
                        1. Network Threat Investigation
                    </button>
                    <button id="splunk-tab-dashboards" onclick="updateSplunkTab('dashboards')" class="tab-btn flex-1 py-4 rounded-2xl font-bold uppercase tracking-widest text-sm border-2 border-slate-200 bg-white text-slate-600 hover:border-blue-400 transition-all">
                        2. Website Threat Investigation
                    </button>
                </div>
                <div id="splunk-investigation-content" class="relative bg-slate-50 rounded-2xl p-8 border border-slate-100 min-h-[350px] transition-all duration-300"></div>
            </div>
        </section>

        <!-- Section 4: Email (Phishing) Overhaul -->
        <section id="project-phishing">
            <div class="mb-8 flex items-center justify-between">
                <div>
                    <div class="flex items-center space-x-2 mb-2">
                        <span class="px-2 py-1 bg-orange-100 text-orange-800 text-xs font-bold uppercase rounded">Incident Triage</span>
                        <span class="text-slate-400 text-sm">|</span>
                        <span class="text-slate-500 text-sm font-medium italic">Adversary Infrastructure Detonation</span>
                    </div>
                    <h2 class="text-3xl font-bold text-slate-900 uppercase tracking-tight">Email Security Analysis</h2>
                </div>
                <a href="https://github.com/GOPIVIRAT" target="_blank" class="proof-badge">
                    <svg class="w-4 h-4" viewBox="0 0 24 24" fill="currentColor"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
                    View Triage Docs
                </a>
            </div>
            <div class="max-w-4xl mx-auto">
                <div class="bg-white rounded-2xl shadow-sm border border-slate-200 p-8">
                    <h3 class="font-bold text-slate-800 mb-6 border-b pb-2 text-sm uppercase tracking-widest">Analysis Workbench</h3>
                    <div class="flex space-x-2 mb-8 overflow-x-auto">
                        <button id="phishing-tab-header" onclick="updatePhishingTab('header')" class="tab-btn active px-4 py-2 rounded-lg text-xs font-bold border border-blue-600 bg-blue-600 text-white whitespace-nowrap uppercase tracking-tighter">1. Header Authentication</button>
                        <button id="phishing-tab-ioc" onclick="updatePhishingTab('ioc')" class="tab-btn px-4 py-2 rounded-lg text-xs font-bold border border-slate-300 bg-white text-slate-600 hover:bg-slate-50 whitespace-nowrap uppercase tracking-tighter">2. URL & Attachment Investigation</button>
                        <button id="phishing-tab-remediation" onclick="updatePhishingTab('remediation')" class="tab-btn px-4 py-2 rounded-lg text-xs font-bold border border-slate-300 bg-white text-slate-600 hover:bg-slate-50 whitespace-nowrap uppercase tracking-tighter">3. Verdict & Escalation</button>
                    </div>
                    <div id="phishing-content" class="bg-slate-50 rounded-xl p-8 border border-slate-200 min-h-[300px]"></div>
                    <div class="mt-6 p-4 bg-blue-50 border-l-4 border-blue-600 rounded-r-xl w-full">
                        <p class="text-[10px] font-black text-blue-800 uppercase tracking-widest mb-1">SOC Relevance</p>
                        <p class="text-xs font-bold text-slate-800 leading-tight">Inspecting phishing emails by validating sender authentication (SPF/DKIM/DMARC) and inspecting URLs and attachments, classifying benign emails and escalating confirmed phishing incidents.</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Section 5: Technical Skills (Bento) -->
        <section id="skills">
            <div class="mb-12">
                <div class="flex items-center space-x-2 mb-2">
                    <span class="px-2 py-1 bg-slate-900 text-white text-xs font-bold uppercase rounded tracking-widest">Expertise</span>
                    <span class="text-slate-400 text-sm">|</span>
                    <span class="text-slate-500 text-sm font-medium italic">Practical Capability Matrix</span>
                </div>
                <h2 class="text-4xl font-black text-slate-900 uppercase tracking-tight mb-2">Technical Skills</h2>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <div class="skill-card-bento border-l-8 border-l-blue-600"><div class="space-y-4"><span class="text-2xl">🔍</span><h3 class="text-lg font-black text-slate-800 uppercase tracking-tighter">SIEM & Ticketing</h3><div class="flex flex-wrap gap-2"><span class="tool-tag">Microsoft Sentinel</span><span class="tool-tag">Splunk</span><span class="tool-tag">KQL</span><span class="tool-tag">ServiceNow (ITSM)</span></div></div></div>
                <div class="skill-card-bento border-l-8 border-l-indigo-600"><div class="space-y-4"><span class="text-2xl">💻</span><h3 class="text-lg font-black text-slate-800 uppercase tracking-tighter">Endpoint Security</h3><div class="flex flex-wrap gap-2"><span class="tool-tag">MS Defender (EDR)</span><span class="tool-tag">Sysmon</span><span class="tool-tag">Windows Event Logs</span><span class="tool-tag">Linux Auth Logs</span></div></div></div>
                <div class="skill-card-bento border-l-8 border-l-emerald-600"><div class="space-y-4"><span class="text-2xl">📧</span><h3 class="text-lg font-black text-slate-800 uppercase tracking-tighter">Email Security</h3><div class="flex flex-wrap gap-2"><span class="tool-tag">Phishing Analysis</span><span class="tool-tag">Header Inspection</span><span class="tool-tag">IOC Validation</span><span class="tool-tag">URL/Attachment</span></div></div></div>
                <div class="skill-card-bento border-l-8 border-l-amber-500"><div class="space-y-4"><span class="text-2xl">🌐</span><h3 class="text-lg font-black text-slate-800 uppercase tracking-tighter">Network Security</h3><div class="flex flex-wrap gap-2"><span class="tool-tag">Wireshark</span><span class="tool-tag">IDS/IPS Logs</span><span class="tool-tag">TCP/IP</span><span class="tool-tag">Firewall Analysis</span></div></div></div>
                <div class="skill-card-bento border-l-8 border-l-orange-600"><div class="space-y-4"><span class="text-2xl">⚙️</span><h3 class="text-lg font-black text-slate-800 uppercase tracking-tighter">Automation & Scripting</h3><div class="flex flex-wrap gap-2"><span class="tool-tag">SOAR (Logic Apps)</span><span class="tool-tag">PowerShell</span><span class="tool-tag">Python</span></div></div></div>
                <div class="skill-card-bento border-l-8 border-l-purple-600"><div class="space-y-4"><span class="text-2xl">🛡️</span><h3 class="text-lg font-black text-slate-800 uppercase tracking-tighter">Frameworks & Cloud</h3><div class="flex flex-wrap gap-2"><span class="tool-tag">MITRE ATT&CK</span><span class="tool-tag">NIST CSF</span><span class="tool-tag">Azure (Entra ID)</span></div></div></div>
            </div>
        </section>

        <!-- Section 6: Verification -->
        <section id="verification" class="bg-slate-900 rounded-3xl p-10 text-center shadow-lg relative overflow-hidden">
            <div class="absolute top-0 right-0 w-64 h-64 bg-blue-600/10 rounded-full -mr-20 -mt-20"></div>
            <h2 class="text-3xl font-black text-white mb-6 uppercase tracking-tighter">Verification & Technical Evidence</h2>
            <div class="flex flex-col sm:flex-row justify-center gap-4 relative z-10">
                <a href="https://github.com/GOPIVIRAT" target="_blank" class="inline-flex items-center justify-center px-6 py-3 text-sm font-black rounded-lg text-slate-900 bg-white hover:bg-slate-100 transition-all uppercase tracking-widest text-center">Github</a>
                <a href="https://www.linkedin.com/in/gopi-soc318314284/" target="_blank" class="inline-flex items-center justify-center px-6 py-3 text-sm font-black rounded-lg text-white bg-blue-700 hover:bg-blue-600 transition-all uppercase tracking-widest text-center">Linkedin</a>
                <a href="https://github.com/user-attachments/files/24908434/Gopi_Siddamsetty.pdf" target="_blank" download class="inline-flex items-center justify-center px-6 py-3 text-sm font-black rounded-lg text-white border-2 border-slate-700 bg-transparent hover:bg-slate-800 transition-all uppercase tracking-widest text-center">Download Resume PDF</a>
            </div>
        </section>

    </main>

    <footer class="bg-white border-t border-slate-200 py-10 text-center text-slate-400 text-xs font-bold uppercase tracking-widest">
        &copy; 2026 Gopi Siddamsetty — SOC Analyst L1 Candidate
    </footer>

    <script>
        const apiKey = "";
        
        async function fetchWithRetry(url, options, maxRetries = 5) {
            let delay = 1000;
            for (let i = 0; i < maxRetries; i++) {
                try {
                    const response = await fetch(url, options);
                    if (response.ok) return await response.json();
                } catch (e) {}
                await new Promise(r => setTimeout(r, delay));
                delay *= 2;
            }
            throw new Error("API failed.");
        }

        function toggleQuery(id) {
            const block = document.getElementById(id);
            block.style.display = block.style.display === 'block' ? 'none' : 'block';
        }

        function pcmToWav(pcmData, sampleRate) {
            const header = new ArrayBuffer(44);
            const view = new DataView(header);
            writeString(view, 0, 'RIFF');
            view.setUint32(4, 36 + pcmData.byteLength, true);
            writeString(view, 8, 'WAVE');
            writeString(view, 12, 'fmt ');
            view.setUint32(16, 16, true);
            view.setUint16(20, 1, true);
            view.setUint16(22, 1, true);
            view.setUint32(24, sampleRate, true);
            view.setUint32(28, sampleRate * 2, true);
            view.setUint16(32, 2, true);
            view.setUint16(34, 16, true);
            writeString(view, 36, 'data');
            view.setUint32(40, pcmData.byteLength, true);
            const wav = new Uint8Array(header.byteLength + pcmData.byteLength);
            wav.set(new Uint8Array(header), 0);
            wav.set(new Uint8Array(pcmData), 44);
            return new Blob([wav], { type: 'audio/wav' });
        }

        function writeString(view, offset, string) {
            for (let i = 0; i < string.length; i++) { view.setUint8(offset + i, string.charCodeAt(i)); }
        }

        async function playProfileAudio() {
            const btn = document.getElementById('audio-btn');
            const icon = document.getElementById('audio-icon');
            const summary = document.getElementById('summary-text').innerText;
            try {
                icon.innerHTML = '<span class="spinner"></span>';
                btn.disabled = true;
                const payload = {
                    contents: [{ parts: [{ text: `Profile briefing for Gopi Siddamsetty: ${summary}` }] }],
                    generationConfig: { responseModalities: ["AUDIO"], speechConfig: { voiceConfig: { prebuiltVoiceConfig: { voiceName: "Kore" } } } },
                    model: "gemini-2.5-flash-preview-tts"
                };
                const result = await fetchWithRetry(`https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-tts:generateContent?key=${apiKey}`, {
                    method: 'POST', headers: { 'Content-Type': 'application/json' }, body: JSON.stringify(payload)
                });
                const binaryString = atob(result.candidates[0].content.parts[0].inlineData.data);
                const pcmData = new Uint8Array(binaryString.length);
                for (let i = 0; i < binaryString.length; i++) pcmData[i] = binaryString.charCodeAt(i);
                const audioUrl = URL.createObjectURL(pcmToWav(pcmData.buffer, 24000));
                const audio = new Audio(audioUrl);
                audio.play();
                audio.onended = () => { icon.innerHTML = '✨'; btn.disabled = false; };
            } catch (err) { icon.innerHTML = '✨'; btn.disabled = false; }
        }

        async function explainWork(context, event) {
            const targetBtn = event.currentTarget;
            const originalText = targetBtn.innerText;
            targetBtn.innerHTML = '<span class="spinner"></span> Analyzing...';
            targetBtn.disabled = true;
            try {
                const result = await fetchWithRetry(`https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-09-2025:generateContent?key=${apiKey}`, {
                    method: 'POST', headers: { 'Content-Type': 'application/json' },
                    body: JSON.stringify({ contents: [{ parts: [{ text: `Explain this SOC task: ${context}. 3 bullets with emojis.` }] }] })
                });
                const aiDiv = document.createElement('div');
                aiDiv.className = "mt-6 p-5 bg-white border border-pink-200 rounded-xl shadow-sm text-xs text-slate-700 italic";
                aiDiv.innerHTML = `<p class="font-black text-pink-600 mb-2 uppercase tracking-widest">✨ Senior Analyst Commentary</p><div>${result.candidates[0].content.parts[0].text.replace(/\n/g, '<br>')}</div>`;
                targetBtn.parentElement.parentElement.appendChild(aiDiv);
            } catch (err) {} finally { targetBtn.innerText = originalText; targetBtn.disabled = false; }
        }

        const projectData = {
            sentinel: {
                endpoint: {
                    title: "Endpoint Investigation - Investigation Lifecycle",
                    github: "https://github.com/GOPIVIRAT/azure-sentinel-soc-automation-project/blob/main/4.Attacking%26Detecting.md",
                    content: `<div class="space-y-8">
                        <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
                            <div class="p-5 bg-white rounded-2xl border border-slate-200 hover:border-blue-300 transition-colors">
                                <div class="flex justify-between mb-3"><span class="mitre-tag">T1078</span><span class="text-[10px] font-bold text-blue-600 uppercase">Detection</span></div>
                                <p class="text-sm text-slate-700 leading-relaxed">Investigated <strong>authentication alerts</strong> (Event IDs 4624/4625), logon patterns, and IP reputation, closing FPs and escalating suspicious access.</p>
                                <button onclick="toggleQuery('q-auth')" class="query-btn mt-3 text-[9px]">View KQL</button>
                                <div id="q-auth" class="query-block">SecurityEvent | where EventID in (4624, 4625) | extend LogonType = tostring(LogonTypeName) | summarize count() by TargetUserName, IpAddress, LogonType</div>
                            </div>
                            <div class="p-5 bg-white rounded-2xl border border-slate-200 hover:border-blue-300 transition-colors">
                                <div class="flex justify-between mb-3"><span class="mitre-tag">T1059.001</span><span class="text-[10px] font-bold text-blue-600 uppercase">Hunt</span></div>
                                <p class="text-sm text-slate-700 leading-relaxed">Analyzed <strong>PowerShell execution</strong> by reviewing parent-child processes and persistence (scheduled tasks, registry Run keys) to identify post-exploitation.</p>
                                <button onclick="toggleQuery('q-ps')" class="query-btn mt-3 text-[9px]">View KQL</button>
                                <div id="q-ps" class="query-block">DeviceProcessEvents | where ProcessCommandLine has "PowerShell" | where InitiatingProcessFileName in ("wscript.exe", "mshta.exe")</div>
                            </div>
                            <div class="p-5 bg-white rounded-2xl border border-slate-200 hover:border-emerald-300 transition-colors">
                                <div class="flex justify-between mb-3"><span class="mitre-tag">Triage</span><span class="text-[10px] font-bold text-emerald-600 uppercase">Response</span></div>
                                <h4 class="text-xs font-black text-slate-800 uppercase mb-2 leading-tight">Incident Confirmation & Escalation</h4>
                                <p class="text-xs text-slate-700 leading-relaxed">Validated confirmed malicious activity, documented findings with evidence, and escalated the incident to L2 analysts for deeper response.</p>
                            </div>
                        </div>
                        
                        <div class="ticket-summary">
                            <div class="ticket-header">
                                <div><p class="ticket-label">Incident Ticket #SENT-2026-084</p><h4 class="text-sm font-black text-slate-900">📄 SOC L1 Escalation Summary</h4></div>
                                <span class="px-3 py-1 bg-red-100 text-red-700 rounded-full text-[10px] font-black uppercase tracking-widest">Severity: High</span>
                            </div>
                            <div class="space-y-4">
                                <div><p class="ticket-label mb-1">Incident Type</p><p class="text-sm font-bold text-slate-800">Account Compromise with Endpoint Persistence</p></div>
                                <div class="grid grid-cols-1 md:grid-cols-2 gap-6 text-xs">
                                    <div class="space-y-3">
                                        <div><p class="ticket-label mb-1 text-[9px]">Detection Trigger</p><p class="text-slate-600 leading-relaxed">Multiple failed/successful auth (4625/4624) from an external IP, indicating brute-force activity.</p></div>
                                        <div><p class="ticket-label mb-1 text-[9px]">Investigation Discovery</p><p class="text-slate-600 leading-relaxed">Confirmed privileged login. Pivoted to telemetry and identified suspicious PS execution with scheduled task creation.</p></div>
                                    </div>
                                    <div class="bg-slate-50 p-4 rounded-xl border border-slate-100">
                                        <p class="ticket-label mb-2 text-[9px]">Key Evidence Artifacts</p>
                                        <ul class="space-y-1 font-bold text-slate-700"><li>• Failed → Successful Logon Pattern</li><li>• Admin-level Account Accessed</li><li>• PS Scheduled Task Established</li></ul>
                                    </div>
                                </div>
                                <div class="pt-4 border-t border-slate-100 flex justify-between items-end">
                                    <div><p class="ticket-label mb-1">Outcome (L1 Disposition)</p><p class="text-xs font-bold text-emerald-700 italic">Confirmed malicious. Escalated to SOC L2 for response.</p></div>
                                    <div class="text-right"><p class="text-[9px] font-bold text-slate-400 uppercase tracking-tighter">Status: Escalated</p></div>
                                </div>
                            </div>
                        </div>

                        <div class="mt-8 flex items-center gap-4">
                            <div class="p-4 bg-blue-50 border-l-4 border-blue-600 rounded-r-xl flex-1"><p class="text-[10px] font-black text-blue-800 uppercase tracking-widest mb-1">SOC Relevance</p><p class="text-sm font-bold text-slate-800 leading-tight">L1 endpoint alert triage and incident investigation lifecycle.</p></div>
                            <button onclick="explainWork('Auth Event IDs and PowerShell parent-child investigation in Sentinel', event)" class="ai-explain-btn self-center">✨ AI Explain Impact</button>
                        </div>
                    </div>`
                },
                soar: {
                    title: "SOAR Playbooks - Automated Triage & Response",
                    github: "https://github.com/GOPIVIRAT/azure-sentinel-soc-automation-project/blob/main/5.Logic%20App%20Playbooks.md",
                    content: `<div class="space-y-6">
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <div class="p-5 bg-white rounded-2xl border border-slate-200 hover:border-emerald-300">
                                <div class="flex justify-between mb-3"><span class="mitre-tag">Automation</span><span class="text-[10px] font-bold text-emerald-600 uppercase">Intel Enrichment</span></div>
                                <p class="text-sm text-slate-700">Applied Sentinel SOAR playbooks to <strong>enrich alerts</strong> with <strong>VirusTotal IP and file-hash</strong> reputation checks for real-time intel.</p>
                            </div>
                            <div class="p-5 bg-white rounded-2xl border border-slate-200 hover:border-emerald-300">
                                <div class="flex justify-between mb-3"><span class="mitre-tag">Optimization</span><span class="text-[10px] font-bold text-emerald-600 uppercase">Triage Reduction</span></div>
                                <p class="text-sm text-slate-700">Configured <strong>auto-handling for low-severity incidents</strong> based on scores, reducing manual investigation effort by <strong>~5–10%</strong>.</p>
                            </div>
                        </div>
                        <div class="mt-8 flex items-center gap-4">
                            <div class="p-4 bg-emerald-50 border-l-4 border-emerald-600 rounded-r-xl flex-1">
                                <p class="text-[10px] font-black text-emerald-800 uppercase tracking-widest mb-1">SOC Relevance</p>
                                <p class="text-sm font-bold text-slate-800 leading-tight">Automated response and investigation efficiency using Logic Apps.</p>
                            </div>
                            <button onclick="explainWork('SOAR Playbook automation in Sentinel', event)" class="ai-explain-btn self-center">✨ AI Explain Impact</button>
                        </div>
                    </div>`
                }
            },
            splunk: {
                investigation: {
                    title: "Network Threat Investigation - Splunk",
                    github: "https://github.com/GOPIVIRAT/Splunk-SOC-Detection-Project/blob/main/Network_level_Attacks/Suricata(NIDS).md",
                    content: `<div class="space-y-6">
                        <ul class="space-y-4">
                            <li class="flex items-start gap-4"><div class="w-8 h-8 rounded-full bg-green-100 text-green-600 flex items-center justify-center shrink-0 font-bold text-sm">1</div><p class="text-slate-700 leading-relaxed pt-1">Detected reconnaissance (Nmap scans) using <strong>Suricata signatures</strong> correlated with network flows in Splunk.</p></li>
                            <li class="flex items-start gap-4"><div class="w-8 h-8 rounded-full bg-green-100 text-green-600 flex items-center justify-center shrink-0 font-bold text-sm">2</div><p class="text-slate-700 leading-relaxed pt-1">Detected and investigated <strong>SSH & RDP brute-force activity</strong> by correlating repeated failures with successful logins.</p></li>
                            <li class="flex items-start gap-4"><div class="w-8 h-8 rounded-full bg-green-100 text-green-600 flex items-center justify-center shrink-0 font-bold text-sm">3</div><p class="text-slate-700 leading-relaxed pt-1">Wrote <strong>custom Suricata rules</strong> to detect scanning, brute-force patterns, and abnormal authentication behavior.</p></li>
                        </ul>
                        <button onclick="toggleQuery('q-spl-net')" class="query-btn mt-3 text-[9px]">View SPL</button>
                        <div id="q-spl-net" class="query-block">index=network sourcetype=suricata event_type=alert | stats count by src_ip, alert.signature | where count > 10</div>
                         <div class="mt-8 p-4 bg-green-50 border-l-4 border-green-600 rounded-r-xl"><p class="text-[10px] font-black text-green-800 uppercase tracking-widest mb-1">SOC Relevance</p><p class="text-sm font-bold text-slate-800">Advanced log correlation and threat hunting using SPL.</p></div>
                    </div>`
                },
                dashboards: {
                    title: "Website Threat Investigation - Splunk",
                    github: "https://github.com/GOPIVIRAT/Splunk-SOC-Detection-Project/blob/main/Network_level_Attacks/DVWA.md",
                    content: `<div class="space-y-6">
                        <ul class="space-y-4">
                            <li class="flex items-start gap-4"><div class="w-8 h-8 rounded-full bg-green-100 text-green-600 flex items-center justify-center shrink-0 font-bold text-sm">1</div><p class="text-slate-700 leading-relaxed pt-1">Performed <strong>brute-force login attacks</strong> against DVWA and analyzed application-level logs in Splunk.</p></li>
                            <li class="flex items-start gap-4"><div class="w-8 h-8 rounded-full bg-green-100 text-green-600 flex items-center justify-center shrink-0 font-bold text-sm">2</div><p class="text-slate-700 leading-relaxed pt-1">Simulated web attacks (SQL injection and XSS) to generate malicious request pattern telemetry.</p></li>
                            <li class="flex items-start gap-4"><div class="w-8 h-8 rounded-full bg-green-100 text-green-600 flex items-center justify-center shrink-0 font-bold text-sm">3</div><p class="text-slate-700 leading-relaxed pt-1">Captured and analyzed attack traffic using <strong>Wireshark</strong> to identify abnormal HTTP payloads and behavior.</p></li>
                            <li class="flex items-start gap-4"><div class="w-8 h-8 rounded-full bg-green-100 text-green-600 flex items-center justify-center shrink-0 font-bold text-sm">4</div><p class="text-slate-700 leading-relaxed pt-1">Correlated application logs in Splunk with network traffic to validate attack activity.</p></li>
                        </ul>
                         <div class="mt-8 p-4 bg-blue-50 border-l-4 border-blue-600 rounded-r-xl"><p class="text-[10px] font-black text-blue-800 uppercase tracking-widest mb-1">SOC Relevance</p><p class="text-sm font-bold text-slate-800">Operational visibility and alerting for rapid web application attack triage.</p></div>
                    </div>`
                }
            },
            phishing: {
                header: { 
                    title: "1. SMTP Header Deconstruction", 
                    content: `<div class="space-y-4">
                        <p class="text-sm font-medium text-slate-700">Validated sender integrity by deconstructing SMTP headers for spoofing detection:</p>
                        <div class="analysis-box">
                            [HEADER_ANALYSIS_REPORT]<br>
                            SPF: FAIL (SoftFail) - IP: 198.51.100.45<br>
                            DKIM: PASS<br>
                            DMARC: FAIL (Alignment Error - From: microsoft.com vs Return-Path: attacker.xyz)<br>
                            Verdict: Technical Spoofing Detected
                        </div>
                        <p class="text-xs text-slate-500 italic mt-2 leading-relaxed">Inspected phishing emails by validating sender authentication (SPF/DKIM/DMARC) to identify impersonation attempts.</p>
                    </div>` 
                },
                ioc: { 
                    title: "2. URL & Attachment Investigation", 
                    content: `<div class="space-y-4">
                        <p class="text-sm font-medium text-slate-700">Conducted deep inspection of embedded URLs and attachments:</p>
                        <ul class="space-y-2 text-[11px] text-slate-600">
                            <li class="flex items-center gap-2"><div class="w-1.5 h-1.5 bg-blue-500 rounded-full"></div> <strong>URL Sandboxing:</strong> Cross-referenced URLs with VirusTotal & URLScan.io.</li>
                            <li class="flex items-center gap-2"><div class="w-1.5 h-1.5 bg-blue-500 rounded-full"></div> <strong>Static Analysis:</strong> Verified file hashes of attachments against known reputation DBs.</li>
                        </ul>
                        <div class="analysis-box border-l-orange-500">
                            Detonation Verdict: Credential Harvesting Portal<br>
                            Source: tinyurl.com/hx921s -> login.ms-office365-verify.com
                        </div>
                    </div>` 
                },
                remediation: { 
                    title: "3. Triage & Incident Disposition", 
                    content: `<div class="space-y-6">
                        <div class="ticket-summary">
                            <div class="ticket-header">
                                <div><p class="ticket-label">Incident Ticket #MAIL-2026-102</p><h4 class="text-sm font-black text-slate-900">📄 SOC L1 Phishing Escalation Summary</h4></div>
                                <span class="px-3 py-1 bg-red-100 text-red-700 rounded-full text-[10px] font-black uppercase tracking-widest">Severity: High</span>
                            </div>
                            <div class="space-y-4">
                                <div><p class="ticket-label mb-1 text-[9px]">Incident Type</p><p class="text-[13px] font-bold text-slate-800">Targeted Credential Harvesting via Domain Impersonation</p></div>
                                <div class="grid grid-cols-1 md:grid-cols-2 gap-6 text-xs">
                                    <div class="space-y-3">
                                        <div><p class="ticket-label mb-1 text-[9px]">Detection Trigger</p><p class="text-slate-600 leading-relaxed italic">User-reported email mimicking IT Department Password Reset Notification.</p></div>
                                        <div><p class="ticket-label mb-1 text-[9px]">Investigation Discovery</p><p class="text-slate-600 leading-relaxed italic">Header analysis revealed DMARC alignment failure. URL sandboxing confirmed a credential harvesting landing page masked as M365.</p></div>
                                    </div>
                                    <div class="bg-slate-50 p-4 rounded-xl border border-slate-100">
                                        <p class="ticket-label mb-2 text-[9px]">Key Evidence Artifacts</p>
                                        <ul class="space-y-1 font-bold text-slate-700 italic"><li>• DMARC: FAIL (Alignment Error)</li><li>• hxxps[:]//microsoft-office-update[.]xyz/login</li><li>• VT Score: 12/70 (Credential Harvesting)</li></ul>
                                    </div>
                                </div>
                                <div class="pt-4 border-t border-slate-100 flex justify-between items-end">
                                    <div><p class="ticket-label mb-1">Outcome (L1 Disposition)</p><p class="text-[11px] font-bold text-emerald-700 italic">Confirmed malicious. Initiated automated purge via SOAR and escalated to L2 for user account reset.</p></div>
                                    <div class="text-right"><p class="text-[9px] font-bold text-slate-400 uppercase tracking-tighter">Status: Escalated to L2</p></div>
                                </div>
                            </div>
                        </div>
                    </div>` 
                }
            }
        };

        function updateSentinelTab(tab) {
            document.querySelectorAll('#project-sentinel .tab-btn').forEach(btn => {
                btn.classList.remove('active', 'bg-blue-600', 'text-white', 'border-blue-600', 'shadow-lg', 'shadow-blue-200/50');
                btn.classList.add('bg-white', 'text-slate-600', 'border-slate-200');
            });
            const activeBtn = document.getElementById('sentinel-tab-' + tab);
            if (activeBtn) activeBtn.classList.add('active', 'bg-blue-600', 'text-white', 'border-blue-600', 'shadow-lg', 'shadow-blue-200/50');
            const container = document.getElementById('sentinel-investigation-content');
            if (container) { container.style.opacity = '0'; setTimeout(() => {
                const data = projectData.sentinel[tab];
                container.innerHTML = `<div class="absolute top-6 right-6"><a href="${data.github}" target="_blank" class="proof-badge">Proof of Work</a></div><h4 class="text-xl font-black text-slate-900 mb-6 border-b pb-4 pr-32 uppercase tracking-tighter">${data.title}</h4>${data.content}`;
                container.style.opacity = '1';
            }, 150); }
        }

        function updateSplunkTab(tab) {
            document.querySelectorAll('#project-splunk .tab-btn').forEach(btn => {
                btn.classList.remove('active', 'bg-blue-600', 'text-white', 'border-blue-600', 'shadow-lg', 'shadow-blue-200/50');
                btn.classList.add('bg-white', 'text-slate-600', 'border-slate-200');
            });
            const activeBtn = document.getElementById('splunk-tab-' + tab);
            if (activeBtn) activeBtn.classList.add('active', 'bg-blue-600', 'text-white', 'border-blue-600', 'shadow-lg', 'shadow-blue-200/50');
            const container = document.getElementById('splunk-investigation-content');
            if (container) { container.style.opacity = '0'; setTimeout(() => {
                const data = projectData.splunk[tab];
                container.innerHTML = `<div class="absolute top-6 right-6"><a href="${data.github}" target="_blank" class="proof-badge">Proof of Work</a></div><h4 class="text-xl font-black text-slate-900 mb-6 border-b pb-4 pr-32 uppercase tracking-tighter">${data.title}</h4>${data.content}`;
                container.style.opacity = '1';
            }, 150); }
        }

        function updatePhishingTab(tab) {
            document.querySelectorAll('#project-phishing .tab-btn').forEach(btn => {
                btn.classList.remove('active', 'bg-blue-600', 'text-white', 'border-blue-600');
                btn.classList.add('bg-white', 'text-slate-600', 'border-slate-200');
            });
            const activeBtn = document.getElementById('phishing-tab-' + tab);
            if (activeBtn) activeBtn.classList.add('active', 'bg-blue-600', 'text-white', 'border-blue-600', 'shadow-lg', 'shadow-blue-200/50');
            const container = document.getElementById('phishing-content');
            if (container) { container.innerHTML = `<h4 class="text-lg font-black text-slate-800 mb-4 uppercase tracking-tighter">${projectData.phishing[tab].title}</h4>${projectData.phishing[tab].content}`; }
        }

        document.addEventListener('DOMContentLoaded', () => {
            updateSentinelTab('endpoint');
            updateSplunkTab('investigation');
            updatePhishingTab('header');
        });
    </script>
</body>
</html>
