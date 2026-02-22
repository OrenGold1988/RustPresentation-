
in html
take this code

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8"/>
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=1280, height=720, initial-scale=1.0"/>
    <title>OpenTitan: First Commercial Open-Source RoT</title>

    <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet" crossorigin="anonymous"/>
    <link href="https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@6.4.0/css/all.min.css" rel="stylesheet" crossorigin="anonymous"/>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;700;800&display=swap" rel="stylesheet"/>

    <style>
        :root {
            --bg-1: #0f172a;
            --bg-gradient: radial-gradient(circle at 50% 50%, #1e293b 0%, #0f172a 100%);
            --accent: #38bdf8; 
            --text: #ffffff;
            --card-bg: rgba(30, 41, 59, 0.7); 
        }

        html, body { 
            height: 100%; 
            margin: 0; 
            padding: 0; 
            overflow: hidden; 
            background: var(--bg-1);
            background: var(--bg-gradient);
            color: var(--text);
            font-family: 'Inter', sans-serif;
        }

        .slide-container {
            width: 100vw;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            padding: 0 60px; 
            animation: fadeIn 0.8s ease-out;
        }

        .main-title {
            font-size: 64px;
            font-weight: 800;
            margin-bottom: 15px;
            line-height: 1.1;
            letter-spacing: -0.02em;
        }

        .title-highlight { 
            color: var(--accent);
            text-shadow: 0 0 20px rgba(56, 189, 248, 0.4);
        }

        .definition-box {
            max-width: 85%;
            font-size: 26px;
            line-height: 1.5;
            color: #cbd5e1;
            margin-bottom: 40px;
            border-left: 4px solid var(--accent);
            padding-left: 20px;
        }

        .purpose-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr); 
            gap: 25px;
            width: 100%;
        }

        .purpose-card {
            background: var(--card-bg);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-left: 8px solid var(--accent);
            padding: 30px;
            border-radius: 12px;
            transition: all 0.3s ease;
            display: flex;
            flex-direction: column;
            animation: fadeInUp 0.6s ease-out both;
        }

        /* Staggered animation for cards */
        .purpose-card:nth-child(1) { animation-delay: 0.2s; }
        .purpose-card:nth-child(2) { animation-delay: 0.3s; }
        .purpose-card:nth-child(3) { animation-delay: 0.4s; }
        .purpose-card:nth-child(4) { animation-delay: 0.5s; }

        .purpose-card:hover {
            transform: translateY(-5px);
            background: rgba(30, 41, 59, 0.9);
            box-shadow: 0 20px 40px rgba(0,0,0,0.4), 0 0 15px rgba(56, 189, 248, 0.2);
            border-color: var(--accent);
        }

        .card-title {
            font-weight: 800;
            font-size: 20px;
            color: var(--accent);
            margin-bottom: 15px;
            text-transform: uppercase;
            letter-spacing: 0.05em;
        }

        .tech-tag {
            color: #fff;
            font-weight: 700;
            display: block;
            margin-bottom: 10px;
            font-size: 24px; 
        }

        .card-text { 
            font-size: 20px; 
            color: #94a3b8; 
            line-height: 1.5; 
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

       .bottom-nav {
            position: fixed; 
            bottom: 30px; 
            left: 50px; 
            right: 50px;
            display: flex; 
            justify-content: space-between;
        }

        .nav-btn {
            display: inline-flex; 
            align-items: center; 
            gap: 12px;
            padding: 16px 36px; 
            border-radius: 999px; /* Pill shape */
            color: #0f172a; 
            text-decoration: none;
            font-weight: 800; 
            font-size: 22px; 
            background-color: var(--accent);
            box-shadow: 0 8px 20px rgba(0,0,0,0.3);
            transition: transform 0.2s ease, opacity 0.2s ease;
        }
        
        /* Matching the "Previous" button color from the second slide */
        .nav-prev { 
            background-color: #cbd5e1; 
        }
        .nav-btn:hover {
            transform: translateY(-2px);
            opacity: 0.95;
        }
        
    </style>
</head>
<body>

<div class="slide-container">
    <header>
        <h1 class="main-title">
            <span class="title-highlight">OpenTitan:</span><br>
            Open-Source Root of Trust
        </h1>
        
        <div class="definition-box">
            OpenTitan is a paradigm shift in silicon security, moving away from "black-box" proprietary designs to a <strong>fully transparent, independently verifiable</strong> Root of Trust.
        </div>
    </header>

    <div class="purpose-grid">
        <div class="purpose-card">
            <div class="card-title"><i class="fas fa-eye mr-2"></i> Transparency</div>
            <div class="card-text">
                <span class="tech-tag">"No More Black Boxes"</span>
                Logical design is open for public audit, ensuring no hidden backdoors or proprietary vulnerabilities.
            </div>
        </div>

        <div class="purpose-card">
            <div class="card-title"><i class="fas fa-handshake mr-2"></i> Vendor Neutrality</div>
            <div class="card-text">
                <span class="tech-tag">"Supply Chain Resilience"</span>
                Prevents vendor lock-in. If a manufacturer changes terms, the community-owned design remains accessible.
            </div>
        </div>

        <div class="purpose-card">
            <div class="card-title"><i class="fas fa-chart-line mr-2"></i> Shared Innovation</div>
            <div class="card-text">
                <span class="tech-tag">"Cost Reduction"</span>
                Shared R&D on "non-differentiating" security foundations accelerates time-to-market for all partners.
            </div>
        </div>

        <div class="purpose-card">
            <div class="card-title"><i class="fas fa-shield-halved mr-2"></i> Absolute Integrity</div>
            <div class="card-text">
                <span class="tech-tag">"Rust-Based Ecosystem"</span>
                Pairs with TockOS to provide memory-safe security logic from the very first moment of boot.
            </div>
        </div>
    </div>

    <nav class="bottom-nav">
        <a class="nav-btn nav-prev" href="nuvoton_2.html">
            <i class="fas fa-arrow-left"></i>
            <span>Previous</span>
        </a>
        <a class="nav-btn" href="ot_1.html">
            <span>Next Slide</span>
            <i class="fas fa-arrow-right"></i>
        </a>
    </nav>
</div>

</body>
</html>



match the next code to look like the previous code

in backround color font size and text color

includeing the vevagation buttons

give me back the full html code
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8"/>
<meta content="width=1280, height=720" name="viewport"/>
<title>What Is OpenTitan?</title>
<link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet"/>
<link href="https://cdn.jsdelivr.net/npm/@fortawesome/fontawesome-free@6.4.0/css/all.min.css" rel="stylesheet"/>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700;800&display=swap" rel="stylesheet"/>
<style>
    :root{
        --bg:#0f172a;
        --accent:#3b82f6;
        --accent-2:#8b5cf6;
        --muted:#94a3b8;
        --text:#ffffff;
        --nav-height: 80px;
    }
    html, body { height: 100%; overflow: hidden; }
    body {
        margin: 0; padding: 0;
        font-family: 'Inter', sans-serif;
        background: var(--bg);
        color: var(--text);
        background-image:
            radial-gradient(900px 600px at 90% -10%, #1e293b 0%, var(--bg) 60%),
            radial-gradient(700px 500px at -10% 110%, #0b1222 0%, var(--bg) 60%);
        animation: bgPulse 14s ease-in-out infinite alternate;
    }

    .slide-container {
        width: 100vw; height: 100vh;
        display: flex; flex-direction: column;
        position: relative; overflow: hidden;
        isolation: isolate;
    }

    .header {
        padding: 50px 80px 30px 80px;
        border-bottom: 2px solid rgba(59, 130, 246, 0.3);
        position: relative; z-index: 2;
    }
    .slide-title {
        font-size: 48px; font-weight: 800;
        line-height: 1.15; letter-spacing: -0.02em;
        opacity: 0; transform: translateY(10px);
        animation: fadeInDown 750ms ease-out forwards 80ms;
    }
    .title-highlight { color: var(--accent); }

    .content-wrapper {
        flex: 1;
        padding: 50px 80px calc(var(--nav-height) + 20px) 80px !important;
        display: grid;
        grid-template-columns: 1fr 280px; 
        gap: 60px;
        align-items: center;
        position: relative; z-index: 2;
    }

    /* Summary Box Styling to match the previous page */
    .summary-section {
        opacity: 0;
        animation: fadeUp 800ms ease-out forwards 200ms;
    }

    .summary-text {
        font-size: 24px;
        line-height: 1.6;
        color: #e2e8f0;
    }

    .accent-text {
        color: var(--accent);
        font-weight: 700;
    }

    .logo-sidebar {
        display: flex; flex-direction: column;
        gap: 20px; align-items: center;
        padding: 20px;
        background: rgba(255, 255, 255, 0.03);
        border: 1px solid rgba(255, 255, 255, 0.1);
        border-radius: 16px;
        backdrop-filter: blur(8px);
        opacity: 0; animation: fadeIn 1s ease-out forwards 600ms;
    }
    .logo-sidebar img {
        max-width: 180px; height: auto;
        filter: brightness(0.9) contrast(1.1);
        transition: transform 0.3s ease;
        border-radius: 4px;
    }
    .logo-sidebar img:hover { transform: scale(1.05); }
    .sidebar-label {
        font-size: 12px; font-weight: 700; color: var(--muted);
        text-transform: uppercase; letter-spacing: 0.1em; margin-bottom: 10px;
    }

    .decorative-element {
        position: absolute; border-radius: 50%; opacity: 0.06;
        z-index: 0; pointer-events: none;
    }
    .circle-1 { width: 350px; height: 350px; background-color: var(--accent); top: -100px; right: -80px; animation: floatRight 18s ease-in-out infinite; }
    .circle-2 { width: 250px; height: 250px; background-color: var(--accent-2); bottom: -80px; left: -60px; animation: floatLeft 20s ease-in-out infinite; }
    
    .bottom-nav {
        position: fixed; bottom: 0; left: 0; right: 0;
        height: var(--nav-height); padding: 0 60px;
        display: flex; justify-content: space-between; align-items: center;
        background: linear-gradient(180deg, rgba(15,23,42,0) 0%, rgba(15,23,42,0.95) 100%);
        z-index: 100;
    }
    .nav-btn {
        display: inline-flex; align-items: center; gap: 10px;
        padding: 10px 22px; border-radius: 999px; text-decoration: none;
        font-weight: 700; font-size: 16px; color: white;
        box-shadow: 0 10px 28px rgba(0,0,0,0.35); transition: all 180ms ease;
    }
    .nav-prev { background: #4b5563; }
    .nav-next { background: #2563eb; }
    .nav-btn:hover { transform: translateY(-2px); filter: brightness(1.1); }

    @keyframes fadeUp { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }
    @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
    @keyframes fadeInDown { from { opacity: 0; transform: translateY(-10px); } to { opacity: 1; transform: translateY(0); } }
    @keyframes floatRight { 0%, 100% { transform: translate(0, 0); } 50% { transform: translate(-14px, 10px); } }
    @keyframes floatLeft { 0%, 100% { transform: translate(0, 0); } 50% { transform: translate(14px, -10px); } }
    @keyframes bgPulse { 0% { filter: hue-rotate(0deg); } 100% { filter: hue-rotate(6deg); } }
</style>
</head>
<body>
<div class="slide-container">
    <div class="decorative-element circle-1"></div>
    <div class="decorative-element circle-2"></div>

    <div class="header">
        <h1 class="slide-title">
            The <span class="title-highlight">OpenTitan</span> Collaboration
        </h1>
    </div>

    <div class="content-wrapper">
        <div class="summary-section">
            <p class="summary-text">
                While Google provided the high-level security architecture and vision,<br>
                <span class="accent-text">Nuvoton was the critical partner that turned "code into silicon."</span><br><br>
                Open-source designs are just blueprints (RTL) until a semiconductor expert like <span class="accent-text">Nuvoton applies the engineering required to manufacture them at scale</span>.<br>
                The OpenTitan project is a strategic union designed to bridge the gap between 
                <span class="accent-text">security and commercial hardware</span>.<br><br>
                Nuvoton brings essential <span class="accent-text">manufacturing and Security IC expertise</span> to the table, turning transparent RTL designs into mass-produced, commercial-grade chips. This ensures that the hardware can be <span class="accent-text">independently audited and verified</span>, meeting the growing global demand for a trustworthy, open-source Root of Trust in everything from data centers to critical infrastructure.
            </p>
        </div>

        <div class="logo-sidebar">
            <span class="sidebar-label">Partners</span>
            <img src="Data\Nuvoton_Technology_logo.svg.jpg" alt="Nuvoton">
            <img src="Data\pngimg.com - google_PNG19644.jpg" alt="Google">
            <img src="Data\lowrisc.jpg" alt="RISC-V">
            <img src="Data\giesecke.jpg" alt="Giesecke">
            <img src="Data\ethz_zurich.jpg" alt="ETH Zurich">
        </div>
    </div>

    <div class="bottom-nav">
        <a class="nav-btn nav-prev" href="index_ot.html"><i class="fas fa-arrow-left"></i><span>Previous Slide</span></a>
        <a class="nav-btn nav-next" href="ot_2.html"><span>Next Slide</span><i class="fas fa-arrow-right"></i></a>
    </div>
</div>
</body>
</html>

give me the full html code back