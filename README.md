<!DOCTYPE html>
<html lang="zh">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
    <meta http-equiv="Content-Security-Policy" content="upgrade-insecure-requests">
    <title>与神同行 | 致林泽满</title>
    <link rel="stylesheet" href="https://cdn.bootcss.com/font-awesome/6.4.0/css/all.min.css">
    <style>
        /* 重置样式 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
            -webkit-text-size-adjust: 100%;
            -moz-text-size-adjust: 100%;
            -ms-text-size-adjust: 100%;
        }

        /* 基础布局 */
        html, body {
            width: 100%;
            height: 100%;
            overflow: hidden;
            position: fixed;
            touch-action: none;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'PingFang SC', 'Hiragino Sans GB', 'Microsoft YaHei', sans-serif;
            background: #000;
            color: #fff;
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
            overscroll-behavior: none;
        }

        /* 容器 */
        .container {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
        }

        /* 页面 */
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
            transform: translateY(30px);
            transition: opacity 0.8s cubic-bezier(0.4, 0, 0.2, 1), transform 0.8s cubic-bezier(0.4, 0, 0.2, 1);
            will-change: opacity, transform;
            backface-visibility: hidden;
        }

        .page.active {
            opacity: 1;
            transform: translateY(0);
        }

        /* 内容区域 */
        .page-content {
            text-align: center;
            max-width: 85%;
            width: 100%;
            padding: 0 20px;
        }

        /* 诗句行 */
        .line {
            font-size: clamp(22px, 5vw, 28px);
            line-height: 1.8;
            margin-bottom: 25px;
            opacity: 0;
            transform: translateY(25px);
            transition: all 0.8s cubic-bezier(0.4, 0, 0.2, 1);
            will-change: opacity, transform;
            font-weight: 400;
            letter-spacing: 0.3px;
        }

        .line.show {
            opacity: 1;
            transform: translateY(0);
        }

        /* ====== 高亮文字 - 完全重写版 ====== */
        .highlight {
            color: #FF6666;
            font-weight: 700;
            position: relative;
            font-size: 1.15em;
            display: inline-block;
            margin: 0 3px;
            padding: 0 4px;
            
            /* 彻底移除所有可能的边框/轮廓 */
            outline: none !important;
            -webkit-tap-highlight-color: transparent !important;
            box-shadow: none !important;
            border: none !important;
            text-shadow: none; /* 先移除text-shadow */
            
            /* 防止用户选择和焦点 */
            -webkit-user-select: none;
            -moz-user-select: none;
            -ms-user-select: none;
            user-select: none;
        }

        /* 使用伪元素创建发光效果（避免text-shadow问题） */
        .highlight::before {
            content: attr(data-text);
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            color: #FF6666;
            z-index: -1;
            opacity: 0.7;
            animation: glow-effect 2s infinite alternate;
            
            /* 模糊效果 */
            filter: blur(5px);
            text-shadow: 0 0 10px #FF6666;
        }

        @keyframes glow-effect {
            0% {
                opacity: 0.5;
                filter: blur(4px);
            }
            100% {
                opacity: 0.8;
                filter: blur(6px);
            }
        }

        /* 高亮文字的特殊状态 */
        .highlight:focus,
        .highlight:active,
        .highlight:visited,
        .highlight:hover {
            outline: none !important;
            box-shadow: none !important;
            border: none !important;
            background: none !important;
        }

        /* 希腊文字 */
        .greek {
            font-family: 'Times New Roman', serif;
            color: #0f52ba;
            font-weight: 900;
            font-size: 1.3em;
            display: inline-block;
            margin: 0 5px;
            
            /* 同样移除可能的边框 */
            outline: none !important;
            box-shadow: none !important;
        }

        /* 金色标题 */
        .golden-title {
            font-weight: bold;
            color: #FFD700;
            display: block;
            animation: golden-pulse 2s infinite alternate;
            outline: none !important;
            box-shadow: none !important;
        }

        @keyframes golden-pulse {
            0% {
                opacity: 0.9;
                transform: scale(1);
            }
            100% {
                opacity: 1;
                transform: scale(1.02);
            }
        }

        /* 页码 */
        .page-number {
            position: absolute;
            bottom: 25px;
            right: 25px;
            font-size: 14px;
            opacity: 0.6;
            font-family: 'Courier New', monospace;
            letter-spacing: 1px;
            z-index: 10;
        }

        /* 进度条 */
        .progress-bar {
            position: fixed;
            top: 0;
            left: 0;
            width: 0%;
            height: 3px;
            background: linear-gradient(90deg, #FF6BCB, #6BCEFF);
            transition: width 0.3s ease;
            z-index: 1000;
        }

        /* 滑动提示 */
        .swipe-hint {
            position: absolute;
            bottom: 20px;
            left: 0;
            width: 100%;
            text-align: center;
            font-size: 14px;
            opacity: 0.7;
            animation: float 2s infinite ease-in-out;
            z-index: 5;
            pointer-events: none;
        }

        .swipe-hint i {
            margin-right: 8px;
            color: #6BCEFF;
            animation: bounce 1s infinite alternate;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); opacity: 0.7; }
            50% { transform: translateY(-8px); opacity: 0.9; }
        }

        @keyframes bounce {
            0% { transform: translateY(0); }
            100% { transform: translateY(-5px); }
        }

        /* 标题样式 */
        h1 {
            font-size: clamp(28px, 6vw, 36px);
            margin-bottom: 15px;
            letter-spacing: 1px;
        }

        /* 背景渐变 */
        .page-1 { 
            background: linear-gradient(135deg, #0f0c29, #302b63, #24243e); 
        }
        .page-2 { 
            background: linear-gradient(135deg, #1a2a6c, #b21f1f, #fdbb2b); 
        }
        .page-3 { 
            background: linear-gradient(135deg, #3a1c71, #d76d77, #ffaf7b); 
        }
        .page-4 { 
            background: linear-gradient(135deg, #141e30, #243b55, #141e30); 
        }
        .page-5 { 
            background: linear-gradient(135deg, #2c3e50, #4ca1af, #2c3e50); 
        }
        .page-6 { 
            background: linear-gradient(135deg, #000000, #434343, #000000); 
        }
        .page-7 { 
            background: linear-gradient(135deg, #191970, #2a5298, #0033aa); 
        }
        .page-8 { 
            background: linear-gradient(135deg, #000811, #001122, #000811); 
        }
        .page-9 { 
            background: linear-gradient(135deg, #0f2027, #203a43, #2c5364); 
        }

        /* 首页特别样式 */
        #page1 .page-content {
            padding-top: 10%;
        }

        /* 响应式调整 */
        @media (max-width: 480px) {
            .line {
                font-size: 20px;
                margin-bottom: 20px;
            }
            
            .page-content {
                max-width: 90%;
                padding: 0 15px;
            }
            
            .page {
                padding: 15px;
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
                <div class="line show" style="transition-delay: 0.1s">
                    <h1>与神同行</h1>
                </div>
                <div class="line show" style="transition-delay: 0.3s; font-size: 18px; opacity: 0.9;">
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
                <div class="line" style="transition-delay: 0.3s">她带着<span class="highlight" data-text="星辰坠落">星辰坠落</span>般的光辉降临</div>
            </div>
            <div class="page-number">2/9</div>
        </div>
        
        <!-- 页面3 -->
        <div class="page page-3" id="page3">
            <div class="page-content">
                <div class="line">生来就肩负</div>
                <div class="line" style="transition-delay: 0.3s">在灰烬中<span class="highlight" data-text="重生">重生</span>的使命</div>
            </div>
            <div class="page-number">3/9</div>
        </div>
        
        <!-- 页面4 -->
        <div class="page page-4" id="page4">
            <div class="page-content">
                <div class="line">我只是<span class="highlight" data-text="恰好">恰好</span></div>
                <div class="line" style="transition-delay: 0.3s">见证她<span class="highlight" data-text="羽翼尚浅时的脆弱">羽翼尚浅时的脆弱</span></div>
            </div>
            <div class="page-number">4/9</div>
        </div>
        
        <!-- 页面5 -->
        <div class="page page-5" id="page5">
            <div class="page-content">
                <div class="line">却因此获得这份<span class="highlight" data-text="殊荣">殊荣</span>——</div>
                <div class="line" style="transition-delay: 0.3s">成为她抵御风暴的<span class="highlight" data-text="甲胄">甲胄</span></div>
            </div>
            <div class="page-number">5/9</div>
        </div>
        
        <!-- 页面6 -->
        <div class="page page-6" id="page6">
            <div class="page-content">
                <div class="line">她赠我一颗名为</div>
                <div class="line" style="transition-delay: 0.3s"><span class="greek">"φιλία"</span>的珍珠</div>
            </div>
            <div class="page-number">6/9</div>
        </div>
        
        <!-- 页面7 -->
        <div class="page page-7" id="page7">
            <div class="page-content">
                <div class="line">我将它放在心底最<span class="highlight" data-text="寂静的深海">寂静的深海</span></div>
                <div class="line" style="transition-delay: 0.3s">顿时万丈霞光<span class="highlight" data-text="撕裂亘古">撕裂亘古</span>的暗涌</div>
            </div>
            <div class="page-number">7/9</div>
        </div>
        
        <!-- 页面8 -->
        <div class="page page-8" id="page8">
            <div class="page-content">
                <div class="line">爱的泉眼在<span class="highlight" data-text="灵魂岩层">灵魂岩层</span>上苏醒</div>
                <div class="line" style="transition-delay: 0.3s"><span class="highlight" data-text="源源不断">源源不断</span>的力量从我心底生出</div>
            </div>
            <div class="page-number">8/9</div>
        </div>
        
        <!-- 页面9：终章 -->
        <div class="page page-9" id="page9">
            <div class="page-content">
                <div class="line">于是我便能一万次<span class="highlight" data-text="投身世界灼热的裂缝">投身世界灼热的裂缝</span></div>
                <div class="line" style="transition-delay: 0.3s">直到将我的<span class="highlight" data-text="脊骨">脊骨</span>锻打成温柔的合金</div>
                <div class="line" style="transition-delay: 0.6s; margin-top: 30px; font-size: 22px;">
                    成为她漫长征途里，<br>
                    <span class="golden-title" style="font-size: 28px; margin-top: 10px; display: block;">
                        永不怯懦的副歌。
                    </span>
                </div>
                <div class="line" style="transition-delay: 1.2s; margin-top: 40px; opacity: 0.7; font-size: 16px;">
                    —— 献给我们的友谊
                </div>
            </div>
            <div class="page-number">9/9</div>
        </div>
    </div>

    <script>
        (function() {
            'use strict';
            
            // ====== 1. 变量初始化 ======
            let currentPage = 1;
            const totalPages = 9;
            let isAnimating = false;
            let touchStartY = 0;
            let touchEndY = 0;
            let wheelTimer = null;
            let isMobile = /Android|webOS|iPhone|iPad|iPod|BlackBerry|IEMobile|Opera Mini/i.test(navigator.userAgent);
            
            // ====== 2. DOM元素缓存 ======
            const container = document.getElementById('container');
            const progressBar = document.getElementById('progressBar');
            
            // ====== 3. 触摸事件处理 ======
            function handleTouchStart(e) {
                touchStartY = e.touches[0].clientY;
                e.preventDefault();
            }
            
            function handleTouchEnd(e) {
                if (isAnimating) return;
                
                touchEndY = e.changedTouches[0].clientY;
                const deltaY = touchStartY - touchEndY;
                const minSwipeDistance = 50;
                
                if (deltaY > minSwipeDistance && currentPage < totalPages) {
                    nextPage();
                } else if (deltaY < -minSwipeDistance && currentPage > 1) {
                    prevPage();
                }
                
                e.preventDefault();
            }
            
            // ====== 4. 键盘事件 ======
            function handleKeyDown(e) {
                if (isAnimating) return;
                
                const keyActions = {
                    ' ': () => currentPage < totalPages && nextPage(),
                    'Enter': () => currentPage < totalPages && nextPage(),
                    'ArrowDown': () => currentPage < totalPages && nextPage(),
                    'ArrowRight': () => currentPage < totalPages && nextPage(),
                    'ArrowUp': () => currentPage > 1 && prevPage(),
                    'ArrowLeft': () => currentPage > 1 && prevPage()
                };
                
                if (keyActions[e.key]) {
                    e.preventDefault();
                    keyActions[e.key]();
                }
            }
            
            // ====== 5. 鼠标滚轮事件 ======
            function handleWheel(e) {
                if (isAnimating || isMobile) return;
                
                clearTimeout(wheelTimer);
                wheelTimer = setTimeout(() => {
                    if (e.deltaY > 0 && currentPage < totalPages) {
                        nextPage();
                    } else if (e.deltaY < 0 && currentPage > 1) {
                        prevPage();
                    }
                }, 150);
                
                e.preventDefault();
            }
            
            // ====== 6. 翻页函数 ======
            function nextPage() {
                if (currentPage >= totalPages || isAnimating) return;
                
                isAnimating = true;
                const currentElem = document.getElementById(`page${currentPage}`);
                
                if (currentElem) {
                    currentElem.classList.remove('active');
                    revealLines(currentPage);
                }
                
                currentPage++;
                const nextElem = document.getElementById(`page${currentPage}`);
                
                if (nextElem) {
                    nextElem.classList.add('active');
                    
                    setTimeout(() => {
                        revealLines(currentPage);
                    }, 350);
                }
                
                updateProgress();
                
                setTimeout(() => {
                    isAnimating = false;
                }, 850);
            }
            
            function prevPage() {
                if (currentPage <= 1 || isAnimating) return;
                
                isAnimating = true;
                const currentElem = document.getElementById(`page${currentPage}`);
                
                if (currentElem) {
                    currentElem.classList.remove('active');
                }
                
                currentPage--;
                const prevElem = document.getElementById(`page${currentPage}`);
                
                if (prevElem) {
                    prevElem.classList.add('active');
                }
                
                updateProgress();
                
                setTimeout(() => {
                    isAnimating = false;
                }, 800);
            }
            
            // ====== 7. 诗句显示动画 ======
            function revealLines(pageNum) {
                const page = document.getElementById(`page${pageNum}`);
                if (!page) return;
                
                const lines = page.querySelectorAll('.line:not(.show)');
                
                lines.forEach((line, index) => {
                    setTimeout(() => {
                        line.classList.add('show');
                    }, index * 300);
                });
            }
            
            // ====== 8. 进度条更新 ======
            function updateProgress() {
                const progress = ((currentPage - 1) / (totalPages - 1)) * 100;
                if (progressBar) {
                    progressBar.style.width = `${progress}%`;
                }
                
                for (let i = 1; i <= totalPages; i++) {
                    const pageNumElem = document.querySelector(`#page${i} .page-number`);
                    if (pageNumElem) {
                        pageNumElem.textContent = `${i}/${totalPages}`;
                    }
                }
            }
            
            // ====== 9. 添加滑动提示 ======
            function addSwipeHint() {
                setTimeout(() => {
                    const hint = document.createElement('div');
                    hint.className = 'swipe-hint';
                    hint.innerHTML = '<i class="fas fa-hand-point-up"></i> 向上滑动继续';
                    hint.style.opacity = '0';
                    
                    if (container) {
                        container.appendChild(hint);
                        
                        setTimeout(() => {
                            hint.style.transition = 'opacity 0.8s ease';
                            hint.style.opacity = '0.7';
                        }, 100);
                        
                        setTimeout(() => {
                            hint.style.opacity = '0';
                            setTimeout(() => {
                                if (hint.parentNode) {
                                    hint.parentNode.removeChild(hint);
                                }
                            }, 1000);
                        }, 5000);
                    }
                }, 2000);
            }
            
            // ====== 10. 初始化 ======
            function init() {
                revealLines(1);
                
                if (container) {
                    container.addEventListener('touchstart', handleTouchStart, { passive: false });
                    container.addEventListener('touchend', handleTouchEnd, { passive: false });
                    container.addEventListener('wheel', handleWheel, { passive: false });
                }
                
                document.addEventListener('keydown', handleKeyDown);
                addSwipeHint();
                updateProgress();
                
                document.addEventListener('touchmove', (e) => {
                    if (e.target.tagName !== 'INPUT' && e.target.tagName !== 'TEXTAREA') {
                        e.preventDefault();
                    }
                }, { passive: false });
            }
            
            // ====== 11. 启动 ======
            if (document.readyState === 'loading') {
                document.addEventListener('DOMContentLoaded', init);
            } else {
                init();
            }
        })();
    </script>
</body>
</html>
