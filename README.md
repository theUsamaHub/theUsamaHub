<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Usama Saleem · GitHub profile</title>
    <!-- Font Awesome for some extra icons (optional but clean) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        /* global reset / smooth fonts */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(145deg, #f0f4fa 0%, #e6ecf5 100%);
            font-family: 'Segoe UI', Roboto, system-ui, -apple-system, BlinkMacSystemFont, 'Helvetica Neue', sans-serif;
            display: flex;
            justify-content: center;
            padding: 2rem 1rem;
            line-height: 1.5;
            color: #1e2a41;
        }

        /* card container — simulates GitHub README style but polished */
        .profile-card {
            max-width: 1100px;
            width: 100%;
            background-color: #ffffffdd;
            backdrop-filter: blur(2px);
            background: #ffffff;
            border-radius: 2.5rem;
            box-shadow: 0 25px 45px -12px rgba(0,20,40,0.35), 0 4px 12px rgba(0,0,0,0.08);
            padding: 2.5rem 2.8rem;
            border: 1px solid rgba(255,255,255,0.6);
        }

        /* header with wave and name */
        .profile-header {
            display: flex;
            align-items: center;
            gap: 1rem;
            margin-bottom: 1.2rem;
            flex-wrap: wrap;
        }
        .avatar-emoji {
            font-size: 3.8rem;
            line-height: 1;
            filter: drop-shadow(2px 6px 8px rgba(0,80,120,0.2));
        }
        .name-title h1 {
            font-size: 2.6rem;
            font-weight: 700;
            letter-spacing: -0.5px;
            background: linear-gradient(140deg, #1f2b4b, #2f4172);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 0.2rem;
        }
        .badge {
            background: #0e75b6;
            color: white;
            padding: 0.3rem 1rem;
            border-radius: 40px;
            font-weight: 500;
            font-size: 1.1rem;
            display: inline-block;
            box-shadow: 0 6px 12px #0e75b630;
        }
        .badge i {
            margin-right: 6px;
            font-size: 1rem;
        }

        /* profile view counter + trophy row */
        .stats-row {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: space-between;
            margin: 1.8rem 0 2rem 0;
            background: #f2f6fd;
            padding: 0.8rem 1.8rem;
            border-radius: 60px;
            border: 1px solid #cdddf5;
        }
        .view-counter {
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 1.2rem;
        }
        .view-counter img {
            height: 26px;
            border-radius: 20px;
        }
        .trophy-img {
            max-width: 400px;
        }
        .trophy-img img {
            max-width: 100%;
            display: block;
            border-radius: 40px;
        }

        /* about section (work, learn, etc) */
        .about-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 1.6rem;
            margin: 2.5rem 0 2rem;
        }
        .about-item {
            background: #f7faff;
            padding: 1.2rem 1.5rem;
            border-radius: 2rem;
            border-left: 6px solid #0e75b6;
            box-shadow: 0 6px 14px #dadef0;
            transition: 0.15s ease;
        }
        .about-item:hover {
            transform: translateY(-3px);
            background: #ffffff;
        }
        .about-item .icon {
            font-size: 2rem;
            margin-right: 12px;
            color: #0e75b6;
        }
        .about-item h3 {
            display: flex;
            align-items: center;
            font-weight: 600;
            font-size: 1.4rem;
            margin-bottom: 0.8rem;
            color: #13273e;
        }
        .about-item p {
            font-size: 1.05rem;
            color: #24455f;
            margin-left: 0.3rem;
        }
        .about-item a {
            color: #0e75b6;
            font-weight: 500;
            text-decoration: none;
        }
        .about-item a:hover {
            text-decoration: underline;
        }

        /* connect & tools combined sections */
        .connect-tools {
            display: flex;
            flex-wrap: wrap;
            gap: 1.8rem;
            margin: 2.2rem 0 2.5rem;
        }
        .connect {
            flex: 1 1 240px;
            background: linear-gradient(135deg, #f1f7fe, #e7f0fd);
            border-radius: 2rem;
            padding: 1.5rem 1.8rem;
        }
        .connect h3, .tools-head h3 {
            font-size: 1.6rem;
            font-weight: 600;
            margin-bottom: 1.2rem;
            display: flex;
            align-items: center;
            gap: 10px;
            color: #163A5F;
        }
        .social-links {
            display: flex;
            gap: 1.5rem;
            align-items: center;
        }
        .social-links a {
            display: inline-block;
            transition: 0.2s;
        }
        .social-links a img {
            width: 48px;
            height: 48px;
            background: white;
            border-radius: 50%;
            padding: 8px;
            box-shadow: 0 8px 18px #0e75b640;
        }
        .social-links a:hover {
            transform: scale(1.1) rotate(3deg);
        }

        .tools-head {
            flex: 3 1 500px;
            background: #ffffff;
            border-radius: 2rem;
            padding: 1.5rem 1.8rem;
            box-shadow: inset 0 2px 8px #f0f5ff, 0 8px 18px #d4e0f0;
        }
        .icons-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem 1.8rem;
            align-items: center;
        }
        .icons-grid a {
            display: inline-flex;
            align-items: center;
            gap: 6px;
            background: #f2f8ff;
            padding: 0.4rem 1.2rem 0.4rem 0.8rem;
            border-radius: 40px;
            text-decoration: none;
            color: #1f3b5c;
            font-weight: 500;
            box-shadow: 0 4px 8px #bfd6f0;
            transition: 0.1s;
            border: 1px solid transparent;
        }
        .icons-grid a:hover {
            background: #ddeeff;
            border-color: #0e75b6;
        }
        .icons-grid a img {
            height: 36px;
            width: 36px;
            object-fit: contain;
        }
        /* special for mssql plain svg (use custom style) */
        .mssql-icon {
            display: inline-block;
            width: 36px;
            height: 36px;
            background: #a12d2d; /* fallback */
            mask: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 128 128"><path fill="%23a12d2d" d="M17.5 29.3L64 6.5l46.5 22.8v66.9L64 119.5 17.5 96.2V29.3zm88.7 8.9L64 21.7 29.8 43.8 64 65.9l34.2-22.1v40.3l19.1 9.4V38.2zM41.8 86.2l18.4 9.3v-18L41.8 68.2v18zm42.7-18l-18.4 9.3v18l18.4-9.3v-18z"/></svg>') no-repeat center;
            background: #b53b3b;
            mask-size: contain;
        }

        /* stats panels */
        .stats-panels {
            display: flex;
            flex-wrap: wrap;
            gap: 1.8rem;
            margin: 2.5rem 0 1rem;
            align-items: center;
            justify-content: center;
        }
        .stat-card {
            background: white;
            border-radius: 2rem;
            padding: 1.2rem 1.8rem;
            box-shadow: 0 18px 28px -12px #2f4f8b40;
            flex: 1 1 280px;
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            border: 1px solid #bed9ff;
        }
        .stat-card img {
            max-width: 100%;
            border-radius: 18px;
            margin-top: 8px;
        }
        .compact-langs img {
            max-height: 180px;
        }

        .streak-card {
            flex: 1 1 320px;
        }
        .streak-card img {
            max-width: 100%;
        }

        /* bottom separator */
        .footer-note {
            margin-top: 2.8rem;
            font-size: 1rem;
            color: #4f658d;
            text-align: center;
            border-top: 2px dashed #b3cef0;
            padding-top: 1.8rem;
        }
        .footer-note i {
            color: #e65b5b;
        }

        /* small adjustments */
        @media (max-width: 700px) {
            .profile-card { padding: 1.8rem; }
            .name-title h1 { font-size: 2rem; }
        }
    </style>
