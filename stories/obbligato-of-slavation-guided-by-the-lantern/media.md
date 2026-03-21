<style>
    .video-arch-container {
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        margin: 30px 0;
    }

    /* 朴素简约版播放器样式 */
    #bili-player {
        width: 100%;
        aspect-ratio: 1080 / 2400; /* 维持视频原始比例 */
        
        /* 电脑端约束：防止垂直溢出，保持客观比例 */
        max-height: 80vh; 
        max-width: calc(80vh * (1080 / 2400));
        
        background: #000;
        border-radius: 4px; /* 极简微圆角，比直角稍温和 */
        border: 1px solid rgba(255, 255, 255, 0.1); /* 极其低调的深灰色边框 */
        box-shadow: 0 10px 30px rgba(0,0,0,0.5); /* 基础沉降阴影 */
        
        display: block;
    }

    /* 针对进度条消失的补救：如果宽度太窄，B站会隐藏进度条。
       这里设定一个最小物理宽度，尝试强制触发B站显示控制栏。 */
    @media (min-width: 769px) {
        #bili-player {
            min-width: 320px; 
        }
    }

    @media (max-width: 768px) {
        #bili-player {
            max-height: none;
            max-width: 100%;
            border-radius: 0; /* 手机端全屏感，不设圆角 */
        }
    }
</style>

<div class="video-arch-container">
    <iframe id="bili-player" 
            src="https://player.bilibili.com/player.html?bvid=BV1UNptzAECq&page=1&high_quality=1&danmaku=0&allowfull=1" 
            scrolling="no" border="0" frameborder="no" framespacing="0" 
            allowfullscreen="true"
            allow="accelerometer; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share">
    </iframe>
</div>

<div class="p-selector">
    <a href="?file=obbligato-of-slavation-guided-by-the-lantern&p=1" class="p-btn" data-p="1">第五话</a>
    <a href="?file=obbligato-of-slavation-guided-by-the-lantern&p=2" class="p-btn" data-p="2">第六话</a>
</div>