<!DOCTYPE html>
<html lang="hi">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PYASI GLOBAL 🚩 - All-In-One Empire</title>
    <script src="https://unpkg.com/@solana/web3.js@latest/lib/index.iife.min.js"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        :root { --gold: #ff9933; --neon: #14F195; --bg: #050505; }
        body { background: var(--bg); color: #fff; font-family: 'Poppins', sans-serif; margin: 0; text-align: center; overflow-x: hidden; }
        .hero { padding: 80px 20px; background: radial-gradient(circle, #222 0%, #000 100%); border-bottom: 3px solid var(--gold); }
        .glitch { font-size: 80px; font-weight: 900; color: var(--gold); text-shadow: 0 0 20px var(--gold); margin: 0; letter-spacing: 15px; }
        .grid-container { display: grid; grid-template-columns: repeat(auto-fit, minmax(300px, 1fr)); gap: 20px; padding: 40px; max-width: 1200px; margin: auto; }
        .card { background: #111; border: 1px solid #333; border-radius: 25px; padding: 30px; transition: 0.4s; position: relative; overflow: hidden; }
        .card:hover { border-color: var(--gold); transform: translateY(-10px); box-shadow: 0 10px 40px rgba(255,153,51,0.2); }
        .btn { display: block; width: 100%; padding: 18px; margin: 15px 0; border-radius: 15px; font-weight: bold; border: none; cursor: pointer; font-size: 18px; text-decoration: none; transition: 0.3s; }
        .btn-solana { background: linear-gradient(45deg, #9945FF, #14F195); color: #000; }
        .btn-upi { background: #fff; color: #000; }
        .btn-mint { background: var(--gold); color: #000; }
        .qr-img { background: #fff; padding: 10px; border-radius: 15px; width: 180px; margin: 15px auto; }
        .social-links a { font-size: 40px; color: #fff; margin: 0 15px; transition: 0.3s; }
        .social-links a:hover { color: var(--gold); }
        .status-light { display: inline-block; width: 12px; height: 12px; background: var(--neon); border-radius: 50%; box-shadow: 0 0 10px var(--neon); }
    </style>
</head>
<body>

    <div class="hero">
        <h1 class="glitch">PYASI</h1>
        <p style="font-size: 20px; color: var(--gold);">786 . 214 . 1000 | <span class="status-light"></span> LIVE EMPIRE</p>
        <p>कानपुर मुख्यालय - सत्यमेव जयते</p>
    </div>

    <div class="grid-container">
        <div class="card">
            <h2 style="color: var(--neon);"><i class="fas fa-microchip"></i> Web3 Wallet</h2>
            <p>Solana नेटवर्क से जुड़ें और PYC टोकन मैनेज करें</p>
            <button class="btn btn-solana" id="connectWallet">CONNECT PHANTOM</button>
            <div id="status" style="font-size: 12px; margin-top:10px;">Status: Disconnected</div>
        </div>

        <div class="card">
            <h2 style="color: #fff;"><i class="fas fa-qrcode"></i> Instant Pay</h2>
            <p>किसी भी UPI ऐप से सीधा भुगतान करें</p>
            <div class="qr-img">
                <img src="https://api.qrserver.com/v1/create-qr-code/?size=160x160&data=upi://pay?pa=YOUR_UPI_ID@okicici&pn=ABHISHEK" style="width:100%">
            </div>
            <button class="btn btn-upi">SCAN & PAY NOW</button>
        </div>

        <div class="card">
            <h2 style="color: var(--gold);"><i class="fas fa-coins"></i> Token Factory</h2>
            <p>786 अरब सप्लाई वाला सिक्का यहाँ से पैदा करें</p>
            <a href="https://foxy-mint.xyz/" class="btn btn-mint">MINT PYASI COIN</a>
            <p style="font-size: 11px;">सप्लाई: 786,000,000,000 PYC</p>
        </div>
    </div>

    <div class="card" style="max-width: 1100px; margin: 20px auto;">
        <h3>🌎 Global Network</h3>
        <div class="social-links">
            <a href="#"><i class="fab fa-facebook"></i></a>
            <a href="#"><i class="fab fa-instagram"></i></a>
            <a href="#"><i class="fab fa-x-twitter"></i></a>
            <a href="#"><i class="fab fa-telegram"></i></a>
            <a href="#"><i class="fab fa-youtube"></i></a>
        </div>
    </div>

    <footer style="padding: 50px; color: #444;">
        © 2026 PYASI GLOBAL | Designed for the Future
    </footer>

    <script>
        const btn = document.getElementById('connectWallet');
        const status = document.getElementById('status');

        async function connect() {
            if (window.solana) {
                try {
                    const resp = await window.solana.connect();
                    status.innerText = "Wallet Connected: " + resp.publicKey.toString().substring(0,6) + "...";
                    btn.innerText = "CONNECTED ✅";
                    btn.style.background = "#14F195";
                } catch (err) { status.innerText = "User Cancelled"; }
            } else {
                alert("Phantom App का ब्राउज़र इस्तेमाल करें!");
            }
        }
        btn.addEventListener('click', connect);
    </script>
</body>
</html>