</head>
<body>
    <div class="profile-card">

        <!-- header with name and passionate -->
        <div class="profile-header">
            <span class="avatar-emoji">👋</span>
            <div class="name-title">
                <h1>I'm Usama Saleem</h1>
                <span class="badge"><i class="fas fa-code"></i> passionate C# developer</span>
            </div>
        </div>

        <!-- profile views + trophy (exact images) -->
        <div class="stats-row">
            <div class="view-counter">
                <img src="https://komarev.com/ghpvc/?username=theUsamaHub&label=Profile%20views&color=0e75b6&style=flat" alt="profile views">
                <span style="font-weight:450;">profile views</span>
            </div>
            <div class="trophy-img">
                <img src="https://github-profile-trophy.vercel.app/?username=theUsamaHub" alt="GitHub trophies">
            </div>
        </div>

        <!-- what i'm doing grid -->
        <div class="about-grid">
            <div class="about-item">
                <h3><span class="icon">🔭</span> working on</h3>
                <p><strong>Auth system</strong> in .NET CORE WebAPI (personal project)</p>
            </div>
            <div class="about-item">
                <h3><span class="icon">🌱</span> learning</h3>
                <p>Flutter & Dart — building cross‑platform magic</p>
            </div>
            <div class="about-item">
                <h3><span class="icon">👯</span> collaborate on</h3>
                <p>.NET CORE MVC, Laravel, .NET CORE WebAPI</p>
            </div>
            <div class="about-item">
                <h3><span class="icon">📫</span> reach me</h3>
                <p><a href="mailto:u641332@gmail.com">u641332@gmail.com</a></p>
            </div>
            <div class="about-item">
                <h3><span class="icon">⚡</span> fun fact</h3>
                <p>I think I am good at explaining 👨‍🏫</p>
            </div>
        </div>

        <!-- connect + languages/tools combined row -->
        <div class="connect-tools">
            <!-- connect section -->
            <div class="connect">
                <h3><i class="fas fa-user-plus"></i> Connect with me</h3>
                <div class="social-links">
                    <a href="https://github.com/theUsamaHub" target="_blank" rel="noopener">
                        <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/github.svg" alt="GitHub">
                    </a>
                    <!-- you can add more official socials later, but original markdown only had GitHub -->
                    <span style="color:#1e3b5c; opacity:0.7; font-style:italic;">theUsamaHub</span>
                </div>
                <!-- small extra: github direct link -->
                <p style="margin-top:1rem;"><i class="fab fa-github"></i> <a href="https://github.com/theUsamaHub" style="color:#0e75b6;">@theUsamaHub</a></p>
            </div>

            <!-- Languages and tools (with skill icons) -->
            <div class="tools-head">
                <h3><i class="fas fa-laptop-code"></i> Languages & Tools</h3>
                <div class="icons-grid">
                    <!-- csharp -->
                    <a href="#"><img src="https://skillicons.dev/icons?i=cs" alt="csharp"> C#</a>
                    <a href="#"><img src="https://skillicons.dev/icons?i=css" alt="css"> CSS</a>
                    <a href="#"><img src="https://skillicons.dev/icons?i=dart" alt="dart"> Dart</a>
                    <a href="#"><img src="https://skillicons.dev/icons?i=docker" alt="docker"> Docker</a>
                    <a href="#"><img src="https://skillicons.dev/icons?i=dotnet" alt="dotnet"> .NET</a>
                    <a href="#"><img src="https://skillicons.dev/icons?i=figma" alt="figma"> Figma</a>
                    <a href="#"><img src="https://skillicons.dev/icons?i=flutter" alt="flutter"> Flutter</a>
                    <a href="#"><img src="https://skillicons.dev/icons?i=git" alt="git"> Git</a>
                    <a href="#"><img src="https://skillicons.dev/icons?i=html" alt="html"> HTML</a>
                    <a href="#"><img src="https://skillicons.dev/icons?i=js" alt="js"> JS</a>
                    <a href="#"><img src="https://skillicons.dev/icons?i=laravel" alt="laravel"> Laravel</a>
                    <!-- mssql custom fallback + icon -->
                    <a href="#">
                        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/microsoftsqlserver/microsoftsqlserver-plain.svg" alt="mssql" width="36" height="36" style="background:transparent;"> MSSQL
                    </a>
                    <a href="#"><img src="https://skillicons.dev/icons?i=mysql" alt="mysql"> MySQL</a>
                    <a href="#"><img src="https://skillicons.dev/icons?i=php" alt="php"> PHP</a>
                    <a href="#"><img src="https://skillicons.dev/icons?i=postgres" alt="postgres"> PostgreSQL</a>
                </div>
                <p style="margin-top:1rem; font-size:0.9rem; color:#526e8a;"><i class="fas fa-tools"></i> also experienced with MSSQL, Docker, and more</p>
            </div>
        </div>

        <!-- GitHub stats row (top langs, stats, streak) exactly from source -->
        <div class="stats-panels">
            <div class="stat-card compact-langs">
                <h4><i class="fas fa-chart-pie"></i> top languages</h4>
                <img src="https://github-readme-stats.vercel.app/api/top-langs?username=theUsamaHub&show_icons=true&locale=en&layout=compact" alt="most used languages">
            </div>
            <div class="stat-card">
                <h4><i class="fas fa-thermometer-half"></i> GitHub stats</h4>
                <img src="https://github-readme-stats.vercel.app/api?username=theUsamaHub&show_icons=true&locale=en" alt="github stats">
            </div>
            <div class="stat-card streak-card">
                <h4><i class="fas fa-fire"></i> streak</h4>
                <img src="https://github-readme-streak-stats.herokuapp.com/?user=theUsamaHub&" alt="streak stats">
            </div>
        </div>

        <!-- Extra subtle fun footnote (but keep original information) -->
        <div class="footer-note">
            <i class="fas fa-heart" style="color:#dc4c4c;"></i> craft with .NET & Flutter • always explaining <i class="fas fa-smile-wink"></i>
        </div>

        <!-- hidden note: all links / images preserved as original markdown -->
    </div>
</body>
</html>
