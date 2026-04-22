<!DOCTYPE html>
<html lang="uk">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Меню на 14 днів</title>
<link href="https://fonts.googleapis.com/css2?family=Unbounded:wght@400;700;900&family=Nunito:wght@400;600;700&display=swap" rel="stylesheet">
<style>
  :root {
    --green: #2ecc71;
    --bg: #0d1f17;
    --card: #132a1e;
    --card2: #1a3326;
    --accent: #7fffd4;
    --text: #e8f5ee;
    --muted: #8bb89e;
    --meal1: #f39c12;
    --meal2: #27ae60;
    --meal3: #2980b9;
    --meal4: #8e44ad;
    --meal5: #e74c3c;
  }
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body { background: var(--bg); color: var(--text); font-family: 'Nunito', sans-serif; padding: 20px 12px 60px; }
  body::before { content:''; position:fixed; inset:0; background: radial-gradient(ellipse at 20% 10%, rgba(46,204,113,0.08) 0%, transparent 50%), radial-gradient(ellipse at 80% 90%, rgba(127,255,212,0.06) 0%, transparent 50%); pointer-events:none; z-index:0; }
  .container { position:relative; z-index:1; max-width:920px; margin:0 auto; }

  header { text-align:center; padding:32px 0 30px; }
  header h1 { font-family:'Unbounded',sans-serif; font-size:clamp(1.5rem,5vw,2.6rem); font-weight:900; background:linear-gradient(135deg,var(--green),var(--accent)); -webkit-background-clip:text; -webkit-text-fill-color:transparent; background-clip:text; line-height:1.2; margin-bottom:10px; }
  header p { color:var(--muted); font-size:.9rem; max-width:540px; margin:0 auto; line-height:1.6; }

  .goals { display:flex; gap:8px; flex-wrap:wrap; justify-content:center; margin:20px 0 30px; }
  .goal-tag { background:rgba(46,204,113,.12); border:1px solid rgba(46,204,113,.3); color:var(--green); padding:5px 14px; border-radius:20px; font-size:.78rem; font-weight:700; }

  /* WEEK SWITCHER */
  .week-tabs { display:flex; gap:8px; justify-content:center; margin-bottom:24px; }
  .week-tab { background:var(--card); border:2px solid transparent; color:var(--muted); padding:10px 24px; border-radius:30px; font-family:'Unbounded',sans-serif; font-size:.75rem; cursor:pointer; transition:all .2s; }
  .week-tab.active,.week-tab:hover { border-color:var(--green); color:var(--green); background:rgba(46,204,113,.08); }

  /* CALORIE BADGE for week */
  .week-badge { text-align:center; margin-bottom:20px; }
  .kcal-badge { display:inline-flex; align-items:center; gap:8px; background:rgba(46,204,113,.1); border:1px solid rgba(46,204,113,.25); border-radius:30px; padding:7px 20px; font-size:.82rem; color:var(--accent); font-weight:700; }
  .kcal-badge span { color:var(--muted); font-weight:400; font-size:.78rem; }

  .week { display:none; }
  .week.active { display:block; }

  /* DAY CARD */
  .day-card { background:var(--card); border-radius:20px; margin-bottom:18px; overflow:hidden; border:1px solid rgba(46,204,113,.1); transition:transform .2s,border-color .2s; }
  .day-card:hover { transform:translateY(-2px); border-color:rgba(46,204,113,.25); }
  .day-header { display:flex; align-items:center; gap:12px; padding:14px 20px; background:var(--card2); cursor:pointer; user-select:none; }
  .day-num { font-family:'Unbounded',sans-serif; font-size:.68rem; color:var(--muted); background:rgba(0,0,0,.3); padding:3px 8px; border-radius:6px; white-space:nowrap; }
  .day-name { font-family:'Unbounded',sans-serif; font-size:.95rem; font-weight:700; color:var(--accent); flex:1; }
  .day-kcal { font-size:.75rem; color:var(--green); font-weight:700; background:rgba(46,204,113,.1); padding:3px 10px; border-radius:10px; }
  .day-toggle { color:var(--muted); font-size:1.1rem; transition:transform .3s; }
  .day-card.open .day-toggle { transform:rotate(180deg); }
  .day-body { display:none; padding:4px 0 14px; }
  .day-card.open .day-body { display:block; }

  /* MEAL */
  .meal { display:flex; gap:12px; padding:10px 20px; border-bottom:1px solid rgba(255,255,255,.04); align-items:flex-start; }
  .meal:last-child { border-bottom:none; }
  .meal-icon { width:36px; height:36px; border-radius:9px; display:flex; align-items:center; justify-content:center; font-size:1rem; flex-shrink:0; }
  .m1{background:rgba(243,156,18,.15)} .m2{background:rgba(39,174,96,.15)} .m3{background:rgba(41,128,185,.15)} .m4{background:rgba(142,68,173,.15)} .m5{background:rgba(231,76,60,.15)}
  .meal-info { flex:1; min-width:0; }
  .meal-top { display:flex; align-items:center; gap:10px; margin-bottom:5px; flex-wrap:wrap; }
  .meal-label { font-size:.68rem; font-weight:700; text-transform:uppercase; letter-spacing:.08em; }
  .l1{color:var(--meal1)} .l2{color:var(--meal2)} .l3{color:var(--meal3)} .l4{color:var(--meal4)} .l5{color:var(--meal5)}
  .meal-kcal { font-size:.7rem; color:var(--muted); background:rgba(255,255,255,.05); padding:2px 8px; border-radius:8px; }

  .meal-items { display:flex; flex-wrap:wrap; gap:5px; }
  .food-tag { background:rgba(255,255,255,.06); border:1px solid rgba(255,255,255,.08); padding:3px 9px; border-radius:7px; font-size:.8rem; color:var(--text); }
  .food-tag.protein { border-color:rgba(46,204,113,.3); color:#7dffb4; }
  .food-tag.carb { border-color:rgba(255,200,50,.3); color:#ffe57d; }
  .food-tag.fat { border-color:rgba(255,130,50,.3); color:#ffb87d; }
  .food-tag.fruit { border-color:rgba(255,100,100,.3); color:#ffb3b3; }

  /* SWAP HINT */
  .swap-hint { font-size:.7rem; color:var(--muted); margin-top:5px; display:flex; align-items:center; gap:5px; flex-wrap:wrap; }
  .swap-opt { background:rgba(46,204,113,.07); border:1px solid rgba(46,204,113,.18); border-radius:8px; padding:2px 8px; font-size:.75rem; color:#7dffb4; font-weight:700; }
  .swap-opt .sk { color:var(--accent); font-size:.68rem; margin-left:4px; }
  .swap-sep { color:var(--muted); font-size:.72rem; }

  .note-bar { background:rgba(46,204,113,.07); border-top:1px solid rgba(46,204,113,.1); padding:9px 20px; color:var(--muted); font-size:.76rem; display:flex; align-items:center; gap:8px; flex-wrap:wrap; }
  .note-bar strong { color:var(--green); }

  /* TIPS */
  .tips-section { margin-top:36px; background:var(--card); border-radius:20px; padding:22px; border:1px solid rgba(127,255,212,.15); }
  .tips-section h3 { font-family:'Unbounded',sans-serif; font-size:.85rem; color:var(--accent); margin-bottom:14px; }
  .tip { display:flex; gap:11px; margin-bottom:11px; align-items:flex-start; }
  .tip-icon { font-size:1rem; flex-shrink:0; margin-top:2px; }
  .tip-text { font-size:.82rem; color:var(--muted); line-height:1.55; }
  .tip-text strong { color:var(--text); }
  .tip-highlight { background:rgba(231,76,60,.08); border:1px solid rgba(231,76,60,.2); border-radius:12px; padding:11px 13px; }
  .tip-highlight .tip-text strong { color:#ff9a9a; }
  .tip-swap { background:rgba(46,204,113,.07); border:1px solid rgba(46,204,113,.2); border-radius:12px; padding:11px 13px; }
  .tip-swap .tip-text strong { color:var(--accent); }

  footer { text-align:center; margin-top:44px; color:var(--muted); font-size:.72rem; opacity:.6; }
</style>
</head>
<body>
<div class="container">
<header>
  <h1>🥗 Меню на 14 днів</h1>
  <p>Програма харчування для зниження ваги та покращення форми. </p>
</header>

<div class="goals">
  <span class="goal-tag">⚖️ Зниження ваги</span>
  <span class="goal-tag">💪 Покращення форми</span>
  <span class="goal-tag">💧 Зменшення набряків</span>
  <span class="goal-tag">🥦 Нова піраміда харчування</span>
  <span class="goal-tag">🔄 Вуглеводи↔Білки взаємозамінні</span>
</div>

<div class="week-tabs">
  <button class="week-tab active" onclick="showWeek(1,this)">Тиждень 1</button>
  <button class="week-tab" onclick="showWeek(2,this)">Тиждень 2</button>
</div>

<!-- ===================== WEEK 1 ===================== -->
<div class="week active" id="week1">
<div class="week-badge"><div class="kcal-badge">🔥 ~1350–1550 ккал/день <span>· базовий тиждень</span></div></div>

<!-- MON W1 -->
<div class="day-card open">
  <div class="day-header" onclick="toggleDay(this)">
    <span class="day-num">День 1</span><span class="day-name">Понеділок</span><span class="day-kcal">~1380 ккал</span><span class="day-toggle">▼</span>
  </div>
  <div class="day-body">
    <div class="meal"><div class="meal-icon m1">☀️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l1">Сніданок</span><span class="meal-kcal">~270 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Вівсянка 30г</span>
        <span class="food-tag fat">Грецький горіх 10г</span>
        <span class="food-tag fat">Гарбузове насіння 10г</span>
        <span class="food-tag protein">Яйце варене 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m2">🍱</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l2">Перекус</span><span class="meal-kcal">~230 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Бурий рис 50г</span>
        <span class="food-tag fat">Олія 10г</span>
        <span class="food-tag protein">Яєчня 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m3">🍽️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l3">Обід</span><span class="meal-kcal">~390 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Гречка 100г</span>
        <span class="food-tag fat">Філе смажене 70г</span>
      </div>
      <div class="swap-hint">🔄 Білок:
        <span class="swap-opt">Біла риба 100г<span class="sk">~82 ккал</span></span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m4">🥙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l4">Перекус</span><span class="meal-kcal">~240 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Макарони цз 70г</span>
        <span class="food-tag fat">Олія 5г</span>
        <span class="food-tag fat">Сир твердий 20г</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m5">🌙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l5">Вечеря</span><span class="meal-kcal">~100 ккал</span></div>
      <div class="meal-items"><span class="food-tag protein">Кисломолочний Сир 5% 100г</span></div>
    </div></div>
  </div>
  <div class="note-bar">🥦 <strong>До кожного прийому:</strong> овочі + зелень 100–150г · 🍎 фрукти 1–2 на день · 💧 вода 1.5–2.5л</div>
</div>

<!-- TUE W1 -->
<div class="day-card">
  <div class="day-header" onclick="toggleDay(this)">
    <span class="day-num">День 2</span><span class="day-name">Вівторок</span><span class="day-kcal">~1390 ккал</span><span class="day-toggle">▼</span>
  </div>
  <div class="day-body">
    <div class="meal"><div class="meal-icon m1">☀️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l1">Сніданок</span><span class="meal-kcal">~290 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Вівсянка 30г</span>
        <span class="food-tag fat">Грецький горіх 20г</span>
        <span class="food-tag fat">Гарбузове насіння 10г</span>
        <span class="food-tag protein">Яйце варене 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m2">🍱</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l2">Перекус</span><span class="meal-kcal">~200 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Ячна крупа 100г</span>
        <span class="food-tag fat">Олія 5г</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m3">🍽️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l3">Обід</span><span class="meal-kcal">~400 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Гречка 100г</span>
        <span class="food-tag fat">Олія 10г</span>
      </div>
      <div class="swap-hint">🔄 Білок:
        <span class="swap-opt">Філе відварне 70г<span class="sk">~112 ккал</span></span>
        <span class="swap-sep">або</span>
        <span class="swap-opt">Біла риба 100г<span class="sk">~82 ккал</span></span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m4">🥙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l4">Перекус</span><span class="meal-kcal">~230 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Бурий рис 50г</span>
        <span class="food-tag fat">Олія 15г</span>
        <span class="food-tag protein">Яйце варене 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m5">🌙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l5">Вечеря</span><span class="meal-kcal">~100 ккал</span></div>
      <div class="meal-items"><span class="food-tag protein">Кисломолочний сир 5% 100г</span></div>
    </div></div>
  </div>
  <div class="note-bar">🥦 <strong>До кожного прийому:</strong> овочі + зелень 100–150г · 🍎 фрукти 1–2 на день · 💧 вода 1.5–2.5л</div>
</div>

<!-- WED W1 -->
<div class="day-card">
  <div class="day-header" onclick="toggleDay(this)">
    <span class="day-num">День 3</span><span class="day-name">Середа</span><span class="day-kcal">~1400 ккал</span><span class="day-toggle">▼</span>
  </div>
  <div class="day-body">
    <div class="meal"><div class="meal-icon m1">☀️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l1">Сніданок</span><span class="meal-kcal">~265 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Вівсянка 30г</span>
        <span class="food-tag fat">Грецький горіх 10г</span>
        <span class="food-tag fat">Гарбузове насіння 10г</span>
        <span class="food-tag protein">Яєчня 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m2">🍱</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l2">Перекус</span><span class="meal-kcal">~260 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Булгур 100г</span>
        <span class="food-tag fat">Олія 10г</span>
        <span class="food-tag fruit">Яблуко 150г</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m3">🍽️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l3">Обід</span><span class="meal-kcal">~380 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Гречка 100г</span>
        <span class="food-tag fat">Олія 10г</span>
        <span class="food-tag protein">Яйце варене 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m4">🥙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l4">Перекус</span><span class="meal-kcal">~290 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Макарони цз 100г</span>
        <span class="food-tag fat">Олія 5г</span>
        <span class="food-tag fat">Сир твердий 30г</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m5">🌙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l5">Вечеря</span><span class="meal-kcal">~100 ккал</span></div>
      <div class="meal-items"><span class="food-tag protein">Кисломолочний сир 5% 100г</span></div>
    </div></div>
  </div>
  <div class="note-bar">🥦 <strong>До кожного прийому:</strong> овочі + зелень 100–150г · 🍎 фрукти 1–2 на день · 💧 вода 1.5–2.5л</div>
</div>

<!-- THU W1 -->
<div class="day-card">
  <div class="day-header" onclick="toggleDay(this)">
    <span class="day-num">День 4</span><span class="day-name">Четвер</span><span class="day-kcal">~1370 ккал</span><span class="day-toggle">▼</span>
  </div>
  <div class="day-body">
    <div class="meal"><div class="meal-icon m1">☀️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l1">Сніданок</span><span class="meal-kcal">~290 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Вівсянка 40г</span>
        <span class="food-tag fat">Арахіс 20г</span>
        <span class="food-tag fat">Гарбузове насіння 10г</span>
        <span class="food-tag protein">Яйце варене 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m2">🍱</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l2">Перекус</span><span class="meal-kcal">~220 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Перлова крупа 100г</span>
        <span class="food-tag fat">Олія 10г</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m3">🍽️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l3">Обід</span><span class="meal-kcal">~360 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Гречка 100г</span>
        <span class="food-tag fat">Олія 10г</span>
      </div>
      <div class="swap-hint">🔄 Білок:
        <span class="swap-opt">Філе смажене 50г<span class="sk">~85 ккал</span></span>
        <span class="swap-sep">або</span>
        <span class="swap-opt">Біла риба 80г<span class="sk">~66 ккал</span></span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m4">🥙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l4">Перекус</span><span class="meal-kcal">~310 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Макарони цз 100г</span>
        <span class="food-tag fat">Олія 10г</span>
      </div>
      <div class="swap-hint">🔄 Білок:
        <span class="swap-opt">Філе відварне 50г<span class="sk">~80 ккал</span></span>
        <span class="swap-sep">або</span>
        <span class="swap-opt">Яйце 1шт<span class="sk">~70 ккал</span></span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m5">🌙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l5">Вечеря</span><span class="meal-kcal">~100 ккал</span></div>
      <div class="meal-items"><span class="food-tag protein">Кисломолочний сир 5% 100г</span></div>
    </div></div>
  </div>
  <div class="note-bar">🥦 <strong>До кожного прийому:</strong> овочі + зелень 100–150г · 🍎 фрукти 1–2 на день · 💧 вода 1.5–2.5л</div>
</div>

<!-- FRI W1 -->
<div class="day-card">
  <div class="day-header" onclick="toggleDay(this)">
    <span class="day-num">День 5</span><span class="day-name">П'ятниця</span><span class="day-kcal">~1360 ккал</span><span class="day-toggle">▼</span>
  </div>
  <div class="day-body">
    <div class="meal"><div class="meal-icon m1">☀️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l1">Сніданок</span><span class="meal-kcal">~305 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Вівсянка 40г</span>
        <span class="food-tag fat">Грецький горіх 20г</span>
        <span class="food-tag fat">Гарбузове насіння 10г</span>
        <span class="food-tag protein">Яєчня 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m2">🍱</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l2">Перекус</span><span class="meal-kcal">~215 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Бурий рис 50г</span>
        <span class="food-tag fat">Олія 10г</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m3">🍽️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l3">Обід</span><span class="meal-kcal">~340 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Гречка 80г</span>
        <span class="food-tag fat">Олія 10г</span>
      </div>
      <div class="swap-hint">🔄 Білок:
        <span class="swap-opt">Філе смажене 50г<span class="sk">~85 ккал</span></span>
        <span class="swap-sep">або</span>
        <span class="swap-opt">Біла риба 80г<span class="sk">~66 ккал</span></span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m4">🥙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l4">Перекус</span><span class="meal-kcal">~255 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Ячна крупа 80г</span>
        <span class="food-tag fat">Олія 10г</span>
        <span class="food-tag protein">Яйце варене 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m5">🌙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l5">Вечеря</span><span class="meal-kcal">~100 ккал</span></div>
      <div class="meal-items"><span class="food-tag protein">Кисломолочний сир 5% 100г</span></div>
    </div></div>
  </div>
  <div class="note-bar">🥦 <strong>До кожного прийому:</strong> овочі + зелень 100–150г · 🍎 фрукти 1–2 на день · 💧 вода 1.5–2.5л</div>
</div>

<!-- SAT W1 -->
<div class="day-card">
  <div class="day-header" onclick="toggleDay(this)">
    <span class="day-num">День 6</span><span class="day-name">Субота</span><span class="day-kcal">~1410 ккал</span><span class="day-toggle">▼</span>
  </div>
  <div class="day-body">
    <div class="meal"><div class="meal-icon m1">☀️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l1">Сніданок</span><span class="meal-kcal">~250 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Вівсянка 20г</span>
        <span class="food-tag fat">Грецький горіх 20г</span>
        <span class="food-tag fat">Гарбузове насіння 10г</span>
        <span class="food-tag protein">Яйце варене 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m2">🍱</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l2">Перекус</span><span class="meal-kcal">~220 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Перлова крупа 100г</span>
        <span class="food-tag fat">Олія 10г</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m3">🍽️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l3">Обід</span><span class="meal-kcal">~400 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Гречка 100г</span>
        <span class="food-tag fat">Олія 10г</span>
      </div>
      <div class="swap-hint">🔄 Білок:
        <span class="swap-opt">Філе смажене 70г<span class="sk">~119 ккал</span></span>
        <span class="swap-sep">або</span>
        <span class="swap-opt">Біла риба 100г<span class="sk">~82 ккал</span></span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m4">🥙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l4">Перекус</span><span class="meal-kcal">~330 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Макарони цз 150г</span>
        <span class="food-tag fat">Олія 5г</span>
        <span class="food-tag fat">Сир твердий 30г</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m5">🌙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l5">Вечеря</span><span class="meal-kcal">~100 ккал</span></div>
      <div class="meal-items"><span class="food-tag protein">Кисломолочний сир 5% 100г</span></div>
    </div></div>
  </div>
  <div class="note-bar">🥦 <strong>До кожного прийому:</strong> овочі + зелень 100–150г · 🍎 фрукти 1–2 на день · 💧 вода 1.5–2.5л</div>
</div>

<!-- SUN W1 —  -->
<div class="day-card">
  <div class="day-header" onclick="toggleDay(this)">
    <span class="day-num">День 7</span><span class="day-name">Неділя </span><span class="day-kcal">~1420 ккал</span><span class="day-toggle">▼</span>
  </div>
  <div class="day-body">
    <div class="meal"><div class="meal-icon m1">☀️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l1">Сніданок</span><span class="meal-kcal">~270 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Вівсянка 30г</span>
        <span class="food-tag fat">Грецький горіх 10г</span>
        <span class="food-tag fat">Гарбузове насіння 10г</span>
        <span class="food-tag protein">Яйце варене 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m2">🍱</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l2">Перекус</span><span class="meal-kcal">~220 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Макарони цз 50г</span>
        <span class="food-tag fat">Сир твердий 20г</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m3">🍽️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l3">Обід</span><span class="meal-kcal">~430 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Гречка 120г</span>
        <span class="food-tag fat">Олія 10г</span>
      </div>
      <div class="swap-hint">🔄 Білок:
        <span class="swap-opt">Філе смажене 70г<span class="sk">~119 ккал</span></span>
        <span class="swap-sep">або</span>
        <span class="swap-opt">Біла риба 100г<span class="sk">~82 ккал</span></span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m4">🥙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l4">Перекус</span><span class="meal-kcal">~280 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Бурий рис 50г</span>
        <span class="food-tag fat">Олія 10г</span>
        <span class="food-tag protein">Яєчня 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m5">🌙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l5">Вечеря</span><span class="meal-kcal">~100 ккал</span></div>
      <div class="meal-items"><span class="food-tag protein">Кисломолочний сир 5% 100г</span></div>
    </div></div>
  </div>
  <div class="note-bar">🏁 <strong>Вже напівдорозі — оцінка результату тижня!</strong> Зважитись вранці натщесерце · 💧 вода дуже важлива сьогодні сьогодні</div>
</div>

</div><!-- /week1 -->

<!-- ===================== WEEK 2 ===================== -->
<div class="week" id="week2">
<div class="week-badge"><div class="kcal-badge">🔥 ~1550–1750 ккал/день <span>· +150–200 ккал від тижня 1</span></div></div>

<!-- MON W2 -->
<div class="day-card open">
  <div class="day-header" onclick="toggleDay(this)">
    <span class="day-num">День 8</span><span class="day-name">Понеділок</span><span class="day-kcal">~1560 ккал</span><span class="day-toggle">▼</span>
  </div>
  <div class="day-body">
    <div class="meal"><div class="meal-icon m1">☀️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l1">Сніданок</span><span class="meal-kcal">~310 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Вівсянка 40г</span>
        <span class="food-tag fat">Грецький горіх 15г</span>
        <span class="food-tag fat">Гарбузове насіння 10г</span>
        <span class="food-tag protein">Яйце варене 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m2">🍱</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l2">Перекус</span><span class="meal-kcal">~265 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Бурий рис 70г</span>
        <span class="food-tag fat">Олія 10г</span>
        <span class="food-tag protein">Яєчня 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m3">🍽️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l3">Обід</span><span class="meal-kcal">~440 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Гречка 110г</span>
        <span class="food-tag fat">Олія 10г</span>
      </div>
      <div class="swap-hint">🔄 Білок:
        <span class="swap-opt">Філе смажене 80г<span class="sk">~136 ккал</span></span>
        <span class="swap-sep">або</span>
        <span class="swap-opt">Біла риба 120г<span class="sk">~98 ккал</span></span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m4">🥙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l4">Перекус</span><span class="meal-kcal">~270 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Макарони цз 80г</span>
        <span class="food-tag fat">Олія 5г</span>
        <span class="food-tag fat">Сир твердий 25г</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m5">🌙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l5">Вечеря</span><span class="meal-kcal">~120 ккал</span></div>
      <div class="meal-items"><span class="food-tag protein">Кисломолочний сир 5% 120г</span></div>
    </div></div>
  </div>
  <div class="note-bar">🥦 <strong>До кожного прийому:</strong> овочі + зелень 100–150г · 🍎 фрукти 2 на день · 💧 вода 2–3л</div>
</div>

<!-- TUE W2 -->
<div class="day-card">
  <div class="day-header" onclick="toggleDay(this)">
    <span class="day-num">День 9</span><span class="day-name">Вівторок</span><span class="day-kcal">~1570 ккал</span><span class="day-toggle">▼</span>
  </div>
  <div class="day-body">
    <div class="meal"><div class="meal-icon m1">☀️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l1">Сніданок</span><span class="meal-kcal">~320 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Вівсянка 40г</span>
        <span class="food-tag fat">Грецький горіх 20г</span>
        <span class="food-tag fat">Гарбузове насіння 10г</span>
        <span class="food-tag protein">Яйце варене 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m2">🍱</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l2">Перекус</span><span class="meal-kcal">~230 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Ячна крупа 120г</span>
        <span class="food-tag fat">Олія 5г</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m3">🍽️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l3">Обід</span><span class="meal-kcal">~430 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Гречка 110г</span>
        <span class="food-tag fat">Олія 10г</span>
      </div>
      <div class="swap-hint">🔄 Білок:
        <span class="swap-opt">Філе відварне 80г<span class="sk">~128 ккал</span></span>
        <span class="swap-sep">або</span>
        <span class="swap-opt">Біла риба 120г<span class="sk">~98 ккал</span></span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m4">🥙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l4">Перекус</span><span class="meal-kcal">~270 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Бурий рис 60г</span>
        <span class="food-tag fat">Олія 15г</span>
        <span class="food-tag protein">Яйце варене 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m5">🌙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l5">Вечеря</span><span class="meal-kcal">~120 ккал</span></div>
      <div class="meal-items"><span class="food-tag protein">Кисломолочний сир 5% 120г</span></div>
    </div></div>
  </div>
  <div class="note-bar">🥦 <strong>До кожного прийому:</strong> овочі + зелень 100–150г · 🍎 фрукти 2 на день · 💧 вода 2–3л</div>
</div>

<!-- WED W2 -->
<div class="day-card">
  <div class="day-header" onclick="toggleDay(this)">
    <span class="day-num">День 10</span><span class="day-name">Середа</span><span class="day-kcal">~1600 ккал</span><span class="day-toggle">▼</span>
  </div>
  <div class="day-body">
    <div class="meal"><div class="meal-icon m1">☀️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l1">Сніданок</span><span class="meal-kcal">~290 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Вівсянка 35г</span>
        <span class="food-tag fat">Грецький горіх 15г</span>
        <span class="food-tag fat">Гарбузове насіння 10г</span>
        <span class="food-tag protein">Яєчня 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m2">🍱</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l2">Перекус</span><span class="meal-kcal">~290 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Булгур 120г</span>
        <span class="food-tag fat">Олія 10г</span>
        <span class="food-tag fruit">Яблуко 150г</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m3">🍽️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l3">Обід</span><span class="meal-kcal">~420 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Гречка 110г</span>
        <span class="food-tag fat">Олія 10г</span>
        <span class="food-tag protein">Яйце варене 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m4">🥙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l4">Перекус</span><span class="meal-kcal">~350 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Макарони цз 120г</span>
        <span class="food-tag fat">Олія 5г</span>
        <span class="food-tag fat">Сир твердий 35г</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m5">🌙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l5">Вечеря</span><span class="meal-kcal">~120 ккал</span></div>
      <div class="meal-items"><span class="food-tag protein">Кисломолочний сир 5% 120г</span></div>
    </div></div>
  </div>
  <div class="note-bar">🥦 <strong>До кожного прийому:</strong> овочі + зелень 100–150г · 🍎 фрукти 2 на день · 💧 вода 2–3л</div>
</div>

<!-- THU W2 -->
<div class="day-card">
  <div class="day-header" onclick="toggleDay(this)">
    <span class="day-num">День 11</span><span class="day-name">Четвер</span><span class="day-kcal">~1580 ккал</span><span class="day-toggle">▼</span>
  </div>
  <div class="day-body">
    <div class="meal"><div class="meal-icon m1">☀️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l1">Сніданок</span><span class="meal-kcal">~320 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Вівсянка 40г</span>
        <span class="food-tag fat">Арахіс 25г</span>
        <span class="food-tag fat">Гарбузове насіння 10г</span>
        <span class="food-tag protein">Яйце варене 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m2">🍱</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l2">Перекус</span><span class="meal-kcal">~245 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Перлова крупа 120г</span>
        <span class="food-tag fat">Олія 10г</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m3">🍽️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l3">Обід</span><span class="meal-kcal">~420 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Гречка 110г</span>
        <span class="food-tag fat">Олія 10г</span>
      </div>
      <div class="swap-hint">🔄 Білок:
        <span class="swap-opt">Філе смажене 65г<span class="sk">~110 ккал</span></span>
        <span class="swap-sep">або</span>
        <span class="swap-opt">Біла риба 100г<span class="sk">~82 ккал</span></span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m4">🥙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l4">Перекус</span><span class="meal-kcal">~360 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Макарони цз 120г</span>
        <span class="food-tag fat">Олія 10г</span>
      </div>
      <div class="swap-hint">🔄 Білок:
        <span class="swap-opt">Філе відварне 65г<span class="sk">~104 ккал</span></span>
        <span class="swap-sep">або</span>
        <span class="swap-opt">Яйце 1шт<span class="sk">~70 ккал</span></span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m5">🌙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l5">Вечеря</span><span class="meal-kcal">~120 ккал</span></div>
      <div class="meal-items"><span class="food-tag protein">Кисломолочний сир 5% 120г</span></div>
    </div></div>
  </div>
  <div class="note-bar">🥦 <strong>До кожного прийому:</strong> овочі + зелень 100–150г · 🍎 фрукти 2 на день · 💧 вода 2–3л</div>
</div>

<!-- FRI W2 -->
<div class="day-card">
  <div class="day-header" onclick="toggleDay(this)">
    <span class="day-num">День 12</span><span class="day-name">П'ятниця</span><span class="day-kcal">~1560 ккал</span><span class="day-toggle">▼</span>
  </div>
  <div class="day-body">
    <div class="meal"><div class="meal-icon m1">☀️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l1">Сніданок</span><span class="meal-kcal">~335 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Вівсянка 45г</span>
        <span class="food-tag fat">Грецький горіх 20г</span>
        <span class="food-tag fat">Гарбузове насіння 10г</span>
        <span class="food-tag protein">Яєчня 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m2">🍱</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l2">Перекус</span><span class="meal-kcal">~245 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Бурий рис 60г</span>
        <span class="food-tag fat">Олія 10г</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m3">🍽️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l3">Обід</span><span class="meal-kcal">~390 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Гречка 100г</span>
        <span class="food-tag fat">Олія 10г</span>
      </div>
      <div class="swap-hint">🔄 Білок:
        <span class="swap-opt">Філе смажене 65г<span class="sk">~110 ккал</span></span>
        <span class="swap-sep">або</span>
        <span class="swap-opt">Біла риба 100г<span class="sk">~82 ккал</span></span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m4">🥙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l4">Перекус</span><span class="meal-kcal">~295 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Ячна крупа 100г</span>
        <span class="food-tag fat">Олія 10г</span>
        <span class="food-tag protein">Яйце варене 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m5">🌙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l5">Вечеря</span><span class="meal-kcal">~120 ккал</span></div>
      <div class="meal-items"><span class="food-tag protein">Кисломолочний сир 5% 120г</span></div>
    </div></div>
  </div>
  <div class="note-bar">🥦 <strong>До кожного прийому:</strong> овочі + зелень 100–150г · 🍎 фрукти 2 на день · 💧 вода 2–3л</div>
</div>

<!-- SAT W2 -->
<div class="day-card">
  <div class="day-header" onclick="toggleDay(this)">
    <span class="day-num">День 13</span><span class="day-name">Субота</span><span class="day-kcal">~1590 ккал</span><span class="day-toggle">▼</span>
  </div>
  <div class="day-body">
    <div class="meal"><div class="meal-icon m1">☀️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l1">Сніданок</span><span class="meal-kcal">~275 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Вівсянка 30г</span>
        <span class="food-tag fat">Грецький горіх 20г</span>
        <span class="food-tag fat">Гарбузове насіння 10г</span>
        <span class="food-tag protein">Яйце варене 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m2">🍱</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l2">Перекус</span><span class="meal-kcal">~250 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Перлова крупа 120г</span>
        <span class="food-tag fat">Олія 10г</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m3">🍽️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l3">Обід</span><span class="meal-kcal">~440 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Гречка 110г</span>
        <span class="food-tag fat">Олія 10г</span>
      </div>
      <div class="swap-hint">🔄 Білок:
        <span class="swap-opt">Філе смажене 80г<span class="sk">~136 ккал</span></span>
        <span class="swap-sep">або</span>
        <span class="swap-opt">Біла риба 120г<span class="sk">~98 ккал</span></span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m4">🥙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l4">Перекус</span><span class="meal-kcal">~360 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Макарони цз 150г</span>
        <span class="food-tag fat">Олія 5г</span>
        <span class="food-tag fat">Сир твердий 35г</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m5">🌙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l5">Вечеря</span><span class="meal-kcal">~120 ккал</span></div>
      <div class="meal-items"><span class="food-tag protein">Кисломолочний сир 5% 120г</span></div>
    </div></div>
  </div>
  <div class="note-bar">🥦 <strong>До кожного прийому:</strong> овочі + зелень 100–150г · 🍎 фрукти 2 на день · 💧 вода 2–3л</div>
</div>

<!-- SUN W2 — Фінал -->
<div class="day-card">
  <div class="day-header" onclick="toggleDay(this)">
    <span class="day-num">День 14</span><span class="day-name">Неділя — ФІНАЛ 🏆</span><span class="day-kcal">~1620 ккал</span><span class="day-toggle">▼</span>
  </div>
  <div class="day-body">
    <div class="meal"><div class="meal-icon m1">☀️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l1">Сніданок</span><span class="meal-kcal">~310 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Вівсянка 40г</span>
        <span class="food-tag fat">Грецький горіх 15г</span>
        <span class="food-tag fat">Гарбузове насіння 10г</span>
        <span class="food-tag protein">Яйце варене 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m2">🍱</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l2">Перекус</span><span class="meal-kcal">~250 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Макарони цз 60г</span>
        <span class="food-tag fat">Сир твердий 25г</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m3">🍽️</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l3">Обід</span><span class="meal-kcal">~480 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Гречка 130г</span>
        <span class="food-tag fat">Олія 10г</span>
      </div>
      <div class="swap-hint">🔄 Білок:
        <span class="swap-opt">Філе смажене 80г<span class="sk">~136 ккал</span></span>
        <span class="swap-sep">або</span>
        <span class="swap-opt">Біла риба 120г<span class="sk">~98 ккал</span></span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m4">🥙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l4">Перекус</span><span class="meal-kcal">~330 ккал</span></div>
      <div class="meal-items">
        <span class="food-tag carb">Бурий рис 60г</span>
        <span class="food-tag fat">Олія 10г</span>
        <span class="food-tag protein">Яєчня 1шт</span>
      </div>
    </div></div>
    <div class="meal"><div class="meal-icon m5">🌙</div><div class="meal-info">
      <div class="meal-top"><span class="meal-label l5">Вечеря</span><span class="meal-kcal">~120 ккал</span></div>
      <div class="meal-items"><span class="food-tag protein">Кисломолочний сир 5% 120г</span></div>
    </div></div>
  </div>
  <div class="note-bar">🏆 <strong>ФІНАЛ — зважитись та порівняти з днем 1!</strong> Зробіть фото результату · Відзначте найкращий день тижня</div>
</div>

</div><!-- /week2 -->

<!-- TIPS -->
<div class="tips-section">
  <h3>💡 Правила програми</h3>

  <div class="tip tip-highlight">
    <div class="tip-icon">🌙</div>
    <div class="tip-text"><strong>Не їсти за 3 години до сну.</strong> Якщо лягаєте о 23:00 — вечеря не пізніше 20:00. Ідеально — їсти о 18–19 год. Дослідження підтвердили кращий контроль цукру та прискорене спалювання жирів.</div>
  </div>

  <div class="tip tip-swap">
    <div class="tip-icon">🔄</div>
    <div class="tip-text"><strong>Вуглеводи та білки — взаємозамінні.</strong> Можна в будь-який прийом замінити крупу на додатковий білок або навпаки. Приклад: замість 100г гречки — додаткові 120г курки або риби.</div>
  </div>

  <div class="tip">
    <div class="tip-icon">🥦</div>
    <div class="tip-text"><strong>Памʼятажте що в нас Нова харчова піраміда? Овочі та фрукти в основі.</strong> Мінімум 500г овочів щодня. Фрукти 1–2 шт. Клітковина = детокс + довге насичення + здоровий мікробіом.</div>
  </div>

  <div class="tip">
    <div class="tip-icon">💧</div>
    <div class="tip-text"><strong>Вода 1.5–2.5л (тиждень 1) → 2–3л (тиждень 2).</strong> Головний інструмент проти набряків. Пити між прийомами їжі. Мінімум солі — замінювати спеціями та лимоном.</div>
  </div>

  <div class="tip">
    <div class="tip-icon">📈</div>
    <div class="tip-text"><strong>Тиждень 2 = +150–200 ккал.</strong> Збільшення відбувається за рахунок трохи більших порцій крупи (+10–20г) та білку (+10–15г). Тіло адаптується і метаболізм не сповільнюється.</div>
  </div>

  <div class="tip">
    <div class="tip-icon">⚖️</div>
    <div class="tip-text"><strong>Корекція порцій по вазі:</strong> до 65кг — мінус 10% · 65–80кг — норма · від 80кг — плюс 10–15% до білку та круп.</div>
  </div>

  <div class="tip">
    <div class="tip-icon">🏁</div>
    <div class="tip-text"><strong>Полуфінал (день 7) та Фінал (день 14):</strong> зважуватись вранці натщесерце в однакових умовах. Порівняти самопочуття, набряки, форму.</div>
  </div>
</div>

<footer> Мета: форма + мінус набряки · 14 днів</footer>
</div>

<script>
function showWeek(n,btn){
  document.querySelectorAll('.week').forEach(w=>w.classList.remove('active'));
  document.querySelectorAll('.week-tab').forEach(t=>t.classList.remove('active'));
  document.getElementById('week'+n).classList.add('active');
  btn.classList.add('active');
}
function toggleDay(header){
  header.parentElement.classList.toggle('open');
}
</script>
</body>
</html>
