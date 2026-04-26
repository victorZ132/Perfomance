<!DOCTYPE html>
<html lang="fr" class="scroll-smooth">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Vision & Structuration du Poste : Performance Manager</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
    <style>
        /* Custom Styles & Chart Container Enforcement */
        body { font-family: 'Inter', system-ui, -apple-system, sans-serif; background-color: #f8fafc; color: #0f172a; }
        .glass-panel { background: rgba(255, 255, 255, 0.9); backdrop-filter: blur(10px); border: 1px solid rgba(226, 232, 240, 0.8); }
        .nav-link.active { background-color: #2563eb; color: white; font-weight: 600; }
        
        /* Mandatory Chart Container Constraints */
        .chart-container {
            position: relative;
            width: 100%;
            max-width: 600px;
            margin: 0 auto;
            height: 350px;
            max-height: 400px;
        }
        @media (max-width: 768px) {
            .chart-container { height: 280px; max-height: 300px; }
        }

        /* Custom Scrollbar */
        ::-webkit-scrollbar { width: 8px; }
        ::-webkit-scrollbar-track { background: #f1f5f9; }
        ::-webkit-scrollbar-thumb { background: #cbd5e1; border-radius: 4px; }
        ::-webkit-scrollbar-thumb:hover { background: #94a3b8; }

        /* AI Loading Spinner */
        .spinner {
            border: 3px solid rgba(255, 255, 255, 0.3);
            border-radius: 50%;
            border-top: 3px solid #fff;
            width: 20px;
            height: 20px;
            animation: spin 1s linear infinite;
            display: inline-block;
            vertical-align: middle;
            margin-right: 8px;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
    </style>
</head>
<body class="flex flex-col md:flex-row h-screen overflow-hidden">

    <!-- Chosen Palette: Slate (Neutrals) + Blue (Trust/Corporate) + Emerald (Performance/Growth) -->
    <!-- Application Structure Plan: 
         A dashboard-style SPA to present the role of "Performance Manager" to the CEO.
         Integration of Gemini API for "Action Plan Generation" and "Feedback Analysis".
    -->

    <!-- Sidebar Navigation -->
    <nav class="w-full md:w-64 bg-slate-900 text-white flex flex-col justify-between shadow-xl z-20 flex-shrink-0 md:h-full">
        <div class="p-6">
            <h1 class="text-2xl font-bold tracking-tight text-blue-400 mb-2">TSE</h1>
            <p class="text-sm text-slate-400 uppercase tracking-wider font-semibold mb-8">Performance Manager</p>
            <ul class="space-y-2 flex flex-row md:flex-col overflow-x-auto md:overflow-visible pb-2 md:pb-0">
                <li><button onclick="navTo('vision')" id="nav-vision" class="nav-link active w-full text-left px-4 py-3 rounded-lg transition-colors whitespace-nowrap">👁️ Vision & Mantra</button></li>
                <li><button onclick="navTo('missions')" id="nav-missions" class="nav-link w-full text-left px-4 py-3 rounded-lg transition-colors whitespace-nowrap">🎯 Missions Clés</button></li>
                <li><button onclick="navTo('perimetre')" id="nav-perimetre" class="nav-link w-full text-left px-4 py-3 rounded-lg transition-colors whitespace-nowrap">🔄 Périmètre Transversal</button></li>
                <li><button onclick="navTo('incentives')" id="nav-incentives" class="nav-link w-full text-left px-4 py-3 rounded-lg transition-colors whitespace-nowrap">💰 KPIs & Incentives</button></li>
                <li><button onclick="navTo('ai-lab')" id="nav-ai-lab" class="nav-link w-full text-left px-4 py-3 rounded-lg transition-colors whitespace-nowrap border-t border-slate-700 mt-2 pt-4 text-emerald-400">✨ Lab IA Performance</button></li>
            </ul>
        </div>
        <div class="p-6 hidden md:block text-xs text-slate-500">
            Document de cadrage stratégique<br>Conçu pour présentation Direction.
        </div>
    </nav>

    <!-- Main Content Area -->
    <main class="flex-1 h-full overflow-y-auto bg-slate-50 p-4 md:p-10 scroll-smooth" id="main-content">
        
        <!-- SECTION 1: VISION -->
        <section id="vision" class="min-h-full flex flex-col justify-center mb-24 pt-10 md:pt-0">
            <div class="max-w-4xl">
                <h2 class="text-sm font-bold text-blue-600 uppercase tracking-widest mb-2">Le Rôle</h2>
                <h3 class="text-4xl md:text-5xl font-extrabold text-slate-900 mb-6 leading-tight">Performance Manager <br><span class="text-transparent bg-clip-text bg-gradient-to-r from-blue-600 to-emerald-500">Le pont entre la stratégie et le terrain.</span></h3>
                
                <div class="glass-panel p-8 rounded-2xl shadow-lg border-l-4 border-blue-500 mb-8">
                    <p class="text-xl text-slate-700 leading-relaxed mb-4">
                        <strong>Le Mantra :</strong> "Injecter, mesurer et monétiser la performance à toutes les strates de l'entreprise."
                    </p>
                    <p class="text-slate-600">
                        Ce poste n'est pas un simple "Responsable Qualité". C'est le garant de l'alignement entre les enjeux financiers du Comex (rentabilité, croissance) et la réalité de la production. Il transforme les données brutes (qualité, formation, satisfaction) en plans d'action concrets générateurs de valeur mesurable.
                    </p>
                </div>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                    <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-100">
                        <div class="text-3xl mb-3">🧭</div>
                        <h4 class="font-bold text-slate-800 mb-2">Orienter</h4>
                        <p class="text-sm text-slate-600">Traduire la vision Comex en KPIs opérationnels clairs pour les équipes.</p>
                    </div>
                    <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-100">
                        <div class="text-3xl mb-3">🛠️</div>
                        <h4 class="font-bold text-slate-800 mb-2">Optimiser</h4>
                        <p class="text-sm text-slate-600">Déployer des feuilles de route d'amélioration continue (chantiers prioritaires).</p>
                    </div>
                    <div class="bg-white p-6 rounded-xl shadow-sm border border-slate-100">
                        <div class="text-3xl mb-3">💶</div>
                        <h4 class="font-bold text-slate-800 mb-2">Rentabiliser</h4>
                        <p class="text-sm text-slate-600">Passer du contrôle qualité (centre de coût) à la création de valeur (marge, fidélisation).</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- SECTION 2: MISSIONS -->
        <section id="missions" class="min-h-full flex flex-col justify-center mb-24 pt-10 md:pt-0">
            <div class="max-w-5xl w-full">
                <h2 class="text-sm font-bold text-blue-600 uppercase tracking-widest mb-2">Le Quotidien</h2>
                <h3 class="text-3xl font-bold text-slate-900 mb-8">4 Piliers d'Action</h3>

                <p class="text-slate-600 mb-8"><em>Cliquez sur chaque pilier pour découvrir les actions concrètes inspirées des nouveaux modèles de BPO (IA, data-driven, coaching).</em></p>

                <div class="grid grid-cols-2 gap-4 mb-8">
                    <button onclick="showMissionDetail('qa')" id="btn-qa" class="mission-btn bg-blue-50 border-2 border-blue-500 text-blue-700 p-4 rounded-xl font-bold text-left hover:bg-blue-100 transition-all">1. Qualité & Formation 2.0</button>
                    <button onclick="showMissionDetail('ci')" id="btn-ci" class="mission-btn bg-white border-2 border-transparent text-slate-700 hover:border-slate-300 p-4 rounded-xl font-bold text-left transition-all shadow-sm">2. Amélioration Continue</button>
                    <button onclick="showMissionDetail('data')" id="btn-data" class="mission-btn bg-white border-2 border-transparent text-slate-700 hover:border-slate-300 p-4 rounded-xl font-bold text-left transition-all shadow-sm">3. Data & Gouvernance</button>
                    <button onclick="showMissionDetail('client')" id="btn-client" class="mission-btn bg-white border-2 border-transparent text-slate-700 hover:border-slate-300 p-4 rounded-xl font-bold text-left transition-all shadow-sm">4. Valeur Client (Comité de Pil.)</button>
                </div>

                <div id="mission-detail-panel" class="bg-white p-8 rounded-2xl shadow-md border border-slate-200 min-h-[250px]"></div>
            </div>
        </section>

        <!-- SECTION 3: PERIMETRE TRANSVERSAL -->
        <section id="perimetre" class="min-h-full flex flex-col justify-center mb-24 pt-10 md:pt-0">
            <div class="max-w-5xl w-full">
                <h2 class="text-sm font-bold text-emerald-600 uppercase tracking-widest mb-2">Impact Transversal</h2>
                <h3 class="text-3xl font-bold text-slate-900 mb-6">De l'annonce de recrutement à la facture client</h3>
                
                <div class="flex flex-col md:flex-row justify-between items-center space-y-6 md:space-y-0 relative">
                    <div class="hidden md:block absolute top-1/2 left-0 w-full h-1 bg-slate-200 -z-10 transform -translate-y-1/2"></div>
                    <div class="bg-white w-full md:w-1/4 p-6 rounded-xl shadow-lg border border-slate-100 relative group cursor-pointer" onclick="updateFlowText('recrutement')">
                        <div class="absolute -top-4 -left-4 bg-emerald-500 text-white w-8 h-8 rounded-full flex items-center justify-center font-bold">1</div>
                        <h4 class="font-bold text-slate-800 text-center mb-2">Recrutement & Onboarding</h4>
                        <div class="text-center text-2xl mb-2">🤝</div>
                    </div>
                    <div class="bg-white w-full md:w-1/4 p-6 rounded-xl shadow-lg border border-slate-100 relative group cursor-pointer" onclick="updateFlowText('prod')">
                        <div class="absolute -top-4 -left-4 bg-blue-500 text-white w-8 h-8 rounded-full flex items-center justify-center font-bold">2</div>
                        <h4 class="font-bold text-slate-800 text-center mb-2">Production & QM</h4>
                        <div class="text-center text-2xl mb-2">🎧</div>
                    </div>
                    <div class="bg-white w-full md:w-1/4 p-6 rounded-xl shadow-lg border border-slate-100 relative group cursor-pointer" onclick="updateFlowText('client')">
                        <div class="absolute -top-4 -left-4 bg-purple-500 text-white w-8 h-8 rounded-full flex items-center justify-center font-bold">3</div>
                        <h4 class="font-bold text-slate-800 text-center mb-2">Satisfaction & Upsell</h4>
                        <div class="text-center text-2xl mb-2">⭐</div>
                    </div>
                </div>

                <div class="mt-8 bg-slate-100 p-6 rounded-xl border-l-4 border-slate-400" id="flow-detail-text">
                    <p class="text-slate-700"><em>Cliquez sur une étape ci-dessus pour voir le rôle du Performance Manager.</em></p>
                </div>
            </div>
        </section>

        <!-- SECTION 4: INCENTIVES -->
        <section id="incentives" class="min-h-full flex flex-col justify-center mb-24 pt-10 md:pt-0">
            <div class="max-w-6xl w-full">
                <h2 class="text-sm font-bold text-blue-600 uppercase tracking-widest mb-2">Modèle de Rémunération</h2>
                <h3 class="text-3xl font-bold text-slate-900 mb-8">Critères de Succès & Incentives</h3>
                
                <div class="grid grid-cols-1 lg:grid-cols-2 gap-10">
                    <div class="space-y-4">
                        <div class="bg-white p-5 rounded-xl border border-slate-200 shadow-sm">
                            <h4 class="font-bold text-slate-800 flex items-center"><span class="mr-2 text-emerald-500">💰</span> 1. Rentabilité & Marge</h4>
                            <p class="text-sm text-slate-600 mt-1">Baisse du coût par contact, réduction des erreurs, optimisation AHT.</p>
                        </div>
                        <div class="bg-white p-5 rounded-xl border border-slate-200 shadow-sm">
                            <h4 class="font-bold text-slate-800 flex items-center"><span class="mr-2 text-blue-500">⭐</span> 2. Qualité & CX</h4>
                            <p class="text-sm text-slate-600 mt-1">Progression QS, CSAT, NPS, CES et bonus contractuels clients.</p>
                        </div>
                        <div class="bg-white p-5 rounded-xl border border-slate-200 shadow-sm">
                            <h4 class="font-bold text-slate-800 flex items-center"><span class="mr-2 text-purple-500">📈</span> 3. Performance Sales / Business</h4>
                            <p class="text-sm text-slate-600 mt-1">Amélioration conversion, rétention et hausse panier moyen.</p>
                        </div>
                    </div>
                    <div class="flex flex-col items-center justify-center bg-white p-6 rounded-2xl shadow-lg border border-slate-100">
                        <h4 class="font-bold text-slate-700 mb-4 text-center">Équilibre des KPIs du Performance Manager</h4>
                        <div class="chart-container">
                            <canvas id="kpiRadarChart"></canvas>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- SECTION 5: AI LAB ✨ -->
        <section id="ai-lab" class="min-h-full flex flex-col justify-center pb-20 pt-10 md:pt-0">
            <div class="max-w-5xl w-full">
                <div class="flex items-center mb-2">
                    <span class="text-2xl mr-2">✨</span>
                    <h2 class="text-sm font-bold text-emerald-600 uppercase tracking-widest">Lab IA Performance (Powered by Gemini)</h2>
                </div>
                <h3 class="text-3xl font-bold text-slate-900 mb-8">Outils d'aide à la décision stratégique</h3>

                <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                    
                    <!-- Tool 1: Action Plan Generator -->
                    <div class="bg-white p-6 rounded-2xl shadow-xl border border-emerald-100 flex flex-col">
                        <h4 class="text-xl font-bold text-slate-800 mb-4 flex items-center">
                            Générateur de Plan d'Action ✨
                        </h4>
                        <p class="text-sm text-slate-600 mb-4">Décrivez un problème (ex: "Baisse de CSAT sur le projet Telco") pour obtenir une roadmap structurée.</p>
                        <textarea id="ai-problem-input" class="flex-1 p-3 border border-slate-200 rounded-lg text-sm mb-4 focus:ring-2 focus:ring-emerald-500 outline-none h-32" placeholder="Ex: Le temps de traitement moyen a augmenté de 20% ce mois-ci sur le pôle SAV..."></textarea>
                        <button onclick="generateActionPlan()" id="btn-gen-action" class="bg-emerald-600 hover:bg-emerald-700 text-white font-bold py-3 px-4 rounded-lg transition-all flex items-center justify-center">
                            Générer la Roadmap ✨
                        </button>
                    </div>

                    <!-- Tool 2: Feedback Analyzer -->
                    <div class="bg-white p-6 rounded-2xl shadow-xl border border-emerald-100 flex flex-col">
                        <h4 class="text-xl font-bold text-slate-800 mb-4 flex items-center">
                            Analyseur de Feedback Client ✨
                        </h4>
                        <p class="text-sm text-slate-600 mb-4">Collez des verbatims clients (positifs ou négatifs) pour identifier des leviers de performance.</p>
                        <textarea id="ai-feedback-input" class="flex-1 p-3 border border-slate-200 rounded-lg text-sm mb-4 focus:ring-2 focus:ring-emerald-500 outline-none h-32" placeholder="Collez les verbatims ici..."></textarea>
                        <button onclick="analyzeFeedback()" id="btn-analyze-feedback" class="bg-blue-600 hover:bg-blue-700 text-white font-bold py-3 px-4 rounded-lg transition-all flex items-center justify-center">
                            Analyser les Verbatims ✨
                        </button>
                    </div>

                </div>

                <!-- AI Output Display -->
                <div id="ai-output-container" class="mt-8 hidden">
                    <div class="bg-slate-900 text-slate-100 p-8 rounded-2xl shadow-2xl relative">
                        <div class="flex justify-between items-center mb-6">
                            <h5 class="text-emerald-400 font-bold uppercase tracking-widest text-xs">Résultat Analyse IA</h5>
                            <button onclick="closeAiOutput()" class="text-slate-400 hover:text-white">✕</button>
                        </div>
                        <div id="ai-result-content" class="prose prose-invert max-w-none text-slate-200 leading-relaxed whitespace-pre-line">
                            <!-- AI Content will appear here -->
                        </div>
                    </div>
                </div>
            </div>
        </section>

    </main>

    <!-- JavaScript Logic -->
    <script>
        const apiKey = ""; // Runtime provided key

        // --- Navigation Logic ---
        function navTo(sectionId) {
            document.querySelectorAll('.nav-link').forEach(link => {
                link.classList.remove('active', 'bg-blue-600', 'text-white', 'font-semibold');
                link.classList.add('text-slate-300', 'hover:bg-slate-800');
            });
            const activeLink = document.getElementById(`nav-${sectionId}`);
            if(activeLink) {
                activeLink.classList.remove('text-slate-300', 'hover:bg-slate-800');
                activeLink.classList.add('active', 'bg-blue-600', 'text-white', 'font-semibold');
            }

            const section = document.getElementById(sectionId);
            const mainContent = document.getElementById('main-content');
            mainContent.scrollTo({
                top: section.offsetTop - mainContent.offsetTop,
                behavior: 'smooth'
            });
        }

        // --- Gemini API Integration ---
        async function callGemini(prompt, systemInstruction) {
            const url = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-09-2025:generateContent?key=${apiKey}`;
            const payload = {
                contents: [{ parts: [{ text: prompt }] }],
                systemInstruction: { parts: [{ text: systemInstruction }] }
            };

            for (let i = 0; i < 5; i++) {
                try {
                    const response = await fetch(url, {
                        method: 'POST',
                        headers: { 'Content-Type': 'application/json' },
                        body: JSON.stringify(payload)
                    });
                    if (!response.ok) throw new Error('API request failed');
                    const data = await response.json();
                    return data.candidates?.[0]?.content?.parts?.[0]?.text || "Erreur : aucune réponse générée.";
                } catch (error) {
                    const delay = Math.pow(2, i) * 1000;
                    await new Promise(resolve => setTimeout(resolve, delay));
                }
            }
            return "Désolé, une erreur technique est survenue après plusieurs tentatives. Veuillez réessayer plus tard.";
        }

        function showAiLoader(btnId) {
            const btn = document.getElementById(btnId);
            btn.disabled = true;
            btn.innerHTML = `<span class="spinner"></span> Analyse en cours...`;
            document.getElementById('ai-output-container').classList.add('hidden');
        }

        function hideAiLoader(btnId, originalText) {
            const btn = document.getElementById(btnId);
            btn.disabled = false;
            btn.innerHTML = originalText;
        }

        async function generateActionPlan() {
            const problem = document.getElementById('ai-problem-input').value;
            if (!problem.trim()) return;

            showAiLoader('btn-gen-action');
            const systemPrompt = "Tu es un Performance Manager expert en BPO. Ta mission est de transformer un problème opérationnel en plan d'action structuré : Cause identifiée, Action prévue, Propriétaire, Délai, Impact attendu (CX/Coût). Sois concis, pragmatique, et utilise un ton professionnel et direct. Réponds en français.";
            const result = await callGemini(problem, systemPrompt);
            
            displayAiResult(result);
            hideAiLoader('btn-gen-action', 'Générer la Roadmap ✨');
        }

        async function analyzeFeedback() {
            const feedbacks = document.getElementById('ai-feedback-input').value;
            if (!feedbacks.trim()) return;

            showAiLoader('btn-analyze-feedback');
            const systemPrompt = "Tu es un expert en Quality Monitoring et CX. Analyse les verbatims clients fournis pour en extraire : 1. Les irritants majeurs. 2. Des recommandations concrètes pour la grille de qualité ou les scripts agents. 3. Des pistes d'amélioration pour créer de la valeur perçue. Sois très précis et analytique. Réponds en français.";
            const result = await callGemini(feedbacks, systemPrompt);
            
            displayAiResult(result);
            hideAiLoader('btn-analyze-feedback', 'Analyser les Verbatims ✨');
        }

        function displayAiResult(text) {
            const container = document.getElementById('ai-output-container');
            const content = document.getElementById('ai-result-content');
            content.innerText = text;
            container.classList.remove('hidden');
            container.scrollIntoView({ behavior: 'smooth' });
        }

        function closeAiOutput() {
            document.getElementById('ai-output-container').classList.add('hidden');
        }

        // --- Missions Tab Logic ---
        const missionData = {
            qa: { icon: '🎧', title: 'Qualité & Formation 2.0', content: `<ul class="list-disc pl-5 space-y-2 text-slate-700"><li><strong>Moderniser le QM :</strong> Transition vers le Speech Analytics (IA).</li><li><strong>Coaching ciblé :</strong> Accompagnement sur les comportements créateurs de valeur.</li><li><strong>Refonte des formations :</strong> Aligner les modules sur les réalités terrain.</li></ul>` },
            ci: { icon: '🚀', title: 'Amélioration Continue', content: `<ul class="list-disc pl-5 space-y-2 text-slate-700"><li><strong>Roadmaps ciblées :</strong> Piloter 3 à 5 chantiers prioritaires.</li><li><strong>Méthodologie :</strong> Cause, action, propriétaire, délai, impact.</li><li><strong>Réduire le gaspillage :</strong> Éliminer les contacts à faible valeur ajoutée.</li></ul>` },
            data: { icon: '📊', title: 'Data & Gouvernance', content: `<ul class="list-disc pl-5 space-y-2 text-slate-700"><li><strong>Source of Truth :</strong> Tableaux de bord croisés (Prod/RH/Qualité).</li><li><strong>Suivi impact :</strong> Mesure du ROI des décisions stratégiques.</li><li><strong>Alerting :</strong> Identifier les dérives avant l'impact client.</li></ul>` },
            client: { icon: '🤝', title: 'Valeur Client & Maturité', content: `<ul class="list-disc pl-5 space-y-2 text-slate-700"><li><strong>Copils stratégiques :</strong> Passer de l'opérationnel au structurel.</li><li><strong>Monétiser la Qualité :</strong> Modèles de rémunération au résultat.</li><li><strong>Alignement :</strong> Adapter le service à la valeur perçue par le client.</li></ul>` }
        };

        function showMissionDetail(id) {
            document.querySelectorAll('.mission-btn').forEach(btn => {
                btn.classList.remove('bg-blue-50', 'border-blue-500', 'text-blue-700');
                btn.classList.add('bg-white', 'border-transparent', 'text-slate-700');
            });
            const activeBtn = document.getElementById(`btn-${id}`);
            activeBtn.classList.remove('bg-white', 'border-transparent', 'text-slate-700');
            activeBtn.classList.add('bg-blue-50', 'border-blue-500', 'text-blue-700');
            const data = missionData[id];
            document.getElementById('mission-detail-panel').innerHTML = `<div class="flex items-center mb-4"><span class="text-4xl mr-4">${data.icon}</span><h4 class="text-2xl font-bold text-slate-800">${data.title}</h4></div>${data.content}`;
        }

        // --- Flow Logic ---
        const flowData = {
            recrutement: { color: 'emerald', title: 'Recrutement & Intégration', text: "Analyse des corrélations entre profils recrutés, turnover et résultats de formation." },
            prod: { color: 'blue', title: 'Production & QM', text: "QM orienté coaching, optimisation AHT et mesure de performance quotidienne." },
            client: { color: 'purple', title: 'Satisfaction Client', text: "Transformation des verbatims en actions et évolution vers des Copils stratégiques." }
        };

        function updateFlowText(step) {
            const container = document.getElementById('flow-detail-text');
            const data = flowData[step];
            container.className = `mt-8 p-6 rounded-xl border-l-4 bg-${data.color}-50 border-${data.color}-500 transition-all duration-300`;
            container.innerHTML = `<h5 class="font-bold text-${data.color}-700 text-lg mb-2">${data.title}</h5><p class="text-slate-700">${data.text}</p>`;
        }

        // --- Charts ---
        document.addEventListener('DOMContentLoaded', () => {
            showMissionDetail('qa');
            const ctx = document.getElementById('kpiRadarChart').getContext('2d');
            new Chart(ctx, {
                type: 'radar',
                data: {
                    labels: ['Rentabilité', 'Qualité (NPS/CSAT)', 'Conformité', 'Ventes', 'Rétention Agents'],
                    datasets: [{
                        label: 'Variable PM',
                        data: [35, 25, 15, 15, 10],
                        backgroundColor: 'rgba(37, 99, 235, 0.2)',
                        borderColor: 'rgba(37, 99, 235, 1)',
                        pointBackgroundColor: 'rgba(16, 185, 129, 1)',
                        borderWidth: 2
                    }]
                },
                options: {
                    responsive: true,
                    maintainAspectRatio: false,
                    scales: { r: { ticks: { display: false, max: 40 }, pointLabels: { font: { size: 10 } } } },
                    plugins: { legend: { display: false } }
                }
            });
        });
    </script>
</body>
</html>
