<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MY GAMING BLOG - IGN Style</title>
    <link href="https://fonts.googleapis.com/css2?family=Oswald:wght@500;700&family=Roboto:wght@400;500&display=swap" rel="stylesheet">
    <style>
        /* --- CSS 变量定义 --- */
        :root {
            --ign-red: #bf1313;
            --bg-dark: #121212;
            --bg-card: #1f1f1f;
            --text-white: #ffffff;
            --text-gray: #b0b0b0;
            --gap: 20px;
        }

        * { margin: 0; padding: 0; box-sizing: border-box; }

        body {
            background-color: var(--bg-dark);
            color: var(--text-white);
            font-family: 'Roboto', sans-serif;
        }

        h1, h2, h3, .nav-link {
            font-family: 'Oswald', sans-serif;
            text-transform: uppercase;
        }

        a { text-decoration: none; color: inherit; transition: 0.3s; }

        /* --- 导航栏 --- */
        .navbar {
            background: #000;
            padding: 0 40px;
            height: 60px;
            display: flex;
            align-items: center;
            position: sticky;
            top: 0;
            z-index: 1000;
            border-bottom: 3px solid var(--ign-red);
        }

        .logo {
            font-size: 28px;
            font-weight: 700;
            color: var(--ign-red);
            margin-right: 40px;
        }

        .nav-links { display: flex; gap: 25px; }
        .nav-link { font-weight: 500; font-size: 14px; letter-spacing: 1px; }
        .nav-link:hover { color: var(--ign-red); }

        /* --- Hero 区域 (头图) --- */
        .hero {
            height: 60vh;
            position: relative;
            background: url('https://images.unsplash.com/photo-1542751371-adc38448a05e?ixlib=rb-4.0.3&auto=format&fit=crop&w=1920&q=80') center/cover no-repeat;
            display: flex;
            align-items: flex-end;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            background: linear-gradient(to bottom, transparent 50%, var(--bg-dark) 100%);
        }

        .hero-content {
            position: relative;
            z-index: 2;
            padding: 40px;
            max-width: 800px;
        }

        .hero-tag {
            background: var(--ign-red);
            padding: 4px 8px;
            font-size: 12px;
            font-weight: bold;
            text-transform: uppercase;
            display: inline-block;
            margin-bottom: 10px;
        }

        .hero-title { font-size: 48px; line-height: 1.1; margin-bottom: 10px; }
        .hero-subtitle { color: var(--text-gray); font-size: 18px; }

        /* --- 内容网格 --- */
        .container {
            max-width: 1200px;
            margin: 40px auto;
            padding: 0 20px;
        }

        .section-title {
            font-size: 24px;
            margin-bottom: 20px;
            border-left: 5px solid var(--ign-red);
            padding-left: 15px;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 25px;
        }

        /* --- IGN 风格卡片 --- */
        .card {
            background: var(--bg-card);
            border-radius: 4px;
            overflow: hidden;
            transition: transform 0.2s ease;
            position: relative;
        }

        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.5);
        }

        .card-img-wrapper {
            position: relative;
            width: 100%;
            padding-top: 56.25%; /* 16:9 比例 */
        }

        .card-img {
            position: absolute;
            top: 0; left: 0; width: 100%; height: 100%;
            object-fit: cover;
        }

        /* --- 评分六边形 --- */
        .rating-badge {
            position: absolute;
            bottom: -15px;
            right: 15px;
            width: 50px;
            height: 50px;
            background-color: var(--ign-red);
            clip-path: polygon(25% 0%, 75% 0%, 100% 50%, 75% 100%, 25% 100%, 0% 50%);
            display: flex;
            justify-content: center;
            align-items: center;
            font-family: 'Oswald', sans-serif;
            font-weight: 700;
            font-size: 20px;
            color: white;
            z-index: 10;
            box-shadow: 0 2px 5px rgba(0,0,0,0.5);
        }

        .card-content { padding: 25px 15px 15px; } /* Top padding 为评分留位置 */
        
        .card-meta {
            font-size: 11px;
            color: var(--ign-red);
            font-weight: bold;
            text-transform: uppercase;
            margin-bottom: 5px;
        }

        .card-title { font-size: 18px; line-height: 1.3; margin-bottom: 8px; }
        .card-excerpt { font-size: 13px; color: var(--text-gray); line-height: 1.5; }

        /* --- 底部 --- */
        footer {
            background: #000;
            padding: 40px;
            margin-top: 60px;
            text-align: center;
            border-top: 1px solid #333;
        }
        
        /* 移动端适配 */
        @media (max-width: 768px) {
            .hero-title { font-size: 32px; }
            .navbar { padding: 0 20px; }
        }
    </style>
