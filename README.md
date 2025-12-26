<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>与神同行 | 年度总结报告</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
        }

        body {
            font-family: 'PingFang SC', 'Hiragino Sans GB', 'Microsoft YaHei', sans-serif;
            background: #000;
            color: #fff;
            overflow: hidden;
            height: 100vh;
            margin: 0;
            font-weight: 500;
        }

        .container {
            position: relative;
            height: 100vh;
            width: 100%;
            overflow: hidden;
        }

        .page {
            position: absolute;
            width: 100%;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 20px;
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.8s ease, transform 0.8s ease;
            background-size: cover;
            background-position: center;
            top: 0;
            left: 0;
        }

        .page.active {
            opacity: 1;
            transform: translateY(0);
        }

        .page-content {
            text-align: center;
            max-width: 85%;
        }

        .line {
            font-size: 24px;
            line-height: 1.6;
            margin-bottom: 20px;
            opacity: 0;
            transform: translateY(20px);
            transition: all 0.8s ease;
        }

        .line.show {
            opacity: 1;
            transform: translateY(0);
        }

        .highlight {
            color: #FF6666;
            font-weight: 700;
            text-shadow: 0 0 8px rgba(0, 240, 255, 0.6);
            position: relative;
            padding: 0 2px;
            font-size: 110%;
            display: inline-block;
            transform: scale(1.05);
            transform-origin: center bottom;
            margin: 0 2px;
            padding: 0 3px;
            letter-spacing: 0.5px;
        }
        
        .greek {
            font-family: 'Times New Roman', serif;
            color: #0f52ba;
            font-weight: 1000;
        }

        .page-number {
            position: absolute;
            bottom: 30px;
            right: 30px;
            font-size: 14px;
            opacity: 0.6;
        }

        .progress-bar {
            position: absolute;
            top: 0;
            left: 0;
            width: 0%;
            height: 3px;
            background: linear-gradient(to right, #FF6BCB, #6BCEFF);
            transition: width 0.3s ease;
            z-index: 1000;
        }

        .swipe-hint {
            position: absolute;
            bottom: 20px;
            width: 100%;
            text-align: center;
            font-size: 14px;
            opacity: 0.7;
            animation: float 2s infinite ease-in-out;
        }

        .swipe-hint i {
            margin-right: 5px;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-5px); }
        }

        /* 每页不同的背景渐变 */
        .page-1 { background: linear-gradient(135deg, #0f0c29, #302b63, #24243e); }
        .page-2 { background: linear-gradient(135deg, #1a2a6c, #b21f1f, #fdbb2d); }
        .page-3 { background: linear-gradient(135deg, #3a1c71, #d76d77, #ffaf7b); }
        .page-4 { background: linear-gradient(135deg, #141e30, #243b55, #141e30); }
        .page-5 { background: linear-gradient(135deg, #2c3e50, #4ca1af, #2c3e50); }
        .page-6 { background: linear-gradient(135deg, #000000, #434343, #000000); }
        .page-7 { background: linear-gradient(135deg, #191970, #2a5298, #0033aa); }
        .page-8 { background: linear-gradient(135deg, #000811, #001122, #000811); }
        .page-final { background: linear-gradient(135deg, #0f2027, #203a43, #2c5364); }

        /* 响应式设计 */
        @media (max-width: 768px) {
            .line {
                font-size: 20px;
                margin-bottom: 15px;
            }
            
            .page-content {
                max-width: 90%;
            }
            
            .highlight {
                font-size: 105%;
            }
        }

        @media (max-width: 480px) {
            .line {
                font-size: 18px;
                margin-bottom: 12px;
            }
            
            .page-number {
                bottom: 20px;
                right: 20px;
                font-size: 12px;
            }
            
            .page-1 h1 {
                font-size: 28px !important;
            }
        }
    </style>
</head>
<body>
    <div class="progress-bar" id="progressBar"></div>
    
    <div class="container" id="container">
        <!-- 页面1：标题页 -->
        <div class="page page-1 active" id="page1">
            <div class="page-content">
                <div class="line show">
                    <i class="fas fa-heart" style="color:#FF6BCB;margin-bottom:20px;font-size:40px;"></i>
                </div>
                <div class="line show" style="transition-delay:0.2s">
                    <h1 style="font-size:32px;margin-bottom:10px;">与神同行</h1>
                </div>
                <div class="line show" style="transition-delay:0.4s">
                    <p style="opacity:0.8;">谨以此，送给我心中珍贵的家人最好的朋友<br>林泽满</p>
                </div>
            </div>
            <div class="page-number">1/9</div>
        </div>
        
        <!-- 页面2：诗句 -->
        <div class="page page-2" id="page2">
            <div class="page-content">
                <div class="line">我与神明有一段友谊</div>
                <div class="line" style="transition-delay:0.6s">她带着<span class="highlight">星辰坠落</span>般的光辉降临</div>
            </div>
            <div class="page-number">2/9</div>
        </div>
        
        <!-- 页面3：诗句 -->
        <div class="page page-3" id="page3">
            <div class="page-content">
                <div class="line">生来就肩负</div>
                <div class="line" style="transition-delay:0.6s">在灰烬中<span class="highlight">重生</span>的使命</div>
            </div>
            <div class="page-number">3/9</div>
        </div>
        
        <!-- 页面4：诗句 -->
        <div class="page page-4" id="page4">
            <div class="page-content">
                <div class="line">我只是<span class="highlight">恰好</span></div>
                <div class="line" style="transition-delay:0.6s">见证她<span class="highlight">羽翼尚浅时的脆弱</span></div>
            </div>
            <div class="page-number">4/9</div>
        </div>
        
        <!-- 页面5：诗句 -->
        <div class="page page-5" id="page5">
            <div class="page-content">
                <div class="line">却因此获得这份<span class="highlight">殊荣</span>——</div>
                <div class="line" style="transition-delay:0.6s">成为她抵御风暴的<span class="highlight">甲胄</span></div>
            </div>
            <div class="page-number">5/9</div>
        </div>
        
        <!-- 页面6：诗句 -->
        <div class="page page-6" id="page6">
            <div class="page-content">
                <div class="line">她赠我一颗名为</div>
                <div class="line" style="transition-delay:0.6s"><span class="greek">"φιλία"</span>的珍珠</div>
            </div>
            <div class="page-number">6/9</div>
        </div>

        <!-- 页面7：诗句 -->
        <div class="page page-7" id="page7">
            <div class="page-content">
                <div class="line">我将它放在心底最<span class="highlight">寂静的深海</span></div>
                <div class="line" style="transition-delay:0.6s">顿时万丈霞光<span class="highlight">撕裂亘古</span>的暗涌</div>
            </div>
            <div class="page-number">7/9</div>
        </div>
        
        <!-- 页面8：诗句 -->
        <div class="page page-8" id="page8">
            <div class="page-content">
                <div class="line">爱的泉眼在<span class="highlight">灵魂岩层</span>上苏醒</div>
                <div class="line" style="transition-delay:0.6s"><span class="highlight">源源不断</span>的力量从我心底生出</div>
            </div>
            <div class="page-number">8/9</div>
        </div>
        
        <!-- 页面9：结束页 -->
        <div class="page page-final" id="page9">
            <div class="page-content">
                <div class="line">于是我便能一万次<span class="highlight">投身世界灼热的裂缝</span></div>
                <div class="line" style="transition-delay:0.6s">直到将我的<span class="highlight">脊骨</span>锻打成温柔的合金</div>
                <div class="line" style="transition-delay:1.2s; margin-top: 30px; font-size: 20px;">
                    成为她漫长征途里，<br>
                    <span style="font-size: 28px; font-weight: bold;
                        color: #FF6666;
                        text-shadow: 0 0 10px, 0 0 20px orange;
                        display: block;
                        margin-top: 10px;">
                        永不怯懦的副歌。
                    </span>
                </div>
                <div class="line" style="transition-delay:3s; margin-top: 40px; opacity: 0.7; font-size: 16px;">
                    —— 献给我们的友谊
                </div>
            </div>
            <div class="page-number">9/9</div>
        </div>
    </div>

    <script>
        let currentPage = 1;
        const totalPages = 9;
        let isAnimating = false;
        let startY = 0;
        let endY = 0;
        let wheelTimeout;

        const container = document.getElementById('container');
        const progressBar = document.getElementById('progressBar');

        // 触摸事件
        container.addEventListener('touchstart', function(e) {
            startY = e.touches[0].clientY;
        }, { passive: true });

        container.addEventListener('touchend', function(e) {
            if (isAnimating) return;
            
            endY = e.changedTouches[0].clientY;
            const diffY = startY - endY;
            
            if (diffY > 50 && currentPage < totalPages) {
                nextPage();
            } else if (diffY < -50 && currentPage > 1) {
                prevPage();
            }
        }, { passive: true });

        // 键盘事件
        document.addEventListener('keydown', function(e) {
            if (isAnimating) return;
            
            if ((e.key === ' ' || e.key === 'Enter' ||
                 e.key === 'ArrowDown' || e.key === 'ArrowRight') &&
                currentPage < totalPages) {
                e.preventDefault();
                nextPage();
            } else if ((e.key === 'ArrowUp' || e.key === 'ArrowLeft') &&
                       currentPage > 1) {
                e.preventDefault();
                prevPage();
            }
        });

        // 滚轮事件
        container.addEventListener('wheel', function(e) {
            if (isAnimating) return;
            
            clearTimeout(wheelTimeout);
            wheelTimeout = setTimeout(() => {
                if (e.deltaY > 0 && currentPage < totalPages) {
                    nextPage();
                } else if (e.deltaY < 0 && currentPage > 1) {
                    prevPage();
                }
            }, 100);
        });

        // 翻页函数
        function nextPage() {
            if (currentPage >= totalPages || isAnimating) return;
            
            isAnimating = true;
            
            const currentPageElement = document.getElementById(`page${currentPage}`);
            currentPageElement.classList.remove('active');
            
            showLinesInPage(currentPage);
            
            currentPage++;
            
            const nextPageElement = document.getElementById(`page${currentPage}`);
            nextPageElement.classList.add('active');
            
            setTimeout(() => {
                showLinesInPage(currentPage);
            }, 300);
            
            updateProgress();
            
            setTimeout(() => {
                isAnimating = false;
            }, 800);
        }

        function prevPage() {
            if (currentPage <= 1 || isAnimating) return;
            
            isAnimating = true;
            
            const currentPageElement = document.getElementById(`page${currentPage}`);
            currentPageElement.classList.remove('active');
            
            currentPage--;
            
            const prevPageElement = document.getElementById(`page${currentPage}`);
            prevPageElement.classList.add('active');
            
            updateProgress();
            
            setTimeout(() => {
                isAnimating = false;
            }, 800);
        }

        // 辅助函数
        function showLinesInPage(pageNum) {
            const pageElement = document.getElementById(`page${pageNum}`);
            const lines = pageElement.querySelectorAll('.line:not(.show)');
            
            lines.forEach((line, index) => {
                setTimeout(() => {
                    line.classList.add('show');
                }, index * 300);
            });
        }

        function updateProgress() {
            const progress = ((currentPage - 1) / (totalPages - 1)) * 100;
            progressBar.style.width = `${progress}%`;
            
            for (let i = 1; i <= totalPages; i++) {
                const pageNumberElement = document.querySelector(`#page${i} .page-number`);
                if (pageNumberElement) {
                    pageNumberElement.textContent = `${i}/${totalPages}`;
                }
            }
        }

        // 初始化
        window.addEventListener('DOMContentLoaded', function() {
            showLinesInPage(1);
            
            setTimeout(() => {
                const swipeHint = document.createElement('div');
                swipeHint.className = 'swipe-hint';
                swipeHint.innerHTML = '<i class="fas fa-hand-point-up"></i> 向上滑动继续';
                container.appendChild(swipeHint);
                
                setTimeout(() => {
                    swipeHint.style.opacity = '0';
                    swipeHint.style.transition = 'opacity 1s ease';
                    setTimeout(() => {
                        if (swipeHint.parentNode) {
                            swipeHint.parentNode.removeChild(swipeHint);
                        }
                    }, 1000);
                }, 5000);
            }, 3000);
            
            updateProgress();
        });
    </script>
</body>
</html>
