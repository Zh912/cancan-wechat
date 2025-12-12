<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>灿灿 ✨ 甜美展示</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
        body {
            background: linear-gradient(135deg, #ffcfe0 0%, #ff9bc9 25%, #ff7eb3 50%, #ff5d8f 100%);
            min-height: 100vh; display: flex; justify-content: center; align-items: center;
            font-family: -apple-system, BlinkMacSystemFont, 'Helvetica Neue', sans-serif;
            overflow: hidden; position: relative; padding: 20px;
        }
        .container {
            text-align: center; z-index: 10; padding: 30px 20px;
            background-color: rgba(255, 255, 255, 0.95); border-radius: 30px;
            box-shadow: 0 15px 30px rgba(255, 105, 180, 0.25), 0 0 40px rgba(255, 182, 193, 0.3);
            position: relative; width: 100%; max-width: 500px; border: 8px solid #ffcfe0;
        }
        .title { color: #ff5d8f; font-size: 24px; margin-bottom: 25px; font-weight: bold; }
        .characters { display: flex; justify-content: center; gap: 20px; margin: 30px 0; }
        .character {
            font-size: 80px; font-weight: bold; color: #ff5d8f;
            animation: bounce 3s infinite ease-in-out; background: linear-gradient(45deg, #ff5d8f, #ff97b7);
            -webkit-background-clip: text; -webkit-text-fill-color: transparent;
        }
        @keyframes bounce { 0%,100% { transform: translateY(0); } 50% { transform: translateY(-15px); } }
        .button {
            display: inline-block; margin-top: 25px; padding: 14px 28px;
            background: linear-gradient(45deg, #ff5d8f, #ff97b7); color: white;
            border: none; border-radius: 50px; font-size: 16px; font-weight: bold;
            cursor: pointer; transition: all 0.3s ease;
            box-shadow: 0 6px 15px rgba(255, 105, 180, 0.3);
        }
        .button:active { transform: scale(0.98); }
        .floating-hearts { position: absolute; top:0; left:0; width:100%; height:100%; pointer-events: none; }
        .heart { position: absolute; animation: floatUp linear infinite; }
        @keyframes floatUp { 0% { transform: translateY(100vh); opacity: 0; } 10% { opacity: 0.7; } 90% { opacity: 0.7; } 100% { transform: translateY(-100px); opacity: 0; } }
    </style>
</head>
<body>
    <div class="floating-hearts" id="hearts"></div>
    <div class="container">
        <h1 class="title">灿灿 ✨ 可爱展示</h1>
        <div class="characters"><div class="character">灿</div><div class="character">灿</div></div>
        <div style="color:#ff5d8f; margin:25px 0; padding:15px; background:rgba(255,207,224,0.3); border-radius:15px; text-align:left;">
            <div>🌟 <strong>"灿灿"含义：</strong> 形容光彩耀眼，明亮的样子。像阳光一样温暖，像星星一样闪耀。</div>
            <div style="margin-top:10px;">❤ <strong>象征意义：</strong> 代表光明、温暖、希望和正能量，像小太阳一样照亮周围的一切。</div>
        </div>
        <button class="button" id="magicBtn">✨ 点亮魔法</button>
        <div style="color:#999; font-size:12px; margin-top:15px;">提示：点击按钮有惊喜效果</div>
    </div>
    
    <script>
        // 漂浮爱心
        for(let i=0;i<15;i++){
            let heart=document.createElement('div'); heart.className='heart'; heart.innerHTML='❤';
            heart.style.fontSize=(Math.random()*15+10)+'px'; heart.style.left=Math.random()*100+'%';
            heart.style.animationDelay=Math.random()*5+'s'; heart.style.animationDuration=(Math.random()*15+10)+'s';
            heart.style.opacity=Math.random()*0.3+0.4; document.getElementById('hearts').appendChild(heart);
        }
        // 按钮效果
        document.getElementById('magicBtn').addEventListener('click',function(){
            this.style.background='linear-gradient(45deg,#ff97b7,#ff5d8f)';
            this.innerHTML='✨✨ 魔法释放中...';
            setTimeout(()=>{ this.innerHTML='✨ 再次点亮'; this.style.background='linear-gradient(45deg,#ff5d8f,#ff97b7)'; },800);
            document.querySelectorAll('.character').forEach(char=>{
                char.style.transform='scale(1.2)';
                setTimeout(()=>{char.style.transform='scale(1)';},300);
            });
        });
    </script>
</body>
</html>
