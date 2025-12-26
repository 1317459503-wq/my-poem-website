<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>与神同行 | 致林泽满</title>
    <style>
        /* 最简CSS - 无任何特效 */
        * { margin: 0; padding: 0; box-sizing: border-box; }
        
        html, body {
            width: 100%;
            height: 100%;
            overflow: hidden;
        }
        
        body {
            font-family: sans-serif;
            background: #000;
            color: white;
            text-align: center;
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
            transition: opacity 0.5s ease;
        }
        
        .line.show {
            opacity: 1;
        }
        
        /* 完全删除.highlight类，用普通span */
        .red-text {
            color: #FF6666;  /* 只改颜色，无其他样式 */
        }
        
        .blue-text {
            color: #0f52ba;  /* 希腊字颜色 */
            font-family: 'Times New Roman', serif;
        }
        
        .page-number {
            position: absolute;
            bottom: 20px;
            right: 20px;
            font-size: 14px;
            opacity: 0.6;
        }
        
        /* 纯色背景 */
        .page-1 { background: #0f0c29; }
        .page-2 { background: #1a2a6c; }
        .page-3 { background: #3a1c71; }
        .page-4 { background: #141e30; }
        .page-5 { background: #2c3e50; }
        .page-6 { background: #000000; }
        .page-7 { background: #191970; }
        .page-8 { background: #000811; }
        .page-9 { background: #0f2027; }
    </style>
</head>
<body>
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
                <div class="line" style="transition-delay:0.3s">她带着<span class="red-text">星辰坠落</span>般的光辉降临</div>
            </div>
            <div class="page-number">2/9</div>
        </div>
        
        <!-- 页面3 -->
        <div class="page page-3" id="page3">
            <div class="page-content">
                <div class="line">生来就肩负</div>
                <div class="line" style="transition-delay:0.3s">在灰烬中<span class="red-text">重生</span>的使命</div>
            </div>
            <div class="page-number">3/9</div>
        </div>
        
        <!-- 页面4 -->
        <div class="page page-4" id="page4">
            <div class="page-content">
                <div class="line">我只是<span class="red-text">恰好</span></div>
                <div class="line" style="transition-delay:0.3s">见证她<span class="red-text">羽翼尚浅时的脆弱</span></div>
            </div>
            <div class="page-number">4/9</div>
        </div>
        
        <!-- 页面5 -->
        <div class="page page-5" id="page5">
            <div class="page-content">
                <div class="line">却因此获得这份<span class="red-text">殊荣</span>——</div>
                <div class="line" style="transition-delay:0.3s">成为她抵御风暴的<span class="red-text">甲胄</span></div>
            </div>
            <div class="page-number">5/9</div>
        </div>
        
        <!-- 页面6 -->
        <div class="page page-6" id="page6">
            <div class="page-content">
                <div class="line">她赠我一颗名为</div>
                <div class="line" style="transition-delay:0.3s"><span class="blue-text">"φιλία"</span>的珍珠</div>
            </div>
            <div class="page-number">6/9</div>
        </div>
        
        <!-- 页面7 -->
        <div class="page page-7" id="page7">
            <div class="page-content">
                <div class="line">我将它放在心底最<span class="red-text">寂静的深海</span></div>
                <div class="line" style="transition-delay:0.3s">顿时万丈霞光<span class="red-text">撕裂亘古</span>的暗涌</div>
            </div>
            <div class="page-number">7/9</div>
        </div>
        
        <!-- 页面8 -->
        <div class="page page-8" id="page8">
            <div class="page-content">
                <div class="line">爱的泉眼在<span class="red-text">灵魂岩层</span>上苏醒</div>
                <div class="line" style="transition-delay:0.3s"><span class="red-text">源源不断</span>的力量从我心底生出</div>
            </div>
            <div class="page-number">8/9</div>
        </div>
        
        <!-- 页面9 -->
        <div class="page page-9" id="page9">
            <div class="page-content">
                <div class="line">于是我便能一万次<span class="red-text">投身世界灼热的裂缝</span></div>
                <div class="line" style="transition-delay:0.3s">直到将我的<span class="red-text">脊骨</span>锻打成温柔的合金</div>
                <div class="line" style="margin-top:30px; font-size:20px;">
                    成为她漫长征途里，<br>
                    <span style="color:#FF6666; font-size:28px; display:block; margin-top:10px;">
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
        // 最简JS
        let currentPage = 1;
        const totalPages = 9;
        let isAnimating = false;
        
        const container = document.getElementById('container');
        
        // 触摸滑动
        let touchStart = 0;
        
        container.addEventListener('touchstart', function(e) {
            touchStart = e.touches[0].clientY;
        });
        
        container.addEventListener('touchend', function(e) {
            if (isAnimating) return;
            
            const touchEnd = e.changedTouches[0].clientY;
            const diff = touchStart - touchEnd;
            
            if (diff > 50 && currentPage < totalPages) {
                nextPage();
            } else if (diff < -50 && currentPage > 1) {
                prevPage();
            }
        });
        
        // 键盘
        document.addEventListener('keydown', function(e) {
            if (e.key === ' ' || e.key === 'ArrowDown') {
                if (currentPage < totalPages) nextPage();
            } else if (e.key === 'ArrowUp') {
                if (currentPage > 1) prevPage();
            }
        });
        
        function nextPage() {
            if (currentPage >= totalPages || isAnimating) return;
            
            isAnimating = true;
            document.getElementById('page' + currentPage).classList.remove('active');
            showLines(currentPage);
            
            currentPage++;
            document.getElementById('page' + currentPage).classList.add('active');
            
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
        
        // 初始化
        window.addEventListener('load', function() {
            showLines(1);
        });
    </script>
</body>
</html>
