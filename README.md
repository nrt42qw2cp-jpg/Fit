
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<meta name="theme-color" content="#0c110e">
<title>FitTrack Premium</title>
<style>
:root{
  --bg:#0c110e;
  --surface:#141b16;
  --surface2:#1b251e;
  --surface3:#263329;
  --line:#2b382e;
  --text:#f4f7f1;
  --muted:#99a89b;
  --lime:#c7ff70;
  --lime-dark:#253b17;
  --orange:#ffb76b;
  --blue:#91c8ff;
  --red:#ff8e8e;
  --radius:23px;
}
*{box-sizing:border-box}
html{scroll-behavior:smooth}
body{
  margin:0;
  background:var(--bg);
  color:var(--text);
  font-family:-apple-system,BlinkMacSystemFont,"Segoe UI",sans-serif;
  font-size:15px;
  line-height:1.5;
  padding-bottom:100px;
}
button,input,select{font:inherit}
button{cursor:pointer}
button:focus-visible,input:focus-visible,select:focus-visible{outline:2px solid var(--lime);outline-offset:3px}
.app{max-width:1000px;margin:auto}
.topbar{
  padding:calc(20px + env(safe-area-inset-top)) 22px 15px;
  display:flex;align-items:center;justify-content:space-between;gap:12px;
}
.logo{font-size:23px;font-weight:900;letter-spacing:-1px}
.logo span{color:var(--lime)}
.avatar{
  width:42px;height:42px;border-radius:50%;
  background:var(--surface3);display:grid;place-items:center;
  color:var(--lime);font-size:19px;border:1px solid var(--line)
}
main{padding:0 17px}
.page{display:none;animation:fade .18s ease}
.page.active{display:block}
@keyframes fade{from{opacity:.65;transform:translateY(3px)}to{opacity:1;transform:none}}
.eyebrow{color:var(--lime);font-size:11px;font-weight:800;letter-spacing:1.6px;text-transform:uppercase}
h1{font-size:30px;line-height:1.15;letter-spacing:-1px;margin:7px 0 9px;font-weight:850}
h2{font-size:19px;letter-spacing:-.35px;margin:0;font-weight:800}
h3{margin:0;font-size:15px}
p{margin:0}
.muted{color:var(--muted)}
.small{font-size:12px}
.pagehead{padding:12px 3px 22px}
.pagehead p{font-size:13px;color:var(--muted);margin-top:7px}
.section-head{display:flex;justify-content:space-between;align-items:center;gap:12px;margin:27px 3px 13px}
.section-head button{flex-shrink:0}
.panel{
  background:var(--surface);
  border:1px solid rgba(180,210,180,.075);
  border-radius:var(--radius);
  padding:19px;margin-bottom:14px;
}
.hero{
  border-radius:29px;padding:23px 20px;
  background:radial-gradient(ellipse at 100% 0%,#2c4424 0%,transparent 56%),linear-gradient(145deg,#1b281d,#131b15 75%);
  border:1px solid #34472e;position:relative;overflow:hidden;
}
.hero-top{display:flex;justify-content:space-between;align-items:center;gap:10px}
.date-pill{background:#263729;color:#dce9d7;padding:7px 11px;border-radius:30px;font-size:11px}
.hero-content{display:grid;grid-template-columns:1fr 150px;gap:12px;align-items:center;margin-top:17px}
.hero h2{font-size:20px;margin-bottom:9px}
.hero .big-number{font-size:42px;font-weight:900;letter-spacing:-2px;line-height:1.1}
.hero .big-number span{font-size:14px;color:var(--muted);letter-spacing:0;font-weight:500}
.hero-copy{font-size:12px;color:#b0bfb0;margin-top:10px;max-width:200px}
.ring-wrap{width:145px;height:145px;position:relative;display:grid;place-items:center;margin:auto}
.ring-wrap svg{width:100%;height:100%;transform:rotate(-90deg)}
.ring-track{fill:none;stroke:#344331;stroke-width:10}
.ring-progress{fill:none;stroke:var(--lime);stroke-width:10;stroke-linecap:round;transition:stroke-dashoffset .4s}
.ring-label{position:absolute;text-align:center}
.ring-label strong{display:block;font-size:24px;letter-spacing:-1px}
.ring-label span{font-size:10px;color:var(--muted)}
.hero-foot{border-top:1px solid #344331;margin-top:20px;padding-top:15px;display:flex;justify-content:space-between;gap:10px}
.hero-foot div{font-size:11px;color:var(--muted)}
.hero-foot strong{display:block;color:var(--text);font-size:15px;margin-top:3px}
.hero-foot .lime{color:var(--lime)}
.stats-grid{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:12px}
.stat-card{
  background:var(--surface);border:1px solid rgba(180,210,180,.075);
  border-radius:21px;padding:17px;min-width:0;
}
.stat-top{display:flex;justify-content:space-between;align-items:center;gap:6px}
.stat-icon{width:36px;height:36px;display:grid;place-items:center;border-radius:12px;background:var(--surface3);font-size:17px}
.stat-value{font-size:27px;font-weight:850;letter-spacing:-1px;margin-top:13px;line-height:1.15}
.stat-value small{font-size:12px;color:var(--muted);font-weight:500;letter-spacing:0}
.stat-label{font-size:12px;color:var(--muted);margin-top:5px}
.progress-track{height:5px;background:#2c382f;border-radius:10px;margin-top:13px;overflow:hidden}
.progress-fill{height:100%;width:0;background:var(--lime);border-radius:10px;transition:width .3s}
.macro-list{display:grid;gap:17px;margin-top:19px}
.macro-row{display:grid;grid-template-columns:44px 1fr auto;gap:11px;align-items:center}
.macro-letter{height:42px;width:42px;display:grid;place-items:center;border-radius:13px;font-weight:850;background:var(--surface3)}
.macro-info strong{font-size:13px;display:block}
.macro-info .progress-track{margin-top:7px}
.macro-total{text-align:right;font-size:12px;color:var(--muted)}
.macro-total strong{font-size:14px;color:var(--text)}
.btn{
  display:inline-flex;align-items:center;justify-content:center;gap:7px;
  background:var(--lime);color:#14200e;border:0;border-radius:13px;
  padding:12px 15px;font-size:12px;font-weight:850;transition:filter .15s;
}
.btn:hover{filter:brightness(1.07)}
.btn.secondary{background:var(--surface3);color:var(--text);border:1px solid var(--line)}
.btn.ghost{background:transparent;color:var(--lime);padding:9px 4px}
.btn.danger{background:#482829;color:#ffdede}
.btn.block{width:100%}
.btn.sm{padding:8px 11px;font-size:11px;border-radius:10px}
.action-grid{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:10px}
.action-tile{
  border:1px solid var(--line);background:var(--surface);
  border-radius:18px;padding:17px 8px;text-align:center;color:var(--text);
}
.action-tile .action-icon{font-size:23px;display:block;margin-bottom:9px}
.action-tile strong{font-size:11px;display:block}
.action-tile span{font-size:10px;color:var(--muted)}
.meal-item,.activity-item,.weight-item{
  display:flex;align-items:center;gap:13px;padding:13px 0;
  border-bottom:1px solid var(--line);
}
.meal-item:last-child,.activity-item:last-child,.weight-item:last-child{border-bottom:0;padding-bottom:0}
.food-thumb{width:54px;height:54px;object-fit:cover;border-radius:15px;background:var(--surface3);flex-shrink:0}
.item-main{flex:1;min-width:0}
.item-main strong{display:block;font-size:13px;overflow-wrap:anywhere}
.item-main p{font-size:11px;color:var(--muted);margin-top:4px}
.item-side{text-align:right;flex-shrink:0}
.item-side strong{font-size:13px;display:block}
.item-side span{font-size:10px;color:var(--muted)}
.water-card{display:flex;align-items:center;gap:15px}
.water-icon{font-size:29px;width:54px;height:54px;display:grid;place-items:center;background:#20384a;border-radius:17px;flex-shrink:0}
.water-main{flex:1;min-width:0}
.water-main strong{font-size:23px;letter-spacing:-.7px}
.water-actions{display:flex;gap:7px;margin-top:12px}
.water-actions .btn{flex:1}
.chips{display:flex;gap:8px;overflow-x:auto;padding:2px 0 12px;scrollbar-width:none}
.chips::-webkit-scrollbar{display:none}
.chip{white-space:nowrap;background:var(--surface2);color:var(--muted);border:1px solid var(--line);border-radius:30px;padding:9px 14px;font-size:11px;font-weight:750}
.chip.active{background:var(--lime);border-color:var(--lime);color:#15200f}
.searchbox{position:relative;margin-bottom:13px}
.searchbox input{padding-left:40px}
.search-icon{position:absolute;left:14px;top:50%;transform:translateY(-50%);font-size:17px;color:var(--muted)}
input,select{
  background:#101712;color:var(--text);border:1px solid var(--line);
  border-radius:13px;padding:13px;width:100%;min-width:0;
}
input::placeholder{color:#718074}
label{display:block;font-size:11px;color:var(--muted);margin-bottom:7px;font-weight:650}
.field{margin-bottom:14px}
.form-grid{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:12px}
.recipe-grid{display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:12px}
.recipe-card{
  background:var(--surface);border:1px solid rgba(180,210,180,.08);
  border-radius:20px;overflow:hidden;min-width:0;
}
.recipe-image-wrap{height:142px;position:relative;background:var(--surface3);overflow:hidden}
.recipe-image{width:100%;height:100%;object-fit:cover;display:block;transition:transform .35s}
.recipe-card:hover .recipe-image{transform:scale(1.04)}
.recipe-tag{position:absolute;top:9px;left:9px;background:#111a15e8;border:1px solid #ffffff20;border-radius:30px;padding:5px 8px;font-size:9px;font-weight:750}
.recipe-body{padding:13px}
.recipe-name{font-size:13px;font-weight:850;line-height:1.35;min-height:35px}
.recipe-sub{font-size:10px;color:var(--muted);margin-top:5px}
.recipe-calories{font-size:20px;font-weight:850;letter-spacing:-.6px;margin-top:12px}
.recipe-calories small{font-size:10px;color:var(--muted);font-weight:500;letter-spacing:0}
.recipe-macros{display:flex;gap:7px;flex-wrap:wrap;margin-top:9px}
.recipe-macros span{font-size:9px;color:#d0ded1;background:var(--surface2);padding:5px 6px;border-radius:7px}
.recipe-body .btn{width:100%;margin-top:12px}
.empty{text-align:center;padding:26px 12px;color:var(--muted);font-size:12px}
.empty-icon{font-size:28px;margin-bottom:7px}
.day-summary{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:8px;margin-top:15px}
.day-summary div{background:var(--surface2);border-radius:13px;padding:12px 8px;text-align:center}
.day-summary strong{display:block;font-size:17px}
.day-summary span{display:block;font-size:10px;color:var(--muted);margin-top:3px}
.divider{height:1px;background:var(--line);margin:17px 0}
.modal{
  display:none;position:fixed;inset:0;z-index:20;background:#000c;
  padding:16px;overflow:auto;align-items:flex-start;justify-content:center;
}
.modal.open{display:flex}
.modal-box{
  width:min(100%,560px);background:var(--surface);border:1px solid var(--line);
  border-radius:25px;padding:18px;margin:auto;max-height:94vh;overflow:auto;
}
.modal-head{display:flex;justify-content:space-between;align-items:center;gap:10px;margin-bottom:15px}
.close-btn{width:36px;height:36px;border-radius:12px;background:var(--surface3);color:var(--text);border:0}
.detail-image{width:100%;height:230px;object-fit:cover;border-radius:17px;background:var(--surface3)}
.detail-title{font-size:25px;font-weight:900;letter-spacing:-.7px;margin-top:15px}
.detail-stats{display:grid;grid-template-columns:repeat(4,minmax(0,1fr));gap:8px;margin:16px 0}
.detail-stat{background:var(--surface2);padding:11px 6px;border-radius:13px;text-align:center}
.detail-stat strong{display:block;font-size:15px}
.detail-stat span{font-size:10px;color:var(--muted)}
.detail-section{font-size:16px;font-weight:850;margin:20px 0 9px}
.ingredient{display:flex;gap:10px;padding:9px 0;border-bottom:1px solid var(--line);font-size:12px;color:#d6e0d6}
.ingredient:last-child{border:0}
.ingredient:before{content:"✓";color:var(--lime);font-weight:900}
.steps{padding-left:19px;color:#c5d1c6;font-size:12px}
.steps li{padding:4px 0 9px}
.bottom-nav{
  position:fixed;z-index:8;bottom:0;left:0;right:0;
  padding:9px 5px calc(9px + env(safe-area-inset-bottom));
  background:#101611f5;border-top:1px solid #2b382e;
  display:flex;justify-content:space-around;gap:1px;
  backdrop-filter:blur(18px);
}
.nav-btn{flex:1;display:flex;align-items:center;justify-content:center;flex-direction:column;gap:4px;background:transparent;color:#829084;border:0;padding:5px 1px;font-size:9px;font-weight:700}
.nav-icon{font-size:19px;line-height:1.2}
.nav-btn.active{color:var(--lime)}
.nav-btn.active .nav-icon{background:var(--lime-dark);border-radius:11px;padding:5px 13px}
.toast{
  display:none;position:fixed;z-index:40;left:50%;bottom:95px;transform:translateX(-50%);
  background:var(--lime);color:#14200e;padding:12px 17px;border-radius:13px;
  font-size:12px;font-weight:850;max-width:90vw;box-shadow:0 8px 30px #0006;
}
@media(min-width:650px){
  main{padding:0 25px}
  .topbar{padding-left:28px;padding-right:28px}
  .stats-grid{grid-template-columns:repeat(4,minmax(0,1fr))}
  .recipe-grid{grid-template-columns:repeat(3,minmax(0,1fr));gap:16px}
  .recipe-image-wrap{height:175px}
  .hero{padding:28px}
  .hero-content{grid-template-columns:1fr 175px}
  .ring-wrap{width:165px;height:165px}
}
@media(max-width:360px){
  main{padding:0 11px}
  .hero-content{grid-template-columns:1fr 115px}
  .ring-wrap{width:112px;height:112px}
  .hero .big-number{font-size:35px}
  .recipe-image-wrap{height:112px}
  .recipe-body{padding:10px}
  .recipe-macros{gap:4px}
}
</style>
</head>
<body>
<div class="app">
<header class="topbar">
  <div>
    <div class="logo">FIT<span>TRACK</span></div>
    <div class="muted small">YOUR HEALTH. YOUR PACE.</div>
  </div>
  <div class="avatar">✦</div>
</header>

<main>
<section class="page active" id="home">
  <div class="pagehead">
    <div class="eyebrow">YOUR DAILY OVERVIEW</div>
    <h1>Stay on track.</h1>
    <p>A little progress every day adds up.</p>
  </div>

  <div class="hero">
    <div class="hero-top">
      <span class="eyebrow">CALORIE INTAKE</span>
      <span class="date-pill" id="dateLabel">TODAY</span>
    </div>
    <div class="hero-content">
      <div>
        <h2>Daily energy</h2>
        <div class="big-number" id="remaining">2,000 <span>kcal left</span></div>
        <p class="hero-copy" id="calorieMessage">You're ready to make today count.</p>
      </div>
      <div class="ring-wrap">
        <svg viewBox="0 0 120 120" aria-label="Calorie progress">
          <circle class="ring-track" cx="60" cy="60" r="49"/>
          <circle class="ring-progress" id="calorieRing" cx="60" cy="60" r="49" stroke-dasharray="307.9" stroke-dashoffset="307.9"/>
        </svg>
        <div class="ring-label"><strong id="ringPercent">0%</strong><span>CONSUMED</span></div>
      </div>
    </div>
    <div class="hero-foot">
      <div>Consumed<strong id="consumed">0 kcal</strong></div>
      <div>Burned<strong class="lime" id="burned">0 kcal</strong></div>
      <div>Daily goal<strong id="goalDisplay">2,000 kcal</strong></div>
    </div>
  </div>

  <div class="section-head"><h2>Your activity</h2><button class="btn ghost" onclick="showPage('activity')">View all ↗</button></div>
  <div class="stats-grid">
    <div class="stat-card">
      <div class="stat-top"><div class="stat-icon">👟</div><span class="muted small">STEPS</span></div>
      <div class="stat-value" id="stepsValue">0</div>
      <div class="stat-label">Daily movement</div>
      <div class="progress-track"><div class="progress-fill" id="stepsBar"></div></div>
    </div>
    <div class="stat-card">
      <div class="stat-top"><div class="stat-icon">🔥</div><span class="muted small">BURNED</span></div>
      <div class="stat-value" id="burnValue">0 <small>kcal</small></div>
      <div class="stat-label">Logged activity</div>
      <div class="progress-track"><div class="progress-fill" id="burnBar"></div></div>
    </div>
    <div class="stat-card">
      <div class="stat-top"><div class="stat-icon">💧</div><span class="muted small">HYDRATION</span></div>
      <div class="stat-value" id="waterValue">0 <small>ml</small></div>
      <div class="stat-label">Water intake</div>
      <div class="progress-track"><div class="progress-fill" id="waterBar"></div></div>
    </div>
    <div class="stat-card">
      <div class="stat-top"><div class="stat-icon">🏋️</div><span class="muted small">WORKOUTS</span></div>
      <div class="stat-value" id="workoutValue">0</div>
      <div class="stat-label">Sessions today</div>
      <div class="progress-track"><div class="progress-fill" id="workoutBar"></div></div>
    </div>
  </div>

  <div class="section-head"><h2>Nutrition breakdown</h2><button class="btn ghost" onclick="showPage('food')">Food diary ↗</button></div>
  <div class="panel">
    <div class="macro-list">
      <div class="macro-row">
        <div class="macro-letter" style="color:var(--lime)">P</div>
        <div class="macro-info"><strong>Protein</strong><div class="progress-track"><div class="progress-fill" id="proteinBar"></div></div></div>
        <div class="macro-total"><strong id="proteinValue">0 g</strong><br><span id="proteinGoal">of 130 g</span></div>
      </div>
      <div class="macro-row">
        <div class="macro-letter" style="color:var(--orange)">C</div>
        <div class="macro-info"><strong>Carbohydrates</strong><div class="progress-track"><div class="progress-fill" id="carbsBar" style="background:var(--orange)"></div></div></div>
        <div class="macro-total"><strong id="carbsValue">0 g</strong><br><span id="carbsGoal">of 220 g</span></div>
      </div>
      <div class="macro-row">
        <div class="macro-letter" style="color:var(--blue)">F</div>
        <div class="macro-info"><strong>Fat</strong><div class="progress-track"><div class="progress-fill" id="fatBar" style="background:var(--blue)"></div></div></div>
        <div class="macro-total"><strong id="fatValue">0 g</strong><br><span id="fatGoal">of 65 g</span></div>
      </div>
    </div>
  </div>

  <div class="section-head"><h2>Quick actions</h2></div>
  <div class="action-grid">
    <button class="action-tile" onclick="showPage('food')"><span class="action-icon">＋</span><strong>Add food</strong><span>Log a meal</span></button>
    <button class="action-tile" onclick="showPage('recipes')"><span class="action-icon">🍽️</span><strong>Recipes</strong><span>Find a meal</span></button>
    <button class="action-tile" onclick="showPage('activity')"><span class="action-icon">↗</span><strong>Activity</strong><span>Log a workout</span></button>
  </div>

  <div class="section-head"><h2>Today's meals</h2><button class="btn ghost" onclick="showPage('food')">See all ↗</button></div>
  <div class="panel" id="homeMeals"></div>

  <div class="section-head"><h2>Stay hydrated</h2></div>
  <div class="panel water-card">
    <div class="water-icon">💧</div>
    <div class="water-main"><div class="muted small">WATER INTAKE</div><strong id="waterSummary">0 ml</strong><div class="muted small" id="waterTargetText">of 2,500 ml daily goal</div></div>
  </div>
  <div class="water-actions" style="margin-top:-4px;margin-bottom:15px">
    <button class="btn block" onclick="addWater(250)">＋ 250 ml</button>
    <button class="btn secondary block" onclick="addWater(500)">＋ 500 ml</button>
    <button class="btn secondary block" onclick="addWater(-250)">− 250 ml</button>
  </div>
</section>

<section class="page" id="food">
  <div class="pagehead"><div class="eyebrow">NUTRITION</div><h1>Food diary.</h1><p>Your meals, your macros, all in one place.</p></div>
  <div class="hero">
    <div class="eyebrow">TODAY'S INTAKE</div>
    <div class="big-number" style="margin-top:9px" id="foodCalories">0 <span>kcal</span></div>
    <div class="muted small" id="foodGoalCaption">of 2,000 kcal daily goal</div>
    <div class="progress-track" style="height:7px;margin-top:17px"><div class="progress-fill" id="foodCalBar"></div></div>
    <div class="day-summary">
      <div><strong id="foodProtein">0g</strong><span>Protein</span></div>
      <div><strong id="foodCarbs">0g</strong><span>Carbs</span></div>
      <div><strong id="foodFat">0g</strong><span>Fat</span></div>
    </div>
  </div>
  <div class="section-head"><h2>Add to your diary</h2></div>
  <div class="panel">
    <div class="field"><label>Food name</label><input id="foodName" placeholder="e.g. Grilled chicken breast"></div>
    <div class="form-grid">
      <div class="field"><label>Meal</label><select id="foodMeal"><option>Breakfast</option><option>Lunch</option><option>Dinner</option><option>Snack</option></select></div>
      <div class="field"><label>Calories (kcal)</label><input id="foodCal" type="number" min="0" placeholder="350"></div>
      <div class="field"><label>Protein (g)</label><input id="foodP" type="number" min="0" placeholder="30"></div>
      <div class="field"><label>Carbs (g)</label><input id="foodC" type="number" min="0" placeholder="40"></div>
      <div class="field"><label>Fat (g)</label><input id="foodF" type="number" min="0" placeholder="10"></div>
    </div>
    <button class="btn block" onclick="addFood()">＋ Add to food diary</button>
    <button class="btn secondary block" style="margin-top:9px" onclick="showPage('recipes')">Explore recipes instead</button>
  </div>
  <div class="section-head"><h2>Logged meals</h2><span class="muted small" id="foodCount"></span></div>
  <div class="panel" id="foodList"></div>
</section>

<section class="page" id="recipes">
  <div class="pagehead"><div class="eyebrow">FIND YOUR NEXT FAVORITE</div><h1>Eat well.</h1><p>Delicious ideas that fit your goals.</p></div>
  <div class="searchbox"><span class="search-icon">⌕</span><input id="recipeSearch" placeholder="Search meals or ingredients..." oninput="renderRecipes()"></div>
  <div class="chips" id="categoryChips"></div>
  <div class="row" style="margin:8px 2px 16px">
    <span class="muted small" id="recipeCount">18 recipes</span>
    <select id="recipeSort" style="width:auto;max-width:175px;padding:9px;font-size:11px" onchange="renderRecipes()">
      <option value="recommended">Recommended</option><option value="calories">Lowest calories</option><option value="protein">Highest protein</option><option value="time">Quickest</option>
    </select>
  </div>
  <div class="recipe-grid" id="recipeGrid"></div>
</section>

<section class="page" id="activity">
  <div class="pagehead"><div class="eyebrow">MOVE WITH PURPOSE</div><h1>Activity.</h1><p>Every step counts. Every session matters.</p></div>
  <div class="stats-grid">
    <div class="stat-card"><div class="stat-icon">👟</div><div class="stat-value" id="activitySteps">0</div><div class="stat-label">Steps today</div></div>
    <div class="stat-card"><div class="stat-icon">🔥</div><div class="stat-value" id="activityBurn">0 <small>kcal</small></div><div class="stat-label">Calories burned</div></div>
  </div>
  <div class="section-head"><h2>Log a workout</h2></div>
  <div class="panel">
    <div class="field"><label>Activity name</label><input id="activityName" placeholder="e.g. Running, walking, gym"></div>
    <div class="form-grid">
      <div class="field"><label>Duration (minutes)</label><input id="activityMinutes" type="number" min="0" placeholder="30"></div>
      <div class="field"><label>Calories burned</label><input id="activityCalories" type="number" min="0" placeholder="250"></div>
    </div>
    <button class="btn block" onclick="addActivity()">Save workout</button>
    <div class="divider"></div>
    <label>Steps today</label><input id="stepsInput" type="number" min="0" placeholder="Enter your total steps">
    <button class="btn secondary block" style="margin-top:10px" onclick="saveSteps()">Update steps</button>
  </div>
  <div class="section-head"><h2>Today's sessions</h2></div>
  <div class="panel" id="activityList"></div>
</section>

<section class="page" id="progress">
  <div class="pagehead"><div class="eyebrow">YOUR JOURNEY</div><h1>Progress.</h1><p>Focus on consistency, not perfection.</p></div>
  <div class="hero">
    <div class="eyebrow">LATEST WEIGHT</div>
    <div class="big-number" style="margin-top:12px" id="latestWeight">— <span>kg</span></div>
    <p class="hero-copy">Record your weight periodically and look at the long-term trend.</p>
  </div>
  <div class="section-head"><h2>Log your weight</h2></div>
  <div class="panel">
    <label>Weight (kg)</label><input id="weightInput" type="number" min="1" step="0.1" placeholder="e.g. 76.5">
    <button class="btn block" style="margin-top:12px" onclick="addWeight()">Save weight</button>
  </div>
  <div class="section-head"><h2>Weight history</h2></div>
  <div class="panel" id="weightList"></div>
</section>

<section class="page" id="settings">
  <div class="pagehead"><div class="eyebrow">MAKE IT YOURS</div><h1>Settings.</h1><p>Personalize your daily goals and manage your data.</p></div>
  <div class="section-head"><h2>Daily targets</h2></div>
  <div class="panel">
    <div class="field"><label>Calories (kcal)</label><input id="goalCalories" type="number" min="0"></div>
    <div class="form-grid">
      <div class="field"><label>Protein (g)</label><input id="goalProtein" type="number" min="0"></div>
      <div class="field"><label>Carbs (g)</label><input id="goalCarbs" type="number" min="0"></div>
      <div class="field"><label>Fat (g)</label><input id="goalFat" type="number" min="0"></div>
      <div class="field"><label>Water (ml)</label><input id="goalWater" type="number" min="0"></div>
    </div>
    <button class="btn block" onclick="saveSettings()">Save daily targets</button>
  </div>
  <div class="section-head"><h2>Your data</h2></div>
  <div class="panel">
    <p class="muted small">Your records are saved in this browser. Export a backup before clearing browser data or switching devices.</p>
    <div class="actions" style="display:flex;gap:9px;margin-top:16px">
      <button class="btn" style="flex:1" onclick="exportData()">Export backup</button>
      <button class="btn secondary" style="flex:1" onclick="document.getElementById('importFile').click()">Import backup</button>
    </div>
    <input id="importFile" type="file" accept=".json,application/json" style="display:none" onchange="importData(event)">
    <div class="divider"></div>
    <button class="btn danger block" onclick="resetData()">Reset all data</button>
  </div>
</section>
</main>
</div>

<nav class="bottom-nav">
  <button class="nav-btn active" data-page="home" onclick="showPage('home')"><span class="nav-icon">⌂</span>Home</button>
  <button class="nav-btn" data-page="food" onclick="showPage('food')"><span class="nav-icon">◉</span>Food</button>
  <button class="nav-btn" data-page="recipes" onclick="showPage('recipes')"><span class="nav-icon">✳</span>Recipes</button>
  <button class="nav-btn" data-page="activity" onclick="showPage('activity')"><span class="nav-icon">↗</span>Activity</button>
  <button class="nav-btn" data-page="progress" onclick="showPage('progress')"><span class="nav-icon">▥</span>Progress</button>
  <button class="nav-btn" data-page="settings" onclick="showPage('settings')"><span class="nav-icon">⚙</span>Settings</button>
</nav>

<div class="modal" id="recipeModal" onclick="if(event.target===this)closeRecipe()">
  <div class="modal-box" id="recipeDetails"></div>
</div>
<div class="toast" id="toast"></div>

<script>
const STORAGE_KEY='fittrack_premium_v2';
const DEFAULT_STATE={
  settings:{calories:2000,protein:130,carbs:220,fat:65,water:2500},
  days:{},weights:[]
};
function clone(obj){return JSON.parse(JSON.stringify(obj))}
function loadState(){
  try{
    const raw=localStorage.getItem(STORAGE_KEY);
    if(raw){
      const s=JSON.parse(raw);
      if(s.settings&&s.days){
        s.weights=s.weights||[];
        s.settings={...DEFAULT_STATE.settings,...s.settings};
        return s;
      }
    }
  }catch(e){}
  return clone(DEFAULT_STATE);
}
let state=loadState();
let selectedCategory='All';
let selectedRecipe=null;
let toastTimer;
function save(){try{localStorage.setItem(STORAGE_KEY,JSON.stringify(state))}catch(e){notify('Storage is full. Export a backup.');}}
function todayKey(){const d=new Date();return d.getFullYear()+'-'+String(d.getMonth()+1).padStart(2,'0')+'-'+String(d.getDate()).padStart(2,'0')}
function getDay(){
  const key=todayKey();
  if(!state.days[key])state.days[key]={food:[],activity:[],water:0,steps:0};
  return state.days[key];
}
function safe(v){return String(v??'').replace(/[&<>"']/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]))}
function fmt(v){return Math.round(Number(v)||0).toLocaleString('en-US')}
function showPage(id){
  document.querySelectorAll('.page').forEach(p=>p.classList.toggle('active',p.id===id));
  document.querySelectorAll('.nav-btn').forEach(b=>b.classList.toggle('active',b.dataset.page===id));
  if(id==='recipes')renderRecipes();
  if(id==='food')renderAll();
  window.scrollTo({top:0,behavior:'smooth'});
}
function notify(msg){
  const el=document.getElementById('toast');el.textContent=msg;el.style.display='block';
  clearTimeout(toastTimer);toastTimer=setTimeout(()=>el.style.display='none',2200);
}

const recipes=[
{id:1,name:'Protein Overnight Oats',category:'Breakfast',kcal:390,p:30,c:48,f:9,time:5,vegetarian:true,desc:'Creamy oats prepared ahead for a busy morning.',img:'https://images.unsplash.com/photo-1517673132405-a56a62b18caf?auto=format&fit=crop&w=800&q=80',ingredients:['50 g rolled oats','150 g Greek yogurt','100 ml milk','Half a banana','15 g chia seeds'],steps:['Combine oats, yogurt, milk and chia seeds.','Mix well in a sealed container.','Refrigerate overnight.','Top with banana before serving.']},
{id:2,name:'Egg & Avocado Toast',category:'Breakfast',kcal:360,p:19,c:32,f:18,time:10,vegetarian:true,desc:'Toasted bread with eggs and creamy avocado.',img:'https://images.unsplash.com/photo-1525351484163-7529414344d8?auto=format&fit=crop&w=800&q=80',ingredients:['2 eggs','2 slices whole-grain bread','Half an avocado','Salt and pepper'],steps:['Toast the bread.','Cook the eggs to your preference.','Mash avocado with seasoning.','Spread on toast and top with eggs.']},
{id:3,name:'Berry Yogurt Bowl',category:'Breakfast',kcal:310,p:25,c:39,f:6,time:5,vegetarian:true,desc:'Greek yogurt with berries and crunchy oats.',img:'https://images.unsplash.com/photo-1488477181946-6428a0291777?auto=format&fit=crop&w=800&q=80',ingredients:['200 g Greek yogurt','100 g mixed berries','25 g granola','1 tsp honey'],steps:['Add yogurt to a bowl.','Top with berries and granola.','Drizzle with honey.']},
{id:4,name:'Chicken & Rice Bowl',category:'Lunch',kcal:520,p:46,c:60,f:10,time:25,desc:'Lean chicken, rice and colorful vegetables.',img:'https://images.unsplash.com/photo-1546069901-ba9599a7e63c?auto=format&fit=crop&w=800&q=80',ingredients:['160 g chicken breast','180 g cooked rice','100 g broccoli','1 tsp olive oil','Paprika and garlic'],steps:['Season chicken with paprika and garlic.','Cook chicken thoroughly in a pan.','Steam or sauté the broccoli.','Serve over rice with olive oil.']},
{id:5,name:'Tuna Crunch Wrap',category:'Lunch',kcal:420,p:37,c:40,f:12,time:10,desc:'A quick tuna wrap packed with protein.',img:'https://images.unsplash.com/photo-1626700051175-6818013e1d4f?auto=format&fit=crop&w=800&q=80',ingredients:['1 whole-wheat tortilla','120 g drained tuna','2 tbsp Greek yogurt','Lettuce','Chopped cucumber'],steps:['Mix tuna with Greek yogurt.','Add lettuce and cucumber to the tortilla.','Spoon tuna over the vegetables.','Fold tightly and serve.']},
{id:6,name:'Salmon & Roasted Potatoes',category:'Dinner',kcal:570,p:40,c:48,f:24,time:30,desc:'Oven-baked salmon with crisp potatoes.',img:'https://images.unsplash.com/photo-1467003909585-2f8a72700288?auto=format&fit=crop&w=800&q=80',ingredients:['150 g salmon fillet','200 g potatoes','1 tsp olive oil','Lemon','Asparagus'],steps:['Heat oven to 200°C.','Cut potatoes into wedges and season.','Roast potatoes until nearly tender.','Add salmon and asparagus; bake until cooked.','Finish with lemon juice.']},
{id:7,name:'Turkey Tomato Pasta',category:'Dinner',kcal:490,p:39,c:58,f:10,time:25,desc:'Tomato pasta with lean turkey.',img:'https://images.unsplash.com/photo-1473093295043-cdd812d0e601?auto=format&fit=crop&w=800&q=80',ingredients:['75 g dry pasta','150 g lean turkey mince','150 g tomato sauce','Garlic','Italian herbs'],steps:['Boil pasta according to its package.','Brown turkey mince in a pan.','Add garlic, tomato sauce and herbs.','Simmer until cooked.','Combine with drained pasta.']},
{id:8,name:'Lentil Vegetable Soup',category:'Vegetarian',kcal:330,p:20,c:49,f:5,time:30,vegetarian:true,desc:'A hearty plant-based soup with lentils.',img:'https://images.unsplash.com/photo-1547592180-85f173990554?auto=format&fit=crop&w=800&q=80',ingredients:['150 g cooked lentils','1 carrot','Half an onion','400 ml vegetable stock','Chopped tomatoes'],steps:['Dice the carrot and onion.','Soften vegetables in a pot.','Add lentils, stock and tomatoes.','Simmer for 20 minutes and season.']},
{id:9,name:'Tofu Veggie Stir-Fry',category:'Vegetarian',kcal:380,p:25,c:35,f:15,time:20,vegetarian:true,desc:'Crispy tofu with vegetables and savory sauce.',img:'https://images.unsplash.com/photo-1512621776951-a57141f2eefd?auto=format&fit=crop&w=800&q=80',ingredients:['180 g firm tofu','1 bell pepper','100 g broccoli','1 tbsp soy sauce','1 tsp sesame oil'],steps:['Press tofu dry and cut into cubes.','Brown tofu in a pan.','Add chopped vegetables.','Stir-fry until tender-crisp.','Add soy sauce and sesame oil.']},
{id:10,name:'Banana Protein Pancakes',category:'Breakfast',kcal:410,p:32,c:44,f:11,time:15,vegetarian:true,desc:'Fluffy banana pancakes with extra protein.',img:'https://images.unsplash.com/photo-1528207776546-365bb710ee93?auto=format&fit=crop&w=800&q=80',ingredients:['1 banana','2 eggs','30 g oat flour','20 g protein powder','A splash of milk'],steps:['Mash banana in a bowl.','Whisk in eggs, oat flour and protein powder.','Add milk if needed.','Cook small pancakes in a nonstick pan.']},
{id:11,name:'Cottage Cheese Bowl',category:'Snack',kcal:230,p:27,c:19,f:5,time:5,vegetarian:true,desc:'A simple high-protein snack with fruit.',img:'https://images.unsplash.com/photo-1490645935967-10de6ba17061?auto=format&fit=crop&w=800&q=80',ingredients:['200 g cottage cheese','Half an apple','10 g walnuts','Cinnamon'],steps:['Spoon cottage cheese into a bowl.','Chop the apple and add it.','Sprinkle walnuts and cinnamon.']},
{id:12,name:'Chocolate Protein Yogurt',category:'Dessert',kcal:250,p:30,c:22,f:5,time:5,vegetarian:true,desc:'Chocolate yogurt for a sweet protein boost.',img:'https://images.unsplash.com/photo-1488477181946-6428a0291777?auto=format&fit=crop&w=800&q=80',ingredients:['200 g Greek yogurt','15 g cocoa powder','20 g protein powder','Honey if desired'],steps:['Add yogurt to a bowl.','Mix in cocoa and protein powder.','Add a little milk if needed.','Chill briefly and serve.']},
{id:13,name:'Garlic Shrimp Noodles',category:'Dinner',kcal:440,p:34,c:55,f:9,time:20,desc:'Quick noodles with garlic shrimp.',img:'https://images.unsplash.com/photo-1569718212165-3a8278d5f624?auto=format&fit=crop&w=800&q=80',ingredients:['150 g shrimp','75 g dry noodles','2 garlic cloves','1 tsp oil','Soy sauce and spring onions'],steps:['Cook noodles according to package.','Sauté garlic briefly in oil.','Add shrimp and cook until opaque.','Toss with noodles and soy sauce.','Garnish with spring onions.']},
{id:14,name:'Chicken Caesar Salad',category:'Lunch',kcal:390,p:42,c:20,f:15,time:15,desc:'A crisp chicken salad with a lighter dressing.',img:'https://images.unsplash.com/photo-1512621776951-a57141f2eefd?auto=format&fit=crop&w=800&q=80',ingredients:['140 g cooked chicken breast','Romaine lettuce','15 g parmesan','Croutons','2 tbsp light Caesar dressing'],steps:['Chop lettuce and slice chicken.','Toss lettuce with dressing.','Add chicken, parmesan and croutons.','Serve immediately.']},
{id:15,name:'Apple Peanut Butter Bites',category:'Snack',kcal:210,p:6,c:26,f:11,time:5,vegetarian:true,desc:'Sweet apple slices with peanut butter.',img:'https://images.unsplash.com/photo-1568702846914-96b305d2aaeb?auto=format&fit=crop&w=800&q=80',ingredients:['1 apple','1 tbsp peanut butter','Cinnamon'],steps:['Slice the apple.','Serve with peanut butter.','Sprinkle with cinnamon.']},
{id:16,name:'Protein Banana Smoothie',category:'High Protein',kcal:320,p:32,c:38,f:5,time:5,vegetarian:true,desc:'A quick smoothie for breakfast or after training.',img:'https://images.unsplash.com/photo-1505252585461-04db1eb84625?auto=format&fit=crop&w=800&q=80',ingredients:['1 banana','1 scoop protein powder','200 ml milk','Ice cubes'],steps:['Add all ingredients to a blender.','Blend until smooth.','Adjust thickness with milk or ice.']},
{id:17,name:'Chickpea Avocado Salad',category:'Vegetarian',kcal:360,p:13,c:38,f:18,time:10,vegetarian:true,desc:'Chickpeas, vegetables and avocado.',img:'https://images.unsplash.com/photo-1512621776951-a57141f2eefd?auto=format&fit=crop&w=800&q=80',ingredients:['150 g cooked chickpeas','Half an avocado','Cherry tomatoes','Cucumber','Lemon juice'],steps:['Rinse and drain chickpeas.','Chop avocado and vegetables.','Combine everything in a bowl.','Dress with lemon juice and seasoning.']},
{id:18,name:'Greek Yogurt Berry Pops',category:'Dessert',kcal:150,p:14,c:19,f:2,time:5,vegetarian:true,desc:'Frozen yogurt treats with berries.',img:'https://images.unsplash.com/photo-1490474418585-ba9bad8fd0ea?auto=format&fit=crop&w=800&q=80',ingredients:['150 g Greek yogurt','80 g berries','1 tsp honey'],steps:['Mix yogurt, berries and honey.','Spoon into ice-pop molds.','Freeze until firm before serving.']}
];

const categories=['All','Breakfast','Lunch','Dinner','High Protein','Vegetarian','Snack','Dessert'];
function renderCategoryChips(){
  document.getElementById('categoryChips').innerHTML=categories.map(c=>
    `<button class="chip ${selectedCategory===c?'active':''}" onclick="selectCategory('${c}')">${c}</button>`
  ).join('');
}
function selectCategory(c){selectedCategory=c;renderCategoryChips();renderRecipes()}
function renderRecipes(){
  const q=(document.getElementById('recipeSearch').value||'').toLowerCase().trim();
  const sort=document.getElementById('recipeSort').value;
  let list=recipes.filter(r=>{
    const searchable=(r.name+' '+r.category+' '+r.desc+' '+r.ingredients.join(' ')).toLowerCase();
    let cat=selectedCategory==='All'||r.category===selectedCategory;
    if(selectedCategory==='High Protein')cat=r.p>=25;
    if(selectedCategory==='Vegetarian')cat=!!r.vegetarian;
    return cat&&searchable.includes(q);
  });
  if(sort==='calories')list.sort((a,b)=>a.kcal-b.kcal);
  if(sort==='protein')list.sort((a,b)=>b.p-a.p);
  if(sort==='time')list.sort((a,b)=>a.time-b.time);
  document.getElementById('recipeCount').textContent=list.length+' recipes';
  document.getElementById('recipeGrid').innerHTML=list.map(r=>`
    <article class="recipe-card">
      <div class="recipe-image-wrap">
        <img class="recipe-image" src="${r.img}" alt="${safe(r.name)}" loading="lazy" onerror="this.style.opacity='.15'">
        <span class="recipe-tag">${safe(r.category)}</span>
      </div>
      <div class="recipe-body">
        <div class="recipe-name">${safe(r.name)}</div>
        <div class="recipe-sub">◷ ${r.time} min · 1 serving</div>
        <div class="recipe-calories">${r.kcal} <small>kcal</small></div>
        <div class="recipe-macros"><span>P ${r.p}g</span><span>C ${r.c}g</span><span>F ${r.f}g</span></div>
        <button class="btn" onclick="openRecipe(${r.id})">View recipe ↗</button>
      </div>
    </article>`).join('')||'<div class="empty" style="grid-column:1/-1"><div class="empty-icon">⌕</div>No recipes found. Try another search.</div>';
}
function openRecipe(id){
  selectedRecipe=recipes.find(r=>r.id===id);if(!selectedRecipe)return;
  const r=selectedRecipe;
  document.getElementById('recipeDetails').innerHTML=`
    <div class="modal-head"><span class="eyebrow">RECIPE DETAILS</span><button class="close-btn" onclick="closeRecipe()">✕</button></div>
    <img class="detail-image" src="${r.img}" alt="${safe(r.name)}" onerror="this.style.opacity='.15'">
    <div class="detail-title">${safe(r.name)}</div>
    <p class="muted small" style="margin-top:7px">${safe(r.desc)}</p>
    <div class="detail-stats">
      <div class="detail-stat"><strong>${r.kcal}</strong><span>kcal</span></div>
      <div class="detail-stat"><strong>${r.p}g</strong><span>Protein</span></div>
      <div class="detail-stat"><strong>${r.c}g</strong><span>Carbs</span></div>
      <div class="detail-stat"><strong>${r.f}g</strong><span>Fat</span></div>
    </div>
    <p class="muted small">◷ ${r.time} minutes · Values are estimates per serving.</p>
    <div class="divider"></div>
    <div class="field"><label>Add to meal</label><select id="recipeMeal"><option>Breakfast</option><option>Lunch</option><option>Dinner</option><option>Snack</option></select></div>
    <div class="field"><label>Number of servings</label><select id="recipeServings"><option value=".5">½ serving</option><option value="1" selected>1 serving</option><option value="1.5">1½ servings</option><option value="2">2 servings</option><option value="3">3 servings</option></select></div>
    <button class="btn block" onclick="addRecipeToDiary()">＋ Add to food diary</button>
    <div class="detail-section">Ingredients</div>
    ${r.ingredients.map(i=>`<div class="ingredient">${safe(i)}</div>`).join('')}
    <div class="detail-section">Instructions</div>
    <ol class="steps">${r.steps.map(s=>`<li>${safe(s)}</li>`).join('')}</ol>`;
  document.getElementById('recipeModal').classList.add('open');
  document.body.style.overflow='hidden';
}
function closeRecipe(){document.getElementById('recipeModal').classList.remove('open');document.body.style.overflow=''}
function addRecipeToDiary(){
  const r=selectedRecipe;if(!r)return;
  const servings=Number(document.getElementById('recipeServings').value);
  const meal=document.getElementById('recipeMeal').value;
  getDay().food.push({name:r.name+(servings===1?'':' × '+servings),meal,cal:Math.round(r.kcal*servings),p:Math.round(r.p*servings),c:Math.round(r.c*servings),f:Math.round(r.f*servings),recipeId:r.id,at:Date.now()});
  save();renderAll();closeRecipe();showPage('food');notify('Recipe added to your food diary');
}
function addFood(){
  const name=document.getElementById('foodName').value.trim();
  const cal=Number(document.getElementById('foodCal').value);
  if(!name||document.getElementById('foodCal').value===''||!Number.isFinite(cal)||cal<0){alert('Enter a food name and valid calories.');return}
  const getNum=id=>Math.max(0,Number(document.getElementById(id).value)||0);
  getDay().food.push({name,meal:document.getElementById('foodMeal').value,cal,p:getNum('foodP'),c:getNum('foodC'),f:getNum('foodF'),at:Date.now()});
  ['foodName','foodCal','foodP','foodC','foodF'].forEach(id=>document.getElementById(id).value='');
  save();renderAll();notify('Food added');
}
function deleteFood(i){getDay().food.splice(i,1);save();renderAll();notify('Food entry removed')}
function addActivity(){
  const name=document.getElementById('activityName').value.trim();
  const minutes=Number(document.getElementById('activityMinutes').value)||0;
  const cal=Number(document.getElementById('activityCalories').value)||0;
  if(!name){alert('Enter an activity name.');return}
  if(minutes<0||cal<0){alert('Enter valid numbers.');return}
  getDay().activity.push({name,minutes,cal,at:Date.now()});
  ['activityName','activityMinutes','activityCalories'].forEach(id=>document.getElementById(id).value='');
  save();renderAll();notify('Workout saved');
}
function deleteActivity(i){getDay().activity.splice(i,1);save();renderAll()}
function saveSteps(){
  const raw=document.getElementById('stepsInput').value,v=Number(raw);
  if(raw===''||!Number.isFinite(v)||v<0){alert('Enter valid steps.');return}
  getDay().steps=Math.round(v);save();renderAll();notify('Steps updated');
}
function addWater(ml){
  const d=getDay();d.water=Math.max(0,d.water+ml);save();renderAll();
  notify(ml>0?'Water intake updated':'Water intake adjusted');
}
function addWeight(){
  const raw=document.getElementById('weightInput').value,w=Number(raw);
  if(raw===''||!Number.isFinite(w)||w<1){alert('Enter a valid weight.');return}
  state.weights.push({date:todayKey(),weight:w,at:Date.now()});
  state.weights.sort((a,b)=>b.at-a.at);
  document.getElementById('weightInput').value='';
  save();renderAll();notify('Weight saved');
}
function deleteWeight(i){state.weights.splice(i,1);save();renderAll()}
function saveSettings(){
  const ids={calories:'goalCalories',protein:'goalProtein',carbs:'goalCarbs',fat:'goalFat',water:'goalWater'};
  const next={};
  for(const [k,id] of Object.entries(ids)){
    const raw=document.getElementById(id).value,v=Number(raw);
    if(raw===''||!Number.isFinite(v)||v<0){alert('Enter valid daily goals.');return}
    next[k]=v;
  }
  state.settings={...state.settings,...next};save();renderAll();notify('Daily goals updated');
}
function renderFoodItems(){
  const d=getDay();
  const groups=['Breakfast','Lunch','Dinner','Snack'];
  document.getElementById('foodList').innerHTML=groups.map(meal=>{
    const items=d.food.map((f,i)=>({...f,_index:i})).filter(f=>(f.meal||'Snack')===meal);
    const total=items.reduce((a,f)=>a+(Number(f.cal)||0),0);
    return `<div style="margin-bottom:15px">
      <div class="row" style="padding:3px 0 7px"><h3>${meal}</h3><span class="muted small">${fmt(total)} kcal</span></div>
      ${items.length?items.map(f=>`
        <div class="meal-item">
          <div class="food-thumb" style="display:grid;place-items:center;font-size:21px">${f.recipeId?'🍽️':'🥗'}</div>
          <div class="item-main"><strong>${safe(f.name)}</strong><p>P ${fmt(f.p)}g · C ${fmt(f.c)}g · F ${fmt(f.f)}g</p></div>
          <div class="item-side"><strong>${fmt(f.cal)}</strong><span>kcal</span><button class="btn danger sm" style="margin-top:6px" onclick="deleteFood(${f._index})">Remove</button></div>
        </div>`).join(''):'<div class="muted small" style="padding:8px 0 13px">Nothing logged yet.</div>'}
    </div>`;
  }).join('');
}
function renderAll(){
  const d=getDay(),s=state.settings;
  const totals=d.food.reduce((a,f)=>({cal:a.cal+(Number(f.cal)||0),p:a.p+(Number(f.p)||0),c:a.c+(Number(f.c)||0),f:a.f+(Number(f.f)||0)}),{cal:0,p:0,c:0,f:0});
  const burned=d.activity.reduce((a,x)=>a+(Number(x.cal)||0),0);
  const remaining=s.calories-totals.cal;
  const pct=Math.min(100,totals.cal/Math.max(1,s.calories)*100);
  const stepsPct=Math.min(100,d.steps/10000*100);
  const waterPct=Math.min(100,d.water/Math.max(1,s.water)*100);
  const burnPct=Math.min(100,burned/500*100);
  document.getElementById('dateLabel').textContent=new Date().toLocaleDateString('en-US',{weekday:'short',month:'short',day:'numeric'}).toUpperCase();
  document.getElementById('remaining').innerHTML=fmt(remaining)+' <span>kcal left</span>';
  document.getElementById('consumed').textContent=fmt(totals.cal)+' kcal';
  document.getElementById('burned').textContent=fmt(burned)+' kcal';
  document.getElementById('goalDisplay').textContent=fmt(s.calories)+' kcal';
  document.getElementById('ringPercent').textContent=Math.round(pct)+'%';
  document.getElementById('calorieRing').style.strokeDashoffset=307.9-(307.9*pct/100);
  document.getElementById('calorieMessage').textContent=remaining<0?'You have exceeded your calorie target today.':pct>=85?'You are getting close to your daily goal.':'You are building consistency, one meal at a time.';
  document.getElementById('stepsValue').textContent=fmt(d.steps);
  document.getElementById('stepsBar').style.width=stepsPct+'%';
  document.getElementById('burnValue').innerHTML=fmt(burned)+' <small>kcal</small>';
  document.getElementById('burnBar').style.width=burnPct+'%';
  document.getElementById('waterValue').innerHTML=fmt(d.water)+' <small>ml</small>';
  document.getElementById('waterBar').style.width=waterPct+'%';
  document.getElementById('workoutValue').textContent=d.activity.length;
  document.getElementById('workoutBar').style.width=Math.min(100,d.activity.length/3*100)+'%';
  document.getElementById('proteinValue').textContent=fmt(totals.p)+' g';
  document.getElementById('carbsValue').textContent=fmt(totals.c)+' g';
  document.getElementById('fatValue').textContent=fmt(totals.f)+' g';
  document.getElementById('proteinGoal').textContent='of '+fmt(s.protein)+' g';
  document.getElementById('carbsGoal').textContent='of '+fmt(s.carbs)+' g';
  document.getElementById('fatGoal').textContent='of '+fmt(s.fat)+' g';
  document.getElementById('proteinBar').style.width=Math.min(100,totals.p/Math.max(1,s.protein)*100)+'%';
  document.getElementById('carbsBar').style.width=Math.min(100,totals.c/Math.max(1,s.carbs)*100)+'%';
  document.getElementById('fatBar').style.width=Math.min(100,totals.f/Math.max(1,s.fat)*100)+'%';
  document.getElementById('waterSummary').textContent=fmt(d.water)+' ml';
  document.getElementById('waterTargetText').textContent='of '+fmt(s.water)+' ml daily goal';
  document.getElementById('foodCalories').innerHTML=fmt(totals.cal)+' <span style="font-size:13px;color:var(--muted);letter-spacing:0">kcal</span>';
  document.getElementById('foodGoalCaption').textContent='of '+fmt(s.calories)+' kcal daily goal';
  document.getElementById('foodCalBar').style.width=pct+'%';
  document.getElementById('foodProtein').textContent=fmt(totals.p)+'g';
  document.getElementById('foodCarbs').textContent=fmt(totals.c)+'g';
  document.getElementById('foodFat').textContent=fmt(totals.f)+'g';
  document.getElementById('foodCount').textContent=d.food.length+' entries';
  renderFoodItems();
  const home=d.food.slice(-3).reverse();
  document.getElementById('homeMeals').innerHTML=home.length?home.map(f=>`
    <div class="meal-item"><div class="food-thumb" style="display:grid;place-items:center;font-size:21px">${f.recipeId?'🍽️':'🥗'}</div><div class="item-main"><strong>${safe(f.name)}</strong><p>${safe(f.meal||'Snack')} · P ${fmt(f.p)}g</p></div><div class="item-side"><strong>${fmt(f.cal)}</strong><span>kcal</span></div></div>`).join(''):'<div class="empty"><div class="empty-icon">🥗</div>Your meals will appear here.<br>Start by adding food or choosing a recipe.</div>';
  document.getElementById('activitySteps').textContent=fmt(d.steps);
  document.getElementById('activityBurn').innerHTML=fmt(burned)+' <small>kcal</small>';
  document.getElementById('activityList').innerHTML=d.activity.length?d.activity.map((a,i)=>`
    <div class="activity-item"><div class="food-thumb" style="display:grid;place-items:center;font-size:23px">🏃</div><div class="item-main"><strong>${safe(a.name)}</strong><p>${fmt(a.minutes)} min · ${fmt(a.cal)} kcal burned</p></div><button class="btn danger sm" onclick="deleteActivity(${i})">Remove</button></div>`).join(''):'<div class="empty"><div class="empty-icon">🏃</div>No workouts logged today.</div>';
  document.getElementById('stepsInput').value=d.steps||'';
  document.getElementById('latestWeight').innerHTML=state.weights.length?Number(state.weights[0].weight).toFixed(1)+' <span>kg</span>':'— <span>kg</span>';
  document.getElementById('weightList').innerHTML=state.weights.length?state.weights.map((w,i)=>`
    <div class="weight-item"><div class="item-main"><strong>${Number(w.weight).toFixed(1)} kg</strong><p>${safe(w.date)}</p></div><button class="btn danger sm" onclick="deleteWeight(${i})">Remove</button></div>`).join(''):'<div class="empty"><div class="empty-icon">▥</div>Your weight history will appear here.</div>';
  document.getElementById('goalCalories').value=s.calories;
  document.getElementById('goalProtein').value=s.protein;
  document.getElementById('goalCarbs').value=s.carbs;
  document.getElementById('goalFat').value=s.fat;
  document.getElementById('goalWater').value=s.water;
}
function exportData(){
  const blob=new Blob([JSON.stringify(state,null,2)],{type:'application/json'});
  const url=URL.createObjectURL(blob),a=document.createElement('a');
  a.href=url;a.download='fittrack-backup.json';a.click();URL.revokeObjectURL(url);
}
function importData(event){
  const file=event.target.files[0];if(!file)return;
  const reader=new FileReader();
  reader.onload=()=>{
    try{
      const data=JSON.parse(reader.result);
      if(!data.settings||!data.days||!Array.isArray(data.weights))throw new Error('Invalid backup');
      if(!confirm('Replace current FitTrack data with this backup?'))return;
      state=data;state.settings={...DEFAULT_STATE.settings,...state.settings};save();renderAll();notify('Backup imported');
    }catch(e){alert('This file is not a valid FitTrack backup.')}
    finally{event.target.value=''}
  };
  reader.readAsText(file);
}
function resetData(){
  if(!confirm('Delete all FitTrack data? Export a backup first if needed.'))return;
  state=clone(DEFAULT_STATE);save();renderAll();notify('Data reset');
}
document.addEventListener('keydown',e=>{if(e.key==='Escape')closeRecipe()});
renderCategoryChips();
renderRecipes();
renderAll();
</script>
</body>
</html>
