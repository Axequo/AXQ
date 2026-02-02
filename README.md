<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AXQ - The Great Deflation</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body { background-color: #050505; color: white; font-family: 'Inter', sans-serif; }
        .solana-gradient { background: linear-gradient(90deg, #9945FF, #14F195); -webkit-background-clip: text; -webkit-text-fill-color: transparent; }
        .stats-card { background: rgba(255, 255, 255, 0.03); border: 1px solid rgba(255, 255, 255, 0.1); }
    </style>
</head>
<body>
    <div class="max-w-4xl mx-auto px-6 py-16 text-center">
        <h1 class="text-7xl font-black solana-gradient mb-2 tracking-tighter uppercase">AXQ</h1>
        <p class="text-zinc-500 uppercase tracking-[0.3em] text-sm mb-12">Solana Deflationary Protocol</p>

        <div class="grid grid-cols-1 md:grid-cols-3 gap-4 mb-12">
            <div class="stats-card p-6 rounded-3xl opacity-60">
                <p class="text-zinc-500 text-xs uppercase mb-1">Original Supply</p>
                <div class="text-xl font-mono">1,000,000,000</div>
            </div>
            <div class="flex items-center justify-center text-green-400 text-2xl font-bold">
                →
            </div>
            <div class="stats-card p-6 rounded-3xl border-green-500/50">
                <p class="text-green-400 text-xs uppercase mb-1">Final Goal</p>
                <div class="text-3xl font-mono font-bold">10,000</div>
            </div>
        </div>

        <div class="stats-card p-10 rounded-3xl mb-12">
            <p class="text-zinc-500 text-xs uppercase mb-2">Current Live Supply</p>
            <div id="supply-count" class="text-6xl font-mono font-bold tracking-tight text-white">1,000,000,000</div>
            
            <div id="status-box" class="mt-8 p-6 rounded-2xl bg-green-500/10 border border-green-500/20">
                <p id="system-msg" class="text-2xl font-semibold leading-tight text-green-300 italic uppercase">Initializing The Great Burn...</p>
            </div>
        </div>

        <button class="bg-white text-black px-12 py-5 rounded-full font-black hover:scale-105 transition uppercase tracking-widest text-sm">Connect Wallet</button>

        <p class="mt-16 text-zinc-600 text-sm max-w-xl mx-auto">
            From 1 Billion to 10,000 units. A 99.999% reduction. <br>
            <span class="text-zinc-400 uppercase font-bold">Scarcity is the only mission.</span>
        </p>
    </div>

    <script>
        const START_SUPPLY = 1000000000;
        const TARGET_SUPPLY = 10000;

        function updateDeflation(current) {
            const supplyDisplay = document.getElementById('supply-count');
            const msg = document.getElementById('system-msg');
            supplyDisplay.innerText = current.toLocaleString();

            if (current <= TARGET_SUPPLY) {
                msg.innerText = "🏆 YOU MADE IT! ONLY 10,000 UNITS REMAIN!";
            } else if (current <= 100000) {
                msg.innerText = "LEGENDARY LEVEL! ALMOST AT THE FINISH LINE! 💎";
            } else if (current <= 1000000) {
                msg.innerText = "DIAMOND LEVEL! UNDER 1 MILLION UNITS LEFT! 🔥";
            } else if (current <= 500000000) {
                msg.innerText = "GOLD LEVEL! 50% OF THE WORLD SUPPLY BURNED! 🚀";
            } else {
                msg.innerText = "THE JOURNEY TO 10,000 UNITS HAS BEGUN! ✨";
            }
        }
        
        // Simulación inicial
        updateDeflation(1000000000); 
    </script>
</body>
</html>
