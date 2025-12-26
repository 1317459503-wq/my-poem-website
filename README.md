<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>与神同行 | 致林泽满</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* 极简版CSS */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        html, body {
            width: 100%;
            height: 100%;
            overflow: hidden;
        }
        
        body {
            font-family: 'PingFang SC', 'Hiragino Sans GB', 'Microsoft YaHei', sans-serif;
            background: #000;
            color: white;
        }
        
        .container {
            width: 100%;
            height: 100%;
            position: relative;
        }
        
        .page {
            position: absolute;
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 20px;
            opacity: 0;
            transition: opacity 0.5s ease;
            text-align: center;
        }
        
        .page.active {
            opacity: 1;
        }
        
        .page-content {
            max-width: 90%;
        }
        
        .line {
            font-size: 24px;
            line-height: 1.6;
            margin-bottom: 20px;
            opacity: 0;
            transform: translateY(10px);
            transition: all 0.5s ease;
        }
        
        .line.show {
            opacity: 1;
            transform: translateY(0);
        }
        
        /* 简化版高亮 - 只有颜色，没有边框 */
        .highlight {
            color: #FF6666;
            font-weight: bold;
        }
        
        .greek {
            font-family: 'Times New Roman', serif;
            color: #0f52ba;
            font-weight: bold;
        }
        
        .page-number {
            position: absolute;
            bottom: 20px;
            right: 20px;
            font-size: 14px;
            opacity: 0.6;
        }
        
        .progress-bar {
            position: fixed;
            top: 0;
            left: 0;
            width: 0%;
            height: 3px;
            background: #FF6BCB;
            transition: width 0.3s ease;
            z-index: 1000;
        }
        
        /* 背景色 - 用纯色替代渐变，更稳定 */
        .page-1 { background: #0f0c29; }
        .page-2 { background: #1a2a6c; }
        .page-3 { background: #3a1c71; }
        .page-4 { background: #141e30; }
        .page-5 { background: #2c3e50; }
        .page-6 { background: #000000; }
        .page-7 { background: #191970; }
        .page-8 { background: #000811; }
        .page-9 { background: #0f2027; }
        
        /* 最后一页的特殊文字 */
        .final-highlight {
            color: #FF6666;
            font-weight: bold;
            font-size: 28px;
            display: block;
            margin-top: 10px;
        }
    </style>
</head>
<body>
    <div class="progress-bar" id="progressBar"></div>
    
    <div class="container" id="container">
        <!-- 页面1 -->
        <div class="page page-1 active" id="page1">
            <div class="page-content">
                <div class="line show">
                    <h1 style="font-size:32px; margin-bottom:15px;">与神同行</h1>
                </div>
                <div class="line show" style="font-size:18px; opacity:0.9;">
                    <p>谨以此，送给我心中珍贵的家人</p>
                    <p>最好的朋友 林泽满</p>
                </div>
            </div>
            <div class="page-number">1/9</div>
        </div>
        
        <!-- 页面2 -->
        <div class="page page-2" id="page2">
            <div class="page-content">
                <div class="line">我与神明有一段友谊</div>
                <div class="line" style="transition-delay:0.3s">她带着<span class="highlight">星辰坠落</span>般的光辉降临</div>
            </div>
            <div class="page-number">2/9</div>
        </div>
        
        <!-- 页面3 -->
        <div class="page page-3" id="page3">
            <div class="page-content">
                <div class="line">生来就肩负</div>
                <div class="line" style="transition-delay:0.3s">在灰烬中<span class="highlight">重生</span>的使命</div>
            </div>
            <div class="page-number">3/9</div>
        </div>
        
        <!-- 页面4 -->
        <div class="page page-4" id="page4">
            <div class="page-content">
                <div class="line">我只是<span class="highlight">恰好</span></div>
                <div class="line" style="transition-delay:0.3s">见证她<span class="highlight">羽翼尚浅时的脆弱</span></div>
            </div>
            <div class="page-number">4/9</div>
        </div>
        
        <!-- 页面5 -->
        <div class="page page-5" id="page5">
            <div class="page-content">
                <div class="line">却因此获得这份<span class="highlight">殊荣</span>——</div>
                <div class="line" style="transition-delay:0.3s">成为她抵御风暴的<span class="highlight">甲胄</span></div>
            </div>
            <div class="page-number">5/9</div>
        </div>
        
        <!-- 页面6 -->
        <div class="page page-6" id="page6">
            <div class="page-content">
                <div class="line">她赠我一颗名为</div>
                <div class="line" style="transition-delay:0.3s"><span class="greek">"φιλία"</span>的珍珠</div>
            </div>
            <div class="page-number">6/9</div>
        </div>
        
        <!-- 页面7 -->
        <div class="page page-7" id="page7">
            <div class="page-content">
                <div class="line">我将它放在心底最<span class="highlight">寂静的深海</span></div>
                <div class="line" style="transition-delay:0.3s">顿时万丈霞光<span class="highlight">撕裂亘古</span>的暗涌</div>
            </div>
            <div class="page-number">7/9</div>
        </div>
        
        <!-- 页面8 -->
        <div class="page page-8" id="page8">
            <div class="page-content">
                <div class="line">爱的泉眼在<span class="highlight">灵魂岩层</span>上苏醒</div>
                <div class="line" style="transition-delay:0.3s"><span class="highlight">源源不断</span>的力量从我心底生出</div>
            </div>
            <div class="page-number">8/9</div>
        </div>
        
        <!-- 页面9 -->
        <div class="page page-9" id="page9">
            <div class="page-content">
                <div class="line">于是我便能一万次<span class="highlight">投身世界灼热的裂缝</span></div>
                <div class="line" style="transition-delay:0.3s">直到将我的<span class="highlight">脊骨</span>锻打成温柔的合金</div>
                <div class="line" style="margin-top:30px; font-size:20px;">
                    成为她漫长征途里，<br>
                    <span class="final-highlight">
                        永不怯懦的副歌。
                    </span>
                </div>
                <div class="line" style="margin-top:40px; opacity:0.7; font-size:16px;">
                    —— 献给我们的友谊
                </div>
            </div>
            <div class="page-number">9/9</div>
        </div>
    </div>

    <script>
        // 极简版JS
        let currentPage = 1;
        const totalPages = 9;
        let isAnimating = false;
        
        const container = document.getElementById('container');
        const progressBar = document.getElementById('progressBar');
        
        // 触摸事件
        let startY = 0;
        
        container.addEventListener('touchstart', function(e) {
            startY = e.touches[0].clientY;
        });
        
        container.addEventListener('touchend', function(e) {
            if (isAnimating) return;
            
            const endY = e.changedTouches[0].clientY;
            const diff = startY - endY;
            
            if (diff > 50 && currentPage < totalPages) {
                nextPage();
            } else if (diff < -50 && currentPage > 1) {
                prevPage();
            }
        });
        
        // 键盘事件
        document.addEventListener('keydown', function(e) {
            if (isAnimating) return;
            
            if ((e.key === ' ' || e.key === 'Enter' || e.key === 'ArrowDown') && currentPage < totalPages) {
                nextPage();
            } else if (e.key === 'ArrowUp' && currentPage > 1) {
                prevPage();
            }
        });
        
        // 翻页函数
        function nextPage() {
            if (currentPage >= totalPages || isAnimating) return;
            
            isAnimating = true;
            
            // 隐藏当前页
            document.getElementById('page' + currentPage).classList.remove('active');
            
            // 显示当前页诗句
            showLines(currentPage);
            
            // 显示下一页
            currentPage++;
            document.getElementById('page' + currentPage).classList.add('active');
            
            // 更新进度条
            updateProgress();
            
            // 延迟显示诗句
            setTimeout(() => {
                showLines(currentPage);
                isAnimating = false;
            }, 300);
        }
        
        function prevPage() {
            if (currentPage <= 1 || isAnimating) return;
            
            isAnimating = true;
            
            document.getElementById('page' + currentPage).classList.remove('active');
            currentPage--;
            document.getElementById('page' + currentPage).classList.add('active');
            
            updateProgress();
            
            setTimeout(() => {
                isAnimating = false;
            }, 300);
        }
        
        function showLines(pageNum) {
            const page = document.getElementById('page' + pageNum);
            const lines = page.querySelectorAll('.line:not(.show)');
            
            lines.forEach((line, index) => {
                setTimeout(() => {
                    line.classList.add('show');
                }, index * 200);
            });
        }
        
        function updateProgress() {
            const progress = ((currentPage - 1) / (totalPages - 1)) * 100;
            progressBar.style.width = progress + '%';
            
            // 更新页码
            for (let i = 1; i <= totalPages; i++) {
                const pageNum = document.querySelector('#page' + i + ' .page-number');
                if (pageNum) {
                    pageNum.textContent = i + '/' + totalPages;
                }
            }
        }
        
        // 初始化
        window.addEventListener('load', function() {
            showLines(1);
            updateProgress();
        });
    </script>
</body>
</html>
