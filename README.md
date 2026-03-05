<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PYASI GLOBAL - Solana Web3 Hub</title>
    <script src="https://unpkg.com/@solana/web3.js@latest/lib/index.iife.min.js"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        :root { --solana-green: #14F195; --solana-purple: #9945FF; --gold: #ff9933; }
        body { background: #000; color: #fff; font-family: 'Poppins', sans-serif; margin: 0; text-align: center; }
        .hero-section { padding: 60px 20px; background: linear-gradient(135deg, #111, #000); border-bottom: 2px solid var(--solana-green); }
        .brand { font-size: 70px; font-weight: 900; letter-spacing: 10px; color: var(--gold); text-shadow: 0 0 20px var(--gold); margin: 0; }
        .action-box { background: rgba(255,255,255,0.05); border: 1px solid #333; border-radius: 25px; padding: 30px; margin: 20px auto; max-width: 500px; backdrop-filter: blur(10px); }
        .web3-btn { background: linear-gradient(45deg, var(--solana-purple), var(--solana-green)); color: #000; padding: 18px 30px; border-radius: 50px; border: none; font-weight: bold; font-size: 20px; cursor: pointer; transition: 0.3s; width: 100%; box-shadow: 0 0 15px var(--solana-green); }
        .web3-btn:hover { transform: scale(1.05); box-shadow: 0 0 25px var(--solana-purple); }
        .status { margin-top: 15px; color: var(--solana-green); font-family: monospace; word-break: break-all; }
        .social-row { display: flex; justify-content: center; gap: 25px; margin-top: 40px; font-size: 35px; }
        .social-row a { color: #fff; transition: 0.3s; }
        .social-row a:hover { color: var(--gold); }
    </style>
</head>
<body>

    <div class="hero-section">
        <h1 class="brand">PYASI</h1>
        <p style="letter-spacing: 3px;">🚩 786 | 214 | 1000 ● SOLANA NETWORK 🚩</p>
    </div>

    <div class="action-box">
        <h3>🪙 PYASI Token Ecosystem</h3>
        <p>Solana वॉलेट कनेक्ट करें और ट्रांजैक्शन शुरू करें</p>
        <button class="web3-btn" id="connectBtn">
            <i class="fas fa-wallet"></i> CONNECT SOLANA WALLET
        </button>
        <div id="walletStatus" class="status"></div>
    </div>

    <div class="action-box">
        <h3>🔗 Digital Connect</h3>
        <div class="social-row">
            <a href="https://facebook.com/your_id"><i class="fab fa-facebook"></i></a>
            <a href="https://instagram.com/your_id"><i class="fab fa-instagram"></i></a>
            <a href="https://x.com/your_id"><i class="fab fa-x-twitter"></i></a>
            <a href="https://youtube.com/your_id"><i class="fab fa-youtube"></i></a>
        </div>
    </div>

    <footer style="padding: 40px; color: #444; font-size: 14px;">
        कानपुर मुख्यालय | सत्यमेव जयते | Powered by Solana Web3
    </footer>

    <script>
        // Solana Wallet Connection Logic
        const connectBtn = document.getElementById('connectBtn');
        const walletStatus = document.getElementById('walletStatus');

        async function connectWallet() {
            const isPhantomInstalled = window.solana && window.solana.isPhantom;

            if (isPhantomInstalled) {
                try {
                    const response = await window.solana.connect();
                    const pubKey = response.publicKey.toString();
                    walletStatus.innerHTML = "✅ Connected!<br>Wallet ID: " + pubKey.substring(0,6) + "..." + pubKey.substring(pubKey.length - 4);
                    connectBtn.innerHTML = "WALLET CONNECTED";
                    connectBtn.style.background = "#14F195";
                } catch (err) {
                    console.error("Connect Error:", err);
                    walletStatus.innerText = "Connection Cancelled";
                }
            } else {
                walletStatus.innerHTML = "❌ Phantom Wallet नहीं मिला! <br> <a href='https://phantom.app/' target='_blank' style='color:white;'>यहाँ से डाउनलोड करें</a>";
            }
        }

        connectBtn.addEventListener('click', connectWallet);
    </script>

</body>
</html>