</head>
<body>

    <!-- 导航栏 -->
    <nav class="navbar">
        <div class="logo">MYBLOG</div>
        <div class="nav-links">
            <a href="#" class="nav-link">News</a>
            <a href="#" class="nav-link">Reviews</a>
            <a href="#" class="nav-link">Videos</a>
            <a href="#" class="nav-link">Tech</a>
        </div>
    </nav>

    <!-- Hero 首屏 -->
    <header class="hero">
        <div class="hero-content">
            <span class="hero-tag">Featured Review</span>
            <h1 class="hero-title">赛博朋克 2077: 往日之影 深度评测</h1>
            <p class="hero-subtitle">夜之城从未如此迷人，也从未如此危险。</p>
        </div>
    </header>

    <!-- 主要内容区 -->
    <div class="container">
        <h2 class="section-title">LATEST REVIEWS</h2>
        
        <div class="grid">
            <!-- 卡片 1 (带评分) -->
            <article class="card">
                <a href="#">
                    <div class="card-img-wrapper">
                        <img src="https://images.unsplash.com/photo-1538481199705-c710c4e965fc?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" class="card-img" alt="Game 1">
                        <!-- 评分徽章 -->
                        <div class="rating-badge">9.5</div>
                    </div>
                    <div class="card-content">
                        <div class="card-meta">PlayStation 5</div>
                        <h3 class="card-title">战神：诸神黄昏 - 史诗般的终结</h3>
                        <p class="card-excerpt">奎托斯与阿特柔斯的旅程达到了情感的高潮...</p>
                    </div>
                </a>
            </article>

            <!-- 卡片 2 (带评分) -->
            <article class="card">
                <a href="#">
                    <div class="card-img-wrapper">
                        <img src="https://images.unsplash.com/photo-1552820728-8b83bb6b773f?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" class="card-img" alt="Game 2">
                        <div class="rating-badge">8.0</div>
                    </div>
                    <div class="card-content">
                        <div class="card-meta">PC / Steam</div>
                        <h3 class="card-title">艾尔登法环：DLC 试玩报告</h3>
                        <p class="card-excerpt">虽然难度依旧，但新的地图探索感无与伦比...</p>
                    </div>
                </a>
            </article>

            <!-- 卡片 3 (新闻，无评分) -->
            <article class="card">
                <a href="#">
                    <div class="card-img-wrapper">
                        <img src="https://images.unsplash.com/photo-1593640408182-31c70c8268f5?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" class="card-img" alt="News">
                    </div>
                    <div class="card-content">
                        <div class="card-meta">Hardware</div>
                        <h3 class="card-title">RTX 5090 传闻汇总：发布日期与规格</h3>
                        <p class="card-excerpt">英伟达的下一代显卡可能比我们想象的要来得更早。</p>
                    </div>
                </a>
            </article>

            <!-- 卡片 4 -->
            <article class="card">
                <a href="#">
                    <div class="card-img-wrapper">
                        <img src="https://images.unsplash.com/photo-1605901309584-818e25960b8f?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" class="card-img" alt="Game 4">
                        <div class="rating-badge">7.5</div>
                    </div>
                    <div class="card-content">
                        <div class="card-meta">Xbox Series X</div>
                        <h3 class="card-title">星空 (Starfield) - 一年后值得回坑吗？</h3>
                        <p class="card-excerpt">在多次更新补丁后，这款太空RPG现在的表现如何？</p>
                    </div>
                </a>
            </article>
        </div>
    </div>

    <footer>
        <p>&copy; 2023 My Gaming Blog. Inspired by IGN.</p>
    </footer>

</body>
</html>
