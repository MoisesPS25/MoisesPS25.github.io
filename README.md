# moisesps25.github.io
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI Resume Generator | M.CUNHA</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&display=swap');
        body { font-family: 'Inter', sans-serif; background-color: #0f172a; color: #f1f5f9; }
        .neon-border { border: 1px solid rgba(34, 211, 238, 0.3); box-shadow: 0 0 15px rgba(34, 211, 238, 0.1); }
        .neon-text { text-shadow: 0 0 8px rgba(34, 211, 238, 0.6); }
        .preview-container { filter: blur(2px); transition: filter 0.5s ease; user-select: none; }
        .resume-paper { background: white; color: #1e293b; box-shadow: 0 25px 50px -12px rgba(0,0,0,0.5); }
        .circuit-overlay { display: none; position: fixed; inset: 0; background: rgba(15, 23, 42, 0.9); z-index: 100; justify-content: center; align-items: center; flex-direction: column; }
        .loader-line { width: 200px; height: 2px; background: rgba(34, 211, 238, 0.2); position: relative; overflow: hidden; }
        .loader-line::after { content: ''; position: absolute; left: -100%; width: 100%; height: 100%; background: #22d3ee; animation: flow 1.5s infinite; }
        @keyframes flow { 100% { left: 100%; } }
    </style>
</head>
<body>

    <div id="loader" class="circuit-overlay">
        <div class="mb-4 text-cyan-400 font-bold tracking-widest">PROCESSANDO IA M.CUNHA...</div>
        <div class="loader-line"></div>
    </div>

    <header class="p-5 border-b border-slate-800 bg-slate-900/80 backdrop-blur-md sticky top-0 z-40">
        <div class="container mx-auto flex justify-between items-center">
            <h1 class="text-xl font-black tracking-tighter neon-text">CURRÍCULO <span class="text-cyan-400">IA</span></h1>
            <div class="text-xs uppercase tracking-widest text-slate-500">M.CUNHA • Tecnologia ATS</div>
        </div>
    </header>

    <main class="container mx-auto p-4 lg:p-10 grid grid-cols-1 lg:grid-cols-2 gap-10">
        <section class="space-y-6">
            <div class="neon-border p-6 rounded-3xl bg-slate-800/30">
                <h2 class="text-cyan-400 font-semibold mb-6 flex items-center gap-2">Dados do Profissional</h2>
                <input type="text" id="nome" placeholder="Seu Nome Completo" class="w-full bg-slate-900 border border-slate-700 p-4 rounded-xl focus:ring-2 focus:ring-cyan-500 outline-none text-white mb-4">
                <input type="text" id="cargo" placeholder="Cargo (Ex: Faturamento Médico)" class="w-full bg-slate-900 border border-slate-700 p-4 rounded-xl focus:ring-2 focus:ring-cyan-500 outline-none text-white">
            </div>

            <button onclick="gerarCurriculo()" class="w-full py-5 bg-cyan-500 hover:bg-cyan-400 text-slate-900 font-black rounded-2xl transition-all shadow-[0_0_30px_rgba(34,211,238,0.3)]">
                GERAR PRÉVIA AGORA
            </button>
        </section>

        <section class="relative">
            <div id="preview-area" class="resume-paper rounded-sm p-12 min-h-[600px] relative preview-container">
                <h1 class="text-3xl font-bold uppercase" id="out-nome text-slate-900">NOME DO CANDIDATO</h1>
                <p class="text-cyan-700 font-bold mb-4" id="out-cargo">CARGO PRETENDIDO</p>
                <div class="space-y-4">
                    <div class="h-3 bg-slate-100 rounded"></div>
                    <div class="h-3 bg-slate-100 rounded w-5/6"></div>
                    <div class="h-3 bg-slate-100 rounded w-4/6"></div>
                </div>
                <div class="absolute inset-0 flex items-center justify-center opacity-5 rotate-12 pointer-events-none">
                    <span class="text-6xl font-black">PRÉVIA BLOQUEADA</span>
                </div>
            </div>
            
            <div class="mt-6 p-4 bg-slate-800 rounded-xl text-center border border-cyan-500/20">
                <p class="text-sm text-slate-400 mb-2">Desbloquear PDF Profissional + Bônus WhatsApp</p>
                <span class="text-cyan-400 font-bold">R$ 1,99</span>
            </div>
        </section>
    </main>

    <script>
        function gerarCurriculo() {
            document.getElementById('loader').style.display = 'flex';
            setTimeout(() => {
                document.getElementById('loader').style.display = 'none';
                document.getElementById('out-nome').innerText = document.getElementById('nome').value || "Moisés Pedro";
                document.getElementById('out-cargo').innerText = document.getElementById('cargo').value || "Especialista";
                alert("Prévia gerada com sucesso! Analisando padrões ATS...");
            }, 2000);
        }
    </script>
</body>
</html>
