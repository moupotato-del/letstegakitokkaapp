<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
  <meta name="apple-mobile-web-app-capable" content="yes">
  <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
  <title>VIL Canvas - Handwriting Note</title>
  <style>
    :root {
      --bg-color: #0b0f19;
      --card-bg: #151c2c;
      --primary: #10b981;
      --primary-light: #064e3b;
      --text: #f9fafb;
      --sub-text: #9ca3af;
      --border: #2a354d;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      -webkit-tap-highlight-color: transparent;
      touch-action: manipulation;
    }

    html, body {
      width: 100%;
      height: 100%;
      height: 100dvh;
      overflow: hidden;
      background-color: var(--bg-color);
      color: var(--text);
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
    }

    /* おしゃれなスプラッシュ画面 (2.2秒表示) */
    #splash {
      position: fixed;
      inset: 0;
      background: radial-gradient(circle at center, #1a263d 0%, #080b12 100%);
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      z-index: 9999;
      transition: opacity 0.6s cubic-bezier(0.4, 0, 0.2, 1);
    }
    #splash.fade-out {
      opacity: 0;
      pointer-events: none;
    }
    .splash-icon {
      font-size: 3rem;
      margin-bottom: 10px;
      filter: drop-shadow(0 0 12px rgba(16, 185, 129, 0.4));
    }
    .splash-logo {
      font-size: 2.8rem;
      font-weight: 900;
      letter-spacing: 0.25em;
      background: linear-gradient(135deg, #ffffff 0%, var(--primary) 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      margin-bottom: 6px;
    }
    .splash-sub {
      font-size: 0.8rem;
      color: var(--sub-text);
      letter-spacing: 0.3em;
      font-weight: 600;
      text-transform: uppercase;
    }

    /* Main Container */
    .app-container {
      display: flex;
      flex-direction: column;
      height: 100dvh;
      max-width: 600px;
      margin: 0 auto;
      padding: 12px;
      gap: 12px;
    }

    /* Header */
    header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 4px 6px;
      flex-shrink: 0;
    }
    .brand {
      font-size: 1.2rem;
      font-weight: 800;
      color: var(--primary);
      letter-spacing: 0.15em;
    }
    .status-badge {
      font-size: 0.75rem;
      color: #10b981;
      background: rgba(16, 185, 129, 0.12);
      border: 1px solid rgba(16, 185, 129, 0.3);
      padding: 4px 10px;
      border-radius: 20px;
      font-weight: bold;
      display: flex;
      align-items: center;
      gap: 6px;
    }
    .status-dot {
      width: 7px;
      height: 7px;
      background: #10b981;
      border-radius: 50%;
      display: inline-block;
      animation: pulse 2s infinite;
    }

    @keyframes pulse {
      0% { opacity: 1; }
      50% { opacity: 0.3; }
      100% { opacity: 1; }
    }

    /* 1. 一番上：手書きキャンバスエリア (手書き特化・拡大表示) */
    .handdraw-section {
      flex: 1;
      background: var(--card-bg);
      border: 1.5px solid var(--border);
      border-radius: 16px;
      padding: 12px;
      display: flex;
      flex-direction: column;
      gap: 10px;
      min-height: 0;
      box-shadow: 0 8px 24px rgba(0, 0, 0, 0.3);
    }

    .canvas-wrapper {
      flex: 1;
      position: relative;
      background: #05070c;
      border-radius: 12px;
      border: 1px solid var(--border);
      overflow: hidden;
      display: flex;
      justify-content: center;
      align-items: center;
    }

    canvas {
      touch-action: none;
      cursor: crosshair;
      width: 100%;
      height: 100%;
    }

    .canvas-tools {
      display: flex;
      gap: 8px;
      justify-content: space-between;
      align-items: center;
      flex-shrink: 0;
    }

    .tool-btn {
      background: #222d45;
      color: var(--text);
      border: 1px solid var(--border);
      padding: 10px 16px;
      border-radius: 10px;
      font-weight: bold;
      font-size: 0.85rem;
      cursor: pointer;
    }
    .tool-btn:active { background: #2c3b5a; }
    .tool-btn.primary {
      background: var(--primary);
      color: #05070c;
      border: none;
    }

    /* 2. 一番下：カレンダー */
    .calendar-section {
      height: 210px;
      background: var(--card-bg);
      border: 1.5px solid var(--border);
      border-radius: 16px;
      padding: 12px;
      flex-shrink: 0;
      display: flex;
      flex-direction: column;
      box-shadow: 0 4px 16px rgba(0, 0, 0, 0.2);
    }
    .cal-title {
      font-size: 0.88rem;
      font-weight: bold;
      color: var(--sub-text);
      margin-bottom: 8px;
      display: flex;
      justify-content: space-between;
    }
    .cal-grid {
      display: grid;
      grid-template-columns: repeat(7, 1fr);
      gap: 3px;
      text-align: center;
      font-size: 0.75rem;
      flex: 1;
    }
    .cal-head {
      font-weight: bold;
      color: var(--sub-text);
      padding: 2px 0;
    }
    .cal-cell {
      background: #0b0f19;
      border-radius: 6px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: bold;
      color: #d1d5db;
    }
    .cal-cell.today {
      background: rgba(16, 185, 129, 0.2);
      color: var(--primary);
      border: 1px solid var(--primary);
    }
  </style>
</head>
<body>

  <!-- タイトル画面 (手書き特化・2.2秒自動消去) -->
  <div id="splash">
    <div class="splash-icon">✍️</div>
    <div class="splash-logo">CANVAS</div>
    <div class="splash-sub">Handwriting Note</div>
  </div>

  <div class="app-container">
    <header>
      <div class="brand">VIL CANVAS</div>
      <div class="status-badge"><span class="status-dot"></span> リアルタイム常時共有</div>
    </header>

    <!-- 一番上：手書きアニメーションエリア -->
    <section class="handdraw-section">
      <div class="canvas-wrapper" id="canvasContainer">
        <canvas id="mainCanvas"></canvas>
      </div>

      <div class="canvas-tools">
        <button class="tool-btn" onclick="clearCanvas()">クリア</button>
        <button class="tool-btn" onclick="replayAnimation()">▶ 再生</button>
        <button class="tool-btn primary" onclick="autoSyncData()">送信 (自動保存)</button>
      </div>
    </section>

    <!-- 一番下：カレンダー -->
    <section class="calendar-section">
      <div class="cal-title">
        <span id="calMonth">----年--月</span>
        <span style="color:var(--primary); font-weight:bold;">今日</span>
      </div>
      <div class="cal-grid" id="calHeader">
        <div class="cal-head" style="color:#ef4444;">日</div>
        <div class="cal-head">月</div>
        <div class="cal-head">火</div>
        <div class="cal-head">水</div>
        <div class="cal-head">木</div>
        <div class="cal-head">金</div>
        <div class="cal-head" style="color:#3b82f6;">土</div>
      </div>
      <div class="cal-grid" id="calBody"></div>
    </section>
  </div>

  <script>
    const GAS_WEB_APP_URL = "https://script.google.com/macros/s/AKfycbzzX3-your-gas-url/exec";

    // 2.2秒(2200ms)でタイトル画面を消去
    setTimeout(function() {
      const splash = document.getElementById('splash');
      if (splash) {
        splash.classList.add('fade-out');
        setTimeout(() => { splash.style.display = 'none'; }, 600);
      }
    }, 2200);

    let canvas, ctx;
    let isDrawing = false;
    let currentStroke = [];
    let drawHistory = [];
    let startTime = 0;

    window.onload = function() {
      initCanvas();
      renderCalendar();
      setInterval(autoSyncData, 5000); // 5秒ごとのバックグラウンド常時通信
    };

    function initCanvas() {
      const container = document.getElementById('canvasContainer');
      canvas = document.getElementById('mainCanvas');
      canvas.width = container.clientWidth;
      canvas.height = container.clientHeight;

      ctx = canvas.getContext('2d');
      ctx.lineWidth = 4;
      ctx.lineCap = 'round';
      ctx.strokeStyle = '#10b981';

      function getPos(e) {
        const rect = canvas.getBoundingClientRect();
        const clientX = e.touches ? e.touches[0].clientX : e.clientX;
        const clientY = e.touches ? e.touches[0].clientY : e.clientY;
        return { x: clientX - rect.left, y: clientY - rect.top };
      }

      function startDraw(e) {
        isDrawing = true;
        if (drawHistory.length === 0) startTime = Date.now();
        const pos = getPos(e);
        ctx.beginPath();
        ctx.moveTo(pos.x, pos.y);
        currentStroke = [{ type: 'start', x: pos.x, y: pos.y, t: Date.now() - startTime }];
      }

      function moveDraw(e) {
        if (!isDrawing) return;
        e.preventDefault();
        const pos = getPos(e);
        ctx.lineTo(pos.x, pos.y);
        ctx.stroke();
        currentStroke.push({ type: 'move', x: pos.x, y: pos.y, t: Date.now() - startTime });
      }

      function endDraw() {
        if (isDrawing) {
          isDrawing = false;
          drawHistory.push(currentStroke);
          saveLocal();
        }
      }

      canvas.addEventListener('mousedown', startDraw);
      canvas.addEventListener('mousemove', moveDraw);
      canvas.addEventListener('mouseup', endDraw);
      canvas.addEventListener('touchstart', startDraw);
      canvas.addEventListener('touchmove', moveDraw);
      canvas.addEventListener('touchend', endDraw);

      loadLocal();
    }

    function clearCanvas() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      drawHistory = [];
      saveLocal();
    }

    function saveLocal() {
      localStorage.setItem('VIL_CANVAS_DATA', JSON.stringify(drawHistory));
    }

    function loadLocal() {
      const data = localStorage.getItem('VIL_CANVAS_DATA');
      if (data) {
        drawHistory = JSON.parse(data);
        replayAnimation();
      }
    }

    function replayAnimation() {
      if (drawHistory.length === 0) return;
      ctx.clearRect(0, 0, canvas.width, canvas.height);

      let allPoints = [];
      drawHistory.forEach(stroke => { allPoints = allPoints.concat(stroke); });

      let idx = 0;
      const startT = Date.now();

      function step() {
        const elapsed = Date.now() - startT;
        while (idx < allPoints.length && allPoints[idx].t <= elapsed) {
          const pt = allPoints[idx];
          if (pt.type === 'start') {
            ctx.beginPath();
            ctx.moveTo(pt.x, pt.y);
          } else if (pt.type === 'move') {
            ctx.lineTo(pt.x, pt.y);
            ctx.stroke();
          }
          idx++;
        }
        if (idx < allPoints.length) {
          requestAnimationFrame(step);
        }
      }
      requestAnimationFrame(step);
    }

    function autoSyncData() {
      if (drawHistory.length === 0) return;

      fetch(GAS_WEB_APP_URL, {
        method: 'POST',
        headers: { 'Content-Type': 'text/plain' },
        body: JSON.stringify({ canvasData: drawHistory })
      })
      .then(res => res.json())
      .then(res => {
        if (res.canvasData && JSON.stringify(res.canvasData) !== JSON.stringify(drawHistory)) {
          drawHistory = res.canvasData;
          saveLocal();
          replayAnimation();
        }
      })
      .catch(err => console.log('オンライン同期待機中...'));
    }

    function renderCalendar() {
      const now = new Date();
      const year = now.getFullYear();
      const month = now.getMonth();
      document.getElementById('calMonth').innerText = `${year}年 ${month + 1}月`;

      const firstDay = new Date(year, month, 1).getDay();
      const totalDays = new Date(year, month + 1, 0).getDate();
      const body = document.getElementById('calBody');
      body.innerHTML = '';

      for (let i = 0; i < firstDay; i++) {
        body.appendChild(document.createElement('div'));
      }

      for (let day = 1; day <= totalDays; day++) {
        const cell = document.createElement('div');
        cell.className = 'cal-cell';
        if (day === now.getDate()) cell.classList.add('today');
        cell.innerText = day;
        body.appendChild(cell);
      }
    }
  </script>
</body>
</html>
