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
    opacity: 0;
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
  margin: 0 2px; /* 左右外间距 */
    padding: 0 3px; /* 左右内间距 */
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

.music-note {
    position: absolute;
    font-size: 20px;
    opacity: 0.3;
}

@keyframes float {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-5px); }
}

@keyframes sparkle {
    0% { opacity: 0.2; transform: scale(1); }
    50% { opacity: 0.8; transform: scale(1.1); }
    100% { opacity: 0.2; transform: scale(1); }
}

/* 每页不同的背景渐变 */
.page-1 { background: linear-gradient(135deg, #0f0c29, #302b63, #24243e); }
.page-2 { background: linear-gradient(135deg, #1a2a6c, #b21f1f, #fdbb2b); }
.page-3 { background: linear-gradient(135deg, #3a1c71, #d76d77, #ffaf7b); }
.page-4 { background: linear-gradient(135deg, #141e30, #243b55, #141e30); }
.page-5 { background: linear-gradient(135deg, #2c3e50, #4ca1af, #2c3e50); }
.page-6 { background: linear-gradient(135deg, #000000, #434343, #000000); }
.page-7 { background: linear-gradient(135deg, #191970, #2a5298, #0033aa); }
.page-8 { background: linear-gradient(135deg, #000811, #001122, #000811); }
.page-final { background: linear-gradient(135deg, #0f2027, #203a43, #2c5364); }
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
                <div class="line" style="transition-delay: 0.3s">她带着<span class="highlight">星辰坠落</span>般的光辉降临</div>
            </div>
            <div class="page-number">2/9</div>
        </div>
        
        <!-- 页面3 -->
        <div class="page page-3" id="page3">
            <div class="page-content">
                <div class="line">生来就肩负</div>
                <div class="line" style="transition-delay: 0.3s">在灰烬中<span class="highlight">重生</span>的使命</div>
            </div>
            <div class="page-number">3/9</div>
        </div>
        
        <!-- 页面4 -->
        <div class="page page-4" id="page4">
            <div class="page-content">
                <div class="line">我只是<span class="highlight">恰好</span></div>
                <div class="line" style="transition-delay: 0.3s">见证她<span class="highlight">羽翼尚浅时的脆弱</span></div>
            </div>
            <div class="page-number">4/9</div>
        </div>
        
        <!-- 页面5 -->
        <div class="page page-5" id="page5">
            <div class="page-content">
                <div class="line">却因此获得这份<span class="highlight">殊荣</span>——</div>
                <div class="line" style="transition-delay: 0.3s">成为她抵御风暴的<span class="highlight">甲胄</span></div>
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
                <div class="line">我将它放在心底最<span class="highlight">寂静的深海</span></div>
                <div class="line" style="transition-delay: 0.3s">顿时万丈霞光<span class="highlight">撕裂亘古</span>的暗涌</div>
            </div>
            <div class="page-number">7/9</div>
        </div>
        
        <!-- 页面8 -->
        <div class="page page-8" id="page8">
            <div class="page-content">
                <div class="line">爱的泉眼在<span class="highlight">灵魂岩层</span>上苏醒</div>
                <div class="line" style="transition-delay: 0.3s"><span class="highlight">源源不断</span>的力量从我心底生出</div>
            </div>
            <div class="page-number">8/9</div>
        </div>
        
        <!-- 页面9：终章 -->
        <div class="page page-9" id="page9">
            <div class="page-content">
                <div class="line">于是我便能一万次<span class="highlight">投身世界灼热的裂缝</span></div>
                <div class="line" style="transition-delay: 0.3s">直到将我的<span class="highlight">脊骨</span>锻打成温柔的合金</div>
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
            
            // ====== 3. 触摸事件处理（移动端优化） ======
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
            
            // ====== 5. 鼠标滚轮事件（桌面端） ======
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
                    
                    // 延迟显示新页面的诗句
                    setTimeout(() => {
                        revealLines(currentPage);
                    }, 350);
                }
                
                updateProgress();
                
                // 动画完成后解锁
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
                
                // 更新所有页码显示
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
                        
                        // 淡入效果
                        setTimeout(() => {
                            hint.style.transition = 'opacity 0.8s ease';
                            hint.style.opacity = '0.7';
                        }, 100);
                        
                        // 5秒后淡出并移除
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
                // 显示第一页的诗句
                revealLines(1);
                
                // 添加事件监听器
                if (container) {
                    container.addEventListener('touchstart', handleTouchStart, { passive: false });
                    container.addEventListener('touchend', handleTouchEnd, { passive: false });
                    container.addEventListener('wheel', handleWheel, { passive: false });
                }
                
                document.addEventListener('keydown', handleKeyDown);
                
                // 添加滑动提示
                addSwipeHint();
                
                // 更新进度条
                updateProgress();
                
                // 防止页面滚动
                document.addEventListener('touchmove', (e) => {
                    if (e.target.tagName !== 'INPUT' && e.target.tagName !== 'TEXTAREA') {
                        e.preventDefault();
                    }
                }, { passive: false });
                
                // 页面加载完成提示
                console.log('诗歌页面加载完成，当前页面：', currentPage);
            }
            
            // ====== 11. 启动 ======
            if (document.readyState === 'loading') {
                document.addEventListener('DOMContentLoaded', init);
            } else {
                init();
            }
            
            // 暴露函数到全局（便于调试）
            window.poemApp = {
                nextPage,
                prevPage,
                getCurrentPage: () => currentPage,
                goToPage: (page) => {
                    if (page >= 1 && page <= totalPages && !isAnimating) {
                        const oldPage = currentPage;
                        currentPage = page;
                        
                        const oldElem = document.getElementById(`page${oldPage}`);
                        const newElem = document.getElementById(`page${currentPage}`);
                        
                        if (oldElem) oldElem.classList.remove('active');
                        if (newElem) newElem.classList.add('active');
                        
                        revealLines(currentPage);
                        updateProgress();
                    }
                }
            };
        })();
    </script>
</body>
</html>
