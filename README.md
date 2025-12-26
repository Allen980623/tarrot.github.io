<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>完整塔罗牌占卜 - 78张牌全收录</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 50%, #0f3460 100%);
            color: #e6e6ff;
            min-height: 100vh;
            padding: 20px;
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        header {
            text-align: center;
            margin-bottom: 40px;
            padding: 20px;
            border-bottom: 1px solid rgba(255, 255, 255, 0.1);
        }

        h1 {
            font-size: 2.8rem;
            margin-bottom: 10px;
            color: #d4af37;
            text-shadow: 0 0 10px rgba(212, 175, 55, 0.5);
        }

        .subtitle {
            font-size: 1.2rem;
            opacity: 0.8;
            max-width: 600px;
            margin: 0 auto;
        }

        /* 抽牌按钮区域 */
        .draw-section {
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 300px;
        }

        .draw-btn {
            background: linear-gradient(to bottom right, #9d4edd, #560bad);
            color: white;
            border: none;
            padding: 25px 60px;
            font-size: 1.8rem;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.4s ease;
            box-shadow: 0 10px 25px rgba(157, 78, 221, 0.4);
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .draw-btn:hover {
            transform: translateY(-8px);
            box-shadow: 0 15px 30px rgba(157, 78, 221, 0.6);
        }

        /* 洗牌动画区域 */
        .shuffle-section {
            min-height: 400px;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .shuffle-container {
            text-align: center;
        }

        .shuffle-cards {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-bottom: 30px;
            position: relative;
            height: 200px;
        }

        .card-shuffle {
            width: 140px;
            height: 220px;
            background: linear-gradient(145deg, #3a0ca3, #4361ee);
            border-radius: 12px;
            position: absolute;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.5);
            animation: shuffle 2s infinite ease-in-out;
        }

        /* 洗牌动画关键帧 */
        @keyframes shuffle {
            0%, 100% { transform: translateY(0px) rotate(-5deg); }
            25% { transform: translateY(-30px) rotate(5deg); }
            50% { transform: translateY(0px) rotate(-8deg); }
            75% { transform: translateY(-20px) rotate(2deg); }
        }

        .shuffle-text {
            font-size: 1.5rem;
            color: #d4af37;
            animation: pulse 1.5s infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 0.7; }
            50% { opacity: 1; }
        }

        /* 结果区域 */
        .result-section {
            text-align: center;
            animation: fadeIn 1s ease-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        .instruction {
            font-size: 1.3rem;
            margin-bottom: 40px;
            color: #b8b8ff;
        }

        .cards-container {
            display: flex;
            justify-content: center;
            gap: 30px;
            flex-wrap: wrap;
            margin-bottom: 50px;
        }

        /* 卡牌样式 - 背面 */
        .tarot-card {
            width: 220px;
            height: 340px;
            perspective: 1000px;
            cursor: pointer;
            transition: transform 0.3s;
        }

        .tarot-card:hover {
            transform: translateY(-10px);
        }

        .card-inner {
            position: relative;
            width: 100%;
            height: 100%;
            transition: transform 0.8s;
            transform-style: preserve-3d;
        }

        .tarot-card.flipped .card-inner {
            transform: rotateY(180deg);
        }

        .card-front, .card-back {
            position: absolute;
            width: 100%;
            height: 100%;
            backface-visibility: hidden;
            border-radius: 15px;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.4);
            overflow: hidden;
        }

        /* 卡牌背面 - 六芒星设计 */
        .card-back {
            background: linear-gradient(145deg, #0a1128, #001f54);
            display: flex;
            justify-content: center;
            align-items: center;
            border: 2px solid #d4af37;
        }

        /* 使用CSS绘制六芒星 */
        .hexagram {
            width: 120px;
            height: 120px;
            position: relative;
            background: #d4af37;
            clip-path: polygon(
                50% 0%, 61% 35%, 98% 35%, 68% 57%,
                79% 91%, 50% 70%, 21% 91%, 32% 57%,
                2% 35%, 39% 35%
            );
            box-shadow: 0 0 20px rgba(212, 175, 55, 0.7);
        }

        /* 卡牌正面 */
        .card-front {
            background: white;
            color: #333;
            transform: rotateY(180deg);
            display: flex;
            flex-direction: column;
        }

        .card-image {
            height: 75%;
            background-size: cover;
            background-position: center;
            border-top-left-radius: 15px;
            border-top-right-radius: 15px;
            background-color: #f5f5f5;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
        }

        .card-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .card-info {
            padding: 15px;
            height: 25%;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .card-name {
            font-weight: bold;
            font-size: 1.2rem;
            margin-bottom: 5px;
            color: #1a1a2e;
        }

        .card-orientation {
            font-size: 0.9rem;
            padding: 3px 10px;
            border-radius: 20px;
            display: inline-block;
            width: fit-content;
            margin: 0 auto 8px;
        }

        .upright {
            background-color: #4cc9f0;
            color: #1a1a2e;
        }

        .reversed {
            background-color: #f72585;
            color: white;
        }

        .card-position {
            font-size: 0.9rem;
            color: #666;
        }

        /* 解读区域 */
        .interpretation {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 15px;
            padding: 25px;
            margin: 40px auto;
            max-width: 900px;
            text-align: left;
            border-left: 5px solid #d4af37;
        }

        .interpretation h3 {
            color: #d4af37;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .meanings {
            margin-top: 20px;
        }

        .meaning-item {
            background: rgba(255, 255, 255, 0.03);
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 15px;
        }

        .meaning-item h4 {
            color: #b8b8ff;
            margin-bottom: 8px;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        /* 重置按钮 */
        .reset-btn {
            background: rgba(255, 255, 255, 0.1);
            color: white;
            border: 1px solid rgba(255, 255, 255, 0.3);
            padding: 15px 40px;
            font-size: 1.2rem;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            margin-top: 20px;
        }

        .reset-btn:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-3px);
        }

        /* 占卜历史 */
        .history-section {
            margin-top: 40px;
            padding-top: 20px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        .history-container {
            display: flex;
            overflow-x: auto;
            gap: 15px;
            padding: 10px 0;
        }

        .history-card {
            min-width: 100px;
            height: 150px;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 8px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 10px;
            cursor: pointer;
            transition: transform 0.2s;
        }

        .history-card:hover {
            transform: translateY(-5px);
            background: rgba(255, 255, 255, 0.1);
        }

        .history-card-name {
            font-size: 0.8rem;
            margin-top: 5px;
            text-align: center;
        }

        /* 响应式设计 */
        @media (max-width: 768px) {
            .cards-container {
                flex-direction: column;
                align-items: center;
            }
            
            h1 {
                font-size: 2.2rem;
            }
            
            .draw-btn {
                padding: 20px 40px;
                font-size: 1.5rem;
            }
            
            .tarot-card {
                width: 200px;
                height: 310px;
            }
        }
        
        /* 占卜类型选择 */
        .spread-options {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 20px;
            flex-wrap: wrap;
        }
        
        .spread-option {
            background: rgba(255, 255, 255, 0.05);
            padding: 15px 25px;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s;
            border: 1px solid transparent;
        }
        
        .spread-option:hover {
            background: rgba(255, 255, 255, 0.1);
            border-color: #d4af37;
        }
        
        .spread-option.active {
            background: rgba(212, 175, 55, 0.2);
            border-color: #d4af37;
        }
        
        .spread-option h3 {
            font-size: 1.2rem;
            margin-bottom: 5px;
        }
        
        .spread-option p {
            font-size: 0.9rem;
            opacity: 0.8;
        }
        
        /* 加载状态 */
        .loading {
            text-align: center;
            padding: 30px;
        }
        
        .spinner {
            border: 5px solid rgba(255, 255, 255, 0.1);
            border-top: 5px solid #d4af37;
            border-radius: 50%;
            width: 50px;
            height: 50px;
            animation: spin 1s linear infinite;
            margin: 0 auto 20px;
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        /* 图片占位符 */
        .placeholder-image {
            width: 80%;
            height: 80%;
            background: linear-gradient(45deg, #f5f5f5 25%, #e0e0e0 25%, #e0e0e0 50%, #f5f5f5 50%, #f5f5f5 75%, #e0e0e0 75%, #e0e0e0);
            background-size: 20px 20px;
            border-radius: 8px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #999;
            font-size: 0.9rem;
            text-align: center;
            padding: 10px;
        }
        
        /* 牌面图片样式 */
        .card-img-placeholder {
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
            color: #666;
            font-size: 0.8rem;
            text-align: center;
            padding: 10px;
        }
        
        /* 进度条 */
        .progress-container {
            width: 100%;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            margin: 20px 0;
            overflow: hidden;
        }
        
        .progress-bar {
            height: 10px;
            background: linear-gradient(to right, #9d4edd, #560bad);
            width: 0%;
            transition: width 0.5s ease;
        }
        
        /* 牌面信息 */
        .card-suit {
            font-size: 0.8rem;
            color: #888;
            margin-top: 2px;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1><i class="fas fa-star-and-crescent"></i> 完整塔罗牌占卜</h1>
            <p class="subtitle">包含78张完整塔罗牌，每张牌都有正位和逆位解读</p>
            
            <div class="progress-container">
                <div class="progress-bar" id="progressBar"></div>
            </div>
            <p id="progressText">准备中...</p>
            
            <div class="spread-options">
                <div class="spread-option active" data-spread="three-cards">
                    <h3>三张牌阵</h3>
                    <p>过去、现在、未来</p>
                </div>
                <div class="spread-option" data-spread="celtic-cross">
                    <h3>凯尔特十字</h3>
                    <p>10张牌，全面分析</p>
                </div>
                <div class="spread-option" data-spread="single-card">
                    <h3>单张牌</h3>
                    <p>每日指引</p>
                </div>
            </div>
        </header>

        <main>
            <!-- 初始状态：显示抽牌按钮 -->
            <section class="draw-section" id="drawSection">
                <button class="draw-btn" id="drawBtn">
                    <i class="fas fa-hand-point-down"></i> 开始抽牌
                </button>
            </section>

            <!-- 洗牌动画区域 -->
            <section class="shuffle-section" id="shuffleSection" style="display:none;">
                <div class="shuffle-container">
                    <div class="shuffle-cards">
                        <!-- 洗牌动画时显示的动态卡牌 -->
                        <div class="card-shuffle"></div>
                        <div class="card-shuffle"></div>
                        <div class="card-shuffle"></div>
                    </div>
                    <p class="shuffle-text">正在洗牌中，请集中你的意念...</p>
                </div>
            </section>

            <!-- 结果显示区域 -->
            <section class="result-section" id="resultSection" style="display:none;">
                <h2 id="spreadTitle">你的牌阵已经就绪</h2>
                <p class="instruction">点击每张牌揭开其奥秘</p>
                <div class="cards-container" id="cardsContainer">
                    <!-- 卡牌将由JavaScript动态生成 -->
                </div>
                
                <!-- 解读区域 -->
                <div class="interpretation" id="interpretation">
                    <h3><i class="fas fa-book-open"></i> 综合解读</h3>
                    <p id="interpretationText">请翻开所有卡牌以查看解读。</p>
                    <div class="meanings" id="detailedMeanings"></div>
                </div>
                
                <button class="reset-btn" id="resetBtn"><i class="fas fa-redo"></i> 重新抽牌</button>
                
                <!-- 占卜历史 -->
                <div class="history-section" id="historySection" style="display:none;">
                    <h3><i class="fas fa-history"></i> 占卜历史</h3>
                    <div class="history-container" id="historyContainer"></div>
                </div>
            </section>
        </main>
    </div>

    <script>
        // 完整的78张塔罗牌数据，包含图片URL
        const tarotDeck = [
            // 大阿卡那牌 (0-21)
            {
                name: "愚者",
                number: 0,
                suit: "major",
                image: "https://www.trustedtarot.com/img/cards/the-fool.png",
                englishName: "The Fool",
                upright: {
                    meaning: "新的开始，冒险，自由，信任生活",
                    keywords: ["天真", "自由", "冒险", "信任"],
                    description: "愚者代表一段新的旅程或冒险的开始。它鼓励你相信自己的直觉，拥抱未知的可能性。"
                },
                reversed: {
                    meaning: "鲁莽，犹豫不决，风险",
                    keywords: ["鲁莽", "犹豫", "风险", "愚蠢"],
                    description: "逆位的愚者可能表示你正在做出不明智的决定，或者在面对机会时过于犹豫。"
                }
            },
            {
                name: "魔术师",
                number: 1,
                suit: "major",
                image: "https://www.trustedtarot.com/img/cards/the-magician.png",
                englishName: "The Magician",
                upright: {
                    meaning: "力量，技能，创造力，沟通",
                    keywords: ["力量", "创造力", "技能", "沟通"],
                    description: "魔术师代表你拥有实现目标所需的所有工具和资源。这是行动和显化的时刻。"
                },
                reversed: {
                    meaning: "欺骗，未使用的潜力，沟通不畅",
                    keywords: ["欺骗", "未开发潜力", "沟通问题"],
                    description: "逆位的魔术师可能表示你未能充分利用自己的能力，或者存在沟通不畅的问题。"
                }
            },
            {
                name: "女祭司",
                number: 2,
                suit: "major",
                image: "https://www.trustedtarot.com/img/cards/the-high-priestess.png",
                englishName: "The High Priestess",
                upright: {
                    meaning: "直觉，神秘，潜意识，神圣知识",
                    keywords: ["直觉", "神秘", "潜意识", "内在知识"],
                    description: "女祭司邀请你倾听自己的直觉和内在智慧。现在是关注梦境和潜意识信息的时候。"
                },
                reversed: {
                    meaning: "隐藏的信息，肤浅，忽视直觉",
                    keywords: ["隐藏", "肤浅", "忽视直觉"],
                    description: "逆位的女祭司可能表示你忽视了自己的直觉，或者某些信息被隐藏了起来。"
                }
            },
            {
                name: "女皇",
                number: 3,
                suit: "major",
                image: "https://www.trustedtarot.com/img/cards/the-empress.png",
                englishName: "The Empress",
                upright: {
                    meaning: "丰富，创造力，自然，养育",
                    keywords: ["丰富", "创造力", "自然", "养育"],
                    description: "女皇代表丰饶、创造力和与自然的连接。她鼓励你培育自己的想法和关系。"
                },
                reversed: {
                    meaning: "依赖，忽视，创造性阻碍",
                    keywords: ["依赖", "忽视", "创造性阻碍"],
                    description: "逆位的女皇可能表示创造性阻碍，或在某些方面缺乏滋养和支持。"
                }
            },
            {
                name: "皇帝",
                number: 4,
                suit: "major",
                image: "https://www.trustedtarot.com/img/cards/the-emperor.png",
                englishName: "The Emperor",
                upright: {
                    meaning: "权威，结构，稳定，领导力",
                    keywords: ["权威", "结构", "稳定", "领导力"],
                    description: "皇帝代表秩序、结构和权威。他鼓励你建立坚实的基础并为自己的领域负责。"
                },
                reversed: {
                    meaning: "控制欲，僵化，滥用权力",
                    keywords: ["控制欲", "僵化", "滥用权力"],
                    description: "逆位的皇帝可能表示过度控制、僵化或滥用权力的问题。"
                }
            },
            {
                name: "教皇",
                number: 5,
                suit: "major",
                image: "https://www.trustedtarot.com/img/cards/the-hierophant.png",
                englishName: "The Hierophant",
                upright: {
                    meaning: "传统，精神指导，教育，信仰体系",
                    keywords: ["传统", "精神指导", "教育", "信仰"],
                    description: "教皇代表传统、精神指导和既定制度。他鼓励你寻求传统智慧或精神导师的帮助。"
                },
                reversed: {
                    meaning: "叛逆，打破传统，非传统信仰",
                    keywords: ["叛逆", "打破传统", "非传统信仰"],
                    description: "逆位的教皇可能表示你正在挑战传统或探索非传统的信仰体系。"
                }
            },
            {
                name: "恋人",
                number: 6,
                suit: "major",
                image: "https://www.trustedtarot.com/img/cards/the-lovers.png",
                englishName: "The Lovers",
                upright: {
                    meaning: "爱情，和谐，伙伴关系，选择",
                    keywords: ["爱情", "和谐", "伙伴关系", "选择"],
                    description: "恋人牌代表关系、选择和价值观的一致。它可能表示重要的关系或需要做出的重大决定。"
                },
                reversed: {
                    meaning: "冲突，不和谐，错误的选择",
                    keywords: ["冲突", "不和谐", "错误选择"],
                    description: "逆位的恋人可能表示关系中的冲突、不和谐，或者你正在做出错误的决定。"
                }
            },
            {
                name: "战车",
                number: 7,
                suit: "major",
                image: "https://www.trustedtarot.com/img/cards/the-chariot.png",
                englishName: "The Chariot",
                upright: {
                    meaning: "胜利，意志力，控制，前进",
                    keywords: ["胜利", "意志力", "控制", "前进"],
                    description: "战车牌代表通过意志力和决心取得成功。它鼓励你控制自己的情绪和方向，朝着目标前进。"
                },
                reversed: {
                    meaning: "缺乏方向，失控，障碍",
                    keywords: ["缺乏方向", "失控", "障碍"],
                    description: "逆位的战车可能表示你失去了方向感，或者在某种情况下失去了控制。"
                }
            },
            {
                name: "力量",
                number: 8,
                suit: "major",
                image: "https://www.trustedtarot.com/img/cards/strength.png",
                englishName: "Strength",
                upright: {
                    meaning: "勇气，耐心，控制，同情心",
                    keywords: ["勇气", "耐心", "控制", "同情心"],
                    description: "力量牌代表内在的力量、勇气和耐心。它鼓励你以温和的方式处理挑战，而不是使用蛮力。"
                },
                reversed: {
                    meaning: "自我怀疑，软弱，缺乏纪律",
                    keywords: ["自我怀疑", "软弱", "缺乏纪律"],
                    description: "逆位的力量可能表示你正在经历自我怀疑，或者缺乏处理挑战所需的内心力量。"
                }
            },
            {
                name: "隐士",
                number: 9,
                suit: "major",
                image: "https://www.trustedtarot.com/img/cards/the-hermit.png",
                englishName: "The Hermit",
                upright: {
                    meaning: "内省，孤独，寻求真理，指导",
                    keywords: ["内省", "孤独", "寻求真理", "指导"],
                    description: "隐士代表内省、孤独和对真理的寻求。它鼓励你花时间独处，倾听内心的声音。"
                },
                reversed: {
                    meaning: "孤立，拒绝帮助，迷失",
                    keywords: ["孤立", "拒绝帮助", "迷失"],
                    description: "逆位的隐士可能表示你过于孤立自己，或者拒绝接受他人的帮助和指导。"
                }
            },
            {
                name: "命运之轮",
                number: 10,
                suit: "major",
                image: "https://www.trustedtarot.com/img/cards/wheel-of-fortune.png",
                englishName: "Wheel of Fortune",
                upright: {
                    meaning: "命运，转折点，运气，循环",
                    keywords: ["命运", "转折点", "运气", "循环"],
                    description: "命运之轮代表命运的转折点、好运和生活的循环。它表示变化是不可避免的，而且通常是积极的。"
                },
                reversed: {
                    meaning: "坏运气，抵抗变化，挫折",
                    keywords: ["坏运气", "抵抗变化", "挫折"],
                    description: "逆位的命运之轮可能表示坏运气、挫折，或者你在抵抗必要的变化。"
                }
            },
            {
                name: "正义",
                number: 11,
                suit: "major",
                image: "https://www.trustedtarot.com/img/cards/justice.png",
                englishName: "Justice",
                upright: {
                    meaning: "正义，真理，因果，法律",
                    keywords: ["正义", "真理", "因果", "法律"],
                    description: "正义牌代表真理、公正和因果报应。它鼓励你为自己的行为负责，并寻求平衡与和谐。"
                },
                reversed: {
                    meaning: "不公正，偏见，不负责任",
                    keywords: ["不公正", "偏见", "不负责任"],
                    description: "逆位的正义可能表示不公正、偏见，或者你逃避对自己行为的责任。"
                }
            },
            {
                name: "倒吊人",
                number: 12,
                suit: "major",
                image: "https://www.trustedtarot.com/img/cards/the-hanged-man.png",
                englishName: "The Hanged Man",
                upright: {
                    meaning: "牺牲，新视角，放手，等待",
                    keywords: ["牺牲", "新视角", "放手", "等待"],
                    description: "倒吊人代表牺牲、新视角和等待。它鼓励你从不同的角度看待情况，并接受必要的牺牲。"
                },
                reversed: {
                    meaning: "停滞，抗拒牺牲，自私",
                    keywords: ["停滞", "抗拒牺牲", "自私"],
                    description: "逆位的倒吊人可能表示停滞不前，或者你拒绝做出必要的牺牲以取得进展。"
                }
            },
            {
                name: "死神",
                number: 13,
                suit: "major",
                image: "https://www.trustedtarot.com/img/cards/death.png",
                englishName: "Death",
                upright: {
                    meaning: "结束，转变，新的开始，释放",
                    keywords: ["结束", "转变", "新的开始", "释放"],
                    description: "死神牌代表结束、转变和新的开始。它鼓励你释放不再为你服务的东西，为新的成长腾出空间。"
                },
                reversed: {
                    meaning: "抗拒变化，停滞，恐惧结束",
                    keywords: ["抗拒变化", "停滞", "恐惧结束"],
                    description: "逆位的死神可能表示你抗拒必要的变化，或者恐惧某种情况的结束。"
                }
            },
            {
                name: "节制",
                number: 14,
                suit: "major",
                image: "https://www.trustedtarot.com/img/cards/temperance.png",
                englishName: "Temperance",
                upright: {
                    meaning: "平衡，和谐，耐心，适度",
                    keywords: ["平衡", "和谐", "耐心", "适度"],
                    description: "节制牌代表平衡、和谐与耐心。它鼓励你寻找对立面之间的中间道路，并实践自我控制。"
                },
                reversed: {
                    meaning: "不平衡，极端，缺乏耐心",
                    keywords: ["不平衡", "极端", "缺乏耐心"],
                    description: "逆位的节制可能表示生活中的不平衡，或者你正在走向极端。"
                }
            },
            {
                name: "恶魔",
                number: 15,
                suit: "major",
                image: "https://www.trustedtarot.com/img/cards/the-devil.png",
                englishName: "The Devil",
                upright: {
                    meaning: "束缚，唯物主义，无知，欲望",
                    keywords: ["束缚", "唯物主义", "无知", "欲望"],
                    description: "恶魔牌代表束缚、唯物主义和欲望。它可能表示你被物质或消极模式所束缚。"
                },
                reversed: {
                    meaning: "释放，摆脱束缚，克服上瘾",
                    keywords: ["释放", "摆脱束缚", "克服上瘾"],
                    description: "逆位的恶魔可能表示你正在摆脱束缚，克服上瘾或消极模式。"
                }
            },
            {
                name: "高塔",
                number: 16,
                suit: "major",
                image: "https://www.trustedtarot.com/img/cards/the-tower.png",
                englishName: "The Tower",
                upright: {
                    meaning: "突然的变化，破坏，启示，解放",
                    keywords: ["突然的变化", "破坏", "启示", "解放"],
                    description: "高塔牌代表突然的变化、破坏和启示。它可能表示一个突然的事件打破了现状。"
                },
                reversed: {
                    meaning: "避免灾难，恐惧变化，压抑",
                    keywords: ["避免灾难", "恐惧变化", "压抑"],
                    description: "逆位的高塔可能表示你避免了灾难，但也在恐惧变化或压抑必要的改变。"
                }
            },
            {
                name: "星星",
                number: 17,
                suit: "major",
                image: "https://www.trustedtarot.com/img/cards/the-star.png",
                englishName: "The Star",
                upright: {
                    meaning: "希望，灵感，宁静，信心",
                    keywords: ["希望", "灵感", "宁静", "信心"],
                    description: "星星牌代表希望、灵感和信心。它鼓励你保持积极，相信未来，并跟随你的灵感。"
                },
                reversed: {
                    meaning: "绝望，缺乏信心，失望",
                    keywords: ["绝望", "缺乏信心", "失望"],
                    description: "逆位的星星可能表示绝望、缺乏信心或失望。"
                }
            },
            {
                name: "月亮",
                number: 18,
                suit: "major",
                image: "https://www.trustedtarot.com/img/cards/the-moon.png",
                englishName: "The Moon",
                upright: {
                    meaning: "幻觉，恐惧，潜意识，未知",
                    keywords: ["幻觉", "恐惧", "潜意识", "未知"],
                    description: "月亮牌代表幻觉、恐惧和潜意识。它鼓励你面对恐惧，探索未知，并信任你的直觉。"
                },
                reversed: {
                    meaning: "释放恐惧，清晰，真相浮现",
                    keywords: ["释放恐惧", "清晰", "真相浮现"],
                    description: "逆位的月亮可能表示你正在释放恐惧，获得清晰度，或者真相正在浮现。"
                }
            },
            {
                name: "太阳",
                number: 19,
                suit: "major",
                image: "https://www.trustedtarot.com/img/cards/the-sun.png",
                englishName: "The Sun",
                upright: {
                    meaning: "快乐，成功，活力，真理",
                    keywords: ["快乐", "成功", "活力", "真理"],
                    description: "太阳牌代表快乐、成功和活力。它表示一个积极、成功和快乐的时期。"
                },
                reversed: {
                    meaning: "暂时的挫折，成功延迟，缺乏活力",
                    keywords: ["暂时的挫折", "成功延迟", "缺乏活力"],
                    description: "逆位的太阳可能表示暂时的挫折、成功延迟或缺乏活力。"
                }
            },
            {
                name: "审判",
                number: 20,
                suit: "major",
                image: "https://www.trustedtarot.com/img/cards/judgement.png",
                englishName: "Judgement",
                upright: {
                    meaning: "重生，内省，觉醒，宽恕",
                    keywords: ["重生", "内省", "觉醒", "宽恕"],
                    description: "审判牌代表重生、内省和觉醒。它鼓励你反思过去，宽恕自己和他人，并拥抱新的开始。"
                },
                reversed: {
                    meaning: "自我怀疑，恐惧改变，拒绝觉醒",
                    keywords: ["自我怀疑", "恐惧改变", "拒绝觉醒"],
                    description: "逆位的审判可能表示自我怀疑、恐惧改变或拒绝必要的觉醒。"
                }
            },
            {
                name: "世界",
                number: 21,
                suit: "major",
                image: "https://www.trustedtarot.com/img/cards/the-world.png",
                englishName: "The World",
                upright: {
                    meaning: "完成，成就，旅行，整合",
                    keywords: ["完成", "成就", "旅行", "整合"],
                    description: "世界牌代表完成、成就和整合。它表示一个周期的成功结束和新的开始。"
                },
                reversed: {
                    meaning: "未完成，延迟，缺乏结束",
                    keywords: ["未完成", "延迟", "缺乏结束"],
                    description: "逆位的世界可能表示未完成的事务、延迟或缺乏适当的结束。"
                }
            },
            
            // 小阿卡那牌 - 权杖牌组
            {
                name: "权杖王牌",
                number: 1,
                suit: "wands",
                image: "https://www.trustedtarot.com/img/cards/ace-of-wands.png",
                englishName: "Ace of Wands",
                upright: {
                    meaning: "创造，开始，冒险，灵感",
                    keywords: ["创造", "开始", "冒险", "灵感"],
                    description: "权杖王牌代表新的创造性能量、冒险和灵感。它表示一个充满热情的新开始。"
                },
                reversed: {
                    meaning: "延迟，缺乏方向，未实现的潜力",
                    keywords: ["延迟", "缺乏方向", "未实现的潜力"],
                    description: "逆位的权杖王牌可能表示延迟、缺乏方向或未实现的创造潜力。"
                }
            },
            {
                name: "权杖二",
                number: 2,
                suit: "wands",
                image: "https://www.trustedtarot.com/img/cards/two-of-wands.png",
                englishName: "Two of Wands",
                upright: {
                    meaning: "规划，决定，发现，进步",
                    keywords: ["规划", "决定", "发现", "进步"],
                    description: "权杖二代表规划、决定和发现。它表示你正在考虑未来的可能性并做出决定。"
                },
                reversed: {
                    meaning: "优柔寡断，恐惧，缺乏规划",
                    keywords: ["优柔寡断", "恐惧", "缺乏规划"],
                    description: "逆位的权杖二可能表示优柔寡断、恐惧或缺乏适当的规划。"
                }
            },
            {
                name: "权杖三",
                number: 3,
                suit: "wands",
                image: "https://www.trustedtarot.com/img/cards/three-of-wands.png",
                englishName: "Three of Wands",
                upright: {
                    meaning: "扩展，远见，合作，成长",
                    keywords: ["扩展", "远见", "合作", "成长"],
                    description: "权杖三代表扩展、远见和合作。它表示你的努力正在产生结果，成长即将到来。"
                },
                reversed: {
                    meaning: "延迟，挫折，缺乏远见",
                    keywords: ["延迟", "挫折", "缺乏远见"],
                    description: "逆位的权杖三可能表示延迟、挫折或缺乏远见。"
                }
            },
            {
                name: "权杖四",
                number: 4,
                suit: "wands",
                image: "https://www.trustedtarot.com/img/cards/four-of-wands.png",
                englishName: "Four of Wands",
                upright: {
                    meaning: "稳定，庆祝，和谐，基础",
                    keywords: ["稳定", "庆祝", "和谐", "基础"],
                    description: "权杖四代表稳定、庆祝和和谐。它表示一个稳固的基础和值得庆祝的成就。"
                },
                reversed: {
                    meaning: "不稳定，缺乏庆祝，不和谐",
                    keywords: ["不稳定", "缺乏庆祝", "不和谐"],
                    description: "逆位的权杖四可能表示不稳定、缺乏庆祝或不和谐。"
                }
            },
            {
                name: "权杖五",
                number: 5,
                suit: "wands",
                image: "https://www.trustedtarot.com/img/cards/five-of-wands.png",
                englishName: "Five of Wands",
                upright: {
                    meaning: "冲突，竞争，斗争，差异",
                    keywords: ["冲突", "竞争", "斗争", "差异"],
                    description: "权杖五代表冲突、竞争和斗争。它表示你正在面对挑战或与他人竞争。"
                },
                reversed: {
                    meaning: "避免冲突，解决，妥协",
                    keywords: ["避免冲突", "解决", "妥协"],
                    description: "逆位的权杖五可能表示避免冲突、寻求解决或妥协。"
                }
            },
            {
                name: "权杖六",
                number: 6,
                suit: "wands",
                image: "https://www.trustedtarot.com/img/cards/six-of-wands.png",
                englishName: "Six of Wands",
                upright: {
                    meaning: "胜利，进步，认可，自信",
                    keywords: ["胜利", "进步", "认可", "自信"],
                    description: "权杖六代表胜利、进步和认可。它表示你的努力得到了认可，你正在走向成功。"
                },
                reversed: {
                    meaning: "失败，缺乏认可，自信不足",
                    keywords: ["失败", "缺乏认可", "自信不足"],
                    description: "逆位的权杖六可能表示失败、缺乏认可或自信不足。"
                }
            },
            {
                name: "权杖七",
                number: 7,
                suit: "wands",
                image: "https://www.trustedtarot.com/img/cards/seven-of-wands.png",
                englishName: "Seven of Wands",
                upright: {
                    meaning: "挑战，防御，坚持，勇气",
                    keywords: ["挑战", "防御", "坚持", "勇气"],
                    description: "权杖七代表挑战、防御和坚持。它表示你正在面对挑战，需要坚持自己的立场。"
                },
                reversed: {
                    meaning: "放弃，不知所措，防御不足",
                    keywords: ["放弃", "不知所措", "防御不足"],
                    description: "逆位的权杖七可能表示放弃、不知所措或防御不足。"
                }
            },
            {
                name: "权杖八",
                number: 8,
                suit: "wands",
                image: "https://www.trustedtarot.com/img/cards/eight-of-wands.png",
                englishName: "Eight of Wands",
                upright: {
                    meaning: "快速行动，进展，消息，旅行",
                    keywords: ["快速行动", "进展", "消息", "旅行"],
                    description: "权杖八代表快速行动、进展和消息。它表示事情正在迅速进展，或者你即将收到消息。"
                },
                reversed: {
                    meaning: "延迟，挫折，缓慢进展",
                    keywords: ["延迟", "挫折", "缓慢进展"],
                    description: "逆位的权杖八可能表示延迟、挫折或进展缓慢。"
                }
            },
            {
                name: "权杖九",
                number: 9,
                suit: "wands",
                image: "https://www.trustedtarot.com/img/cards/nine-of-wands.png",
                englishName: "Nine of Wands",
                upright: {
                    meaning: "韧性，警惕，坚持，经验",
                    keywords: ["韧性", "警惕", "坚持", "经验"],
                    description: "权杖九代表韧性、警惕和坚持。它表示你正在依靠过去的经验来应对当前的挑战。"
                },
                reversed: {
                    meaning: "固执，偏执，疲惫，防御过度",
                    keywords: ["固执", "偏执", "疲惫", "防御过度"],
                    description: "逆位的权杖九可能表示固执、偏执、疲惫或防御过度。"
                }
            },
            {
                name: "权杖十",
                number: 10,
                suit: "wands",
                image: "https://www.trustedtarot.com/img/cards/ten-of-wands.png",
                englishName: "Ten of Wands",
                upright: {
                    meaning: "负担，责任，压力，努力",
                    keywords: ["负担", "责任", "压力", "努力"],
                    description: "权杖十代表负担、责任和压力。它表示你承担了太多的责任，感到压力重重。"
                },
                reversed: {
                    meaning: "释放负担，委派，减轻压力",
                    keywords: ["释放负担", "委派", "减轻压力"],
                    description: "逆位的权杖十可能表示释放负担、委派任务或减轻压力。"
                }
            },
            {
                name: "权杖侍从",
                number: 11,
                suit: "wands",
                image: "https://www.trustedtarot.com/img/cards/page-of-wands.png",
                englishName: "Page of Wands",
                upright: {
                    meaning: "探索，热情，消息，新想法",
                    keywords: ["探索", "热情", "消息", "新想法"],
                    description: "权杖侍从代表探索、热情和新想法。它表示你正在探索新的可能性，充满热情。"
                },
                reversed: {
                    meaning: "缺乏方向，坏消息，热情减退",
                    keywords: ["缺乏方向", "坏消息", "热情减退"],
                    description: "逆位的权杖侍从可能表示缺乏方向、坏消息或热情减退。"
                }
            },
            {
                name: "权杖骑士",
                number: 12,
                suit: "wands",
                image: "https://www.trustedtarot.com/img/cards/knight-of-wands.png",
                englishName: "Knight of Wands",
                upright: {
                    meaning: "行动，冒险，能量，改变",
                    keywords: ["行动", "冒险", "能量", "改变"],
                    description: "权杖骑士代表行动、冒险和能量。它表示你正在采取行动，追求你的目标。"
                },
                reversed: {
                    meaning: "冲动，延迟，挫折，缺乏方向",
                    keywords: ["冲动", "延迟", "挫折", "缺乏方向"],
                    description: "逆位的权杖骑士可能表示冲动、延迟、挫折或缺乏方向。"
                }
            },
            {
                name: "权杖王后",
                number: 13,
                suit: "wands",
                image: "https://www.trustedtarot.com/img/cards/queen-of-wands.png",
                englishName: "Queen of Wands",
                upright: {
                    meaning: "自信，热情，独立，魅力",
                    keywords: ["自信", "热情", "独立", "魅力"],
                    description: "权杖王后代表自信、热情和独立。她是一个充满活力、自信和魅力的领导者。"
                },
                reversed: {
                    meaning: "嫉妒，支配，缺乏自信，喜怒无常",
                    keywords: ["嫉妒", "支配", "缺乏自信", "喜怒无常"],
                    description: "逆位的权杖王后可能表示嫉妒、支配他人、缺乏自信或喜怒无常。"
                }
            },
            {
                name: "权杖国王",
                number: 14,
                suit: "wands",
                image: "https://www.trustedtarot.com/img/cards/king-of-wands.png",
                englishName: "King of Wands",
                upright: {
                    meaning: "领导力，远见，企业家精神，诚实",
                    keywords: ["领导力", "远见", "企业家精神", "诚实"],
                    description: "权杖国王代表领导力、远见和企业家精神。他是一个诚实、有远见的领导者。"
                },
                reversed: {
                    meaning: "支配，无情，不诚实，冲动",
                    keywords: ["支配", "无情", "不诚实", "冲动"],
                    description: "逆位的权杖国王可能表示支配他人、无情、不诚实或冲动。"
                }
            },
            
            // 小阿卡那牌 - 宝剑牌组
            {
                name: "宝剑王牌",
                number: 1,
                suit: "swords",
                image: "https://www.trustedtarot.com/img/cards/ace-of-swords.png",
                englishName: "Ace of Swords",
                upright: {
                    meaning: "突破，新想法，智力，清晰",
                    keywords: ["突破", "新想法", "智力", "清晰"],
                    description: "宝剑王牌代表突破、新想法和智力清晰。它表示一个新的想法或突破性的见解。"
                },
                reversed: {
                    meaning: "混乱，延迟，沟通问题",
                    keywords: ["混乱", "延迟", "沟通问题"],
                    description: "逆位的宝剑王牌可能表示混乱、延迟或沟通问题。"
                }
            },
            {
                name: "宝剑二",
                number: 2,
                suit: "swords",
                image: "https://www.trustedtarot.com/img/cards/two-of-swords.png",
                englishName: "Two of Swords",
                upright: {
                    meaning: "僵局，困难选择，逃避",
                    keywords: ["僵局", "困难选择", "逃避"],
                    description: "宝剑二代表僵局、困难选择和逃避。它表示你正在面对一个困难的决定，可能选择逃避。"
                },
                reversed: {
                    meaning: "优柔寡断，困惑，释放",
                    keywords: ["优柔寡断", "困惑", "释放"],
                    description: "逆位的宝剑二可能表示优柔寡断、困惑或最终释放。"
                }
            },
            {
                name: "宝剑三",
                number: 3,
                suit: "swords",
                image: "https://www.trustedtarot.com/img/cards/three-of-swords.png",
                englishName: "Three of Swords",
                upright: {
                    meaning: "心痛，悲伤，痛苦，分离",
                    keywords: ["心痛", "悲伤", "痛苦", "分离"],
                    description: "宝剑三代表心痛、悲伤和痛苦。它表示你正在经历情感上的痛苦或分离。"
                },
                reversed: {
                    meaning: "恢复，宽恕，移动前进",
                    keywords: ["恢复", "宽恕", "移动前进"],
                    description: "逆位的宝剑三可能表示恢复、宽恕或从痛苦中移动前进。"
                }
            },
            {
                name: "宝剑四",
                number: 4,
                suit: "swords",
                image: "https://www.trustedtarot.com/img/cards/four-of-swords.png",
                englishName: "Four of Swords",
                upright: {
                    meaning: "休息，恢复，冥想，撤退",
                    keywords: ["休息", "恢复", "冥想", "撤退"],
                    description: "宝剑四代表休息、恢复和冥想。它表示你需要从冲突或压力中撤退，以恢复能量。"
                },
                reversed: {
                    meaning: "恢复活动，缺乏休息，精疲力竭",
                    keywords: ["恢复活动", "缺乏休息", "精疲力竭"],
                    description: "逆位的宝剑四可能表示恢复活动、缺乏休息或精疲力竭。"
                }
            },
            {
                name: "宝剑五",
                number: 5,
                suit: "swords",
                image: "https://www.trustedtarot.com/img/cards/five-of-swords.png",
                englishName: "Five of Swords",
                upright: {
                    meaning: "冲突，自私，争论胜利",
                    keywords: ["冲突", "自私", "争论胜利"],
                    description: "宝剑五代表冲突、自私和争论胜利。它表示你可能赢得了争论，但失去了尊重或友谊。"
                },
                reversed: {
                    meaning: "和解，让步，吸取教训",
                    keywords: ["和解", "让步", "吸取教训"],
                    description: "逆位的宝剑五可能表示和解、让步或从过去的冲突中吸取教训。"
                }
            },
            {
                name: "宝剑六",
                number: 6,
                suit: "swords",
                image: "https://www.trustedtarot.com/img/cards/six-of-swords.png",
                englishName: "Six of Swords",
                upright: {
                    meaning: "过渡，离开，前进",
                    keywords: ["过渡", "离开", "前进"],
                    description: "宝剑六代表过渡、离开和前进。它表示你正在离开困难的情况，前往更好的地方。"
                },
                reversed: {
                    meaning: "停滞，无法前进，情感包袱",
                    keywords: ["停滞", "无法前进", "情感包袱"],
                    description: "逆位的宝剑六可能表示停滞不前、无法前进或携带情感包袱。"
                }
            },
            {
                name: "宝剑七",
                number: 7,
                suit: "swords",
                image: "https://www.trustedtarot.com/img/cards/seven-of-swords.png",
                englishName: "Seven of Swords",
                upright: {
                    meaning: "欺骗，策略，独自行动",
                    keywords: ["欺骗", "策略", "独自行动"],
                    description: "宝剑七代表欺骗、策略和独自行动。它表示你可能在试图避免被发现，或独自处理问题。"
                },
                reversed: {
                    meaning: "揭露，建议，忏悔",
                    keywords: ["揭露", "建议", "忏悔"],
                    description: "逆位的宝剑七可能表示欺骗被揭露、寻求建议或忏悔。"
                }
            },
            {
                name: "宝剑八",
                number: 8,
                suit: "swords",
                image: "https://www.trustedtarot.com/img/cards/eight-of-swords.png",
                englishName: "Eight of Swords",
                upright: {
                    meaning: "限制，无力，孤立",
                    keywords: ["限制", "无力", "孤立"],
                    description: "宝剑八代表限制、无力和孤立。它表示你感到被困，但实际上限制可能更多是心理上的。"
                },
                reversed: {
                    meaning: "释放，新视角，自由",
                    keywords: ["释放", "新视角", "自由"],
                    description: "逆位的宝剑八可能表示释放、获得新视角或找到自由。"
                }
            },
            {
                name: "宝剑九",
                number: 9,
                suit: "swords",
                image: "https://www.trustedtarot.com/img/cards/nine-of-swords.png",
                englishName: "Nine of Swords",
                upright: {
                    meaning: "焦虑，噩梦，恐惧",
                    keywords: ["焦虑", "噩梦", "恐惧"],
                    description: "宝剑九代表焦虑、噩梦和恐惧。它表示你正在经历强烈的焦虑或担忧。"
                },
                reversed: {
                    meaning: "希望，释放恐惧，恢复",
                    keywords: ["希望", "释放恐惧", "恢复"],
                    description: "逆位的宝剑九可能表示希望、释放恐惧或从焦虑中恢复。"
                }
            },
            {
                name: "宝剑十",
                number: 10,
                suit: "swords",
                image: "https://www.trustedtarot.com/img/cards/ten-of-swords.png",
                englishName: "Ten of Swords",
                upright: {
                    meaning: "结束，痛苦，背叛",
                    keywords: ["结束", "痛苦", "背叛"],
                    description: "宝剑十代表结束、痛苦和背叛。它表示一个困难情况的结束，可能伴随着痛苦或背叛感。"
                },
                reversed: {
                    meaning: "恢复，新开始，释放痛苦",
                    keywords: ["恢复", "新开始", "释放痛苦"],
                    description: "逆位的宝剑十可能表示恢复、新开始或释放痛苦。"
                }
            },
            {
                name: "宝剑侍从",
                number: 11,
                suit: "swords",
                image: "https://www.trustedtarot.com/img/cards/page-of-swords.png",
                englishName: "Page of Swords",
                upright: {
                    meaning: "好奇心，警惕，新想法",
                    keywords: ["好奇心", "警惕", "新想法"],
                    description: "宝剑侍从代表好奇心、警惕和新想法。它表示你正在探索新的想法，保持警惕。"
                },
                reversed: {
                    meaning: "欺骗，恶意，不负责任",
                    keywords: ["欺骗", "恶意", "不负责任"],
                    description: "逆位的宝剑侍从可能表示欺骗、恶意或不负责任的行为。"
                }
            },
            {
                name: "宝剑骑士",
                number: 12,
                suit: "swords",
                image: "https://www.trustedtarot.com/img/cards/knight-of-swords.png",
                englishName: "Knight of Swords",
                upright: {
                    meaning: "行动，决心，冲动",
                    keywords: ["行动", "决心", "冲动"],
                    description: "宝剑骑士代表行动、决心和冲动。它表示你正在迅速采取行动，追求你的目标。"
                },
                reversed: {
                    meaning: "侵略，不顾后果，拖延",
                    keywords: ["侵略", "不顾后果", "拖延"],
                    description: "逆位的宝剑骑士可能表示侵略性、不顾后果的行为或拖延。"
                }
            },
            {
                name: "宝剑王后",
                number: 13,
                suit: "swords",
                image: "https://www.trustedtarot.com/img/cards/queen-of-swords.png",
                englishName: "Queen of Swords",
                upright: {
                    meaning: "独立，判断力，清晰",
                    keywords: ["独立", "判断力", "清晰"],
                    description: "宝剑王后代表独立、判断力和清晰。她是一个客观、清晰思考和独立的女性。"
                },
                reversed: {
                    meaning: "苛刻，无情，偏见",
                    keywords: ["苛刻", "无情", "偏见"],
                    description: "逆位的宝剑王后可能表示苛刻、无情或带有偏见。"
                }
            },
            {
                name: "宝剑国王",
                number: 14,
                suit: "swords",
                image: "https://www.trustedtarot.com/img/cards/king-of-swords.png",
                englishName: "King of Swords",
                upright: {
                    meaning: "权威，真理，纪律",
                    keywords: ["权威", "真理", "纪律"],
                    description: "宝剑国王代表权威、真理和纪律。他是一个理性、公正和有原则的领导者。"
                },
                reversed: {
                    meaning: "操纵，残酷，滥用权力",
                    keywords: ["操纵", "残酷", "滥用权力"],
                    description: "逆位的宝剑国王可能表示操纵、残酷或滥用权力。"
                }
            },
            
            // 小阿卡那牌 - 圣杯牌组
            {
                name: "圣杯王牌",
                number: 1,
                suit: "cups",
                image: "https://www.trustedtarot.com/img/cards/ace-of-cups.png",
                englishName: "Ace of Cups",
                upright: {
                    meaning: "新感情，直觉，爱，情感开始",
                    keywords: ["新感情", "直觉", "爱", "情感开始"],
                    description: "圣杯王牌代表新的感情、直觉和情感开始。它表示爱、喜悦或新的情感体验的开始。"
                },
                reversed: {
                    meaning: "情感空虚，失去，不稳定",
                    keywords: ["情感空虚", "失去", "不稳定"],
                    description: "逆位的圣杯王牌可能表示情感空虚、失去情感连接或不稳定。"
                }
            },
            {
                name: "圣杯二",
                number: 2,
                suit: "cups",
                image: "https://www.trustedtarot.com/img/cards/two-of-cups.png",
                englishName: "Two of Cups",
                upright: {
                    meaning: "结合，伙伴关系，和谐，吸引力",
                    keywords: ["结合", "伙伴关系", "和谐", "吸引力"],
                    description: "圣杯二代表结合、伙伴关系和和谐。它表示一种平等、和谐的关系或伙伴关系。"
                },
                reversed: {
                    meaning: "不平衡，不和谐，分离",
                    keywords: ["不平衡", "不和谐", "分离"],
                    description: "逆位的圣杯二可能表示不平衡、不和谐或分离。"
                }
            },
            {
                name: "圣杯三",
                number: 3,
                suit: "cups",
                image: "https://www.trustedtarot.com/img/cards/three-of-cups.png",
                englishName: "Three of Cups",
                upright: {
                    meaning: "庆祝，友谊，创造力，社交",
                    keywords: ["庆祝", "友谊", "创造力", "社交"],
                    description: "圣杯三代表庆祝、友谊和创造力。它表示与朋友庆祝、社交活动或创造性合作。"
                },
                reversed: {
                    meaning: "过度放纵，流言，孤立",
                    keywords: ["过度放纵", "流言", "孤立"],
                    description: "逆位的圣杯三可能表示过度放纵、流言蜚语或孤立。"
                }
            },
            {
                name: "圣杯四",
                number: 4,
                suit: "cups",
                image: "https://www.trustedtarot.com/img/cards/four-of-cups.png",
                englishName: "Four of Cups",
                upright: {
                    meaning: "沉思，不满足，撤退",
                    keywords: ["沉思", "不满足", "撤退"],
                    description: "圣杯四代表沉思、不满足和撤退。它表示你对现状感到不满足，正在退一步反思。"
                },
                reversed: {
                    meaning: "觉醒，接受，新可能性",
                    keywords: ["觉醒", "接受", "新可能性"],
                    description: "逆位的圣杯四可能表示觉醒、接受现实或意识到新的可能性。"
                }
            },
            {
                name: "圣杯五",
                number: 5,
                suit: "cups",
                image: "https://www.trustedtarot.com/img/cards/five-of-cups.png",
                englishName: "Five of Cups",
                upright: {
                    meaning: "失落，悲伤，失望",
                    keywords: ["失落", "悲伤", "失望"],
                    description: "圣杯五代表失落、悲伤和失望。它表示你专注于损失，忽视了仍然拥有的东西。"
                },
                reversed: {
                    meaning: "接受，宽恕，前进",
                    keywords: ["接受", "宽恕", "前进"],
                    description: "逆位的圣杯五可能表示接受损失、宽恕或继续前进。"
                }
            },
            {
                name: "圣杯六",
                number: 6,
                suit: "cups",
                image: "https://www.trustedtarot.com/img/cards/six-of-cups.png",
                englishName: "Six of Cups",
                upright: {
                    meaning: "怀旧，童年，天真，礼物",
                    keywords: ["怀旧", "童年", "天真", "礼物"],
                    description: "圣杯六代表怀旧、童年和天真。它表示回忆过去、童年的快乐或收到礼物。"
                },
                reversed: {
                    meaning: "活在当下，放手过去",
                    keywords: ["活在当下", "放手过去"],
                    description: "逆位的圣杯六可能表示活在当下、放手过去或从记忆中解放。"
                }
            },
            {
                name: "圣杯七",
                number: 7,
                suit: "cups",
                image: "https://www.trustedtarot.com/img/cards/seven-of-cups.png",
                englishName: "Seven of Cups",
                upright: {
                    meaning: "选择，幻想，白日梦",
                    keywords: ["选择", "幻想", "白日梦"],
                    description: "圣杯七代表选择、幻想和白日梦。它表示你面临许多选择，但可能不是所有都是现实的。"
                },
                reversed: {
                    meaning: "缺乏目标，困惑，决定",
                    keywords: ["缺乏目标", "困惑", "决定"],
                    description: "逆位的圣杯七可能表示缺乏目标、困惑或最终做出决定。"
                }
            },
            {
                name: "圣杯八",
                number: 8,
                suit: "cups",
                image: "https://www.trustedtarot.com/img/cards/eight-of-cups.png",
                englishName: "Eight of Cups",
                upright: {
                    meaning: "离开，寻求，不满足",
                    keywords: ["离开", "寻求", "不满足"],
                    description: "圣杯八代表离开、寻求和不满足。它表示你正在离开某种情况，寻求更深的意义。"
                },
                reversed: {
                    meaning: "犹豫，恐惧，停滞",
                    keywords: ["犹豫", "恐惧", "停滞"],
                    description: "逆位的圣杯八可能表示犹豫、恐惧离开或停滞不前。"
                }
            },
            {
                name: "圣杯九",
                number: 9,
                suit: "cups",
                image: "https://www.trustedtarot.com/img/cards/nine-of-cups.png",
                englishName: "Nine of Cups",
                upright: {
                    meaning: "满足，愿望成真，自满",
                    keywords: ["满足", "愿望成真", "自满"],
                    description: "圣杯九代表满足、愿望成真和自满。它表示情感上的满足和愿望的实现。"
                },
                reversed: {
                    meaning: "不满意，过度放纵",
                    keywords: ["不满意", "过度放纵"],
                    description: "逆位的圣杯九可能表示不满意、过度放纵或物质主义。"
                }
            },
            {
                name: "圣杯十",
                number: 10,
                suit: "cups",
                image: "https://www.trustedtarot.com/img/cards/ten-of-cups.png",
                englishName: "Ten of Cups",
                upright: {
                    meaning: "和谐，幸福，家庭，情感满足",
                    keywords: ["和谐", "幸福", "家庭", "情感满足"],
                    description: "圣杯十代表和谐、幸福和家庭。它表示情感上的满足、家庭和谐和幸福。"
                },
                reversed: {
                    meaning: "冲突，不和谐，破碎家庭",
                    keywords: ["冲突", "不和谐", "破碎家庭"],
                    description: "逆位的圣杯十可能表示冲突、不和谐或家庭问题。"
                }
            },
            {
                name: "圣杯侍从",
                number: 11,
                suit: "cups",
                image: "https://www.trustedtarot.com/img/cards/page-of-cups.png",
                englishName: "Page of Cups",
                upright: {
                    meaning: "敏感，创造性，新感觉",
                    keywords: ["敏感", "创造性", "新感觉"],
                    description: "圣杯侍从代表敏感、创造性和新感觉。它表示新的情感开始、创造性灵感或直觉信息。"
                },
                reversed: {
                    meaning: "情感不稳定，延迟",
                    keywords: ["情感不稳定", "延迟"],
                    description: "逆位的圣杯侍从可能表示情感不稳定、延迟或创造性阻碍。"
                }
            },
            {
                name: "圣杯骑士",
                number: 12,
                suit: "cups",
                image: "https://www.trustedtarot.com/img/cards/knight-of-cups.png",
                englishName: "Knight of Cups",
                upright: {
                    meaning: "浪漫，魅力，情感到来",
                    keywords: ["浪漫", "魅力", "情感到来"],
                    description: "圣杯骑士代表浪漫、魅力和情感到来。它表示一个浪漫的提议、创造性追求或情感进展。"
                },
                reversed: {
                    meaning: "情绪化，不切实际，延迟",
                    keywords: ["情绪化", "不切实际", "延迟"],
                    description: "逆位的圣杯骑士可能表示情绪化、不切实际或情感延迟。"
                }
            },
            {
                name: "圣杯王后",
                number: 13,
                suit: "cups",
                image: "https://www.trustedtarot.com/img/cards/queen-of-cups.png",
                englishName: "Queen of Cups",
                upright: {
                    meaning: "同情，直觉，关怀，情感平衡",
                    keywords: ["同情", "直觉", "关怀", "情感平衡"],
                    description: "圣杯王后代表同情、直觉和关怀。她是一个富有同情心、直觉敏锐和情感平衡的女性。"
                },
                reversed: {
                    meaning: "情绪不稳定，依赖性",
                    keywords: ["情绪不稳定", "依赖性"],
                    description: "逆位的圣杯王后可能表示情绪不稳定、过度依赖他人或情感不安全感。"
                }
            },
            {
                name: "圣杯国王",
                number: 14,
                suit: "cups",
                image: "https://www.trustedtarot.com/img/cards/king-of-cups.png",
                englishName: "King of Cups",
                upright: {
                    meaning: "情感平衡，同情，智慧",
                    keywords: ["情感平衡", "同情", "智慧"],
                    description: "圣杯国王代表情感平衡、同情和智慧。他是一个情感成熟、富有同情心和智慧的男性。"
                },
                reversed: {
                    meaning: "情绪化，冷漠，操纵",
                    keywords: ["情绪化", "冷漠", "操纵"],
                    description: "逆位的圣杯国王可能表示情绪化、冷漠或情感操纵。"
                }
            },
            
            // 小阿卡那牌 - 星币牌组
            {
                name: "星币王牌",
                number: 1,
                suit: "pentacles",
                image: "https://www.trustedtarot.com/img/cards/ace-of-pentacles.png",
                englishName: "Ace of Pentacles",
                upright: {
                    meaning: "繁荣，新财务，实际机会，富足",
                    keywords: ["繁荣", "新财务", "实际机会", "富足"],
                    description: "星币王牌代表繁荣、新的财务机会和实际的成功。它表示物质富足或新的事业机会。"
                },
                reversed: {
                    meaning: "错失机会，财务损失，缺乏规划",
                    keywords: ["错失机会", "财务损失", "缺乏规划"],
                    description: "逆位的星币王牌可能表示错失机会、财务损失或缺乏规划。"
                }
            },
            {
                name: "星币二",
                number: 2,
                suit: "pentacles",
                image: "https://www.trustedtarot.com/img/cards/two-of-pentacles.png",
                englishName: "Two of Pentacles",
                upright: {
                    meaning: "平衡，适应，资源管理，灵活",
                    keywords: ["平衡", "适应", "资源管理", "灵活"],
                    description: "星币二代表平衡、适应和资源管理。它表示你正在平衡多种责任或财务事务。"
                },
                reversed: {
                    meaning: "不平衡，财务问题，缺乏适应",
                    keywords: ["不平衡", "财务问题", "缺乏适应"],
                    description: "逆位的星币二可能表示不平衡、财务问题或缺乏适应能力。"
                }
            },
            {
                name: "星币三",
                number: 3,
                suit: "pentacles",
                image: "https://www.trustedtarot.com/img/cards/three-of-pentacles.png",
                englishName: "Three of Pentacles",
                upright: {
                    meaning: "团队合作，学习，实施",
                    keywords: ["团队合作", "学习", "实施"],
                    description: "星币三代表团队合作、学习和实施。它表示协作、技能发展和项目进展。"
                },
                reversed: {
                    meaning: "缺乏合作，平庸",
                    keywords: ["缺乏合作", "平庸"],
                    description: "逆位的星币三可能表示缺乏合作、平庸的工作或学习困难。"
                }
            },
            {
                name: "星币四",
                number: 4,
                suit: "pentacles",
                image: "https://www.trustedtarot.com/img/cards/four-of-pentacles.png",
                englishName: "Four of Pentacles",
                upright: {
                    meaning: "保存，控制，安全",
                    keywords: ["保存", "控制", "安全"],
                    description: "星币四代表保存、控制和安全。它表示对财务或资源的保守态度，寻求安全和控制。"
                },
                reversed: {
                    meaning: "贪婪，吝啬，放手",
                    keywords: ["贪婪", "吝啬", "放手"],
                    description: "逆位的星币四可能表示贪婪、吝啬或需要放手控制。"
                }
            },
            {
                name: "星币五",
                number: 5,
                suit: "pentacles",
                image: "https://www.trustedtarot.com/img/cards/five-of-pentacles.png",
                englishName: "Five of Pentacles",
                upright: {
                    meaning: "困难，贫困，孤立",
                    keywords: ["困难", "贫困", "孤立"],
                    description: "星币五代表困难、贫困和孤立。它表示财务困难、感到被排斥或物质匮乏。"
                },
                reversed: {
                    meaning: "恢复，慈善，新开始",
                    keywords: ["恢复", "慈善", "新开始"],
                    description: "逆位的星币五可能表示恢复、接受帮助或新的开始。"
                }
            },
            {
                name: "星币六",
                number: 6,
                suit: "pentacles",
                image: "https://www.trustedtarot.com/img/cards/six-of-pentacles.png",
                englishName: "Six of Pentacles",
                upright: {
                    meaning: "慷慨，慈善，给予",
                    keywords: ["慷慨", "慈善", "给予"],
                    description: "星币六代表慷慨、慈善和给予。它表示给予或接受帮助、慈善行为或财务平衡。"
                },
                reversed: {
                    meaning: "自私，债务，不平衡",
                    keywords: ["自私", "债务", "不平衡"],
                    description: "逆位的星币六可能表示自私、债务或权力不平衡。"
                }
            },
            {
                name: "星币七",
                number: 7,
                suit: "pentacles",
                image: "https://www.trustedtarot.com/img/cards/seven-of-pentacles.png",
                englishName: "Seven of Pentacles",
                upright: {
                    meaning: "耐心，奖励，评估",
                    keywords: ["耐心", "奖励", "评估"],
                    description: "星币七代表耐心、奖励和评估。它表示等待收获、评估进展或长期投资。"
                },
                reversed: {
                    meaning: "缺乏收获，挫折，不耐烦",
                    keywords: ["缺乏收获", "挫折", "不耐烦"],
                    description: "逆位的星币七可能表示缺乏收获、挫折或不耐烦。"
                }
            },
            {
                name: "星币八",
                number: 8,
                suit: "pentacles",
                image: "https://www.trustedtarot.com/img/cards/eight-of-pentacles.png",
                englishName: "Eight of Pentacles",
                upright: {
                    meaning: "工艺，技能，专注",
                    keywords: ["工艺", "技能", "专注"],
                    description: "星币八代表工艺、技能和专注。它表示专注工作、技能发展或学徒期。"
                },
                reversed: {
                    meaning: "缺乏动力，无技能，粗心",
                    keywords: ["缺乏动力", "无技能", "粗心"],
                    description: "逆位的星币八可能表示缺乏动力、技能不足或粗心大意。"
                }
            },
            {
                name: "星币九",
                number: 9,
                suit: "pentacles",
                image: "https://www.trustedtarot.com/img/cards/nine-of-pentacles.png",
                englishName: "Nine of Pentacles",
                upright: {
                    meaning: "丰富，自力更生，成功",
                    keywords: ["丰富", "自力更生", "成功"],
                    description: "星币九代表丰富、自力更生和成功。它表示物质成功、享受劳动成果和独立。"
                },
                reversed: {
                    meaning: "过度放纵，依赖，价值错误",
                    keywords: ["过度放纵", "依赖", "价值错误"],
                    description: "逆位的星币九可能表示过度放纵、依赖他人或价值判断错误。"
                }
            },
            {
                name: "星币十",
                number: 10,
                suit: "pentacles",
                image: "https://www.trustedtarot.com/img/cards/ten-of-pentacles.png",
                englishName: "Ten of Pentacles",
                upright: {
                    meaning: "财富，家庭，传统，遗产",
                    keywords: ["财富", "家庭", "传统", "遗产"],
                    description: "星币十代表财富、家庭和传统。它表示财务安全、家庭幸福和遗产。"
                },
                reversed: {
                    meaning: "家庭冲突，财务失败",
                    keywords: ["家庭冲突", "财务失败"],
                    description: "逆位的星币十可能表示家庭冲突、财务失败或传统束缚。"
                }
            },
            {
                name: "星币侍从",
                number: 11,
                suit: "pentacles",
                image: "https://www.trustedtarot.com/img/cards/page-of-pentacles.png",
                englishName: "Page of Pentacles",
                upright: {
                    meaning: "学习，勤奋，新机会",
                    keywords: ["学习", "勤奋", "新机会"],
                    description: "星币侍从代表学习、勤奋和新机会。它表示新的学习机会、勤奋工作或实际的新开始。"
                },
                reversed: {
                    meaning: "缺乏进步，懒惰，错失机会",
                    keywords: ["缺乏进步", "懒惰", "错失机会"],
                    description: "逆位的星币侍从可能表示缺乏进步、懒惰或错失机会。"
                }
            },
            {
                name: "星币骑士",
                number: 12,
                suit: "pentacles",
                image: "https://www.trustedtarot.com/img/cards/knight-of-pentacles.png",
                englishName: "Knight of Pentacles",
                upright: {
                    meaning: "责任，勤奋，可靠",
                    keywords: ["责任", "勤奋", "可靠"],
                    description: "星币骑士代表责任、勤奋和可靠。它表示稳定进展、可靠性和勤奋工作。"
                },
                reversed: {
                    meaning: "停滞，无聊，不负责任",
                    keywords: ["停滞", "无聊", "不负责任"],
                    description: "逆位的星币骑士可能表示停滞、无聊或不负责任。"
                }
            },
            {
                name: "星币王后",
                number: 13,
                suit: "pentacles",
                image: "https://www.trustedtarot.com/img/cards/queen-of-pentacles.png",
                englishName: "Queen of Pentacles",
                upright: {
                    meaning: "繁荣，培养，安全",
                    keywords: ["繁荣", "培养", "安全"],
                    description: "星币王后代表繁荣、培养和安全。她是一个务实、培养他人和提供安全的女性。"
                },
                reversed: {
                    meaning: "物质主义，嫉妒，不安全",
                    keywords: ["物质主义", "嫉妒", "不安全"],
                    description: "逆位的星币王后可能表示物质主义、嫉妒或不安全感。"
                }
            },
            {
                name: "星币国王",
                number: 14,
                suit: "pentacles",
                image: "https://www.trustedtarot.com/img/cards/king-of-pentacles.png",
                englishName: "King of Pentacles",
                upright: {
                    meaning: "富足，安全，领导",
                    keywords: ["富足", "安全", "领导"],
                    description: "星币国王代表富足、安全和领导。他是一个成功、可靠和提供安全的领导者。"
                },
                reversed: {
                    meaning: "保守，贪婪，独裁",
                    keywords: ["保守", "贪婪", "独裁"],
                    description: "逆位的星币国王可能表示保守、贪婪或独裁行为。"
                }
            }
        ];

        // DOM元素
        const drawBtn = document.getElementById('drawBtn');
        const drawSection = document.getElementById('drawSection');
        const shuffleSection = document.getElementById('shuffleSection');
        const resultSection = document.getElementById('resultSection');
        const cardsContainer = document.getElementById('cardsContainer');
        const interpretationText = document.getElementById('interpretationText');
        const detailedMeanings = document.getElementById('detailedMeanings');
        const resetBtn = document.getElementById('resetBtn');
        const historySection = document.getElementById('historySection');
        const historyContainer = document.getElementById('historyContainer');
        const spreadTitle = document.getElementById('spreadTitle');
        const spreadOptions = document.querySelectorAll('.spread-option');
        const progressBar = document.getElementById('progressBar');
        const progressText = document.getElementById('progressText');
        
        // 状态变量
        let selectedCards = [];
        let flippedCards = 0;
        let currentSpread = 'three-cards';
        let readingHistory = [];
        
        // 初始化
        document.addEventListener('DOMContentLoaded', function() {
            console.log("塔罗牌占卜系统已初始化");
            console.log(`牌组中有 ${tarotDeck.length} 张牌`);
            
            // 更新进度条
            updateProgress(100);
            
            // 设置占卜类型选择
            spreadOptions.forEach(option => {
                option.addEventListener('click', function() {
                    spreadOptions.forEach(opt => opt.classList.remove('active'));
                    this.classList.add('active');
                    currentSpread = this.dataset.spread;
                    
                    // 更新占卜类型标题
                    if (currentSpread === 'three-cards') {
                        spreadTitle.textContent = "三张牌阵 - 过去、现在、未来";
                    } else if (currentSpread === 'celtic-cross') {
                        spreadTitle.textContent = "凯尔特十字牌阵 - 全面分析";
                    } else if (currentSpread === 'single-card') {
                        spreadTitle.textContent = "单张牌 - 每日指引";
                    }
                });
            });
            
            // 从本地存储加载历史记录
            loadHistory();
        });
        
        // 更新进度条
        function updateProgress(percent) {
            progressBar.style.width = `${percent}%`;
            progressText.textContent = `已加载 ${tarotDeck.length}/78 张塔罗牌数据`;
        }
        
        // 1. 开始抽牌按钮点击事件
        drawBtn.addEventListener('click', function() {
            // 隐藏抽牌区域，显示洗牌动画
            drawSection.style.display = 'none';
            shuffleSection.style.display = 'block';
            
            // 根据选择的占卜类型设置洗牌时间
            let shuffleTime = 3000;
            if (currentSpread === 'celtic-cross') {
                shuffleTime = 4000; // 凯尔特十字需要更长洗牌时间
            }
            
            // 设置洗牌时间后显示结果
            setTimeout(() => {
                shuffleSection.style.display = 'none';
                resultSection.style.display = 'block';
                drawCards();
            }, shuffleTime);
        });
        
        // 2. 根据占卜类型抽牌
        function drawCards() {
            // 清空之前的牌和状态
            cardsContainer.innerHTML = '';
            selectedCards = [];
            flippedCards = 0;
            interpretationText.textContent = '请翻开所有卡牌以查看解读。';
            detailedMeanings.innerHTML = '';
            
            // 复制牌组并洗牌
            let shuffledDeck = [...tarotDeck].sort(() => Math.random() - 0.5);
            
            // 根据占卜类型确定抽牌数量
            let numberOfCards = 3;
            let positions = ['过去', '现在', '未来'];
            
            if (currentSpread === 'celtic-cross') {
                numberOfCards = 10;
                positions = [
                    '当前状况', '挑战', '潜意识', '过去', '目标',
                    '未来', '自我', '环境', '希望与恐惧', '结果'
                ];
            } else if (currentSpread === 'single-card') {
                numberOfCards = 1;
                positions = ['今日指引'];
            }
            
            // 取牌
            selectedCards = shuffledDeck.slice(0, numberOfCards);
            
            // 随机决定每张牌是正位还是逆位
            selectedCards = selectedCards.map(card => {
                return {
                    ...card,
                    orientation: Math.random() > 0.5 ? 'upright' : 'reversed',
                    flipped: false
                };
            });
            
            // 创建卡牌DOM元素
            selectedCards.forEach((card, index) => {
                const cardElement = document.createElement('div');
                cardElement.className = 'tarot-card';
                cardElement.dataset.index = index;
                
                // 根据位置设置解读意义
                let position = positions[index] || `位置 ${index + 1}`;
                
                // 确定花色显示
                let suitDisplay = "";
                if (card.suit === "wands") suitDisplay = "权杖";
                else if (card.suit === "swords") suitDisplay = "宝剑";
                else if (card.suit === "cups") suitDisplay = "圣杯";
                else if (card.suit === "pentacles") suitDisplay = "星币";
                else if (card.suit === "major") suitDisplay = "大阿卡那";
                
                cardElement.innerHTML = `
                    <div class="card-inner">
                        <div class="card-back">
                            <div class="hexagram"></div>
                        </div>
                        <div class="card-front">
                            <div class="card-image">
                                ${card.image ? 
                                    `<img src="${card.image}" alt="${card.name}" onerror="this.onerror=null; this.parentElement.innerHTML='<div class=\\'card-img-placeholder\\'><i class=\\"fas fa-image\\" style=\\"font-size:2rem; margin-bottom:10px;\\"></i><div>${card.name}</div><div style=\\"font-size:0.7rem; margin-top:5px;\\">${suitDisplay}</div></div>';" />` : 
                                    `<div class="card-img-placeholder"><i class="fas fa-image" style="font-size:2rem; margin-bottom:10px;"></i><div>${card.name}</div><div style="font-size:0.7rem; margin-top:5px;">${suitDisplay}</div></div>`
                                }
                            </div>
                            <div class="card-info">
                                <div class="card-name">${card.name}</div>
                                <div class="card-suit">${suitDisplay}</div>
                                <div class="card-orientation ${card.orientation}">
                                    ${card.orientation === 'upright' ? '正位' : '逆位'}
                                </div>
                                <div class="card-position">${position}</div>
                            </div>
                        </div>
                    </div>
                `;
                
                // 添加点击翻牌事件
                cardElement.addEventListener('click', function() {
                    flipCard(index);
                });
                
                cardsContainer.appendChild(cardElement);
            });
            
            // 显示历史区域
            historySection.style.display = 'block';
        }
        
        // 3. 翻牌函数
        function flipCard(index) {
            const cardElement = document.querySelector(`.tarot-card[data-index="${index}"]`);
            const card = selectedCards[index];
            
            // 如果牌已经翻开，则不做任何操作
            if (card.flipped) return;
            
            // 添加翻转类触发CSS动画
            cardElement.classList.add('flipped');
            card.flipped = true;
            flippedCards++;
            
            // 显示该牌的解读
            showCardInterpretation(index);
            
            // 如果所有牌都已翻开，显示综合解读并保存到历史
            const totalCards = selectedCards.length;
            if (flippedCards === totalCards) {
                showOverallInterpretation();
                saveToHistory();
            }
        }
        
        // 4. 显示单张牌的解读
        function showCardInterpretation(index) {
            const card = selectedCards[index];
            const meaning = card.orientation === 'upright' ? card.upright : card.reversed;
            
            // 根据占卜类型确定位置名称
            let position = '';
            if (currentSpread === 'three-cards') {
                if (index === 0) position = '过去';
                else if (index === 1) position = '现在';
                else position = '未来';
            } else if (currentSpread === 'celtic-cross') {
                const positions = [
                    '当前状况', '挑战', '潜意识', '过去', '目标',
                    '未来', '自我', '环境', '希望与恐惧', '结果'
                ];
                position = positions[index] || `位置 ${index + 1}`;
            } else if (currentSpread === 'single-card') {
                position = '今日指引';
            }
            
            // 确定花色显示
            let suitDisplay = "";
            if (card.suit === "wands") suitDisplay = "权杖牌组 - 代表行动、能量和创造";
            else if (card.suit === "swords") suitDisplay = "宝剑牌组 - 代表思想、挑战和真理";
            else if (card.suit === "cups") suitDisplay = "圣杯牌组 - 代表情感、关系和直觉";
            else if (card.suit === "pentacles") suitDisplay = "星币牌组 - 代表物质、工作和财富";
            else if (card.suit === "major") suitDisplay = "大阿卡那牌 - 代表人生的重要课题";
            
            // 创建解读元素
            const meaningElement = document.createElement('div');
            meaningElement.className = 'meaning-item';
            meaningElement.innerHTML = `
                <h4><i class="fas fa-star"></i> ${position}: ${card.name} (${card.orientation === 'upright' ? '正位' : '逆位'})</h4>
                <p><strong>所属:</strong> ${suitDisplay}</p>
                <p><strong>含义:</strong> ${meaning.meaning}</p>
                <p><strong>关键词:</strong> ${meaning.keywords ? meaning.keywords.join(', ') : '暂无'}</p>
                <p><strong>详细解读:</strong> ${meaning.description || meaning.meaning}</p>
            `;
            
            detailedMeanings.appendChild(meaningElement);
        }
        
        // 5. 显示综合解读
        function showOverallInterpretation() {
            let overallMessage = `根据你的${getSpreadName(currentSpread)}，`;
            
            // 根据牌阵生成综合解读
            const uprightCount = selectedCards.filter(card => card.orientation === 'upright').length;
            const reversedCount = selectedCards.length - uprightCount;
            
            if (uprightCount === selectedCards.length) {
                overallMessage += `所有牌都是正位，表示你正处在非常积极、顺畅的能量流动中。`;
            } else if (reversedCount === selectedCards.length) {
                overallMessage += `所有牌都是逆位，可能表示你正面临一些挑战或阻碍，需要特别注意。`;
            } else {
                overallMessage += `正位和逆位牌各占一部分，表示你的能量处于变化之中，需要平衡各种力量。`;
            }
            
            // 添加基于具体卡牌的建议
            if (selectedCards.length > 0) {
                const middleIndex = Math.floor(selectedCards.length / 2);
                const middleCard = selectedCards[middleIndex];
                overallMessage += ` 建议你特别关注${middleCard.name}牌传递的信息，它代表了你当前最需要面对的核心课题。`;
            }
            
            interpretationText.textContent = overallMessage;
        }
        
        // 6. 保存到历史记录
        function saveToHistory() {
            const reading = {
                id: Date.now(),
                date: new Date().toLocaleString(),
                spread: currentSpread,
                cards: selectedCards.map(card => ({
                    name: card.name,
                    orientation: card.orientation,
                    suit: card.suit
                }))
            };
            
            readingHistory.unshift(reading); // 添加到开头
            if (readingHistory.length > 10) {
                readingHistory = readingHistory.slice(0, 10); // 只保留最近10次
            }
            
            // 保存到本地存储
            localStorage.setItem('tarotHistory', JSON.stringify(readingHistory));
            
            // 更新历史显示
            updateHistoryDisplay();
        }
        
        // 7. 加载历史记录
        function loadHistory() {
            const savedHistory = localStorage.getItem('tarotHistory');
            if (savedHistory) {
                readingHistory = JSON.parse(savedHistory);
                updateHistoryDisplay();
            }
        }
        
        // 8. 更新历史显示
        function updateHistoryDisplay() {
            historyContainer.innerHTML = '';
            
            if (readingHistory.length === 0) {
                historyContainer.innerHTML = '<p>暂无占卜历史</p>';
                return;
            }
            
            readingHistory.forEach(reading => {
                const historyCard = document.createElement('div');
                historyCard.className = 'history-card';
                
                // 获取第一张牌的花色图标
                let iconClass = "fas fa-star";
                if (reading.cards.length > 0) {
                    const firstCard = reading.cards[0];
                    if (firstCard.suit === "wands") iconClass = "fas fa-fire";
                    else if (firstCard.suit === "swords") iconClass = "fas fa-crosshairs";
                    else if (firstCard.suit === "cups") iconClass = "fas fa-heart";
                    else if (firstCard.suit === "pentacles") iconClass = "fas fa-coins";
                    else if (firstCard.suit === "major") iconClass = "fas fa-crown";
                }
                
                historyCard.innerHTML = `
                    <i class="${iconClass}" style="font-size:1.5rem; color:#d4af37;"></i>
                    <div class="history-card-name">${reading.cards.length}张牌</div>
                    <div class="history-card-name" style="font-size:0.7rem; margin-top:2px;">${reading.date.split(' ')[0]}</div>
                `;
                
                historyCard.addEventListener('click', function() {
                    alert(`占卜时间：${reading.date}\n牌阵：${getSpreadName(reading.spread)}\n牌数：${reading.cards.length}\n第一张牌：${reading.cards[0].name} (${reading.cards[0].orientation === 'upright' ? '正位' : '逆位'})`);
                });
                
                historyContainer.appendChild(historyCard);
            });
        }
        
        // 9. 获取牌阵名称
        function getSpreadName(spreadType) {
            switch(spreadType) {
                case 'three-cards': return '三张牌阵';
                case 'celtic-cross': return '凯尔特十字牌阵';
                case 'single-card': return '单张牌阵';
                default: return '未知牌阵';
            }
        }
        
        // 10. 重新抽牌按钮
        resetBtn.addEventListener('click', function() {
            resultSection.style.display = 'none';
            drawSection.style.display = 'flex';
        });
    </script>
</body>
</html>
