<!DOCTYPE html>
<html lang="my">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>成力 - HSK 1 တရုတ်စာသင်ကြားရေး</title>
<style>
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans+Myanmar:wght@300;400;700;900&family=Noto+Sans+SC:wght@300;400;700;900&family=Noto+Serif+SC:wght@400;700&display=swap');
:root {
  --bg:#0D0014;--card:#160022;--card2:#1A0030;--border:#3D0060;
  --red:#FF2D55;--orange:#FF6B00;--yellow:#FFD60A;--green:#30D158;
  --cyan:#32ADE6;--purple:#BF5AF2;--text:#F5F0FF;--muted:#9980B3;
}
*{margin:0;padding:0;box-sizing:border-box;}
body{font-family:'Noto Sans Myanmar','Noto Sans SC',sans-serif;background:var(--bg);color:var(--text);min-height:100vh;overflow-x:hidden;}
.bg-anim{position:fixed;top:0;left:0;width:100%;height:100%;z-index:0;pointer-events:none;
  background:radial-gradient(ellipse at 20% 50%,#2D0050 0%,transparent 50%),
  radial-gradient(ellipse at 80% 20%,#001A3D 0%,transparent 50%),#0D0014;}
.bg-anim::after{content:'';position:absolute;inset:0;
  background-image:radial-gradient(circle at 1px 1px,rgba(255,214,10,0.07) 1px,transparent 0);
  background-size:40px 40px;animation:gridMove 20s linear infinite;}
@keyframes gridMove{0%{transform:translate(0,0)}100%{transform:translate(40px,40px)}}
.app-wrapper{position:relative;z-index:1;}
header{padding:16px 20px;display:flex;align-items:center;justify-content:space-between;
  border-bottom:1px solid var(--border);background:rgba(13,0,20,0.85);
  backdrop-filter:blur(20px);position:sticky;top:0;z-index:100;}
.logo{font-family:'Noto Serif SC',serif;font-size:1.8rem;font-weight:700;
  background:linear-gradient(135deg,#FFD60A,#FF6B00,#FF2D55);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;letter-spacing:4px;
  filter:drop-shadow(0 0 20px rgba(255,214,10,0.4));}
.logo-sub{font-size:0.6rem;color:var(--muted);letter-spacing:2px;text-transform:uppercase;
  display:block;margin-top:-4px;-webkit-text-fill-color:var(--muted);}
.stats-bar{display:flex;gap:10px;align-items:center;}
.stat-pill{background:rgba(255,214,10,0.1);border:1px solid rgba(255,214,10,0.3);
  border-radius:20px;padding:4px 10px;font-size:0.72rem;color:var(--yellow);
  display:flex;align-items:center;gap:5px;}
.nav-tabs{display:flex;gap:4px;padding:12px 16px;overflow-x:auto;scrollbar-width:none;
  border-bottom:1px solid rgba(61,0,96,0.5);}
.nav-tabs::-webkit-scrollbar{display:none;}
.tab-btn{padding:8px 14px;border-radius:20px;border:1px solid var(--border);
  background:transparent;color:var(--muted);font-family:'Noto Sans Myanmar',sans-serif;
  font-size:0.75rem;cursor:pointer;white-space:nowrap;transition:all 0.2s;}
.tab-btn.active,.tab-btn:hover{background:rgba(191,90,242,0.2);border-color:var(--purple);color:var(--text);}
.main{padding:16px;}
.section{display:none;}
.section.active{display:block;}

/* LEARN */
.hero-word-card{background:linear-gradient(135deg,#1A003A,#0D0025);
  border:1px solid var(--border);border-radius:24px;padding:28px 20px;
  text-align:center;margin-bottom:16px;position:relative;overflow:hidden;}
.chinese-char{font-family:'Noto Serif SC',serif;font-size:6rem;line-height:1;
  background:linear-gradient(135deg,#fff,#BF5AF2);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  filter:drop-shadow(0 0 30px rgba(191,90,242,0.5));margin-bottom:8px;cursor:pointer;}
.pinyin-display{font-size:1.6rem;color:var(--yellow);font-weight:700;letter-spacing:4px;margin-bottom:8px;}
.tone-badge{display:inline-block;padding:4px 14px;border-radius:20px;font-size:0.75rem;
  margin-bottom:10px;border:1px solid;}
.tone-1{color:#32ADE6;border-color:#32ADE6;background:rgba(50,173,230,0.1);}
.tone-2{color:#30D158;border-color:#30D158;background:rgba(48,209,88,0.1);}
.tone-3{color:#FF9500;border-color:#FF9500;background:rgba(255,149,0,0.1);}
.tone-4{color:#FF2D55;border-color:#FF2D55;background:rgba(255,45,85,0.1);}
.tone-0{color:#9980B3;border-color:#9980B3;background:rgba(153,128,179,0.1);}
.meaning-my{font-size:1.1rem;color:var(--text);margin-bottom:4px;}
.meaning-en{font-size:0.85rem;color:var(--muted);margin-bottom:16px;}
.progress-bar{height:3px;background:var(--border);border-radius:2px;margin-bottom:8px;}
.progress-fill{height:100%;background:linear-gradient(90deg,var(--purple),var(--yellow));border-radius:2px;transition:width 0.3s;}
.card-actions{display:flex;gap:8px;justify-content:center;flex-wrap:wrap;margin-bottom:10px;}
.btn{padding:10px 18px;border-radius:20px;border:none;cursor:pointer;
  font-family:'Noto Sans Myanmar',sans-serif;font-size:0.82rem;
  transition:all 0.2s;color:var(--text);}
.btn-prev{background:rgba(255,255,255,0.08);border:1px solid var(--border);}
.btn-audio{background:linear-gradient(135deg,#FF375F,#FF6B00);color:#fff;font-weight:700;}
.btn-next{background:linear-gradient(135deg,var(--yellow),var(--orange));color:#000;font-weight:700;}
.info-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-bottom:16px;}
.info-card{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:16px;}
.info-card h3{font-size:0.68rem;letter-spacing:2px;color:var(--cyan);text-transform:uppercase;margin-bottom:8px;}
.info-card p{font-size:0.82rem;color:var(--muted);line-height:1.6;}
.stroke-section{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:16px;margin-bottom:16px;}
.stroke-section h3{font-size:0.68rem;letter-spacing:2px;color:var(--purple);text-transform:uppercase;margin-bottom:12px;}
.stroke-steps{display:flex;gap:8px;flex-wrap:wrap;}
.stroke-step{width:56px;height:56px;background:rgba(255,255,255,0.03);
  border:1px solid var(--border);border-radius:10px;
  display:flex;align-items:center;justify-content:center;
  font-family:'Noto Serif SC',serif;font-size:1.8rem;color:rgba(255,255,255,0.7);
  position:relative;}
.stroke-step .snum{position:absolute;bottom:2px;right:4px;font-size:0.5rem;color:var(--muted);}
.example-card{background:var(--card);border:1px solid var(--border);border-radius:14px;padding:14px;margin-bottom:8px;}
.ex-cn{font-family:'Noto Serif SC',serif;font-size:1.1rem;color:var(--text);margin-bottom:3px;}
.ex-py{font-size:0.8rem;color:var(--yellow);margin-bottom:3px;}
.ex-my{font-size:0.82rem;color:var(--muted);}

/* VOCAB */
.search-bar{width:100%;padding:12px 16px;background:var(--card);border:1px solid var(--border);
  border-radius:14px;color:var(--text);font-family:'Noto Sans Myanmar',sans-serif;
  font-size:0.88rem;margin-bottom:12px;outline:none;}
.search-bar::placeholder{color:var(--muted);}
.category-filters{display:flex;gap:6px;flex-wrap:wrap;margin-bottom:14px;}
.cat-btn{padding:6px 12px;border-radius:14px;border:1px solid var(--border);
  background:transparent;color:var(--muted);font-family:'Noto Sans Myanmar',sans-serif;
  font-size:0.72rem;cursor:pointer;transition:all 0.2s;}
.cat-btn.active,.cat-btn:hover{background:rgba(191,90,242,0.2);border-color:var(--purple);color:var(--text);}
.vocab-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(150px,1fr));gap:10px;}
.vocab-card{background:var(--card);border:1px solid var(--border);border-radius:14px;
  padding:14px;cursor:pointer;transition:all 0.2s;text-align:center;}
.vocab-card:hover,.vocab-card.known{border-color:var(--purple);}
.vocab-card.known{background:rgba(191,90,242,0.08);}
.vc-char{font-family:'Noto Serif SC',serif;font-size:2rem;margin-bottom:4px;}
.vc-py{font-size:0.75rem;color:var(--yellow);margin-bottom:2px;}
.vc-my{font-size:0.72rem;color:var(--muted);}

/* QUIZ */
.score-display{display:flex;gap:20px;justify-content:center;margin-bottom:16px;}
.score-item{text-align:center;}
.score-num{font-size:2rem;font-weight:700;line-height:1;}
.score-label{font-size:0.68rem;color:var(--muted);letter-spacing:1px;}
.quiz-card{background:var(--card);border:1px solid var(--border);border-radius:20px;
  padding:24px;margin-bottom:16px;text-align:center;}
.quiz-type{font-size:0.68rem;color:var(--cyan);letter-spacing:2px;text-transform:uppercase;margin-bottom:12px;}
.quiz-question{font-family:'Noto Serif SC',serif;font-size:3rem;margin-bottom:8px;}
.quiz-options{display:grid;grid-template-columns:1fr 1fr;gap:10px;}
.quiz-opt{padding:14px;border-radius:12px;border:1px solid var(--border);
  background:transparent;color:var(--text);font-family:'Noto Sans Myanmar',sans-serif;
  font-size:0.85rem;cursor:pointer;transition:all 0.2s;text-align:center;line-height:1.5;}
.quiz-opt:hover{border-color:var(--purple);background:rgba(191,90,242,0.1);}
.quiz-opt.correct{border-color:var(--green);background:rgba(48,209,88,0.15);color:var(--green);}
.quiz-opt.wrong{border-color:var(--red);background:rgba(255,45,85,0.15);color:var(--red);}
.quiz-opt:disabled{cursor:default;}

/* WRITING */
.write-word-card{background:linear-gradient(135deg,#1A003A,#0D0025);
  border:1px solid var(--border);border-radius:20px;padding:20px;
  text-align:center;margin-bottom:14px;}
.write-char{font-family:'Noto Serif SC',serif;font-size:4rem;line-height:1;
  background:linear-gradient(135deg,#fff,#FFD60A);
  -webkit-background-clip:text;-webkit-text-fill-color:transparent;
  filter:drop-shadow(0 0 20px rgba(255,214,10,0.4));margin-bottom:6px;}
.rep-dots{display:flex;gap:5px;justify-content:center;flex-wrap:wrap;max-width:260px;margin:8px auto;}
.rep-dot{width:15px;height:15px;border-radius:50%;border:2px solid var(--border);transition:all 0.3s;}
.rep-dot.done{background:var(--green);border-color:var(--green);}
.rep-dot.current{border-color:var(--yellow);}
.audio-dots{display:flex;gap:4px;justify-content:center;flex-wrap:wrap;max-width:220px;margin:6px auto;}
.audio-dot{width:11px;height:11px;border-radius:50%;border:1.5px solid rgba(50,173,230,0.25);}
.audio-dot.heard{background:var(--cyan);border-color:var(--cyan);}
.canvas-wrap{position:relative;display:flex;justify-content:center;}
.ref-overlay{position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);
  font-family:'Noto Serif SC',serif;font-size:180px;color:rgba(255,214,10,0.07);
  pointer-events:none;z-index:1;user-select:none;line-height:1;display:none;}
#writeCanvas{border:2px solid var(--border);border-radius:14px;background:#0A0018;
  touch-action:none;cursor:crosshair;max-width:100%;display:block;}
.write-actions{display:flex;gap:8px;justify-content:center;flex-wrap:wrap;margin:12px 0;}
.feedback-box{background:var(--card);border:1px solid var(--border);border-radius:16px;
  padding:18px;margin-bottom:14px;text-align:center;display:none;}
.session-complete{display:none;background:linear-gradient(135deg,rgba(48,209,88,0.12),rgba(255,214,10,0.08));
  border:1px solid var(--green);border-radius:20px;padding:20px;margin-bottom:14px;text-align:center;}
.practiced-chip{background:rgba(191,90,242,0.12);border:1px solid rgba(191,90,242,0.3);
  border-radius:8px;padding:4px 10px;font-family:'Noto Serif SC',serif;
  font-size:1.1rem;cursor:pointer;display:inline-block;margin:3px;}

/* PROGRESS */
.prog-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:12px;margin-bottom:16px;}
.prog-card{background:var(--card);border:1px solid var(--border);border-radius:16px;padding:18px;text-align:center;}
.prog-num{font-size:2.2rem;font-weight:900;line-height:1;margin-bottom:4px;}
.prog-label{font-size:0.68rem;color:var(--muted);}
.ring-chart{width:110px;height:110px;margin:16px auto;border-radius:50%;
  background:conic-gradient(var(--purple) 0%,var(--yellow) var(--pct,0%),var(--border) var(--pct,0%));
  display:flex;align-items:center;justify-content:center;}
.ring-inner{width:74px;height:74px;border-radius:50%;background:var(--card);
  display:flex;align-items:center;justify-content:center;font-size:1.1rem;font-weight:700;color:var(--yellow);}

/* KNOWN WORDS */
.known-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(120px,1fr));gap:8px;margin-top:12px;}
.known-chip{background:rgba(48,209,88,0.08);border:1px solid rgba(48,209,88,0.25);
  border-radius:12px;padding:10px;text-align:center;cursor:pointer;transition:all 0.2s;}
.known-chip:hover{border-color:var(--red);}
.known-chip .kc-char{font-family:'Noto Serif SC',serif;font-size:1.6rem;margin-bottom:2px;}
.known-chip .kc-py{font-size:0.68rem;color:var(--yellow);}
.known-chip .kc-my{font-size:0.65rem;color:var(--muted);}

/* CONFETTI */
@keyframes floatUp{0%{transform:translateY(0) scale(1);opacity:1;}100%{transform:translateY(-100px) scale(0);opacity:0;}}
.confetti-piece{position:fixed;pointer-events:none;z-index:9999;font-size:1.5rem;animation:floatUp 1.5s ease forwards;}
@keyframes feedbackPop{0%{transform:scale(0.8);opacity:0;}60%{transform:scale(1.05);}100%{transform:scale(1);opacity:1;}}
.feedback-anim{animation:feedbackPop 0.4s ease forwards;}
</style>
</head>
<body>
<div class="bg-anim"></div>
<div class="app-wrapper">

<header>
  <div>
    <div class="logo">成力</div>
    <span class="logo-sub">HSK 1 • တရုတ်စာ သင်ကြားရေး</span>
  </div>
  <div class="stats-bar">
    <div class="stat-pill">✓ <span id="knownNum">0</span> /150</div>
    <div class="stat-pill">🔥 <span id="streakNum">0</span></div>
  </div>
</header>

<div class="nav-tabs">
  <button class="tab-btn active" onclick="showTab('learn',this)">📖 လေ့လာမည်</button>
  <button class="tab-btn" onclick="showTab('vocab',this)">📚 စကားလုံးများ</button>
  <button class="tab-btn" onclick="showTab('quiz',this)">🎯 စစ်ဆေးမည်</button>
  <button class="tab-btn" onclick="showTab('write',this)">✍️ ရေးလေ့ကျင့်မည်</button>
  <button class="tab-btn" onclick="showTab('known',this)">⭐ သိပြီးသော</button>
  <button class="tab-btn" onclick="showTab('progress',this)">📊 တိုးတက်မှု</button>
</div>

<div class="main">

<!-- LEARN -->
<section id="sec-learn" class="section active">
  <div class="hero-word-card">
    <div class="chinese-char" id="heroChar" onclick="playAudio()">爱</div>
    <div class="pinyin-display" id="heroPinyin">ài</div>
    <div id="heroBadge" class="tone-badge tone-4">စတုတ္ထ Tone (4)</div>
    <div class="meaning-my" id="heroMy">ချစ်ခြင်း / ချစ်သည်</div>
    <div class="meaning-en" id="heroEn">love / to love</div>
    <div class="progress-bar"><div class="progress-fill" id="learnProgress" style="width:1%"></div></div>
    <div style="font-size:0.72rem;color:var(--muted);margin-bottom:12px" id="learnCounter">စကားလုံး ၁/၁၅၀</div>
    <div class="card-actions">
      <button class="btn btn-prev" onclick="prevWord()">← နောက်သို့</button>
      <button class="btn btn-audio" onclick="playAudio()">🔊 အသံနားထောင်ပါ</button>
      <button class="btn btn-next" onclick="nextWord()">ရှေ့သို့ →</button>
    </div>
    <button class="btn" style="background:rgba(48,209,88,0.15);border:1px solid var(--green);color:var(--green);font-size:0.78rem" onclick="markKnown()">✓ သိပြီ</button>
  </div>
  <div class="info-grid">
    <div class="info-card"><h3>🔍 ဇာစ်မြစ်</h3><p id="etymology">-</p></div>
    <div class="info-card"><h3>📝 အမျိုးအစား</h3><p id="category">-</p><br><h3>🎯 အသုံးပြုနည်း</h3><p id="usage">-</p></div>
  </div>
  <div class="stroke-section">
    <h3>✏️ ကြောင်းဆွဲနည်း</h3>
    <div class="stroke-steps" id="strokeSteps"></div>
    <p style="font-size:0.72rem;color:var(--muted);margin-top:10px">💡 ဘယ်မှညာ • အပေါ်မှအောက်</p>
  </div>
  <div id="exampleSentences"></div>
</section>

<!-- VOCAB -->
<section id="sec-vocab" class="section">
  <input class="search-bar" type="text" placeholder="🔍 ရှာဖွေပါ..." id="searchInput" oninput="renderVocab()">
  <div class="category-filters">
    <button class="cat-btn active" onclick="setCat('all',this)">အားလုံး (150)</button>
    <button class="cat-btn" onclick="setCat('pronoun',this)">နာမ်စား</button>
    <button class="cat-btn" onclick="setCat('verb',this)">ကြိယာ</button>
    <button class="cat-btn" onclick="setCat('noun',this)">နာမ်</button>
    <button class="cat-btn" onclick="setCat('number',this)">နံပါတ်</button>
    <button class="cat-btn" onclick="setCat('time',this)">အချိန်</button>
    <button class="cat-btn" onclick="setCat('question',this)">မေးခွန်း</button>
    <button class="cat-btn" onclick="setCat('adjective',this)">နာမဝိသေသန</button>
    <button class="cat-btn" onclick="setCat('particle',this)">ကြိယာဝိဘတ်</button>
  </div>
  <div class="vocab-grid" id="vocabGrid"></div>
</section>

<!-- QUIZ -->
<section id="sec-quiz" class="section">
  <div class="score-display">
    <div class="score-item"><div class="score-num" id="qScore" style="color:var(--green)">0</div><div class="score-label">မှန်သည်</div></div>
    <div class="score-item"><div class="score-num" id="qTotal" style="color:var(--muted)">0</div><div class="score-label">စုစုပေါင်း</div></div>
    <div class="score-item"><div class="score-num" id="qStreak" style="color:var(--yellow)">0</div><div class="score-label">ဆက်တိုက်</div></div>
  </div>
  <div class="quiz-card">
    <div class="quiz-type" id="quizType">-</div>
    <div class="quiz-question" id="quizQ">-</div>
    <div style="font-size:0.88rem;color:var(--yellow);margin-bottom:16px" id="quizHint"></div>
    <div class="quiz-options" id="quizOpts"></div>
    <div id="quizFeedback" style="margin-top:14px;font-size:0.88rem;font-family:'Noto Sans Myanmar',sans-serif"></div>
  </div>
  <div style="display:flex;gap:10px;justify-content:center;flex-wrap:wrap">
    <button class="btn" style="background:rgba(50,173,230,0.15);border:1px solid var(--cyan);color:var(--cyan)" onclick="setQuizType('cn-to-my')">🀄 တရုတ်→မြန်မာ</button>
    <button class="btn" style="background:rgba(191,90,242,0.15);border:1px solid var(--purple);color:var(--purple)" onclick="setQuizType('my-to-cn')">🇲🇲 မြန်မာ→တရုတ်</button>
    <button class="btn" style="background:rgba(255,149,0,0.15);border:1px solid var(--orange);color:var(--orange)" onclick="setQuizType('pinyin')">🔤 Pinyin</button>
  </div>
</section>

<!-- WRITING -->
<section id="sec-write" class="section">
  <div class="write-word-card">
    <div style="font-size:0.62rem;letter-spacing:3px;color:var(--orange);text-transform:uppercase;margin-bottom:8px">✍️ ဤစကားလုံးကို ၂၀ ကြိမ် ရေးပါ</div>
    <div class="write-char" id="writeChar">我</div>
    <div style="font-size:1.1rem;color:var(--yellow);font-weight:700;letter-spacing:3px;margin-bottom:4px" id="writePy">wǒ</div>
    <div style="font-size:0.9rem;font-family:'Noto Sans Myanmar',sans-serif;margin-bottom:2px" id="writeMy">ကျွန်တော်/ကျွန်မ</div>
    <div style="font-size:0.75rem;color:var(--muted);margin-bottom:10px" id="writeEn">I / me</div>
    <div style="font-size:0.68rem;color:var(--muted);margin-bottom:4px">ရေးပြီး: <span id="repLabel" style="color:var(--yellow);font-weight:700">0</span>/20</div>
    <div class="rep-dots" id="repDots"></div>
    <div style="font-size:0.62rem;color:var(--cyan);margin-top:8px;margin-bottom:2px">🔊 Pinyin ကြားသောအကြိမ်: <span id="audioLabel">0</span>/20</div>
    <div class="audio-dots" id="audioDots"></div>
    <div style="display:flex;gap:8px;justify-content:center;flex-wrap:wrap;margin-top:12px">
      <button class="btn" style="background:rgba(255,45,85,0.15);border:1px solid var(--pink);color:var(--pink);font-size:0.75rem;padding:7px 12px" onclick="playWriteAudio()">🔊 Pinyin ကြားပါ</button>
      <button class="btn" style="background:rgba(50,173,230,0.12);border:1px solid var(--cyan);color:var(--cyan);font-size:0.75rem;padding:7px 12px" onclick="toggleGuide()">📐 မျဉ်းကွက်</button>
      <button class="btn" style="background:rgba(191,90,242,0.12);border:1px solid var(--purple);color:var(--purple);font-size:0.75rem;padding:7px 12px" onclick="toggleRef()">👁️ နမူနာ</button>
    </div>
  </div>

  <div style="background:var(--card);border:1px solid var(--border);border-radius:18px;padding:16px;margin-bottom:12px">
    <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:10px">
      <span style="font-size:0.65rem;color:var(--green);letter-spacing:2px;text-transform:uppercase">🖊️ ဒီနေရာတွင် ရေးပါ</span>
      <span id="repCurrent" style="font-size:0.75rem;color:var(--yellow);font-weight:700">အကြိမ် 1</span>
    </div>
    <div class="canvas-wrap">
      <div class="ref-overlay" id="refOverlay"></div>
      <canvas id="writeCanvas" width="280" height="280"></canvas>
    </div>
    <div style="text-align:center;margin-top:8px;font-size:0.68rem;color:var(--muted)">💡 လက်ချောင်းဖြင့် ရေးပါ • ဘယ်မှညာ • အပေါ်မှအောက်</div>
  </div>

  <div class="write-actions">
    <button class="btn" style="background:rgba(255,45,85,0.15);border:1px solid var(--red);color:var(--red)" onclick="clearCanvas()">🗑️ ဖျက်</button>
    <button class="btn" style="background:linear-gradient(135deg,var(--green),#00A040);color:#000;font-weight:700;padding:10px 22px" onclick="checkWrite()">✅ စစ်ဆေး</button>
    <button class="btn" style="background:rgba(255,214,10,0.1);border:1px solid var(--yellow);color:var(--yellow)" onclick="skipWrite()">⏭️ ကျော်</button>
  </div>

  <div class="feedback-box" id="writeFeedback"></div>

  <div class="session-complete" id="sessionDone">
    <div style="font-size:2.5rem;margin-bottom:6px">🎉</div>
    <div style="font-size:1.1rem;font-weight:700;color:var(--green);margin-bottom:4px">၂၀ ကြိမ် ပြည့်ပြီ!</div>
    <div id="sessionWord" style="font-family:'Noto Serif SC',serif;font-size:2.5rem;color:var(--yellow);margin-bottom:4px"></div>
    <div id="sessionInfo" style="font-size:0.8rem;color:var(--muted);margin-bottom:14px"></div>
    <div style="display:flex;gap:10px;justify-content:center;flex-wrap:wrap">
      <button class="btn" style="background:rgba(191,90,242,0.15);border:1px solid var(--purple);color:var(--purple)" onclick="showReview()">📋 ပြန်ကြည့်</button>
      <button class="btn" style="background:linear-gradient(135deg,var(--yellow),var(--orange));color:#000;font-weight:700" onclick="nextWriteWord()">နောက်စကားလုံး →</button>
    </div>
  </div>

  <div style="background:var(--card);border:1px solid var(--border);border-radius:16px;padding:16px;margin-bottom:12px">
    <div style="font-size:0.65rem;color:var(--purple);letter-spacing:2px;text-transform:uppercase;margin-bottom:10px">📋 ကြောင်းဆွဲ အညွှန်း</div>
    <div class="stroke-steps" id="writeStrokes"></div>
    <div style="margin-top:12px;padding:10px;background:rgba(255,214,10,0.05);border-radius:8px;border-left:3px solid var(--yellow)">
      <div style="font-size:0.72rem;color:var(--muted);line-height:1.9">
        ① ဘယ်→ညာ (左→右) &nbsp; ② အပေါ်→အောက် (上→下)<br>
        ③ အလျားလိုက် မတိုင်မီ ဒေါင်လိုက် &nbsp; ④ ဝင်းပိတ်ပြီးမှ အတွင်းကြောင်း
      </div>
    </div>
  </div>

  <div style="background:var(--card);border:1px solid var(--border);border-radius:16px;padding:16px">
    <div style="font-size:0.65rem;color:var(--cyan);letter-spacing:2px;text-transform:uppercase;margin-bottom:12px">📈 ရေးလေ့ကျင့်မှု မှတ်တမ်း</div>
    <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:10px;margin-bottom:12px">
      <div style="text-align:center;background:rgba(48,209,88,0.08);border-radius:10px;padding:10px">
        <div style="font-size:1.6rem;font-weight:900;color:var(--green)" id="wsSessions">0</div>
        <div style="font-size:0.62rem;color:var(--muted)">Session</div>
      </div>
      <div style="text-align:center;background:rgba(255,214,10,0.08);border-radius:10px;padding:10px">
        <div style="font-size:1.6rem;font-weight:900;color:var(--yellow)" id="wsTotal">0</div>
        <div style="font-size:0.62rem;color:var(--muted)">စုစုပေါင်း ရေး</div>
      </div>
      <div style="text-align:center;background:rgba(191,90,242,0.08);border-radius:10px;padding:10px">
        <div style="font-size:1.6rem;font-weight:900;color:var(--purple)" id="wsWords">0</div>
        <div style="font-size:0.62rem;color:var(--muted)">စကားလုံး</div>
      </div>
    </div>
    <div style="font-size:0.68rem;color:var(--muted);margin-bottom:6px">ရေးပြီးသောစကားလုံးများ (နှိပ်ပြီး ထပ်ကျင့်နိုင်):</div>
    <div id="practicedList"></div>
  </div>
</section>

<!-- KNOWN WORDS -->
<section id="sec-known" class="section">
  <div style="background:var(--card);border:1px solid var(--border);border-radius:16px;padding:16px;margin-bottom:14px">
    <div style="font-size:0.65rem;color:var(--yellow);letter-spacing:2px;text-transform:uppercase;margin-bottom:8px">⭐ သင်ကြားပြီးသော စကားလုံးများ</div>
    <div style="font-size:0.82rem;color:var(--muted);margin-bottom:4px">စကားလုံး <span id="knownCount" style="color:var(--yellow);font-weight:700">0</span> လုံး သိပြီ</div>
    <div style="font-size:0.75rem;color:var(--muted)">💡 စကားလုံးကိုနှိပ်ပါ - မသိတော့ဟု ဖျက်နိုင်သည်</div>
  </div>
  <div id="knownWordsGrid" class="known-grid"></div>
  <div id="knownEmpty" style="text-align:center;padding:40px;color:var(--muted);font-family:'Noto Sans Myanmar',sans-serif;display:none">
    <div style="font-size:3rem;margin-bottom:10px">📚</div>
    <div>မှတ်ထားသော စကားလုံး မရှိသေး<br>လေ့လာမည် section တွင် ✓ သိပြီ နှိပ်ပါ</div>
  </div>
</section>

<!-- PROGRESS -->
<section id="sec-progress" class="section">
  <div class="prog-grid">
    <div class="prog-card"><div class="prog-num" style="color:var(--yellow)" id="pgKnown">0</div><div class="prog-label">သိပြီးသော စကားလုံး</div></div>
    <div class="prog-card"><div class="prog-num" style="color:var(--green)" id="pgCorrect">0</div><div class="prog-label">Quiz မှန်သည်</div></div>
    <div class="prog-card"><div class="prog-num" style="color:var(--red)" id="pgWrong">0</div><div class="prog-label">မှားသည်</div></div>
    <div class="prog-card"><div class="prog-num" style="color:var(--purple)" id="pgStreak">0</div><div class="prog-label">ဆက်တိုက်မှန်</div></div>
  </div>
  <div style="background:var(--card);border:1px solid var(--border);border-radius:16px;padding:20px;text-align:center;margin-bottom:16px">
    <div style="font-size:0.65rem;color:var(--yellow);letter-spacing:2px;text-transform:uppercase;margin-bottom:12px">📊 တိုးတက်မှု ရာနှုန်း</div>
    <div class="ring-chart" id="ringChart" style="--pct:0%"><div class="ring-inner" id="ringPct">0%</div></div>
    <div style="color:var(--muted);font-size:0.78rem;margin-top:10px">HSK 1 (150) တွင် သင်ကြားပြီးသော အချိုး</div>
  </div>
  <div style="display:flex;gap:10px;justify-content:center">
    <button class="btn" style="background:rgba(255,45,85,0.15);border:1px solid var(--red);color:var(--red)" onclick="resetAll()">🔄 အားလုံး ပြန်စမည်</button>
  </div>
</section>

</div><!-- .main -->
</div><!-- .app-wrapper -->
<script>
const HSK1 = [
  // Pronouns
  {cn:"我",py:"wǒ",tone:3,my:"ကျွန်တော်/ကျွန်မ (ငါ)",en:"I / me",cat:"pronoun",
   ety:"'ကိုယ်ထိ' ဟုသော အဓိပ္ပာယ်ဖြင့် လက်တစ်ဖတ်နှင့် ကြောင်းတစ်ကြောင်းပေါင်းစပ်ထားသောပုံ",
   usage:"တစ်ဦးချင်း ကိုယ်ကိုကိုးကား (1st person singular)",
   strokes:["我","我","我"],
   examples:[{cn:"我是学生。",py:"Wǒ shì xuésheng.",my:"ကျွန်တော်/မ ကျောင်းသားဖြစ်သည်။",en:"I am a student."},{cn:"我爱你。",py:"Wǒ ài nǐ.",my:"ကျွန်တော်/မ သင့်ကို ချစ်သည်။",en:"I love you."}]},

  {cn:"你",py:"nǐ",tone:3,my:"သင်/ခင်ဗျား (မင်း)",en:"you",cat:"pronoun",
   ety:"'ပုဂ္ဂိုလ်' ဟုသောနာမ်နှင့် 'ကိုအသုံးပြုသည်' ဆိုသောဆိပ်ပေါင်းလုပ်ဆောင်မှုမှဆင်းသက်",
   usage:"ဒုတိယပုဂ္ဂိုလ် တစ်ဦးချင်း (you - singular)",
   strokes:["你","你","你"],
   examples:[{cn:"你好吗？",py:"Nǐ hǎo ma?",my:"သင် ကျန်းမာပါသလား？",en:"How are you?"},{cn:"你叫什么名字？",py:"Nǐ jiào shénme míngzì?",my:"သင့်နာမည် ဘယ်လိုခေါ်သလဲ？",en:"What's your name?"}]},

  {cn:"他",py:"tā",tone:1,my:"သူ (ကောင်လေး/ယောကျ်ားလေး)",en:"he / him",cat:"pronoun",
   ety:"'ပုဂ္ဂိုလ်' + 'လှည့်ကြည့်' ဟု ပေါင်းစပ်ထားသောစာလုံး - တတိယပုဂ္ဂိုလ်",
   usage:"တတိယပုဂ္ဂိုလ် ကျား (he/him)",
   strokes:["他","他","他"],
   examples:[{cn:"他是我的朋友。",py:"Tā shì wǒ de péngyou.",my:"သူသည် ကျွန်တော်၏ သူငယ်ချင်းဖြစ်သည်။",en:"He is my friend."}]},

  {cn:"她",py:"tā",tone:1,my:"သူ (မိန်းကလေး/မိန်းမ)",en:"she / her",cat:"pronoun",
   ety:"'မိန်းမ/女' + 'လှည့်ကြည့်' - '他'နှင့် အသံတူသော်လည်း အရေးအသားကွဲပြားသည်",
   usage:"တတိယပုဂ္ဂိုလ် မ (she/her)",
   strokes:["她","她","她"],
   examples:[{cn:"她是老师。",py:"Tā shì lǎoshī.",my:"သူမသည် ဆရာမဖြစ်သည်။",en:"She is a teacher."}]},

  {cn:"我们",py:"wǒmen",tone:3,my:"ကျွန်တော်တို့ (ငါတို့)",en:"we / us",cat:"pronoun",
   ety:"'我'(ငါ) + '们'(ပုဂ္ဂိုလ်အများ) = ပထမပုဂ္ဂိုလ်အများကိန်း",
   usage:"ပထမပုဂ္ဂိုလ် အများကိန်း (we - plural)",
   strokes:["我","们"],
   examples:[{cn:"我们是朋友。",py:"Wǒmen shì péngyou.",my:"ကျွန်တော်တို့ သူငယ်ချင်းများဖြစ်သည်။",en:"We are friends."}]},

  {cn:"你们",py:"nǐmen",tone:3,my:"သင်တို့ (မင်းတို့)",en:"you (plural)",cat:"pronoun",
   ety:"'你'(သင်) + '们'(အများကိန်း) = ဒုတိယပုဂ္ဂိုလ်အများကိန်း",
   usage:"ဒုတိယပုဂ္ဂိုလ် အများကိန်း (you all)",
   strokes:["你","们"],
   examples:[{cn:"你们好！",py:"Nǐmen hǎo!",my:"သင်တို့ ကျန်းမာကြပါသလား！",en:"Hello everyone!"}]},

  {cn:"他们",py:"tāmen",tone:1,my:"သူတို့ (ယောကျ်ားများ/ရောနှောအုပ်စု)",en:"they / them",cat:"pronoun",
   ety:"'他'(သူ) + '们'(အများကိန်း) = တတိယပုဂ္ဂိုလ်အများကိန်း",
   usage:"တတိယပုဂ္ဂိုလ် အများကိန်း (they)",
   strokes:["他","们"],
   examples:[{cn:"他们是学生。",py:"Tāmen shì xuésheng.",my:"သူတို့သည် ကျောင်းသားများဖြစ်သည်။",en:"They are students."}]},

  // Verbs
  {cn:"爱",py:"ài",tone:4,my:"ချစ်သည် / ချစ်ခြင်းမေတ္တာ",en:"love / to love",cat:"verb",
   ety:"'ကိုင်ဖတ်' + 'နှလုံး' + 'ဖြောင့်' - ဟိုးအရင်ကာလ '愛' ဇာတိမြင်ကွင်းမှ ပြောင်းလဲခဲ့သော",
   usage:"နာမ်ကြိယာနှစ်ရပ်လုံး ဖြစ်နိုင်သည်",
   strokes:["爱","爱"],
   examples:[{cn:"我爱你。",py:"Wǒ ài nǐ.",my:"ကျွန်တော်/မ သင့်ကို ချစ်သည်။",en:"I love you."},{cn:"我爱中国。",py:"Wǒ ài Zhōngguó.",my:"ကျွန်တော်/မ တရုတ်နိုင်ငံကို ချစ်သည်။",en:"I love China."}]},

  {cn:"是",py:"shì",tone:4,my:"ဖြစ်သည် (= ဆိုသည်)",en:"to be (am/is/are)",cat:"verb",
   ety:"'ဒြပ်' + 'ပြောင်း' ဟိုးရှေး 'ဤကဲ့သို့' ဟုအဓိပ္ပာယ်ရ - ပြည့်ဝသောဖိုင်ကြိယာ",
   usage:"နာမ်ဇောင်ခြင်း ကြိယာ (linking verb). ငြင်းပယ်ရာတွင် '不是' ဟု သုံးသည်",
   strokes:["是","是"],
   examples:[{cn:"我是老师。",py:"Wǒ shì lǎoshī.",my:"ကျွန်တော်/မ ဆရာ/မ ဖြစ်သည်။",en:"I am a teacher."},{cn:"这是书。",py:"Zhè shì shū.",my:"ဒါသည် စာအုပ်ဖြစ်သည်။",en:"This is a book."}]},

  {cn:"有",py:"yǒu",tone:3,my:"ရှိသည် / ပိုင်ဆိုင်သည်",en:"to have / there is",cat:"verb",
   ety:"'လက်' + 'အသား' - လက်ဖြင့် ကိုင်ထားသောအသားကို ကိုယ်စားပြုသောပုံ",
   usage:"ပိုင်ဆိုင်မှု သို့မဟုတ် ရှိနေမှုကိုဖော်ပြ. ငြင်းပယ်ရာတွင် '没有' ဟုသုံး",
   strokes:["有","有"],
   examples:[{cn:"我有一个朋友。",py:"Wǒ yǒu yī gè péngyou.",my:"ကျွန်တော်/မ သူငယ်ချင်း တစ်ဦးရှိသည်。",en:"I have a friend."},{cn:"这里有书。",py:"Zhèlǐ yǒu shū.",my:"ဒီမှာ စာအုပ်ရှိသည်。",en:"There are books here."}]},

  {cn:"想",py:"xiǎng",tone:3,my:"ချင်သည် / တွေးတောသည် / လွမ်းသည်",en:"want to / think / miss",cat:"verb",
   ety:"'ဆင်' + 'ပြသ' + 'နှလုံး' - နှလုံးနှင့် ဆင်ဆင်ခြင်ပြီး တွေးခေါ်ခြင်း",
   usage:"'ဘာဆိုဘာ လုပ်ချင်သည်' ဟု ဖော်ပြရာ 想+ကြိယာ",
   strokes:["想","想"],
   examples:[{cn:"我想喝水。",py:"Wǒ xiǎng hē shuǐ.",my:"ကျွန်တော်/မ ရေသောက်ချင်သည်。",en:"I want to drink water."},{cn:"我想你。",py:"Wǒ xiǎng nǐ.",my:"ကျွန်တော်/မ သင့်ကို လွမ်းသည်。",en:"I miss you."}]},

  {cn:"说",py:"shuō",tone:1,my:"ပြောသည် / ဆိုသည်",en:"speak / say / talk",cat:"verb",
   ety:"'နှုတ်' + 'ဖလွယ်' - နှုတ်ဖြင့် အချက်အလက်ဖလှယ်ခြင်း",
   usage:"ဘာသာစကားနှင့် ပတ်သက်၍ မကြာမကြာ '说中文' (တရုတ်ပြောသည်) ဟုသုံး",
   strokes:["说","说"],
   examples:[{cn:"他说中文。",py:"Tā shuō zhōngwén.",my:"သူသည် တရုတ်ဘာသာ ပြောသည်。",en:"He speaks Chinese."},{cn:"你说什么？",py:"Nǐ shuō shénme?",my:"သင် ဘာပြောသနည်း？",en:"What did you say?"}]},

  {cn:"看",py:"kàn",tone:4,my:"ကြည့်သည် / ဖတ်သည်",en:"look / watch / read",cat:"verb",
   ety:"'လက်' + 'မျက်' - မျက်ကန်းမဖြစ်ရန် မျက်လုံးပေါ် လက်ကို ကာ၍ ကြည့်သောပုံ",
   usage:"书 (စာ)နှင့် '看书'(ဖတ်သည်), 电视 (TV) နှင့် '看电视'(TV ကြည့်သည်)",
   strokes:["看","看"],
   examples:[{cn:"我看书。",py:"Wǒ kàn shū.",my:"ကျွန်တော်/မ စာဖတ်သည်。",en:"I read books."},{cn:"我看电视。",py:"Wǒ kàn diànshì.",my:"ကျွန်တော်/မ TV ကြည့်သည်。",en:"I watch TV."}]},

  {cn:"听",py:"tīng",tone:1,my:"နားထောင်သည်",en:"listen / hear",cat:"verb",
   ety:"'귀 귀' (နားရွက်) + 'ဒြပ်' - နားနှင့် ကြားနိုင်ခြင်း၏ ဇာတိပုံ",
   usage:"'听音乐'(သီချင်းနားထောင်) '听老师'(ဆရာ့ကို နားထောင်)",
   strokes:["听","听"],
   examples:[{cn:"我听音乐。",py:"Wǒ tīng yīnyuè.",my:"ကျွန်တော်/မ သီချင်းနားထောင်သည်。",en:"I listen to music."},{cn:"请听我说。",py:"Qǐng tīng wǒ shuō.",my:"ကျွန်တော်/မ ပြောသည်ကို နားထောင်ပါ。",en:"Please listen to me."}]},

  {cn:"写",py:"xiě",tone:3,my:"ရေးသည်",en:"write",cat:"verb",
   ety:"'ဖုံးမ' + 'ကြောင်း' - ချည်ဖြင့် ဖုံးပြီး ကြောင်းဆွဲ၍ ရေးသောပုံ",
   usage:"'写字'(အက္ခရာရေး) '写作业'(အိမ်စာရေး) '写信'(စာပေးစာရေး)",
   strokes:["写","写"],
   examples:[{cn:"我写汉字。",py:"Wǒ xiě hànzì.",my:"ကျွန်တော်/မ တရုတ်အက္ခရာ ရေးသည်。",en:"I write Chinese characters."},{cn:"他写信。",py:"Tā xiě xìn.",my:"သူ/သူမ စာပေးစာ ရေးသည်。",en:"He/She writes a letter."}]},

  {cn:"读",py:"dú",tone:2,my:"ဖတ်သည် / ဆိုသည် (အသံကျယ်ကျယ်နှင့်)",en:"read (aloud)",cat:"verb",
   ety:"'ဝတ်ဆောင်' + 'ပြော' - ဝတ်ဆောင်ပြီးပြောဆိုခြင်း",
   usage:"'看'ထက် ပိုမိုသဘာဝကျသောဖတ်ခြင်း; '读书'(ကျောင်းနေ)",
   strokes:["读","读"],
   examples:[{cn:"请读这个句子。",py:"Qǐng dú zhège jùzi.",my:"ဤဝါကျကို ဖတ်ပါ。",en:"Please read this sentence."}]},

  {cn:"喝",py:"hē",tone:1,my:"သောက်သည်",en:"drink",cat:"verb",
   ety:"'နှုတ်' + 'ဖြတ်' - နှုတ်ဖြင့် အရည်ဖြတ်ချောင်ဆင်ခြင်း",
   usage:"'喝水'(ရေသောက်) '喝茶'(လက်ဖက်ရည်သောက်) '喝咖啡'(ကော်ဖီသောက်)",
   strokes:["喝","喝"],
   examples:[{cn:"我喝水。",py:"Wǒ hē shuǐ.",my:"ကျွန်တော်/မ ရေသောက်သည်。",en:"I drink water."},{cn:"你喝茶吗？",py:"Nǐ hē chá ma?",my:"သင် လက်ဖက်ရည် သောက်သလား？",en:"Do you drink tea?"}]},

  {cn:"吃",py:"chī",tone:1,my:"စားသည်",en:"eat",cat:"verb",
   ety:"'နှုတ်' + 'ဖြတ်ကြောင်း' - နှုတ်ဖြင့် အစာဝါး၍ ကျူးမှုပြုသောပုံ",
   usage:"'吃饭'(ထမင်းစား) '吃饺子'(ဂျောဇာစား) မလိုအပ်ရင် အာဟာရနာမ်မပါပဲ သုံးနိုင်",
   strokes:["吃","吃"],
   examples:[{cn:"我吃饭。",py:"Wǒ chī fàn.",my:"ကျွန်တော်/မ ထမင်းစားသည်。",en:"I eat (rice/food)."},{cn:"你吃什么？",py:"Nǐ chī shénme?",my:"သင် ဘာစားသနည်း？",en:"What do you eat?"}]},

  {cn:"来",py:"lái",tone:2,my:"လာသည်",en:"come",cat:"verb",
   ety:"'ပြောင်း' + 'ဆင်း' - ဘာမြစ်ဆင်ဆင်ချင်းမဟုတ်ပဲ ချဉ်းကပ်လာမှုကိုဖော်ပြ",
   usage:"ပြောသူကို ချဉ်းကပ်လာသောလှုပ်ရှားမှု; '来中国' (တရုတ်ကိုလာ)",
   strokes:["来","来"],
   examples:[{cn:"他来学校了。",py:"Tā lái xuéxiào le.",my:"သူ ကျောင်းကိုလာပြီ။",en:"He came to school."},{cn:"你来我家吧。",py:"Nǐ lái wǒ jiā ba.",my:"ကျွန်တော်/မ အိမ်ကို လာပါ。",en:"Come to my house."}]},

  {cn:"去",py:"qù",tone:4,my:"သွားသည်",en:"go",cat:"verb",
   ety:"'ကောင်ကင်' + 'ကြောင်း' + 'ပြောင်းရွှေ့' - ဝေးသောနေရာကို ဦးတည်သွားသောအိုင်ကွန်",
   usage:"ပြောသူမှ ဝေးကွာသွားသောလှုပ်ရှားမှု; 去+နေရာ",
   strokes:["去","去"],
   examples:[{cn:"我去学校。",py:"Wǒ qù xuéxiào.",my:"ကျွန်တော်/မ ကျောင်းသွားသည်。",en:"I go to school."},{cn:"你去哪里？",py:"Nǐ qù nǎlǐ?",my:"သင် ဘယ်သွားသနည်း？",en:"Where are you going?"}]},

  {cn:"坐",py:"zuò",tone:4,my:"ထိုင်သည် / စီးသည်",en:"sit / ride (transport)",cat:"verb",
   ety:"'ပုဂ္ဂိုလ်+ပုဂ္ဂိုလ်' + 'မြေ' - မြေပေါ်တွင် ထိုင်နေသောပုဂ္ဂိုလ်ပုံ",
   usage:"'坐下'(ထိုင်ချ) '坐车'(ကားစီး) '坐飞机'(လေယာဉ်စီး)",
   strokes:["坐","坐"],
   examples:[{cn:"请坐下。",py:"Qǐng zuò xia.",my:"ကျေးဇူးပြု၍ ထိုင်ပါ。",en:"Please sit down."},{cn:"我坐公共汽车。",py:"Wǒ zuò gōnggòng qìchē.",my:"ကျွန်တော်/မ ဘတ်စ်ကားစီးသည်。",en:"I take the bus."}]},

  {cn:"叫",py:"jiào",tone:4,my:"ခေါ်သည် / အမည်ဖြစ်သည်",en:"call / be named",cat:"verb",
   ety:"'နှုတ်' + 'ကြောင်း' - ကြောင်းဆွဲ၍ ခေါ်ဟစ်ခြင်း",
   usage:"'我叫...'(ကျွန်တော်/မ နာမည် ... ဖြစ်သည်) မိတ်ဆက်ရာတွင် အသုံးများ",
   strokes:["叫","叫"],
   examples:[{cn:"我叫李华。",py:"Wǒ jiào Lǐ Huá.",my:"ကျွန်တော်/မ နာမည် Li Hua ဖြစ်သည်。",en:"My name is Li Hua."},{cn:"你叫什么名字？",py:"Nǐ jiào shénme míngzì?",my:"သင့်နာမည် ဘယ်လိုခေါ်သလဲ？",en:"What is your name?"}]},

  {cn:"工作",py:"gōngzuò",tone:1,my:"အလုပ်လုပ်သည် / အလုပ်",en:"work / job",cat:"verb",
   ety:"'工'(အလုပ်/ပညာ) + '作'(ပြုလုပ်) = နှစ်ကြိယာပေါင်းစပ်",
   usage:"နာမ်ဖြစ်လည်း ကြိယာဖြစ်လည်း ဖြစ်နိုင်",
   strokes:["工","作"],
   examples:[{cn:"他工作很忙。",py:"Tā gōngzuò hěn máng.",my:"သူ အလုပ်များသည်。",en:"He is very busy with work."},{cn:"你的工作是什么？",py:"Nǐ de gōngzuò shì shénme?",my:"သင်၏ အလုပ်သည် ဘာဖြစ်သနည်း？",en:"What is your job?"}]},

  {cn:"学习",py:"xuéxí",tone:2,my:"လေ့လာသည် / ကျောင်းတက်သည်",en:"study / learn",cat:"verb",
   ety:"'学'(ကျောင်းတက်) + '习'(လေ့ကျင့်) - ကျောင်းတက်၍ လေ့ကျင့်ခြင်း",
   usage:"'学习汉语'(တရုတ်ဘာသာ သင်ယူ) '学习努力'(ကြိုးစားသင်ယူ)",
   strokes:["学","习"],
   examples:[{cn:"我学习汉语。",py:"Wǒ xuéxí hànyǔ.",my:"ကျွန်တော်/မ တရုတ်ဘာသာ သင်ယူသည်。",en:"I study Chinese."}]},

  {cn:"打电话",py:"dǎ diànhuà",tone:3,my:"ဖုန်းဆက်သည်",en:"make a phone call",cat:"verb",
   ety:"'打'(ချ/ဆက်) + '电'(လျှပ်စစ်) + '话'(စကားပြော) = လျှပ်စစ်စကားပြော",
   usage:"'给我打电话'(ကျွန်တော်/မကို ဖုန်းဆက်ပါ)",
   strokes:["打","电","话"],
   examples:[{cn:"我给你打电话。",py:"Wǒ gěi nǐ dǎ diànhuà.",my:"ကျွန်တော်/မ သင့်ကို ဖုန်းဆက်ပါမည်。",en:"I will call you."}]},

  {cn:"请",py:"qǐng",tone:3,my:"ကျေးဇူးပြု၍ / ဖိတ်ခေါ်သည်",en:"please / invite",cat:"verb",
   ety:"'ပြော' + 'ပြာသောင်း' - အသနားတောင်း သို့မဟုတ် ဖိတ်ကြားခြင်း",
   usage:"礼貌ဖော်ပြ: '请进'(ဝင်ပါ) '请坐'(ထိုင်ပါ) '请问'(ခွင့်ပြုပါ...)",
   strokes:["请","请"],
   examples:[{cn:"请进！",py:"Qǐng jìn!",my:"ဝင်ပါ！",en:"Please come in!"},{cn:"请问，厕所在哪里？",py:"Qǐngwèn, cèsuǒ zài nǎlǐ?",my:"ခွင့်ပြုပါ၊ အိမ်သာ ဘယ်မှာရှိသနည်း？",en:"Excuse me, where is the restroom?"}]},

  {cn:"住",py:"zhù",tone:4,my:"နေသည် / နေထိုင်သည်",en:"live / reside",cat:"verb",
   ety:"'ပုဂ္ဂိုလ်' + 'ထုံ' - ပုဂ္ဂိုလ်တစ်ဦး တစ်နေရာ ၌ ရပ်တန့်နေသောပုံ",
   usage:"'你住在哪里？'(သင် ဘယ်မှာနေသနည်း？) '住宾馆'(ဟိုတယ်တွင်နေ)",
   strokes:["住","住"],
   examples:[{cn:"我住在北京。",py:"Wǒ zhù zài Běijīng.",my:"ကျွန်တော်/မ ဘေဂျင်းတွင် နေသည်。",en:"I live in Beijing."}]},

  // Numbers
  {cn:"零",py:"líng",tone:2,my:"သုည (0)",en:"zero (0)",cat:"number",
   ety:"'ဘုတ်ဂဏန်း' ဟု ဆိုသောနာမ်မှ ဆင်းသက်လာ; နောက်ပိုင်းမှ 'ကြောင်းသေး' ဟုသောပုံနှင့် ပေါင်း",
   usage:"ဖုန်းနံပါတ် ဖတ်ရာတွင် '○'ကို 'líng'ဟု ဖတ်",
   strokes:["零","零"],
   examples:[{cn:"电话号码里有零。",py:"Diànhuà hàomǎ lǐ yǒu líng.",my:"ဖုန်းနံပါတ်တွင် သုည ပါသည်。",en:"There is a zero in the phone number."}]},

  {cn:"一",py:"yī",tone:1,my:"တစ် (1)",en:"one (1)",cat:"number",
   ety:"အများဆုံးရိုးရှင်းသောတရုတ်အက္ခရာ - ကြောင်းတစ်ကြောင်းသာ",
   usage:"ပတ်ဝန်းကျင်ပေါ်မူတည်၍ 'yí' (4တုန်ခင်) 'yì' (1,2,3တုန်ခင်) ဖြစ်ပြောင်း",
   strokes:["一"],
   examples:[{cn:"我有一本书。",py:"Wǒ yǒu yī běn shū.",my:"ကျွန်တော်/မ စာအုပ် တစ်အုပ်ရှိသည်。",en:"I have one book."}]},

  {cn:"二",py:"èr",tone:4,my:"နှစ် (2)",en:"two (2)",cat:"number",
   ety:"ကြောင်း နှစ်ကြောင်း - ရိုးရှင်းစွာ '2'ကိုဖော်ပြ",
   usage:"ဂဏန်းတစ်ဦးချင်းရေတွက်ရာတွင် 'èr' (两'liǎng'ကို 量词ထဲတွင်)",
   strokes:["二"],
   examples:[{cn:"二加二等于四。",py:"Èr jiā èr děngyú sì.",my:"နှစ် ပေါင်း နှစ် = လေး。",en:"Two plus two equals four."}]},

  {cn:"三",py:"sān",tone:1,my:"သုံး (3)",en:"three (3)",cat:"number",
   ety:"ကြောင်း သုံးကြောင်း - '一','二'မှ ဆက်လက်ပြောင်းလဲ",
   usage:"ကောင်းငြိမ်းသောနံပါတ်ဖြစ်ပြီး တရုတ်ယဉ်ကျေးမှုတွင် အသုံးများ",
   strokes:["三"],
   examples:[{cn:"我有三个苹果。",py:"Wǒ yǒu sān gè píngguǒ.",my:"ကျွန်တော်/မ ပန်းသီး သုံးလုံးရှိသည်。",en:"I have three apples."}]},

  {cn:"四",py:"sì",tone:4,my:"လေး (4)",en:"four (4)",cat:"number",
   ety:"'မြှုပ်ဖုံး' ပုံ - မသေချာ; '死'(သေ)နှင့် အသံတူ၍ တရုတ်ယဉ်ကျေးမှုတွင် မကောင်းနံပါတ်",
   usage:"ဟိုတယ်နှင့် ဆေးရုံများတွင် '4'လွှာ မကြာမကြာ ကျော်တတ်သည်",
   strokes:["四"],
   examples:[{cn:"我四岁了。",py:"Wǒ sì suì le.",my:"ကျွန်တော်/မ လေးနှစ်သားဖြစ်ပြီ。",en:"I am four years old."}]},

  {cn:"五",py:"wǔ",tone:3,my:"ငါး (5)",en:"five (5)",cat:"number",
   ety:"'ကြားဟာ' + 'ဖတ်ကြိုး' - ငါးကြောင်းတင်ကြောင်း; ဟိုးရှေးကာလ ၅ = ကောင်းငြိမ်း",
   usage:"'五月'(မေ) '五星红旗'(နှင်းဆီနီနက်ကြယ်အလံ)",
   strokes:["五"],
   examples:[{cn:"今天是五号。",py:"Jīntiān shì wǔ hào.",my:"ယနေ့ ၅ ရက်ဖြစ်သည်。",en:"Today is the 5th."}]},

  {cn:"六",py:"liù",tone:4,my:"ခြောက် (6)",en:"six (6)",cat:"number",
   ety:"'ဦးခေါင်း' + 'ဒြပ်' - ဟိုးရှေးမှ ပြောင်းလဲလာ; '六六大顺'(ကောင်းမွန်ချောမွေ့)",
   usage:"'六月'(ဇွန်) တရုတ်ယဉ်ကျေးမှုတွင် ကောင်းမွန်သောနံပါတ်",
   strokes:["六"],
   examples:[{cn:"我六点起床。",py:"Wǒ liù diǎn qǐchuáng.",my:"ကျွန်တော်/မ ၆ နာရီတွင် နိုးသည်。",en:"I wake up at 6 o'clock."}]},

  {cn:"七",py:"qī",tone:1,my:"ခုနစ် (7)",en:"seven (7)",cat:"number",
   ety:"'ကြောင်းဖြတ်' - ကြောင်းတစ်ကြောင်းကို နောက်တစ်ကြောင်းဖြင့် ဖြတ်ကူးသောပုံ",
   usage:"'七月'(ဇူလိုင်) '七夕'(တရုတ်ဗယ်လင်တိုင်း)",
   strokes:["七"],
   examples:[{cn:"一周有七天。",py:"Yī zhōu yǒu qī tiān.",my:"တစ်ပတ်တွင် ၇ ရက်ရှိသည်。",en:"There are seven days in a week."}]},

  {cn:"八",py:"bā",tone:1,my:"ရှစ် (8)",en:"eight (8)",cat:"number",
   ety:"'ခွဲ' ဟု ဆိုသောပုံ - '八'=ကံကောင်းခြင်း; '发'(ကြွယ်ဝ)နှင့် အသံဆင်",
   usage:"တရုတ်ယဉ်ကျေးမှုတွင် အကောင်းဆုံးနံပါတ်! ဘေဂျင်းအိုလံပစ်ကို ၂၀၀၈-၀၈-၀၈ မှတ်",
   strokes:["八"],
   examples:[{cn:"八月是夏天。",py:"Bā yuè shì xiàtiān.",my:"ဩဂုတ်လသည် နွေရာသီ ဖြစ်သည်。",en:"August is summer."}]},

  {cn:"九",py:"jiǔ",tone:3,my:"ကိုး (9)",en:"nine (9)",cat:"number",
   ety:"'ဦးခေါင်း' + 'ဦးချ' - '久'(ကြာ)နှင့် အသံတူ၍ ကြာရှည်ကောင်းမွန်ရေးကို ကိုယ်စားပြု",
   usage:"'九月'(စက်တင်ဘာ) ဒ်ုတိယကောင်းငြိမ်းနံပါတ်",
   strokes:["九"],
   examples:[{cn:"九月九日是重阳节。",py:"Jiǔ yuè jiǔ rì shì Chóngyáng Jié.",my:"၉ လ ၉ ရက်သည် Chongyang ပွဲတော်ဖြစ်သည်。",en:"September 9 is the Double Ninth Festival."}]},

  {cn:"十",py:"shí",tone:2,my:"တစ်ဆယ် (10)",en:"ten (10)",cat:"number",
   ety:"ဒေါင်လိုက်ကြောင်း + အလျားလိုက်ကြောင်း = ဆုံနေရာ ၁၀ ဖော်ပြ",
   usage:"'十月'(အောက်တိုဘာ) ၁၁-၁၉ = '十一'(11) '十二'(12) ...",
   strokes:["十"],
   examples:[{cn:"十月是秋天。",py:"Shí yuè shì qiūtiān.",my:"အောက်တိုဘာသည် ဆောင်းဦးရာသီ ဖြစ်သည်。",en:"October is autumn."}]},

  {cn:"百",py:"bǎi",tone:3,my:"တစ်ရာ (100)",en:"hundred (100)",cat:"number",
   ety:"'ဦးခေါင်း' + 'ကြောင်း' - ဦးထိပ်ပေါ်ကြောင်းဖြင့် ထူးချွန်သောနံပါတ်ဖော်ပြ",
   usage:"'一百'(တစ်ရာ) '百分之百'(ရာနှုန်းပြည့်)",
   strokes:["百","百"],
   examples:[{cn:"一百个人。",py:"Yī bǎi gè rén.",my:"လူ တစ်ရာ。",en:"One hundred people."}]},

  {cn:"千",py:"qiān",tone:1,my:"တစ်ထောင် (1000)",en:"thousand (1000)",cat:"number",
   ety:"'ပုဂ္ဂိုလ်' + 'ဆယ်' - 'ပေါင်းကြောင်း'မှ ဆင်းသက်",
   usage:"'一千'(တစ်ထောင်) '千年'(တစ်ထောင်နှစ်)",
   strokes:["千","千"],
   examples:[{cn:"一千块钱。",py:"Yī qiān kuài qián.",my:"ငွေ တစ်ထောင် ယွမ်。",en:"One thousand yuan."}]},

  {cn:"万",py:"wàn",tone:4,my:"တစ်သောင်း (10,000)",en:"ten-thousand (10,000)",cat:"number",
   ety:"'ကင်းမြိတ်' ပုံ - တရုတ်ဂဏန်းစနစ်တွင် ၁ဝ,ဝဝဝ = အခြေခံယူနစ်",
   usage:"တရုတ်ဂဏန်းစနစ် အရေးကြီး! ၁ million = '一百万'",
   strokes:["万","万"],
   examples:[{cn:"一万人。",py:"Yī wàn rén.",my:"လူ တစ်သောင်း。",en:"Ten thousand people."}]},

  // Question words
  {cn:"什么",py:"shénme",tone:2,my:"ဘာ (ဘယ်အရာ)",en:"what",cat:"question",
   ety:"'什'(ဘာ)+' 么'(မေးခွန်းဝိဘတ်) - ဟိုးဆောင်မေးခွန်းမှ ဆင်းသက်",
   usage:"ဝါကျတစ်ကြောင်းတွင် မည်သည့်နေရာ၌မဆို ထားနိုင်",
   strokes:["什","么"],
   examples:[{cn:"这是什么？",py:"Zhè shì shénme?",my:"ဒါ ဘာလဲ？",en:"What is this?"},{cn:"你叫什么名字？",py:"Nǐ jiào shénme míngzì?",my:"သင့်နာမည် ဘာလဲ？",en:"What is your name?"}]},

  {cn:"哪",py:"nǎ",tone:3,my:"ဘယ် (ဘယ်နေရာ/ဘယ်ဟာ)",en:"which / where",cat:"question",
   ety:"'နှုတ်' + 'မြို့' - နေရာမေးမြန်းသောအဓိပ္ပာယ်",
   usage:"'哪里'(ဘယ်မှာ) '哪个'(ဘယ်တစ်ခု) '哪位'(ဘယ်ဝိတ်)",
   strokes:["哪","哪"],
   examples:[{cn:"你去哪里？",py:"Nǐ qù nǎlǐ?",my:"သင် ဘယ်သွားမည်？",en:"Where are you going?"},{cn:"哪个是你的？",py:"Nǎge shì nǐ de?",my:"ဘယ်ဟာ သင်၏ ဖြစ်သနည်း？",en:"Which one is yours?"}]},

  {cn:"哪里",py:"nǎlǐ",tone:3,my:"ဘယ်မှာ (ဘယ်နေရာ)",en:"where",cat:"question",
   ety:"'哪'(ဘယ်) + '里'(အတွင်း/နေရာ)",
   usage:"'你在哪里？'(သင် ဘယ်မှာရှိသနည်း？) '哪里都行'(ဘယ်နေရာမဆို ရပါသည်)",
   strokes:["哪","里"],
   examples:[{cn:"你家在哪里？",py:"Nǐ jiā zài nǎlǐ?",my:"သင်၏ အိမ်သည် ဘယ်မှာ ရှိသနည်း？",en:"Where is your home?"}]},

  {cn:"谁",py:"shéi",tone:2,my:"ဘယ်သူ",en:"who",cat:"question",
   ety:"'ပြော' + 'ပြောင်းသူ' - 'ဘယ်သူ'ကို ရည်ညွှန်းသောအဓိပ္ပာယ်",
   usage:"ဝါကျတွင် ပုဂ္ဂိုလ်ကိုမေး; '这是谁的书？'(ဒါ ဘယ်သူ့ စာအုပ်လဲ？)",
   strokes:["谁","谁"],
   examples:[{cn:"这是谁？",py:"Zhè shì shéi?",my:"ဒါ ဘယ်သူလဲ？",en:"Who is this?"},{cn:"谁是你的老师？",py:"Shéi shì nǐ de lǎoshī?",my:"ဘယ်သူ သင်၏ ဆရာ/မ ဖြစ်သနည်း？",en:"Who is your teacher?"}]},

  {cn:"多少",py:"duōshao",tone:1,my:"ဘယ်လောက် (အရေအတွက်/ပမာဏ)",en:"how many / how much",cat:"question",
   ety:"'多'(များ)+'少'(နည်း) - 'မည်မျှ' ဟု မေးသောအဓိပ္ပာယ်",
   usage:"'多少钱？'(ဘယ်လောက်ကျသနည်း？) '多少人？'(လူ ဘယ်နှစ်ဦးရှိသနည်း？)",
   strokes:["多","少"],
   examples:[{cn:"多少钱？",py:"Duōshao qián?",my:"ဘယ်လောက်ကျသနည်း？",en:"How much does it cost?"},{cn:"这里有多少学生？",py:"Zhèlǐ yǒu duōshao xuésheng?",my:"ဒီမှာ ကျောင်းသား ဘယ်နှစ်ဦးရှိသနည်း？",en:"How many students are here?"}]},

  {cn:"几",py:"jǐ",tone:3,my:"ဘယ်နှစ် (နည်းသောအရေအတွက်မေး)",en:"how many (small number)",cat:"question",
   ety:"'ဝိုင်းဒြပ်' + 'ကြောင်း' - နည်းသောအရေအတွက်ကို မေးသောအဓိပ္ပာယ်",
   usage:"များသောအားဖြင့် ၁-၁၀ ကြားကို မျှော်မှန်းသောအခါ; '几岁？'(အသက် ဘယ်နှစ်နှစ်？)",
   strokes:["几","几"],
   examples:[{cn:"你几岁？",py:"Nǐ jǐ suì?",my:"သင် အသက် ဘယ်နှစ်နှစ်ရှိပြီလဲ？",en:"How old are you?"},{cn:"几点了？",py:"Jǐ diǎn le?",my:"ဘယ်နှစ်နာရီ ရှိပြီလဲ？",en:"What time is it?"}]},

  {cn:"怎么",py:"zěnme",tone:3,my:"ဘယ်လိုလဲ / ဘယ်လို",en:"how",cat:"question",
   ety:"'怎'(မည်သို့) + '么'(မေးဝိဘတ်) - နည်းလမ်းမေးခွန်း",
   usage:"'怎么去？'(ဘယ်လိုသွားမည်？) '怎么了？'(ဘာဖြစ်သွားသလဲ？)",
   strokes:["怎","么"],
   examples:[{cn:"怎么去车站？",py:"Zěnme qù chēzhàn?",my:"ဘူတာ/ကားဂိတ်ကို ဘယ်လိုသွားမည်？",en:"How do I get to the station?"}]},

  {cn:"为什么",py:"wèishénme",tone:4,my:"ဘာကြောင့် / ဘာဖြစ်လို့",en:"why",cat:"question",
   ety:"'为'(ကြောင့်) + '什么'(ဘာ) = ဘာကြောင့်",
   usage:"အကြောင်းရင်း မေးသောကြိတ်ကြော - 'ဘာကြောင့်'",
   strokes:["为","什","么"],
   examples:[{cn:"你为什么学中文？",py:"Nǐ wèishénme xué zhōngwén?",my:"သင် ဘာကြောင့် တရုတ်ဘာသာ သင်ယူသနည်း？",en:"Why do you study Chinese?"}]},

  // Time words
  {cn:"今天",py:"jīntiān",tone:1,my:"ယနေ့",en:"today",cat:"time",
   ety:"'今'(ယနေ့ = ထိပ်ပေါ်မှာ/ကြိုတင်) + '天'(ရက်/ကောင်းကင်)",
   usage:"'今天几号？'(ယနေ့ ဘယ်ရက်？) '今天天气怎么样？'(ယနေ့ မိုးလေဝသ ဘယ်လိုလဲ？)",
   strokes:["今","天"],
   examples:[{cn:"今天是星期一。",py:"Jīntiān shì xīngqīyī.",my:"ယနေ့ တနင်္လာ နေ့ ဖြစ်သည်。",en:"Today is Monday."},{cn:"今天天气很好。",py:"Jīntiān tiānqì hěn hǎo.",my:"ယနေ့ ရာသီဥတု ကောင်းသည်。",en:"The weather is nice today."}]},

  {cn:"明天",py:"míngtiān",tone:2,my:"မနက်ဖြန် / မဟာနက်",en:"tomorrow",cat:"time",
   ety:"'明'(တောက်ပ = နေ+လ) + '天'(ရက်) = တောက်ပသောနေ့",
   usage:"'明天见！'(မနက်ဖြန် တွေ့မည်！) '明天有空吗？'(မနက်ဖြန် အချိန်ရမည်လား？)",
   strokes:["明","天"],
   examples:[{cn:"明天我们去公园。",py:"Míngtiān wǒmen qù gōngyuán.",my:"မနက်ဖြန် ကျွန်တော်တို့ ပန်းခြံသွားမည်。",en:"Tomorrow we go to the park."}]},

  {cn:"昨天",py:"zuótiān",tone:2,my:"မနေ့က / တမန်နေ့",en:"yesterday",cat:"time",
   ety:"'昨'(ကုန်သွားသောနေ့) + '天'(ရက်) = ကျော်လွန်သောနေ့",
   usage:"'昨天晚上'(မနေ့ည) '昨天我去了...'(မနေ့က သွားခဲ့သည်)",
   strokes:["昨","天"],
   examples:[{cn:"昨天下雨了。",py:"Zuótiān xià yǔ le.",my:"မနေ့က မိုးရွာခဲ့သည်。",en:"It rained yesterday."}]},

  {cn:"年",py:"nián",tone:2,my:"နှစ် (ခုနှစ်)",en:"year",cat:"time",
   ety:"'ကောင်းစပါး' ကိုကျိုးကောင်းကောင်း ထမ်းနေသောပုဂ္ဂိုလ်ပုံ - ဆောင်ရာသီနှင့် ဆက်နွှယ်",
   usage:"'今年'(ဤနှစ်) '明年'(နောက်နှစ်) '去年'(မနှစ်) '多少年？'(နှစ်ဘယ်နှစ်？)",
   strokes:["年","年"],
   examples:[{cn:"今年是哪年？",py:"Jīnnián shì nǎ nián?",my:"ဒီနှစ်သည် ဘယ်နှစ်နှစ်ဖြစ်သနည်း？",en:"What year is this year?"}]},

  {cn:"月",py:"yuè",tone:4,my:"လ (တစ်လ / လဆန်း)",en:"month / moon",cat:"time",
   ety:"လ(ကွမ်းခြမ်း)ပုံ - ဟိုးရှေးကာလ လဆန်းဖြင့် ရက်ဖတ်",
   usage:"'一月'(ဇန်နဝါရီ) ... '十二月'(ဒီဇင်ဘာ); '每月'(တိုင်းလ)",
   strokes:["月","月"],
   examples:[{cn:"这个月是几月？",py:"Zhège yuè shì jǐ yuè?",my:"ဒီ လ သည် ဘယ်လဖြစ်သနည်း？",en:"What month is this month?"}]},

  {cn:"日",py:"rì",tone:4,my:"နေ့/ရက် (တရားဝင်ဘာသာ)",en:"day / date (formal)",cat:"time",
   ety:"နေ(ဆိုင်ကယ်)ပုံ - '天'ထက် ပိုတရားဝင်",
   usage:"ဖော်မယ်ဘာသာ; '星期'/'天'ကို ပိုများသောနေ့ရောင်းဝယ်ရာတွင် သုံး",
   strokes:["日","日"],
   examples:[{cn:"今天是三月八日。",py:"Jīntiān shì sān yuè bā rì.",my:"ယနေ့ မတ်လ ၈ ရက် ဖြစ်သည်。",en:"Today is March 8."}]},

  {cn:"天",py:"tiān",tone:1,my:"ကောင်းကင် / နေ့",en:"sky / day",cat:"time",
   ety:"'ကောင်ကြီးသော' ပုဂ္ဂိုလ်ပေါ်ကောင်းကင်ပုံ - '大'(ကြီး)+ကြောင်း",
   usage:"'今天'(ယနေ့) '天气'(ရာသီဥတု) '天空'(ကောင်းကင်) '一天'(တစ်နေ့)",
   strokes:["天","天"],
   examples:[{cn:"天气很好。",py:"Tiānqì hěn hǎo.",my:"ရာသီဥတု ကောင်းသည်。",en:"The weather is great."}]},

  {cn:"星期",py:"xīngqī",tone:1,my:"အပတ် (တစ်ပတ်)",en:"week",cat:"time",
   ety:"'星'(ကြယ်) + '期'(ကာလ) - ကြယ်ကာလ; ယူဂျူလီယန်ပြက္ခဒိန်မှ ဆင်းသက်",
   usage:"'星期一'(တနင်္လာ) ... '星期日/星期天'(တနင်္ဂနွေ)",
   strokes:["星","期"],
   examples:[{cn:"今天是星期几？",py:"Jīntiān shì xīngqī jǐ?",my:"ယနေ့ ဘယ်နေ့ ဖြစ်သနည်း？",en:"What day of the week is today?"}]},

  {cn:"上午",py:"shàngwǔ",tone:4,my:"မနက် (ရုင်မနက်/နောက်နွေး)",en:"morning / AM",cat:"time",
   ety:"'上'(အပေါ်) + '午'(နေ့တည့်) = နေ့ကြောင်းပိုင်းမတိုင်မီ",
   usage:"'上午九点'(မနက် ၉ နာရီ) '上午好！'(မနက် ကျန်းမာပါ！)",
   strokes:["上","午"],
   examples:[{cn:"上午我有课。",py:"Shàngwǔ wǒ yǒu kè.",my:"မနက်ပိုင်းတွင် ကျွန်တော်/မ သင်တန်းရှိသည်。",en:"I have class in the morning."}]},

  {cn:"下午",py:"xiàwǔ",tone:4,my:"ညနေ (နေ့လည်ခင်းနောက်)",en:"afternoon / PM",cat:"time",
   ety:"'下'(အောက်) + '午'(နေ့တည့်) = နေ့ကြောင်းပိုင်းနောက်",
   usage:"'下午三点'(ညနေ ၃ နာရီ)",
   strokes:["下","午"],
   examples:[{cn:"下午我去图书馆。",py:"Xiàwǔ wǒ qù túshūguǎn.",my:"ညနေပိုင်းတွင် ကျွန်တော်/မ စာကြည့်တိုက်သွားမည်。",en:"In the afternoon I go to the library."}]},

  {cn:"晚上",py:"wǎnshang",tone:3,my:"ည (ညနက်)",en:"evening / night",cat:"time",
   ety:"'晚'(နောက်ကျ/ညနေ) + '上'(ကာလ) - ညဖော်ပြ",
   usage:"'晚上好！'(ညနေ ကျန်းမာပါ！) '今天晚上'(ယနေ့ ည)",
   strokes:["晚","上"],
   examples:[{cn:"晚上好！",py:"Wǎnshang hǎo!",my:"ညနေ ကျန်းမာပါ！",en:"Good evening!"},{cn:"晚上我看书。",py:"Wǎnshang wǒ kàn shū.",my:"ည ကျွန်တော်/မ စာဖတ်သည်。",en:"I read at night."}]},

  {cn:"现在",py:"xiànzài",tone:4,my:"ယခု / အခု",en:"now",cat:"time",
   ety:"'现'(ပေါ်ထွက်) + '在'(ရှိ/နေ) = ယခုချိန်တွင် ရှိနေ",
   usage:"'现在几点？'(ယခု ဘယ်နှစ်နာရီ？) '现在我去'(ယခု ငါသွားမည်)",
   strokes:["现","在"],
   examples:[{cn:"现在几点？",py:"Xiànzài jǐ diǎn?",my:"ယခု ဘယ်နှစ်နာရီ ရှိပြီလဲ？",en:"What time is it now?"}]},

  {cn:"时候",py:"shíhou",tone:2,my:"အချိန်/ကာလ (ဘယ်အချိန်)",en:"time / moment / when",cat:"time",
   ety:"'时'(အချိန်) + '候'(စောင့်) = မျှော်နေသောအချိန်",
   usage:"'什么时候？'(ဘယ်အချိန်？) '那时候'(ထိုအချိန်တွင်)",
   strokes:["时","候"],
   examples:[{cn:"你什么时候去？",py:"Nǐ shénme shíhou qù?",my:"သင် ဘယ်အချိန် သွားမည်？",en:"When are you going?"}]},

  // Nouns - People
  {cn:"人",py:"rén",tone:2,my:"လူ / ပုဂ္ဂိုလ်",en:"person / people",cat:"noun",
   ety:"ဘေးနှစ်ဖက်မှ ဖြန့်ကားနေသော ခြေထောက်ရှိပုဂ္ဂိုလ်ပုံ - အရိုးရှင်းဆုံးနိုင်ငံတော်",
   usage:"'中国人'(တရုတ်လူမျိုး) '一个人'(တစ်ဦးတည်း) '人民'(ပြည်သူ)",
   strokes:["人","人"],
   examples:[{cn:"你是中国人吗？",py:"Nǐ shì zhōngguórén ma?",my:"သင် တရုတ်လူမျိုး ဖြစ်သလား？",en:"Are you Chinese?"}]},

  {cn:"朋友",py:"péngyou",tone:2,my:"သူငယ်ချင်း",en:"friend",cat:"noun",
   ety:"'朋'(ငှက်ဒဘျပြ - အဖွဲ့) + '友'(ညာ) = ဘေးချင်းယှဉ်သောသူ",
   usage:"'好朋友'(ကောင်းသောသူငယ်ချင်း) '男朋友'(ချစ်သူ) '女朋友'(ချစ်သူမ)",
   strokes:["朋","友"],
   examples:[{cn:"他是我的好朋友。",py:"Tā shì wǒ de hǎo péngyou.",my:"သူသည် ကျွန်တော်၏ ကောင်းသောသူငယ်ချင်း ဖြစ်သည်。",en:"He is my good friend."}]},

  {cn:"老师",py:"lǎoshī",tone:3,my:"ဆရာ/ဆရာမ",en:"teacher",cat:"noun",
   ety:"'老'(အသက်ကြီး/အတွေ့အကြုံ) + '师'(ကျွမ်းကျင်) = ကျွမ်းကျင်မြောက်မြားသောသူ",
   usage:"'中文老师'(တရုတ်ဘာသာ ဆရာ/မ) '您好，老师！'(ဆရာ/မ ကျန်းမာပါ！)",
   strokes:["老","师"],
   examples:[{cn:"我的老师很好。",py:"Wǒ de lǎoshī hěn hǎo.",my:"ကျွန်တော်/မ ၏ ဆရာ/မ ကောင်းသည်。",en:"My teacher is very good."}]},

  {cn:"学生",py:"xuésheng",tone:2,my:"ကျောင်းသား/ကျောင်းသူ",en:"student",cat:"noun",
   ety:"'学'(သင်ယူ) + '生'(ဖြစ်ပေါ်/ပေါ်ထွက်) = သင်ယူနေသောသူ",
   usage:"'大学生'(တက္ကသိုလ်ကျောင်းသား) '小学生'(မူလတန်းကျောင်းသား)",
   strokes:["学","生"],
   examples:[{cn:"我是大学生。",py:"Wǒ shì dàxuésheng.",my:"ကျွန်တော်/မ တက္ကသိုလ်ကျောင်းသား ဖြစ်သည်。",en:"I am a university student."}]},

  {cn:"医生",py:"yīshēng",tone:1,my:"ဆရာဝန်",en:"doctor",cat:"noun",
   ety:"'医'(ကုသ) + '生'(ဆရာ) = ကျန်းမာရေး ကုသသောသူ",
   usage:"'看医生'(ဆရာဝန်စစ်) '牙医'(သွားဆရာဝန်)",
   strokes:["医","生"],
   examples:[{cn:"我要去看医生。",py:"Wǒ yào qù kàn yīshēng.",my:"ကျွန်တော်/မ ဆရာဝန်ထံ သွားမည်。",en:"I need to see a doctor."}]},

  {cn:"爸爸",py:"bàba",tone:4,my:"အဖ (ဖေဖေ)",en:"dad / father",cat:"noun",
   ety:"'父'(ဖ)မှ ဆင်းသက်; ကလေးဘာသာ တိုက်ရိုက်ပြောနည်း - ပျော်ရွှင်/ချစ်ခင်",
   usage:"တင်းကျပ်သောဘာသာ '父亲' ပိုတရားဝင်",
   strokes:["爸","爸"],
   examples:[{cn:"我爸爸是老师。",py:"Wǒ bàba shì lǎoshī.",my:"ကျွန်တော်/မ ၏ ဖေဖေသည် ဆရာ ဖြစ်သည်。",en:"My dad is a teacher."}]},

  {cn:"妈妈",py:"māma",tone:1,my:"အမိ (မေမေ)",en:"mom / mother",cat:"noun",
   ety:"'母'(မ)မှ ဆင်းသက်; ကလေးဘာသာ - ချစ်ခင်/နီးနီးနေ",
   usage:"တင်းကျပ်သောဘာသာ '母亲' ပိုတရားဝင်",
   strokes:["妈","妈"],
   examples:[{cn:"妈妈做饭很好吃。",py:"Māma zuò fàn hěn hǎo chī.",my:"မေမေ ချက်သောအစာ အရမ်းကောင်းသည်。",en:"Mom's cooking is delicious."}]},

  {cn:"家",py:"jiā",tone:1,my:"အိမ် / မိသားစု",en:"home / family",cat:"noun",
   ety:"'ခေါင်မိုး' + 'ဝက်' - ဝက်ကိုထိန်းသောအခြောက်/အိုးတစ်လုံး = ကောင်းစွာ စီမံပြုပြင်",
   usage:"'我家'(ကျွန်တော်/မ အိမ်) '回家'(အိမ်ပြန်) '家人'(မိသားစုဝင်)",
   strokes:["家","家"],
   examples:[{cn:"我回家了。",py:"Wǒ huí jiā le.",my:"ကျွန်တော်/မ အိမ်ပြန်လာပြီ。",en:"I'm home now."},{cn:"我家有四口人。",py:"Wǒ jiā yǒu sì kǒu rén.",my:"ကျွန်တော်/မ မိသားစုတွင် လူ ၄ ဦးရှိသည်。",en:"My family has four people."}]},

  // Nouns - Objects
  {cn:"书",py:"shū",tone:1,my:"စာအုပ်",en:"book",cat:"noun",
   ety:"'ပြော' + 'ကလပ်' - ပြောဆိုသည့်အရာကို မှတ်တမ်းတင်",
   usage:"'图书馆'(စာကြည့်တိုက်) '书包'(ကျောပိုး) '一本书'(တစ်အုပ်)",
   strokes:["书","书"],
   examples:[{cn:"我喜欢看书。",py:"Wǒ xǐhuan kàn shū.",my:"ကျွန်တော်/မ စာဖတ်ချင်သည်。",en:"I like reading books."}]},

  {cn:"水",py:"shuǐ",tone:3,my:"ရေ",en:"water",cat:"noun",
   ety:"စီးဆင်းနေသောရေ၏ ပုံ - ကြောင်းသုံးကြောင်း စီးဆင်းနေ",
   usage:"'喝水'(ရေသောက်) '水果'(သစ်သီးများ) '热水'(ပူသောရေ)",
   strokes:["水","水"],
   examples:[{cn:"请给我一杯水。",py:"Qǐng gěi wǒ yī bēi shuǐ.",my:"ကျေးဇူးပြု၍ ကျွန်တော်/မကို ရေ တစ်ခွက် ပေးပါ。",en:"Please give me a cup of water."}]},

  {cn:"饭",py:"fàn",tone:4,my:"ထမင်း / အစားအစာ",en:"rice / meal",cat:"noun",
   ety:"'အစာ' + 'ဆုတ်ယုတ်' - ယွမ်းလာသောနှောင်ကြောင်း/ဆန်ဖြစ်ပြောင်း",
   usage:"'吃饭'(ထမင်းစား) '做饭'(ချက်ပြုတ်) '米饭'(ဆန်ပေါင်းထမင်း)",
   strokes:["饭","饭"],
   examples:[{cn:"我做饭。",py:"Wǒ zuò fàn.",my:"ကျွန်တော်/မ ချက်ပြုတ်သည်。",en:"I cook."},{cn:"吃饭了吗？",py:"Chī fàn le ma?",my:"ထမင်းစားပြီးပြီလား？",en:"Have you eaten?"}]},

  {cn:"茶",py:"chá",tone:2,my:"လက်ဖက်ရည်",en:"tea",cat:"noun",
   ety:"'ဒြပ်' + 'ပင်' + 'ကိုင်' - ပင်ပေါ်မှ ချပ်ထုတ်သောအရာ",
   usage:"'喝茶'(လက်ဖက်ရည်သောက်) '绿茶'(ပတ်ကူးလက်ဖက်ရည်) '茶馆'(လက်ဖက်ဆိုင်)",
   strokes:["茶","茶"],
   examples:[{cn:"中国人爱喝茶。",py:"Zhōngguó rén ài hē chá.",my:"တရုတ်လူမျိုးများ လက်ဖက်ရည်သောက်ချင်သည်。",en:"Chinese people love to drink tea."}]},

  {cn:"电脑",py:"diànnǎo",tone:4,my:"ကွန်ပျူတာ",en:"computer",cat:"noun",
   ety:"'电'(လျှပ်စစ်) + '脑'(ဦးနှောက်) = လျှပ်စစ်ဦးနှောက်",
   usage:"'笔记本电脑'(laptop) '台式电脑'(desktop)",
   strokes:["电","脑"],
   examples:[{cn:"我有一台电脑。",py:"Wǒ yǒu yī tái diànnǎo.",my:"ကျွန်တော်/မ ကွန်ပျူတာ တစ်လုံး ရှိသည်。",en:"I have a computer."}]},

  {cn:"手机",py:"shǒujī",tone:3,my:"မိုဘိုင်းဖုန်း",en:"mobile phone",cat:"noun",
   ety:"'手'(လက်) + '机'(စက်/ကိရိယာ) = လက်ကိုင်စက်ပစ္စည်း",
   usage:"'打手机'(မိုဘိုင်းဖုန်းဆက်) '充手机'(ဖုန်းသွင်း) '手机号'(ဖုန်းနံပါတ်)",
   strokes:["手","机"],
   examples:[{cn:"我的手机在哪里？",py:"Wǒ de shǒujī zài nǎlǐ?",my:"ကျွန်တော်/မ ၏ ဖုန်းသည် ဘယ်မှာ ရှိသနည်း？",en:"Where is my phone?"}]},

  {cn:"钱",py:"qián",tone:2,my:"ငွေ",en:"money",cat:"noun",
   ety:"'ကြေး' + 'ဈေး' - ဟိုးရှေး တူနှစ်ချောင်းကွင်းဆွဲဖြင့် ဝယ်ယူနိုင်",
   usage:"'多少钱？'(ဘယ်လောက်？) '块钱'(ယွမ်) '没钱'(ငွေမရှိ)",
   strokes:["钱","钱"],
   examples:[{cn:"多少钱？",py:"Duōshao qián?",my:"ဘယ်လောက်ကျသနည်း？",en:"How much money?"},{cn:"我没有钱。",py:"Wǒ méiyǒu qián.",my:"ကျွန်တော်/မ ငွေမရှိ。",en:"I have no money."}]},

  {cn:"衣服",py:"yīfu",tone:1,my:"အဝတ်အစား",en:"clothes",cat:"noun",
   ety:"'衣'(ကြွေ-ပြင်ပတ်) + '服'(ဝတ်ဆောင်) = ကြွေဆောင်ခြင်း/ဝတ်ဆောင်ခြင်း",
   usage:"'穿衣服'(အဝတ်ဝတ်) '买衣服'(အဝတ်ဝယ်)",
   strokes:["衣","服"],
   examples:[{cn:"我买了一件新衣服。",py:"Wǒ mǎi le yī jiàn xīn yīfu.",my:"ကျွန်တော်/မ အဝတ်အသစ် တစ်ထည် ဝယ်ခဲ့သည်。",en:"I bought a new piece of clothing."}]},

  // Places
  {cn:"学校",py:"xuéxiào",tone:2,my:"ကျောင်း",en:"school",cat:"noun",
   ety:"'学'(သင်ယူ) + '校'(ကျောင်း/နေရာ) = သင်ယူသောနေရာ",
   usage:"'上学'(ကျောင်းတက်) '放学'(ကျောင်းဆင်း) '小学/中学/大学'",
   strokes:["学","校"],
   examples:[{cn:"我去学校上课。",py:"Wǒ qù xuéxiào shàng kè.",my:"ကျွန်တော်/မ ကျောင်းသွားသင်သည်。",en:"I go to school to attend class."}]},

  {cn:"医院",py:"yīyuàn",tone:1,my:"ဆေးရုံ",en:"hospital",cat:"noun",
   ety:"'医'(ဆေးကုသ) + '院'(ဝင်းကျောင်း) = ကုသသောနေရာ",
   usage:"'去医院'(ဆေးရုံသွား) '住院'(ဆေးရုံတက်)",
   strokes:["医","院"],
   examples:[{cn:"医院在学校旁边。",py:"Yīyuàn zài xuéxiào pángbiān.",my:"ဆေးရုံသည် ကျောင်း နား ရှိသည်。",en:"The hospital is next to the school."}]},

  {cn:"饭店",py:"fàndiàn",tone:4,my:"စားသောက်ဆိုင် / ဟိုတယ်",en:"restaurant / hotel",cat:"noun",
   ety:"'饭'(အစားအစာ) + '店'(ဆိုင်/တဲ) = အစားအစာဆိုင်",
   usage:"'中国饭店'(တရုတ်စားသောက်ဆိုင်) ဟိုတယ်ဆိုသည့်အဓိပ္ပာယ်လည်းရ",
   strokes:["饭","店"],
   examples:[{cn:"我们去饭店吃饭吧。",py:"Wǒmen qù fàndiàn chī fàn ba.",my:"ကျွန်တော်တို့ စားသောက်ဆိုင်မှာ ထမင်းစားကြစို့。",en:"Let's go eat at a restaurant."}]},

  {cn:"商店",py:"shāngdiàn",tone:1,my:"ဆိုင် / ကုန်စိုင်",en:"shop / store",cat:"noun",
   ety:"'商'(ကုန်သည်) + '店'(ဆိုင်) = ကုန်သည်ဆိုင်",
   usage:"'小商店'(ဆိုင်သေး) '便利店'(ဆိုင်ငယ် ၂၄ နာရီ)",
   strokes:["商","店"],
   examples:[{cn:"我去商店买东西。",py:"Wǒ qù shāngdiàn mǎi dōngxi.",my:"ကျွန်တော်/မ ဆိုင်မှ ပစ္စည်းဝယ်သည်。",en:"I go to the shop to buy things."}]},

  {cn:"中国",py:"Zhōngguó",tone:1,my:"တရုတ်နိုင်ငံ",en:"China",cat:"noun",
   ety:"'中'(အလယ်ဗဟို) + '国'(နိုင်ငံ) = ကမ္ဘာ၏ဗဟိုနိုင်ငံ",
   usage:"'中国人'(တရုတ်လူမျိုး) '去中国'(တရုတ်သွား) '中国菜'(တရုတ်ဟင်း)",
   strokes:["中","国"],
   examples:[{cn:"我在中国学中文。",py:"Wǒ zài Zhōngguó xué zhōngwén.",my:"ကျွန်တော်/မ တရုတ်နိုင်ငံတွင် တရုတ်ဘာသာ သင်ယူသည်。",en:"I study Chinese in China."}]},

  {cn:"北京",py:"Běijīng",tone:3,my:"ဘေဂျင်း (မြို့တော်)",en:"Beijing (capital)",cat:"noun",
   ety:"'北'(မြောက်) + '京'(မြို့တော်) = မြောက်ဘက်မြို့တော်",
   usage:"တရုတ်၏မြို့တော်; '北京烤鸭'(ဘေဂျင်းဖြတ်ဖတ်ကြက်)",
   strokes:["北","京"],
   examples:[{cn:"北京是中国的首都。",py:"Běijīng shì Zhōngguó de shǒudū.",my:"ဘေဂျင်းသည် တရုတ်နိုင်ငံ၏ မြို့တော် ဖြစ်သည်。",en:"Beijing is China's capital."}]},

  // Adjectives
  {cn:"好",py:"hǎo",tone:3,my:"ကောင်းသည် / ကောင်းသော",en:"good / well",cat:"adjective",
   ety:"'မိန်းမ' + 'ကလေး' - မိဘနှင့်ကလေး = ချမ်းသာခြင်း/ကောင်းခြင်း",
   usage:"'你好'(ကျန်းမာပါ) '好吃'(အရမ်းကောင်း) '很好'(အရမ်းကောင်း) '好的'(ကောင်းပါ)",
   strokes:["好","好"],
   examples:[{cn:"你好！",py:"Nǐ hǎo!",my:"ကျန်းမာပါ！",en:"Hello!"},{cn:"这个很好。",py:"Zhège hěn hǎo.",my:"ဒါ အရမ်းကောင်းသည်。",en:"This is very good."}]},

  {cn:"大",py:"dà",tone:4,my:"ကြီးသည် / ကြီးမားသည်",en:"big / large",cat:"adjective",
   ety:"ခြေထောက်/လက်ဖျန်ဖြန့်နေသောပုဂ္ဂိုလ်ပုံ - ကြီးမားသောမိုကပ်",
   usage:"'大学'(တက္ကသိုလ်) '大家'(အားလုံး) '很大'(အရမ်းကြီး)",
   strokes:["大","大"],
   examples:[{cn:"这个苹果很大。",py:"Zhège píngguǒ hěn dà.",my:"ဤပန်းသီး အရမ်းကြီးသည်。",en:"This apple is very big."}]},

  {cn:"小",py:"xiǎo",tone:3,my:"သေးသည် / ငယ်သည်",en:"small / little",cat:"adjective",
   ety:"ကြားစ-ကြောင်းမှ ဆင်းသကြောင်းများ - ငယ်ရွယ်/သေးငယ်",
   usage:"'小学'(မူလတန်း) '小心'(သတိထား) '很小'(အရမ်းသေး)",
   strokes:["小","小"],
   examples:[{cn:"我的猫很小。",py:"Wǒ de māo hěn xiǎo.",my:"ကျွန်တော်/မ ၏ ကြောင်သည် အရမ်းသေး。",en:"My cat is very small."}]},

  {cn:"多",py:"duō",tone:1,my:"များသည် / များသော",en:"many / much / more",cat:"adjective",
   ety:"'ညနေ' + 'ညနေ' နှစ်ကြိမ် - ညနေ အထပ်ထပ်/များများ",
   usage:"'多少'(ဘယ်လောက်) '很多'(အများကြီး) '多吃点'(ပိုပိုစားပါ)",
   strokes:["多","多"],
   examples:[{cn:"今天有很多人。",py:"Jīntiān yǒu hěn duō rén.",my:"ယနေ့ လူ အများကြီး ရှိသည်。",en:"There are many people today."}]},

  {cn:"少",py:"shǎo",tone:3,my:"နည်းသည် / နည်းသော",en:"few / little / less",cat:"adjective",
   ety:"'小'(သေး)မှ ဆင်းသက်; ပမာဏနည်းသောဖော်ပြ",
   usage:"'多少'(ဘယ်လောက်) '少吃'(နည်းနည်းစား) '减少'(လျှော့ချ)",
   strokes:["少","少"],
   examples:[{cn:"今天人很少。",py:"Jīntiān rén hěn shǎo.",my:"ယနေ့ လူ နည်းသည်。",en:"There are few people today."}]},

  {cn:"冷",py:"lěng",tone:3,my:"အေးသည်",en:"cold",cat:"adjective",
   ety:"'ရေ' + 'အေးဆိုင်း' - ရေ/ဒြပ်ပစ္စည်းကို ဖြင့်ဆင်ပြ",
   usage:"'很冷'(အရမ်းအေး) '天气很冷'(ရာသီဥတုအေး) '怕冷'(အေးကြောက်)",
   strokes:["冷","冷"],
   examples:[{cn:"今天很冷。",py:"Jīntiān hěn lěng.",my:"ယနေ့ အရမ်းအေးသည်。",en:"It is very cold today."}]},

  {cn:"热",py:"rè",tone:4,my:"ပူသည်",en:"hot",cat:"adjective",
   ety:"'မီး' + 'ဖြတ်' - မီးသင်းအပူဖော်ပြ",
   usage:"'很热'(အရမ်းပူ) '热水'(ပူသောရေ) '热情'(ကြင်နာပေ့ပြော)",
   strokes:["热","热"],
   examples:[{cn:"夏天很热。",py:"Xiàtiān hěn rè.",my:"နွေရာသီ အရမ်းပူသည်。",en:"Summer is very hot."}]},

  {cn:"高兴",py:"gāoxìng",tone:1,my:"ဝမ်းသာသည် / ပျော်ရွှင်သည်",en:"happy / glad",cat:"adjective",
   ety:"'高'(မြင့်) + '兴'(ကြော) = စိတ်ဓာတ်မြင့်ကြောင်း",
   usage:"'很高兴认识你！'(ကျွန်တော်/မ သင့်ကိုတွေ့ရ ဝမ်းသာ！) '高兴地跳'(ဝမ်းသာ၍ ခုန်)",
   strokes:["高","兴"],
   examples:[{cn:"我很高兴。",py:"Wǒ hěn gāoxìng.",my:"ကျွန်တော်/မ ဝမ်းသာသည်。",en:"I am very happy."},{cn:"认识你，很高兴！",py:"Rènshi nǐ, hěn gāoxìng!",my:"သင့်ကို သိရ ဝမ်းသာပါသည်！",en:"Nice to meet you!"}]},

  {cn:"漂亮",py:"piàoliang",tone:4,my:"လှသည် / ချောမောသည်",en:"beautiful / pretty",cat:"adjective",
   ety:"'漂'(မျောသည်) + '亮'(တောက်ပ) - မျောတောက်ပသောအလှ",
   usage:"'很漂亮'(အရမ်းလှ) '漂亮的花'(လှသောပန်း) မိန်းမ/ကောင်မလေးကို မကြာမကြာ",
   strokes:["漂","亮"],
   examples:[{cn:"你的衣服很漂亮。",py:"Nǐ de yīfu hěn piàoliang.",my:"သင်၏ အဝတ်သည် အရမ်းလှသည်。",en:"Your clothes are very beautiful."}]},

  {cn:"忙",py:"máng",tone:2,my:"အလုပ်များသည်",en:"busy",cat:"adjective",
   ety:"'နှလုံး' + 'ဆုတ်ယုတ်' - နှလုံးပင်ပန်းနေသောအနေအထား",
   usage:"'很忙'(အရမ်းများ) '你忙吗？'(သင် အလုပ်များသလား？) '工作忙'(အလုပ်များ)",
   strokes:["忙","忙"],
   examples:[{cn:"我今天很忙。",py:"Wǒ jīntiān hěn máng.",my:"ကျွန်တော်/မ ယနေ့ အလုပ်အများကြီးရှိသည်。",en:"I am very busy today."}]},

  {cn:"累",py:"lèi",tone:4,my:"ပင်ပန်းသည် / အားငယ်သည်",en:"tired / exhausted",cat:"adjective",
   ety:"'ပင်ပန်း' ဟုသောဆင်ဆင်ရင်း; ဟိုးဆောင်ပုံမှ ဆင်းသက်",
   usage:"'很累'(အရမ်းပင်ပန်း) '我累了'(ပင်ပန်းနေပြီ) '累坏了'(လုံးဝပင်ပန်း)",
   strokes:["累","累"],
   examples:[{cn:"我今天很累。",py:"Wǒ jīntiān hěn lèi.",my:"ကျွန်တော်/မ ယနေ့ အရမ်းပင်ပန်းသည်。",en:"I am very tired today."}]},

  // Particles & Connectors
  {cn:"的",py:"de",tone:0,my:"၏ / (ပိုင်ဆိုင်မှုဖော်ပြ) / (နာမ်ဝိသေသနဖော်ပြ)",en:"possessive / adj particle",cat:"particle",
   ety:"'ကြေနပ်' + 'ကြောင်း' - တောက်ပသောအရာ; အဓိပ္ပာယ်ဖျော့",
   usage:"[ပိုင်ဆိုင်] 我的(ကျွန်တော်/မ၏) [နာမ်ဝိသေသန] 好的书(ကောင်းသောစာအုပ်)",
   strokes:["的","的"],
   examples:[{cn:"这是我的书。",py:"Zhè shì wǒ de shū.",my:"ဒါသည် ကျွန်တော်/မ ၏ စာအုပ် ဖြစ်သည်。",en:"This is my book."},{cn:"她的名字很好听。",py:"Tā de míngzì hěn hǎo tīng.",my:"သူမ၏ နာမည်သည် ကြားနာကောင်းသည်。",en:"Her name sounds beautiful."}]},

  {cn:"了",py:"le",tone:0,my:"ပြီး (ပြီးစီးချိန်ဖော်ပြ / ပြောင်းလဲမှု)",en:"completed action / change marker",cat:"particle",
   ety:"'ကလေး'ပုံ - ပြီးစီးသောအနေအထားဖော်ပြ",
   usage:"ကြိယာ + 了 = ပြီးစီးခဲ့သည်; '我吃了'(ကျွန်တော်/မ စားပြီ) '他来了'(သူလာပြီ)",
   strokes:["了","了"],
   examples:[{cn:"我吃饭了。",py:"Wǒ chī fàn le.",my:"ကျွန်တော်/မ ထမင်းစားပြီ。",en:"I've eaten."},{cn:"他走了。",py:"Tā zǒu le.",my:"သူ သွားပြီ。",en:"He has left."}]},

  {cn:"吗",py:"ma",tone:0,my:"လား (မေးခွန်းဝိဘတ်)",en:"question particle (yes/no)",cat:"particle",
   ety:"'နှုတ်' + 'မိခင်' - 'မမေး'မှ ဆင်းသကာ ရိုးရိုးမေးခွန်းသဖွင်း",
   usage:"ဝါကျအဆုံးတွင် ထည့်လိုက်ရုံနှင့် Yes/No မေးခွန်းဖြစ်သွား",
   strokes:["吗","吗"],
   examples:[{cn:"你好吗？",py:"Nǐ hǎo ma?",my:"သင် ကောင်းပါသလား？",en:"Are you well?"},{cn:"你是学生吗？",py:"Nǐ shì xuésheng ma?",my:"သင် ကျောင်းသား ဖြစ်သလား？",en:"Are you a student?"}]},

  {cn:"呢",py:"ne",tone:0,my:"ကောမျ / ရော (မေးတန်းဝိဘတ်)",en:"particle: 'what about~?'",cat:"particle",
   ety:"'နှုတ်' + 'ဖွဲ့' - ခဲကျနှုတ်ဆိပ်မှ မေးခွန်းတစ်ကြော",
   usage:"'你呢？'(သင်ကော？) ကနဦးထောင်ကြောင်းနှင့်ဆက်စပ်မေး",
   strokes:["呢","呢"],
   examples:[{cn:"我很好，你呢？",py:"Wǒ hěn hǎo, nǐ ne?",my:"ကျွန်တော်/မ ကောင်းပါသည်၊ သင်ကောမျ？",en:"I'm fine, and you?"},{cn:"他去哪里了呢？",py:"Tā qù nǎlǐ le ne?",my:"သူ ဘယ်မှာ သွားပြီလဲမသိ。",en:"Where did he go, I wonder?"}]},

  {cn:"不",py:"bù",tone:4,my:"မ (ငြင်းဆိုမှု)",en:"no / not",cat:"particle",
   ety:"ကောင်းကင် + မြေ - ကောင်ကင်နှင့်မြေကြားတွင် ပိတ်မြောက်",
   usage:"ကြိယာ/နာမ်ဝိသေသနမတိုင်မီ ထား; '不是'(မဟုတ်) '不好'(မကောင်း) '不去'(မသွား)",
   strokes:["不","不"],
   examples:[{cn:"我不是老师。",py:"Wǒ bú shì lǎoshī.",my:"ကျွန်တော်/မ ဆရာ/မ မဟုတ်ပါ。",en:"I am not a teacher."},{cn:"我不去。",py:"Wǒ bù qù.",my:"ကျွန်တော်/မ မသွားပါ。",en:"I won't go."}]},

  {cn:"没",py:"méi",tone:2,my:"မရှိ (ငြင်းပယ်ကြိယာ)",en:"not have / didn't (past)",cat:"particle",
   ety:"'ရေ' + 'ဒြပ်' - ရေမှ နစ်ဆင်းသွား/ပျောက်ကွယ်ခြင်း",
   usage:"'没有'(မရှိ/မပိုင်) '没去'(မသွားခဲ့) '没吃'(မစားခဲ့); 过去时를 ငြင်းမှ '不'မသုံးနှင့်",
   strokes:["没","没"],
   examples:[{cn:"我没有钱。",py:"Wǒ méiyǒu qián.",my:"ကျွန်တော်/မ ငွေမရှိ。",en:"I don't have money."},{cn:"他没来。",py:"Tā méi lái.",my:"သူ မလာခဲ့ဘူး。",en:"He didn't come."}]},

  {cn:"很",py:"hěn",tone:3,my:"အရမ်း / အလွန်",en:"very",cat:"particle",
   ety:"'ကိုင်ဖြတ်' + 'ပြောင်း' - 'ကြင်ကြင်' ဟုသောဟိုးရှေး; ယနေ့ 'very'",
   usage:"နာမ်ဝိသေသနနှင့် '很+adj': '很好'(အရမ်းကောင်း); '我很好'တွင် 'هن' မပါပဲ ထောက်ခံပုံ",
   strokes:["很","很"],
   examples:[{cn:"这个很贵。",py:"Zhège hěn guì.",my:"ဒါ အရမ်းစျေးကြီးသည်。",en:"This is very expensive."},{cn:"我很喜欢中文。",py:"Wǒ hěn xǐhuan zhōngwén.",my:"ကျွန်တော်/မ တရုတ်ဘာသာကို အရမ်းနှစ်သက်သည်。",en:"I like Chinese very much."}]},

  {cn:"也",py:"yě",tone:3,my:"လည်း (ပါ)",en:"also / too / as well",cat:"particle",
   ety:"'ပုဂ္ဂိုလ်' + 'ဖြန့်' - ကျယ်ကျယ်ဝန်းဝန်း/ပါဝင်",
   usage:"'我也是'(ကျွန်တော်/မ ပါ) '他也来了'(သူလည်း လာသည်) ကြိယာမတိုင်မီ ထား",
   strokes:["也","也"],
   examples:[{cn:"我也喜欢吃饺子。",py:"Wǒ yě xǐhuan chī jiǎozi.",my:"ကျွန်တော်/မ လည်း ဂျောဇာ စားချင်သည်。",en:"I also like eating dumplings."},{cn:"他也是学生。",py:"Tā yě shì xuésheng.",my:"သူ/သူမ လည်း ကျောင်းသားဖြစ်သည်。",en:"He/She is also a student."}]},

  {cn:"都",py:"dōu",tone:1,my:"အကုန်/အားလုံး (တူညီမှု)",en:"all / both / entirely",cat:"particle",
   ety:"'ဖြေ' + 'မြို့' - ကျယ်ပြန့်/ခြုံ",
   usage:"'我们都是'(ကျွန်တော်တို့ အားလုံးဖြစ်) ကြိယာမတိုင်မီ ထား",
   strokes:["都","都"],
   examples:[{cn:"我们都喜欢中文。",py:"Wǒmen dōu xǐhuan zhōngwén.",my:"ကျွန်တော်တို့ အကုန်လုံး တရုတ်ဘာသာကို နှစ်သက်သည်。",en:"We all like Chinese."},{cn:"都是我的书。",py:"Dōu shì wǒ de shū.",my:"အကုန်လုံး ကျွန်တော်/မ ၏ စာအုပ်များ ဖြစ်သည်。",en:"All of them are my books."}]},

  {cn:"和",py:"hé",tone:2,my:"နှင့် / ပြီးတော့ (ဆက်သွယ်)",en:"and / with",cat:"particle",
   ety:"'ပါဝင်' + 'ပြောဆို' - 'ညီညွတ်' ဟု; နှစ်ဦးပေါင်းစပ်",
   usage:"နာမ်+和+နာမ် 'ကော...ပါ'; ဝါကျများ ဆက်ရန် '然后' ကိုသုံး",
   strokes:["和","和"],
   examples:[{cn:"我和你一起去。",py:"Wǒ hé nǐ yīqǐ qù.",my:"ကျွန်တော်/မ သင်နှင့် အတူသွားမည်。",en:"I will go together with you."}]},

  {cn:"在",py:"zài",tone:4,my:"(နေရာ)တွင် ရှိသည် / (နေရာ)တွင် နေသည်",en:"at / in / to be located",cat:"particle",
   ety:"'ပင်' + 'မြေ' - ပင်တစ်ပင် မြေပေါ်တည်ရှိ",
   usage:"'在哪里？'(ဘယ်မှာ？) '我在北京'(ကျွန်တော်/မ ဘေဂျင်းမှာ ရှိ) ကြိယာမတိုင်မီ+位置",
   strokes:["在","在"],
   examples:[{cn:"书在桌子上。",py:"Shū zài zhuōzi shang.",my:"စာအုပ်သည် စားပွဲ ပေါ်တွင် ရှိသည်。",en:"The book is on the table."},{cn:"你在哪里？",py:"Nǐ zài nǎlǐ?",my:"သင် ဘယ်မှာ ရှိသနည်း？",en:"Where are you?"}]},

  {cn:"对",py:"duì",tone:4,my:"မှန်သည် / ဟုတ်ပါသည်",en:"correct / right / toward",cat:"adjective",
   ety:"'ပြောင်းမြောင်' + 'ရွာ' - မြောင်ကိုက်ကြ/မှန်",
   usage:"'对！'(မှန်သည်！) '对不起'(တောင်းပန်ပါသည်) '不对'(မမှန်)",
   strokes:["对","对"],
   examples:[{cn:"对！你说得对。",py:"Duì! Nǐ shuō de duì.",my:"မှန်ပါသည်！ သင် မှန်မှန်ကန်ကန် ပြောသည်。",en:"Correct! You're right."}]},

  // More verbs
  {cn:"知道",py:"zhīdào",tone:1,my:"သိသည်",en:"know",cat:"verb",
   ety:"'知'(သိ) + '道'(လမ်း/ကြောင်း) = 'အသိ+လမ်း'",
   usage:"'你知道吗？'(သင် သိပါသလား？) '我不知道'(ကျွန်တော်/မ မသိ)",
   strokes:["知","道"],
   examples:[{cn:"我不知道。",py:"Wǒ bù zhīdào.",my:"ကျွန်တော်/မ မသိပါ。",en:"I don't know."},{cn:"你知道他在哪里吗？",py:"Nǐ zhīdào tā zài nǎlǐ ma?",my:"သင် သူ ဘယ်မှာ ရှိသည်ကို သိပါသလား？",en:"Do you know where he is?"}]},

  {cn:"喜欢",py:"xǐhuan",tone:3,my:"နှစ်သက်သည် / ကြိုက်သည်",en:"like / enjoy",cat:"verb",
   ety:"'喜'(ဝမ်းသာ) + '欢'(ပျော်ရွှင်) = ဝမ်းသာပျော်ရွှင်မှု",
   usage:"'你喜欢什么？'(ဘာကိုနှစ်သက်သလဲ？) '喜欢+V'(V လုပ်ချင်)",
   strokes:["喜","欢"],
   examples:[{cn:"我喜欢中文。",py:"Wǒ xǐhuan zhōngwén.",my:"ကျွန်တော်/မ တရုတ်ဘာသာကို နှစ်သက်သည်。",en:"I like Chinese."},{cn:"你喜欢什么音乐？",py:"Nǐ xǐhuan shénme yīnyuè?",my:"သင် ဘာသီချင်း ကြိုက်သနည်း？",en:"What music do you like?"}]},

  {cn:"买",py:"mǎi",tone:3,my:"ဝယ်သည်",en:"buy",cat:"verb",
   ety:"'ကွန်ပင်' +'ပြောင်း' - ဈေးဝယ်ရာတွင် သုံးသောဆောင်ကြောင်း",
   usage:"'买东西'(ပစ္စည်းဝယ်) '买票'(လက်မှတ်ဝယ်) '我要买'(ကျွန်တော်/မ ဝယ်မည်)",
   strokes:["买","买"],
   examples:[{cn:"我想买这本书。",py:"Wǒ xiǎng mǎi zhè běn shū.",my:"ကျွန်တော်/မ ဤစာအုပ်ကို ဝယ်ချင်သည်。",en:"I want to buy this book."}]},

  {cn:"卖",py:"mài",tone:4,my:"ရောင်းသည်",en:"sell",cat:"verb",
   ety:"'买'ဆန့်ကျင်; '出'(ထွက်)+ဝယ်သောပုံ",
   usage:"'卖东西'(ပစ္စည်းရောင်း) '卖票'(လက်မှတ်ရောင်း)",
   strokes:["卖","卖"],
   examples:[{cn:"这里卖什么？",py:"Zhèlǐ mài shénme?",my:"ဒီမှာ ဘာ ရောင်းသနည်း？",en:"What do they sell here?"}]},

  {cn:"开",py:"kāi",tone:1,my:"ဖွင့်သည် / မောင်းသည်",en:"open / drive / start",cat:"verb",
   ety:"'တံခါး' + 'ကန်' - တံခါးဖွင့်ခြင်း",
   usage:"'开门'(တံခါးဖွင့်) '开车'(ကားမောင်း) '开始'(စတင်) '开心'(ပျော်)",
   strokes:["开","开"],
   examples:[{cn:"请开门。",py:"Qǐng kāi mén.",my:"ကျေးဇူးပြု၍ တံခါးဖွင့်ပါ。",en:"Please open the door."},{cn:"我会开车。",py:"Wǒ huì kāi chē.",my:"ကျွန်တော်/မ ကားမောင်းတတ်သည်。",en:"I can drive a car."}]},

  {cn:"回",py:"huí",tone:2,my:"ပြန်သည် / ပြန်လာသည်",en:"return / go back",cat:"verb",
   ety:"'ဝဲ' + 'ဝဲ' အတွင်း - တဖန်ပြန်လာ",
   usage:"'回家'(အိမ်ပြန်) '回来'(ပြန်လာ) '回去'(ပြန်သွား)",
   strokes:["回","回"],
   examples:[{cn:"我回家了。",py:"Wǒ huí jiā le.",my:"ကျွန်တော်/မ အိမ်ပြန်မည်/ပြန်ပြီ。",en:"I'm going home."},{cn:"他什么时候回来？",py:"Tā shénme shíhou huí lái?",my:"သူ ဘယ်အချိန် ပြန်လာမည်？",en:"When will he come back?"}]},

  {cn:"用",py:"yòng",tone:4,my:"အသုံးပြုသည် / သုံးသည်",en:"use",cat:"verb",
   ety:"'ကွင်း' + 'ကြောင်း' - ပတ်လည်ကာဝန်ဆောင်ပုံ",
   usage:"'用筷子'(တုတ်ဖျားသုံး) '有用'(သုံးဝင်သည်) '用汉语说'(တရုတ်ဘာသာနဲ့ပြော)",
   strokes:["用","用"],
   examples:[{cn:"请用中文说。",py:"Qǐng yòng zhōngwén shuō.",my:"ကျေးဇူးပြု၍ တရုတ်ဘာသာဖြင့် ပြောပါ。",en:"Please speak in Chinese."}]},

  {cn:"叫",py:"jiào",tone:4,my:"ဟစ်ကြောင်း / ခေါ်",en:"to be called / shout",cat:"verb",
   ety:"'ပုဂ္ဂိုလ်'+'ဆိပ်' - ဟစ်ကြောင်း/ခေါ်သည်",
   usage:"'我叫...'(ကျွန်တော်/မ ...ဟုခေါ်) မိတ်ဆက်ရာတွင်",
   strokes:["叫","叫"],
   examples:[{cn:"狗叫了。",py:"Gǒu jiào le.",my:"ခွေးဟောင်သည်。",en:"The dog barked."}]},

  // More nouns
  {cn:"中文",py:"zhōngwén",tone:1,my:"တရုတ်ဘာသာ (ဆက်သွယ်ရေး)",en:"Chinese language (communication)",cat:"noun",
   ety:"'中'(ကြားဗဟို/တရုတ်) + '文'(ဘာသာ/စာ)",
   usage:"'汉语'ပိုဆိုင်ရာဘာသာ; '学中文'(တရုတ်ဘာသာသင်)",
   strokes:["中","文"],
   examples:[{cn:"我学中文。",py:"Wǒ xué zhōngwén.",my:"ကျွန်တော်/မ တရုတ်ဘာသာ သင်ယူသည်。",en:"I study Chinese."}]},

  {cn:"汉语",py:"hànyǔ",tone:4,my:"တရုတ်ဘာသာ (နာမည်ပေး)",en:"Chinese language (formal)",cat:"noun",
   ety:"'汉'(ဟွန်လူမျိုး/တရုတ်) + '语'(ဘာသာစကား)",
   usage:"'普通话'(စံဘာသာ Mandarin) '汉语老师'(တရုတ်ဘာသာဆရာ/မ)",
   strokes:["汉","语"],
   examples:[{cn:"汉语很有趣。",py:"Hànyǔ hěn yǒuqù.",my:"တရုတ်ဘာသာသည် အရမ်းစိတ်ဝင်စားဖွယ်ကောင်းသည်。",en:"Chinese is very interesting."}]},

  {cn:"名字",py:"míngzì",tone:2,my:"နာမည်",en:"name",cat:"noun",
   ety:"'名'(ကျော်ကြားသော) + '字'(အက္ခရာ) = ကျော်ကြားသောသာမညပုံ",
   usage:"'你叫什么名字？'(သင့်နာမည် ဘာလဲ？) '我的名字是...'",
   strokes:["名","字"],
   examples:[{cn:"你叫什么名字？",py:"Nǐ jiào shénme míngzì?",my:"သင့်နာမည် ဘာလဲ？",en:"What is your name?"}]},

  {cn:"电话",py:"diànhuà",tone:4,my:"ဖုန်း (တယ်လီဖုန်း)",en:"telephone / phone call",cat:"noun",
   ety:"'电'(လျှပ်စစ်) + '话'(စကားပြော) = လျှပ်စစ်ဆက်သွယ်",
   usage:"'打电话'(ဖုန်းဆက်) '电话号码'(ဖုန်းနံပါတ်) '手机'(မိုဘိုင်းဖုန်း)",
   strokes:["电","话"],
   examples:[{cn:"我的电话号码是...",py:"Wǒ de diànhuà hàomǎ shì...",my:"ကျွန်တော်/မ ၏ ဖုန်းနံပါတ်မှာ ...ဖြစ်သည်。",en:"My phone number is..."}]},

  {cn:"苹果",py:"píngguǒ",tone:2,my:"ပန်းသီး",en:"apple",cat:"noun",
   ety:"'苹'(ပျံ) + '果'(သစ်သီး) - 'ပစ်ပျံ' ကော်ကောင်;ဆိုသောသစ်သီး",
   usage:"Apple ကုမ္ပဏီ '苹果公司'(Apple ကော်ပိုရေးရှင်း); '吃苹果'(ပန်းသီးစား)",
   strokes:["苹","果"],
   examples:[{cn:"我喜欢吃苹果。",py:"Wǒ xǐhuan chī píngguǒ.",my:"ကျွန်တော်/မ ပန်းသီးစားချင်သည်。",en:"I like eating apples."}]},

  {cn:"猫",py:"māo",tone:1,my:"ကြောင်",en:"cat",cat:"noun",
   ety:"'ဒြပ်ပိုင်' + 'ဒြပ်ညင်' - ကြောင်အသံ 'mao' ကိုတိုက်ရိုက်ဖော်ပြ",
   usage:"'小猫'(ကြောင်ကလေး) '猫咪'(ချစ်စဖွယ်ကြောင်) '大猫'(ကြောင်ကြီး)",
   strokes:["猫","猫"],
   examples:[{cn:"我有一只猫。",py:"Wǒ yǒu yī zhī māo.",my:"ကျွန်တော်/မ ကြောင် တစ်ကောင်ရှိသည်。",en:"I have a cat."}]},

  {cn:"狗",py:"gǒu",tone:3,my:"ခွေး",en:"dog",cat:"noun",
   ety:"'ဒြပ်ဆောင်'+'ပုဂ္ဂိုလ်' - ဆင်ဆင်ကိုင်/ဆက်ကြောင်ခွေးပုံ",
   usage:"'小狗'(ခွေးကလေး) '看门狗'(အိမ်ကာခွေး) '狗年'(ခွေးနှစ်)",
   strokes:["狗","狗"],
   examples:[{cn:"他有一条大狗。",py:"Tā yǒu yī tiáo dà gǒu.",my:"သူ/သူမ ခွေးကြီး တစ်ကောင်ရှိသည်。",en:"He/She has a big dog."}]},

  {cn:"鱼",py:"yú",tone:2,my:"ငါး",en:"fish",cat:"noun",
   ety:"ငါးတစ်ကောင်ပုံ - ငါးဦး၊ ကိုယ်ထည်၊ အမြီး",
   usage:"'吃鱼'(ငါးစား) '鱼'余'(ကျန်ကြွင်း)နှင့် အသံတူ - ကောင်းငြိမ်း",
   strokes:["鱼","鱼"],
   examples:[{cn:"我喜欢吃鱼。",py:"Wǒ xǐhuan chī yú.",my:"ကျွန်တော်/မ ငါးစားချင်သည်。",en:"I like to eat fish."}]},

  {cn:"鸟",py:"niǎo",tone:3,my:"ငှက်",en:"bird",cat:"noun",
   ety:"ငှက်ကိုဖော်ပြသောပုံ - ကိုယ်ထည်၊ မောင်း၊ ခြေ",
   usage:"'一只鸟'(ငှက်တစ်ကောင်) '小鸟'(ငှက်ကလေး)",
   strokes:["鸟","鸟"],
   examples:[{cn:"树上有很多鸟。",py:"Shù shang yǒu hěn duō niǎo.",my:"ပင်ပေါ်တွင် ငှက် များများ ရှိသည်。",en:"There are many birds in the tree."}]},

  // More vocab
  {cn:"儿子",py:"érzi",tone:2,my:"သား (ကောင်မောင်)",en:"son",cat:"noun",
   ety:"'儿'(ကလေး) + '子'(ကောင်ကလေး/ဆောင်ဝိဘတ်)",
   usage:"'我的儿子'(ကျွန်တော်/မ ၏ သား)",
   strokes:["儿","子"],
   examples:[{cn:"他的儿子很聪明。",py:"Tā de érzi hěn cōngming.",my:"သူ/သူမ ၏ သားသည် ထက်မြက်သည်。",en:"His/Her son is very smart."}]},

  {cn:"女儿",py:"nǚ'ér",tone:3,my:"သမီး",en:"daughter",cat:"noun",
   ety:"'女'(မ) + '儿'(ကလေး) = မကလေး",
   usage:"'我的女儿'(ကျွန်တော်/မ ၏ သမီး)",
   strokes:["女","儿"],
   examples:[{cn:"她有一个女儿。",py:"Tā yǒu yī gè nǚ'ér.",my:"သူမတွင် သမီး တစ်ဦးရှိသည်。",en:"She has one daughter."}]},

  {cn:"号",py:"hào",tone:4,my:"နံပါတ် / ရက်",en:"number / date",cat:"noun",
   ety:"'ပြော' + 'ဆောင်' - ကြေငြာပြောဆိုသောစာ",
   usage:"'几号？'(ဘယ်ရက်？ / ဘယ်နံပါတ်？) '手机号'(ဖုန်းနံပါတ်) '十号'(၁၀ ရက်)",
   strokes:["号","号"],
   examples:[{cn:"今天几号？",py:"Jīntiān jǐ hào?",my:"ယနေ့ ဘယ်ရက်လဲ？",en:"What date is today?"}]},

  {cn:"点",py:"diǎn",tone:3,my:"နာရီ (ကိန်းဂဏန်း+点)",en:"o'clock (time measure)",cat:"noun",
   ety:"'မီး' + 'ဖော်ကြားမှတ်' - မီးလင်းတောက်ပ/မှတ်သားနေရာ",
   usage:"'几点？'(ဘယ်နှစ်နာရီ？) '三点'(သုံးနာရီ) '一点儿'(နည်းနည်း)",
   strokes:["点","点"],
   examples:[{cn:"现在几点？",py:"Xiànzài jǐ diǎn?",my:"ယခု ဘယ်နှစ်နာရီ？",en:"What time is it now?"},{cn:"我们三点见。",py:"Wǒmen sān diǎn jiàn.",my:"ကျွန်တော်တို့ ၃ နာရီတွင် တွေ့မည်。",en:"Let's meet at 3 o'clock."}]},

  {cn:"块",py:"kuài",tone:4,my:"ယွမ် (တရုတ်ငွေကြေး)",en:"yuan (Chinese currency)",cat:"noun",
   ety:"'ဒြပ်' + 'ကိုင်' - 'ဒြပ်ခွဲကလပ်' ဟုဆိုသောနာမ်",
   usage:"'一块钱'(တစ်ယွမ်) '多少块？'(ဘယ်နှနာရေနာ ယွမ်？) '块'=ဝမ်/ယွမ်",
   strokes:["块","块"],
   examples:[{cn:"这本书五块钱。",py:"Zhè běn shū wǔ kuài qián.",my:"ဤစာအုပ်သည် ငါးယွမ်ကျသည်。",en:"This book costs 5 yuan."}]},

  {cn:"本",py:"běn",tone:3,my:"(quan ci) - စာအုပ်/စမ်းသပ်",en:"volume (for books/notebooks)",cat:"particle",
   ety:"'ပင်' + 'မြစ်' ဟုသောဝိသေသနများ - မြစ်/ဇာစ်မြစ်",
   usage:"'一本书'(စာတစ်အုပ်) '一本日记'(မှတ်စုတစ်အုပ်)量词ဖြစ်",
   strokes:["本","本"],
   examples:[{cn:"一本书，两本书。",py:"Yī běn shū, liǎng běn shū.",my:"စာအုပ် တစ်အုပ်၊ နှစ်အုပ်。",en:"One book, two books."}]},

  {cn:"个",py:"gè",tone:4,my:"(quan ci) - ပုဂ္ဂိုလ်/ပစ္စည်းအတွက်",en:"general measure word",cat:"particle",
   ety:"'ပုဂ္ဂိုလ်' + 'ပြော' - 'တစ်ဦး/တစ်ခု' ကို ကိုယ်စားပြု",
   usage:"အသုံးအများဆုံး量词; '一个人'(တစ်ဦး) '一个苹果'(ပန်းသီးတစ်လုံး)",
   strokes:["个","个"],
   examples:[{cn:"三个学生。",py:"Sān gè xuésheng.",my:"ကျောင်းသား သုံးဦး。",en:"Three students."},{cn:"一个苹果。",py:"Yī gè píngguǒ.",my:"ပန်းသီး တစ်လုံး。",en:"One apple."}]},

  {cn:"两",py:"liǎng",tone:3,my:"နှစ် (ပမာဏ量词နှင့်)",en:"two (with measure word)",cat:"number",
   ety:"'二'နှင့် ကွဲပြားသည်; 量词မတိုင်မီ '两'ကိုသုံး",
   usage:"'两个人'(လူနှစ်ဦး) '两本书'(စာနှစ်အုပ်) - 量词ရှေ့တွင်",
   strokes:["两","两"],
   examples:[{cn:"我有两个朋友。",py:"Wǒ yǒu liǎng gè péngyou.",my:"ကျွန်တော်/မ သူငယ်ချင်း နှစ်ဦးရှိသည်。",en:"I have two friends."}]},

  {cn:"下",py:"xià",tone:4,my:"အောက် / ကျ",en:"below / next / fall",cat:"noun",
   ety:"'ကြောင်း' + 'မှတ်' - မှတ်တမ်းကြောင်းအောက်",
   usage:"'下面'(အောက်ဘက်) '下课'(သင်တန်းဆင်း) '下雨'(မိုးရွာ) '下午'(ညနေ)",
   strokes:["下","下"],
   examples:[{cn:"书在桌子下面。",py:"Shū zài zhuōzi xiàmiàn.",my:"စာအုပ်သည် စားပွဲ အောက်တွင် ရှိသည်。",en:"The book is under the table."}]},

  {cn:"上",py:"shàng",tone:4,my:"အပေါ် / တက်",en:"above / top / go up",cat:"noun",
   ety:"'ကြောင်း' + 'မှတ်' - မှတ်တမ်းကြောင်းအပေါ်",
   usage:"'上面'(အပေါ်ဘက်) '上课'(သင်တန်းတက်) '上午'(မနက်ပိုင်း) '上学'(ကျောင်းတက်)",
   strokes:["上","上"],
   examples:[{cn:"书在桌子上。",py:"Shū zài zhuōzi shang.",my:"စာအုပ်သည် စားပွဲ ပေါ်တွင် ရှိသည်。",en:"The book is on the table."}]},

  {cn:"里",py:"lǐ",tone:3,my:"အတွင်း / ထဲတွင်",en:"inside / within",cat:"noun",
   ety:"'ကျောင်းပြောင်း' + 'မြေ' - ကျောင်းဝင်းတွင်း",
   usage:"'家里'(အိမ်ထဲ) '学校里'(ကျောင်းထဲ) '这里'(ဒီမှာ)",
   strokes:["里","里"],
   examples:[{cn:"包里有什么？",py:"Bāo lǐ yǒu shénme?",my:"အိတ်ထဲ ဘာရှိသနည်း？",en:"What's in the bag?"}]},

  {cn:"前",py:"qián",tone:2,my:"ရှေ့ / မတိုင်မီ",en:"front / before",cat:"noun",
   ety:"'ဆင်' + 'ဓား' - ရှေ့ဆုပ်ကိုင်",
   usage:"'前面'(ရှေ့ဘက်) '以前'(ယခင်ကာလ) '前天'(တမန်တနေ့က)",
   strokes:["前","前"],
   examples:[{cn:"学校前面有商店。",py:"Xuéxiào qiánmiàn yǒu shāngdiàn.",my:"ကျောင်းရှေ့ဘက်တွင် ဆိုင်ရှိသည်。",en:"There is a shop in front of the school."}]},

  {cn:"后",py:"hòu",tone:4,my:"နောက် / နောက်ပိုင်း",en:"behind / after",cat:"noun",
   ety:"'ရေ' + 'ကြောင်း' + 'ဗိုင်း' - နောက်သည်/နောက်ကျ",
   usage:"'后面'(နောက်ဘက်) '以后'(နောက်ပိုင်း) '后天'(မဟာမနက်ဖြန်)",
   strokes:["后","后"],
   examples:[{cn:"学校后面是公园。",py:"Xuéxiào hòumiàn shì gōngyuán.",my:"ကျောင်းနောက်ဘက်တွင် ပန်းခြံရှိသည်。",en:"Behind the school is a park."}]},

  {cn:"旁边",py:"pángbiān",tone:2,my:"ဘေး / ဘေးနား",en:"beside / next to",cat:"noun",
   ety:"'旁'(ဘေး) + '边'(ဘက်/ကမ်း) = ဘေးနား",
   usage:"'在...旁边'(... ဘေးတွင်) '学校旁边'(ကျောင်းဘေး)",
   strokes:["旁","边"],
   examples:[{cn:"银行在邮局旁边。",py:"Yínháng zài yóujú pángbiān.",my:"ဘဏ်သည် စာတိုက်ဘေး တွင်ရှိသည်。",en:"The bank is next to the post office."}]},

  {cn:"这",py:"zhè",tone:4,my:"ဒီ / ဤ (ဤပစ္စည်း)",en:"this",cat:"pronoun",
   ety:"'ဝေ' + 'ပြော' - ကြောင်းဆိုင်ရာ ဦးစားပေးသောပုံ",
   usage:"'这是'(ဒါဖြစ်) '这个'(ဒီတစ်ခု) '这里'(ဒီမှာ) '这些'(ဒီတွေ)",
   strokes:["这","这"],
   examples:[{cn:"这是什么？",py:"Zhè shì shénme?",my:"ဒါ ဘာလဲ？",en:"What is this?"},{cn:"这个多少钱？",py:"Zhège duōshao qián?",my:"ဒါ ဘယ်လောက်ကျသနည်း？",en:"How much is this?"}]},

  {cn:"那",py:"nà",tone:4,my:"ဟိုဒီ / ထို (ထိုပစ္စည်း)",en:"that",cat:"pronoun",
   ety:"'ဖြတ်' + 'ပေ' - ဝေးသောနေရာ ညွှန်ပြ",
   usage:"'那是'(ဟိုဒါဖြစ်) '那个'(ဟိုတစ်ခု) '那里'(ဟိုမှာ) '那些'(ဟိုတွေ)",
   strokes:["那","那"],
   examples:[{cn:"那是什么？",py:"Nà shì shénme?",my:"ဟိုဒါ ဘာလဲ？",en:"What is that?"},{cn:"那里有一家店。",py:"Nàlǐ yǒu yī jiā diàn.",my:"ဟိုမှာ ဆိုင်တစ်ဆိုင် ရှိသည်。",en:"There is a shop over there."}]},

  // Additional HSK1 words
  {cn:"同学",py:"tóngxué",tone:2,my:"အတန်းဖော် / ကျောင်းဖော်",en:"classmate",cat:"noun",
   ety:"'同'(အတူ) + '学'(သင်ယူ) = အတူသင်ယူသူ",
   usage:"'我的同学'(ကျွန်တော်/မ ၏ အတန်းဖော်) '同学们'(အတန်းဖော်များ)",
   strokes:["同","学"],
   examples:[{cn:"他是我的同学。",py:"Tā shì wǒ de tóngxué.",my:"သူ ကျွန်တော်/မ ၏ အတန်းဖော် ဖြစ်သည်。",en:"He is my classmate."}]},

  {cn:"宾馆",py:"bīnguǎn",tone:1,my:"ဟိုတယ် / တည်းခိုခန်း",en:"hotel / guesthouse",cat:"noun",
   ety:"'宾'(ပါဝင်) + '馆'(ခန်းမ) = ဧည့်ခံသောအဆောက်အဦ",
   usage:"'住宾馆'(ဟိုတယ်တည်း) '宾馆在哪里？'(ဟိုတယ် ဘယ်မှာ？)",
   strokes:["宾","馆"],
   examples:[{cn:"我住在宾馆里。",py:"Wǒ zhù zài bīnguǎn lǐ.",my:"ကျွန်တော်/မ ဟိုတယ်တွင် တည်းထားသည်。",en:"I am staying at a hotel."}]},

  {cn:"火车站",py:"huǒchēzhàn",tone:3,my:"ရထားဘူတာ",en:"train station",cat:"noun",
   ety:"'火车'(မီးရထား) + '站'(ဘူတာ/ရပ်ကြ) = ရထားဘူတာ",
   usage:"'去火车站'(ရထားဘူတာသွား) '火车站在哪里？'",
   strokes:["火","车","站"],
   examples:[{cn:"火车站怎么走？",py:"Huǒchēzhàn zěnme zǒu?",my:"ရထားဘူတာကို ဘယ်လိုသွားမည်？",en:"How do I get to the train station?"}]},

  {cn:"机场",py:"jīchǎng",tone:1,my:"လေဆိပ်",en:"airport",cat:"noun",
   ety:"'机'(လေယာဉ်/စက်) + '场'(မြင်ကွင်း) = လေယာဉ်မြင်ကွင်း",
   usage:"'去机场'(လေဆိပ်သွား) '在机场'(လေဆိပ်တွင်)",
   strokes:["机","场"],
   examples:[{cn:"我去机场接人。",py:"Wǒ qù jīchǎng jiē rén.",my:"ကျွန်တော်/မ လေဆိပ်မှ လူကြိုမည်。",en:"I go to the airport to pick someone up."}]},

  {cn:"出租车",py:"chūzūchē",tone:1,my:"တက္ကစီ",en:"taxi",cat:"noun",
   ety:"'出租'(ငှားရမ်း) + '车'(ကား) = ငှားရမ်းကား",
   usage:"'坐出租车'(တက္ကစီ စီးသည်) '打出租车'(တက္ကစီ ရပ်တားသည်)",
   strokes:["出","租","车"],
   examples:[{cn:"我坐出租车去机场。",py:"Wǒ zuò chūzūchē qù jīchǎng.",my:"ကျွန်တော်/မ တက္ကစီ စီး၍ လေဆိပ်သွားမည်。",en:"I take a taxi to the airport."}]},

  {cn:"公共汽车",py:"gōnggòng qìchē",tone:1,my:"ဘတ်စ်ကား",en:"bus",cat:"noun",
   ety:"'公共'(အများ) + '汽车'(မော်တော်ကား) = အများပိုင်ကား",
   usage:"'坐公共汽车'(ဘတ်စ်ကားစီး) '公交车'(ဘတ်စ်ကား အတိုကောက်)",
   strokes:["公","共","汽","车"],
   examples:[{cn:"坐公共汽车很便宜。",py:"Zuò gōnggòng qìchē hěn piányí.",my:"ဘတ်စ်ကားစီးသည် အရမ်းဈေးသက်သာသည်。",en:"Taking the bus is very cheap."}]},

  {cn:"天气",py:"tiānqì",tone:1,my:"ရာသီဥတု",en:"weather",cat:"noun",
   ety:"'天'(ကောင်းကင်) + '气'(လေ/ဓာတ်) = ကောင်းကင်တွင် လေကြောင်း",
   usage:"'天气怎么样？'(ရာသီဥတု ဘယ်လိုလဲ？) '好天气'(ကောင်းသောရာသီဥတု)",
   strokes:["天","气"],
   examples:[{cn:"今天天气怎么样？",py:"Jīntiān tiānqì zěnme yàng?",my:"ယနေ့ ရာသီဥတု ဘယ်လိုလဲ？",en:"How is the weather today?"}]},

  {cn:"下雨",py:"xià yǔ",tone:4,my:"မိုးရွာသည်",en:"rain",cat:"verb",
   ety:"'下'(ကျ) + '雨'(မိုး) = မိုးရွာကျ",
   usage:"'下雨了'(မိုးရွာပြီ) '会下雨吗？'(မိုးရွာမည်လား？)",
   strokes:["下","雨"],
   examples:[{cn:"今天下雨了。",py:"Jīntiān xià yǔ le.",my:"ယနေ့ မိုးရွာသည်。",en:"It is raining today."}]},

  {cn:"睡觉",py:"shuì jiào",tone:4,my:"အိပ်သည်",en:"sleep / go to sleep",cat:"verb",
   ety:"'睡'(အိပ်) + '觉'(သိ/ကြေ) = အိပ်မိနေသည်",
   usage:"'睡觉了'(အိပ်ပြီ) '几点睡觉？'(ဘယ်နှစ်နာရီ အိပ်မည်？)",
   strokes:["睡","觉"],
   examples:[{cn:"我晚上十点睡觉。",py:"Wǒ wǎnshang shí diǎn shuì jiào.",my:"ကျွန်တော်/မ ည ၁၀ နာရီတွင် အိပ်သည်。",en:"I go to sleep at 10 PM."}]},

  {cn:"起床",py:"qǐ chuáng",tone:3,my:"နိုးသည် / ထသည်",en:"get up / wake up",cat:"verb",
   ety:"'起'(ထ/တက်) + '床'(ကုတင်) = ကုတင်မှ ထ",
   usage:"'几点起床？'(ဘယ်နှစ်နာရီ နိုးသနည်း？)",
   strokes:["起","床"],
   examples:[{cn:"我六点起床。",py:"Wǒ liù diǎn qǐ chuáng.",my:"ကျွန်တော်/မ ၆ နာရီတွင် နိုးသည်。",en:"I wake up at 6 o'clock."}]},

  {cn:"跑步",py:"pǎo bù",tone:3,my:"ပြေးသည် / ပြေးလေ့ကျင့်",en:"run / jogging",cat:"verb",
   ety:"'跑'(ပြေး) + '步'(ခြေလှမ်း) = ပြေးလှမ်းခြင်း",
   usage:"'跑步机'(ကြမ်းပေါ်ပြေးစက်) '去跑步'(ပြေးလေ့ကျင့်သွား)",
   strokes:["跑","步"],
   examples:[{cn:"我每天跑步。",py:"Wǒ měitiān pǎo bù.",my:"ကျွန်တော်/မ နေ့တိုင်း ပြေးလေ့ကျင့်သည်。",en:"I jog every day."}]},

  {cn:"打篮球",py:"dǎ lánqiú",tone:3,my:"ခြင်းဝိုင်းကန်သည်",en:"play basketball",cat:"verb",
   ety:"'打'(ကန်/ဆော့) + '篮球'(ကောင်းကွင်း) = ကောင်းကွင်းဆော့",
   usage:"'喜欢打篮球'(ခြင်းဝိုင်းဆော့ချင်) '一起打篮球'(အတူ ဆော့)",
   strokes:["打","篮","球"],
   examples:[{cn:"你喜欢打篮球吗？",py:"Nǐ xǐhuan dǎ lánqiú ma?",my:"သင် ခြင်းဝိုင်းဆော့ချင်သလား？",en:"Do you like playing basketball?"}]},

  {cn:"踢足球",py:"tī zúqiú",tone:1,my:"ဘောလုံးကန်သည်",en:"play football/soccer",cat:"verb",
   ety:"'踢'(ကန်) + '足球'(ဘောလုံး) = ဘောလုံးကန်ခြင်း",
   usage:"'喜欢踢足球'(ဘောလုံးကန်ချင်) '去踢足球'(ဘောလုံးကန်သွား)",
   strokes:["踢","足","球"],
   examples:[{cn:"他们踢足球。",py:"Tāmen tī zúqiú.",my:"သူတို့ ဘောလုံးကန်သည်。",en:"They play football."}]},

  {cn:"音乐",py:"yīnyuè",tone:1,my:"သီချင်း / ဂီတ",en:"music",cat:"noun",
   ety:"'音'(အသံ) + '乐'(ပျော်ရွှင်/ဂီတ) = ပျော်ရွှင်သောအသံ",
   usage:"'听音乐'(သီချင်းနားထောင်) '喜欢音乐'(ဂီတနှစ်သက်) '音乐家'(ဂီတပညာရှင်)",
   strokes:["音","乐"],
   examples:[{cn:"我喜欢听音乐。",py:"Wǒ xǐhuan tīng yīnyuè.",my:"ကျွန်တော်/မ သီချင်းနားထောင်ချင်သည်。",en:"I like listening to music."}]},

  {cn:"电影",py:"diànyǐng",tone:4,my:"ရုပ်ရှင် / ဇာတ်ကား",en:"movie / film",cat:"noun",
   ety:"'电'(လျှပ်စစ်) + '影'(ရိပ်/ပုံ) = လျှပ်စစ်ရိပ်ပုံ",
   usage:"'看电影'(ရုပ်ရှင်ကြည့်) '电影院'(ရုပ်ရှင်ရုံ) '好看的电影'(ကောင်းသောဇာတ်ကား)",
   strokes:["电","影"],
   examples:[{cn:"我们去看电影吧。",py:"Wǒmen qù kàn diànyǐng ba.",my:"ကျွန်တော်တို့ ရုပ်ရှင်ကြည့်ကြစို့。",en:"Let's go watch a movie."}]},

  {cn:"水果",py:"shuǐguǒ",tone:3,my:"သစ်သီးများ",en:"fruit",cat:"noun",
   ety:"'水'(ရေ) + '果'(သစ်သီး) = ရေသောက်သစ်သီး",
   usage:"'吃水果'(သစ်သီးစား) '买水果'(သစ်သီးဝယ်)",
   strokes:["水","果"],
   examples:[{cn:"我每天吃水果。",py:"Wǒ měitiān chī shuǐguǒ.",my:"ကျွန်တော်/မ နေ့တိုင်း သစ်သီး စားသည်。",en:"I eat fruit every day."}]},

  {cn:"米饭",py:"mǐfàn",tone:3,my:"ဆန်ပေါင်းထမင်း",en:"cooked rice",cat:"noun",
   ety:"'米'(ဆန်) + '饭'(ထမင်း) = ဆန်ပေါင်းထမင်း",
   usage:"'吃米饭'(ထမင်းစား) '一碗米饭'(ထမင်းတစ်ပန်း)",
   strokes:["米","饭"],
   examples:[{cn:"我爱吃米饭。",py:"Wǒ ài chī mǐfàn.",my:"ကျွန်တော်/မ ဆန်ပေါင်းထမင်း စားချင်သည်。",en:"I love eating rice."}]},

  {cn:"面条",py:"miàntiáo",tone:4,my:"မြောက်ကြော",en:"noodles",cat:"noun",
   ety:"'面'(မျက်နှာ/ဂျုံမှုန့်) + '条'(ကြောင်းဆန်) = ဂျုံမှုန့်ကြောင်း",
   usage:"'吃面条'(မြောက်ကြောစား) '一碗面条'(မြောက်ကြောတစ်ပန်း)",
   strokes:["面","条"],
   examples:[{cn:"我喜欢吃面条。",py:"Wǒ xǐhuan chī miàntiáo.",my:"ကျွန်တော်/မ မြောက်ကြော စားချင်သည်。",en:"I like eating noodles."}]},

  {cn:"鸡蛋",py:"jīdàn",tone:1,my:"ကြက်ဥ",en:"egg",cat:"noun",
   ety:"'鸡'(ကြက်) + '蛋'(ဥ) = ကြက်ဥ",
   usage:"'鸡蛋炒饭'(ကြက်ဥထမင်းကြော) '炒鸡蛋'(ကြက်ဥကြော)",
   strokes:["鸡","蛋"],
   examples:[{cn:"我早上吃鸡蛋。",py:"Wǒ zǎoshang chī jīdàn.",my:"ကျွန်တော်/မ မနက်တွင် ကြက်ဥစားသည်。",en:"I eat eggs in the morning."}]},

  {cn:"牛奶",py:"niúnǎi",tone:2,my:"နွားနို့",en:"milk",cat:"noun",
   ety:"'牛'(နွား) + '奶'(နို့) = နွားနို့",
   usage:"'喝牛奶'(နွားနို့သောက်) '牛奶咖啡'(နို့ကော်ဖီ)",
   strokes:["牛","奶"],
   examples:[{cn:"我每天喝牛奶。",py:"Wǒ měitiān hē niúnǎi.",my:"ကျွန်တော်/မ နေ့တိုင်း နွားနို့သောက်သည်。",en:"I drink milk every day."}]},

  {cn:"咖啡",py:"kāfēi",tone:1,my:"ကော်ဖီ",en:"coffee",cat:"noun",
   ety:"'咖'+'啡' = တိုက်ရိုက်ဘာသာပြန် 'coffee' မှ",
   usage:"'喝咖啡'(ကော်ဖီသောက်) '一杯咖啡'(ကော်ဖီတစ်ခွက်)",
   strokes:["咖","啡"],
   examples:[{cn:"你喝咖啡吗？",py:"Nǐ hē kāfēi ma?",my:"သင် ကော်ဖီသောက်သလား？",en:"Do you drink coffee?"}]},

  {cn:"杯子",py:"bēizi",tone:1,my:"ခွက် (ဖန်ခွက်/တောင်းခွက်)",en:"cup / glass",cat:"noun",
   ety:"'杯'(ခွက်) + '子'(ပစ္စည်းဆောင်ဝိဘတ်) = ခွက်",
   usage:"'一个杯子'(ခွက်တစ်လုံး) '杯子里有水'(ခွက်ထဲ ရေရှိ)",
   strokes:["杯","子"],
   examples:[{cn:"请给我一个杯子。",py:"Qǐng gěi wǒ yī gè bēizi.",my:"ကျေးဇူးပြု၍ ကျွန်တော်/မကို ခွက်တစ်လုံး ပေးပါ。",en:"Please give me a cup."}]},

  {cn:"桌子",py:"zhuōzi",tone:1,my:"စားပွဲ / ဝိုင်းစား",en:"table / desk",cat:"noun",
   ety:"'桌'(ပြားချပ်/ရှောင်) + '子'(ဆောင်ဝိဘတ်) = ပြားချပ်ပစ္စည်း",
   usage:"'桌子上'(စားပွဲ ပေါ်တွင်) '书桌'(ရေးမှတ်ဝိုင်းစား)",
   strokes:["桌","子"],
   examples:[{cn:"书在桌子上。",py:"Shū zài zhuōzi shang.",my:"စာအုပ်သည် စားပွဲပေါ်တွင် ရှိသည်。",en:"The book is on the table."}]},

  {cn:"椅子",py:"yǐzi",tone:3,my:"ကုလားထိုင်",en:"chair",cat:"noun",
   ety:"'椅'(ထိုင်ခုံ/ပင်ပင်) + '子'(ဆောင်ဝိဘတ်) = ထိုင်ခုံ",
   usage:"'坐在椅子上'(ကုလားထိုင်ပေါ်ထိုင်) '一把椅子'(ကုလားထိုင်တစ်ခု)",
   strokes:["椅","子"],
   examples:[{cn:"请坐这把椅子。",py:"Qǐng zuò zhè bǎ yǐzi.",my:"ကျေးဇူးပြု၍ ဤကုလားထိုင်တွင် ထိုင်ပါ。",en:"Please sit in this chair."}]},

  {cn:"钟",py:"zhōng",tone:1,my:"နာရီ (နံရံနာရီ/ဝိုင်းနာရီ)",en:"clock / bell",cat:"noun",
   ety:"'ကြေး' + 'ကလောင်' - ကြေးဝပ်ကလောင်/နာရီ",
   usage:"'一点钟'(တစ်နာရီ) '分钟'(မိနစ်) '闹钟'(နှိုးစက်)",
   strokes:["钟","钟"],
   examples:[{cn:"墙上有一个钟。",py:"Qiáng shang yǒu yī gè zhōng.",my:"နံရံပေါ်တွင် နာရီတစ်လုံး ရှိသည်。",en:"There is a clock on the wall."}]},

  {cn:"地方",py:"dìfang",tone:4,my:"နေရာ / တည်နေရာ",en:"place / location",cat:"noun",
   ety:"'地'(မြေ) + '方'(နေရာ/ဦးတည်ချက်) = မြေပေါ်နေရာ",
   usage:"'这个地方'(ဤနေရာ) '好地方'(ကောင်းသောနေရာ)",
   strokes:["地","方"],
   examples:[{cn:"这是一个好地方。",py:"Zhè shì yī gè hǎo dìfang.",my:"ဒါ ကောင်းသောနေရာ ဖြစ်သည်。",en:"This is a good place."}]},

  {cn:"问题",py:"wèntí",tone:4,my:"မေးခွန်း / ပြဿနာ",en:"question / problem",cat:"noun",
   ety:"'问'(မေး) + '题'(ခေါင်းစဉ်/ပြဿနာ) = မေးမြန်းမှုနှင့် ပြဿနာ",
   usage:"'有问题吗？'(မေးချင်တာ ရှိသလား？) '没有问题'(ပြဿနာမရှိ/ရပါသည်)",
   strokes:["问","题"],
   examples:[{cn:"我有一个问题。",py:"Wǒ yǒu yī gè wèntí.",my:"ကျွန်တော်/မ မေးချင်တာ တစ်ခု ရှိသည်。",en:"I have a question."},{cn:"没有问题！",py:"Méiyǒu wèntí!",my:"ပြဿနာ မရှိပါ！",en:"No problem!"}]},

  {cn:"谢谢",py:"xièxiè",tone:4,my:"ကျေးဇူးတင်ပါသည်",en:"thank you",cat:"verb",
   ety:"'谢'(ကျေးဇူးတင်) နှစ်ကြိမ် - ချစ်ခင်လေးစားသောကျေးဇူးဖော်ပြ",
   usage:"'谢谢你！'(ကျေးဇူးတင်ပါသည်！) '不客气'(မဖြစ်ပါ/ကျေးဇူးမတင်ပါနှင့်)",
   strokes:["谢","谢"],
   examples:[{cn:"谢谢你！",py:"Xièxiè nǐ!",my:"သင့်ကို ကျေးဇူးတင်ပါသည်！",en:"Thank you!"},{cn:"谢谢老师！",py:"Xièxiè lǎoshī!",my:"ဆရာ/မ ကျေးဇူးတင်ပါသည်！",en:"Thank you, teacher!"}]},

  {cn:"对不起",py:"duìbuqǐ",tone:4,my:"တောင်းပန်ပါသည် / ဆောရီ",en:"sorry / I apologize",cat:"verb",
   ety:"'对不起'= 'မမျှတ/မနိုင်' ဟုဆိုသော ဖော်ပြ - 'ညောင်ပင်မဖြစ်'",
   usage:"'对不起！'(ဆောရီ！) '没关系'(ပြဿနာမရှိ/ဝေဝေဝါဝါ)",
   strokes:["对","不","起"],
   examples:[{cn:"对不起，我来晚了。",py:"Duìbuqǐ, wǒ lái wǎn le.",my:"တောင်းပန်ပါသည်၊ ကျွန်တော်/မ နောက်ကျပြီ。",en:"Sorry, I came late."}]},

  {cn:"没关系",py:"méiguānxi",tone:2,my:"ပြဿနာမရှိပါ / ဝေဝေဝါဝါ",en:"never mind / it's OK",cat:"verb",
   ety:"'没'(မ) + '关系'(ဆက်နွှယ်/ပြဿနာ) = မဆိုင်/မပြဿနာ",
   usage:"'对不起' → '没关系' ဟု ပြန်ဆိုလေ့ရှိ",
   strokes:["没","关","系"],
   examples:[{cn:"没关系，不要紧。",py:"Méiguānxi, bùyàojǐn.",my:"ပြဿနာမရှိပါ၊ မဖြစ်ပါ。",en:"It's OK, don't worry."}]},

  {cn:"再见",py:"zàijiàn",tone:4,my:"ဂုဏ်ပြုပါ / ဘိုင်ဘိုင်",en:"goodbye / see you again",cat:"verb",
   ety:"'再'(တဖန်) + '见'(တွေ့) = တဖန်ပြန်တွေ့မည်",
   usage:"'再见！'(ဘိုင်ဘိုင်！) '明天见'(မနက်ဖြန်တွေ့မည်) '下次见'(နောက်ကြိမ်တွေ့မည်)",
   strokes:["再","见"],
   examples:[{cn:"再见！",py:"Zàijiàn!",my:"ဘိုင်ဘိုင်！",en:"Goodbye!"},{cn:"明天再见！",py:"Míngtiān zàijiàn!",my:"မနက်ဖြန် တွေ့မည်！",en:"See you tomorrow!"}]},

  {cn:"你好",py:"nǐhǎo",tone:3,my:"မင်္ဂလာပါ / ကျန်းမာပါ",en:"hello / how do you do",cat:"verb",
   ety:"'你'(သင်) + '好'(ကောင်း) = 'သင်ကောင်းပါစေ'",
   usage:"'你好！'(မင်္ဂလာပါ！) '你们好！'(မင်္ဂလာပါကြ！) '老师好！'(ဆရာ/မ မင်္ဂလာပါ！)",
   strokes:["你","好"],
   examples:[{cn:"你好！我叫李明。",py:"Nǐhǎo! Wǒ jiào Lǐ Míng.",my:"မင်္ဂလာပါ！ ကျွန်တော် Li Ming ဟုခေါ်သည်。",en:"Hello! My name is Li Ming."}]},

  {cn:"不客气",py:"bù kèqi",tone:4,my:"ကျေးဇူးမတင်ပါနှင့် / မဖြစ်ပါ",en:"you're welcome",cat:"verb",
   ety:"'不'(မ) + '客气'(ဧည့်ခံဥပဒေ) = ဧည့်မပြုပါနှင့်/ရိုးရိုးတန်းတန်း",
   usage:"'谢谢'→'不客气' ဟုပြန်ဆို",
   strokes:["不","客","气"],
   examples:[{cn:"谢谢！——不客气！",py:"Xièxiè! —— Bù kèqi!",my:"ကျေးဇူးတင်ပါသည်！—— မဖြစ်ပါ！",en:"Thank you! — You're welcome!"}]},

  {cn:"岁",py:"suì",tone:4,my:"နှစ် (အသက်ရွယ်)",en:"years old (age)",cat:"noun",
   ety:"'山' + 'ကြောင်း' + 'ပတ်' - တပ်တာ; ဟိုးရှေးနှစ်ရောင်တုံးကောင်",
   usage:"'几岁？'(အသက်ဘယ်နှစ်နှစ်？) '二十岁'(နှစ်ဆယ်) '周岁'(ဖွားနှစ်နှစ်)",
   strokes:["岁","岁"],
   examples:[{cn:"我二十岁。",py:"Wǒ èrshí suì.",my:"ကျွန်တော်/မ အသက် ၂၀ နှစ် ဖြစ်သည်。",en:"I am 20 years old."}]},

  {cn:"一下",py:"yīxià",tone:1,my:"တစ်ချက် / နည်းနည်း (ကြိယာ+一下)",en:"once / a moment / briefly",cat:"particle",
   ety:"'一'(တစ်) + '下'(ကြိမ်/ပတ်) = တစ်ကြိမ်တည်း/မြန်မြန်",
   usage:"ကြိယာ+一下 = 'ခဏတာ...ပါ' ('等一下'(ခဏစောင့်))",
   strokes:["一","下"],
   examples:[{cn:"请等一下。",py:"Qǐng děng yīxià.",my:"ကျေးဇူးပြု၍ ခဏ စောင့်ပါ。",en:"Please wait a moment."},{cn:"我看一下。",py:"Wǒ kàn yīxià.",my:"ကျွန်တော်/မ ကြည့်ပါ့မည်。",en:"Let me take a look."}]},

  {cn:"一起",py:"yīqǐ",tone:1,my:"အတူတကွ / ပူးပေါင်း",en:"together",cat:"particle",
   ety:"'一'(တစ်) + '起'(ပေါ်/ထ) = တပ်တိုးသွားမှုတစ်ခု",
   usage:"'一起去'(အတူသွား) '一起吃饭'(အတူထမင်းစား)",
   strokes:["一","起"],
   examples:[{cn:"我们一起去吧！",py:"Wǒmen yīqǐ qù ba!",my:"ကျွန်တော်တို့ အတူသွားကြစို့！",en:"Let's go together!"},{cn:"一起学习中文。",py:"Yīqǐ xuéxí zhōngwén.",my:"အတူ တရုတ်ဘာသာ သင်ကြမည်。",en:"Study Chinese together."}]},

  {cn:"已经",py:"yǐjīng",tone:3,my:"ပြီးသားရှိပြီ / ကြိုတင်ပြီး",en:"already",cat:"particle",
   ety:"'已'(ပြီးစီး) + '经'(ဖြတ်ကျော်) = ဖြတ်ကျော်ပြီးစီး",
   usage:"'已经吃了'(ကြိုတင်စားပြီ) '已经知道'(သိပြီးသားဖြစ်)",
   strokes:["已","经"],
   examples:[{cn:"我已经吃饭了。",py:"Wǒ yǐjīng chī fàn le.",my:"ကျွန်တော်/မ ထမင်းကြိုတင်စားပြီ。",en:"I have already eaten."},{cn:"他已经来了。",py:"Tā yǐjīng lái le.",my:"သူ ရောက်ပြီ။",en:"He has already arrived."}]},
];

// ======== STATE ========
var knownWords = {};
var writeData = {sessions:0, totalReps:0, words:{}};
var quizCorrect = 0, quizWrong = 0, streak = 0;

// ======== STORAGE API ========
async function saveAll() {
  try { await window.storage.set('chengli_known', JSON.stringify(knownWords)); } catch(e) {}
  try { await window.storage.set('chengli_write', JSON.stringify(writeData)); } catch(e) {}
  try { await window.storage.set('chengli_stats', JSON.stringify({quizCorrect:quizCorrect,quizWrong:quizWrong,streak:streak})); } catch(e) {}
}
async function loadAll() {
  try { var r=await window.storage.get('chengli_known'); if(r&&r.value) knownWords=JSON.parse(r.value); } catch(e) {}
  try { var r=await window.storage.get('chengli_write'); if(r&&r.value) writeData=JSON.parse(r.value); } catch(e) {}
  try { var r=await window.storage.get('chengli_stats'); if(r&&r.value){var s=JSON.parse(r.value);quizCorrect=s.quizCorrect||0;quizWrong=s.quizWrong||0;streak=s.streak||0;} } catch(e) {}
}
var currentWordIdx = 0;
var currentCat = 'all';
var quizMode = 'cn-to-my';
var qScore = 0, qTotal = 0, qStreak = 0;
var quizAnswered = false;

// ======== AUDIO ========
function speakChinese(text) {
  try {
    var u = new SpeechSynthesisUtterance(text);
    u.lang = 'zh-CN'; u.rate = 0.8; u.pitch = 1;
    speechSynthesis.cancel();
    speechSynthesis.speak(u);
  } catch(e) {}
}

// ======== SECTIONS ========
function showTab(name, btn) {
  document.querySelectorAll('.section').forEach(function(s){ s.classList.remove('active'); });
  document.querySelectorAll('.tab-btn').forEach(function(b){ b.classList.remove('active'); });
  document.getElementById('sec-' + name).classList.add('active');
  if (btn) btn.classList.add('active');
  if (name === 'vocab') renderVocab();
  if (name === 'quiz') genQuiz();
  if (name === 'known') renderKnown();
  if (name === 'progress') updateStats();
  if (name === 'write') {
    setTimeout(function(){ initCanvas(); loadWriteWord(); }, 80);
  }
}

// ======== LEARN ========
function loadWord(idx) {
  var w = HSK1[idx];
  document.getElementById('heroChar').textContent = w.cn;
  document.getElementById('heroPinyin').textContent = w.py;
  document.getElementById('heroMy').textContent = w.my;
  document.getElementById('heroEn').textContent = w.en;
  document.getElementById('etymology').textContent = w.ety || '-';
  document.getElementById('category').textContent = w.cat || '-';
  document.getElementById('usage').textContent = w.usage || '-';
  var pct = Math.round((idx / (HSK1.length-1)) * 100);
  document.getElementById('learnProgress').style.width = Math.max(1, pct) + '%';
  document.getElementById('learnCounter').textContent = 'စကားလုံး ' + (idx+1) + '/' + HSK1.length;
  var toneNames = {1:'ပထမ',2:'ဒုတိယ',3:'တတိယ',4:'စတုတ္ထ',0:'ကြားကပ်'};
  var badge = document.getElementById('heroBadge');
  badge.className = 'tone-badge tone-' + w.tone;
  badge.textContent = toneNames[w.tone] + ' Tone (' + w.tone + ')';
  // Strokes
  var ss = document.getElementById('strokeSteps');
  ss.innerHTML = '';
  (w.strokes||[]).forEach(function(s,i){
    var d = document.createElement('div');
    d.className = 'stroke-step';
    d.innerHTML = s + '<span class="snum">' + (i+1) + '</span>';
    ss.appendChild(d);
  });
  // Examples
  var ex = document.getElementById('exampleSentences');
  ex.innerHTML = '';
  (w.examples||[]).forEach(function(e){
    var d = document.createElement('div');
    d.className = 'example-card';
    d.innerHTML = '<div class="ex-cn">' + e.cn + '</div><div class="ex-py">' + e.py + '</div><div class="ex-my">' + e.my + '</div>';
    ex.appendChild(d);
  });
}
function playAudio() { speakChinese(HSK1[currentWordIdx].cn); }
function nextWord() { if (currentWordIdx < HSK1.length-1) { currentWordIdx++; loadWord(currentWordIdx); } }
function prevWord() { if (currentWordIdx > 0) { currentWordIdx--; loadWord(currentWordIdx); } }
function markKnown() {
  var w = HSK1[currentWordIdx];
  knownWords[w.cn] = {py:w.py, my:w.my, en:w.en, addedAt: new Date().toLocaleDateString()};
  streak++;
  updateHeaderStats();
  saveAll();
  var btn = event.target;
  btn.textContent = '✓ မှတ်ပြီး!';
  btn.style.background = 'rgba(48,209,88,0.3)';
  setTimeout(function(){ btn.textContent = '✓ သိပြီ'; btn.style.background = 'rgba(48,209,88,0.15)'; nextWord(); }, 800);
}
function updateHeaderStats() {
  document.getElementById('knownNum').textContent = Object.keys(knownWords).length;
  document.getElementById('streakNum').textContent = streak;
}

// ======== VOCAB ========
function renderVocab() {
  var q = document.getElementById('searchInput').value.toLowerCase();
  var grid = document.getElementById('vocabGrid');
  grid.innerHTML = '';
  HSK1.forEach(function(w, idx) {
    if (currentCat !== 'all' && w.cat !== currentCat) return;
    if (q && w.cn.indexOf(q) < 0 && w.py.toLowerCase().indexOf(q) < 0 && w.my.indexOf(q) < 0) return;
    var d = document.createElement('div');
    d.className = 'vocab-card' + (knownWords[w.cn] ? ' known' : '');
    d.innerHTML = '<div class="vc-char">' + w.cn + '</div><div class="vc-py">' + w.py + '</div><div class="vc-my">' + w.my + '</div>';
    d.onclick = (function(i){ return function(){ currentWordIdx=i; showTab('learn', document.querySelector('.tab-btn')); loadWord(i); }; })(idx);
    grid.appendChild(d);
  });
}
function setCat(cat, btn) {
  currentCat = cat;
  document.querySelectorAll('.cat-btn').forEach(function(b){ b.classList.remove('active'); });
  btn.classList.add('active');
  renderVocab();
}

// ======== QUIZ ========
function setQuizType(type) { quizMode = type; qScore=0; qTotal=0; qStreak=0; updateQuizScore(); genQuiz(); }
function updateQuizScore() {
  document.getElementById('qScore').textContent = qScore;
  document.getElementById('qTotal').textContent = qTotal;
  document.getElementById('qStreak').textContent = qStreak;
}
function genQuiz() {
  quizAnswered = false;
  document.getElementById('quizFeedback').innerHTML = '';
  var w = HSK1[Math.floor(Math.random()*HSK1.length)];
  var typeLabels = {'cn-to-my':'တရုတ်→မြန်မာ မည်သည့်အဓိပ္ပာယ်?','my-to-cn':'မြန်မာ→တရုတ် ဘယ်အက္ခရာ?','pinyin':'Pinyin မည်သည်?'};
  document.getElementById('quizType').textContent = typeLabels[quizMode] || '';
  if (quizMode === 'cn-to-my') {
    document.getElementById('quizQ').textContent = w.cn;
    document.getElementById('quizHint').textContent = w.py;
  } else if (quizMode === 'my-to-cn') {
    document.getElementById('quizQ').style.fontFamily = "'Noto Sans Myanmar',sans-serif";
    document.getElementById('quizQ').style.fontSize = '1.5rem';
    document.getElementById('quizQ').textContent = w.my;
    document.getElementById('quizHint').textContent = '';
  } else {
    document.getElementById('quizQ').style.fontFamily = "'Noto Serif SC',serif";
    document.getElementById('quizQ').style.fontSize = '3rem';
    document.getElementById('quizQ').textContent = w.cn;
    document.getElementById('quizHint').textContent = '';
  }
  var opts = [w];
  while (opts.length < 4) {
    var r = HSK1[Math.floor(Math.random()*HSK1.length)];
    if (!opts.find(function(o){ return o.cn === r.cn; })) opts.push(r);
  }
  opts.sort(function(){ return Math.random()-0.5; });
  var container = document.getElementById('quizOpts');
  container.innerHTML = '';
  opts.forEach(function(o){
    var b = document.createElement('button');
    b.className = 'quiz-opt';
    if (quizMode === 'my-to-cn') b.textContent = o.cn;
    else if (quizMode === 'pinyin') b.textContent = o.py;
    else b.textContent = o.my;
    b.onclick = function(){ if (!quizAnswered) checkAnswer(b, o.cn, w.cn, w); };
    container.appendChild(b);
  });
}
function checkAnswer(btn, chosen, correct, w) {
  quizAnswered = true;
  qTotal++;
  document.querySelectorAll('.quiz-opt').forEach(function(b){ b.disabled = true; });
  if (chosen === correct) {
    btn.classList.add('correct');
    qScore++; qStreak++; streak++;
    knownWords[w.cn] = {py:w.py,my:w.my,en:w.en,addedAt:new Date().toLocaleDateString()};
    document.getElementById('quizFeedback').innerHTML = '<span style="color:var(--green)">✅ မှန်ကန်သည်!</span>';
    showConfetti();
    saveAll();
  } else {
    btn.classList.add('wrong');
    qStreak = 0;
    document.querySelectorAll('.quiz-opt').forEach(function(b){
      if (b.textContent === (quizMode==='my-to-cn'?correct:(quizMode==='pinyin'?w.py:w.my))) b.classList.add('correct');
    });
    document.getElementById('quizFeedback').innerHTML = '<span style="color:var(--red)">❌ မမှန်ပါ - မှန်ကန်သည်မှာ: <strong>' + correct + '</strong></span>';
  }
  updateQuizScore(); updateHeaderStats();
  setTimeout(genQuiz, 1800);
}

// ======== KNOWN WORDS ========
function renderKnown() {
  var keys = Object.keys(knownWords);
  document.getElementById('knownCount').textContent = keys.length;
  var grid = document.getElementById('knownWordsGrid');
  var empty = document.getElementById('knownEmpty');
  grid.innerHTML = '';
  if (keys.length === 0) { empty.style.display = 'block'; return; }
  empty.style.display = 'none';
  keys.forEach(function(cn) {
    var w = knownWords[cn];
    var d = document.createElement('div');
    d.className = 'known-chip';
    d.innerHTML = '<div class="kc-char">' + cn + '</div><div class="kc-py">' + w.py + '</div><div class="kc-my">' + w.my + '</div>';
    d.title = 'နှိပ်ပါ - မသိတော့ဟု ဖျက်';
    d.onclick = (function(c){ return function(){
      if (confirm(c + ' ကို သင်ကြားပြီးစာရင်းမှ ဖျက်မည်လား?')) {
        delete knownWords[c];
        saveAll();
        updateHeaderStats();
        renderKnown();
      }
    }; })(cn);
    grid.appendChild(d);
  });
}

// ======== PROGRESS ========
function updateStats() {
  var k = Object.keys(knownWords).length;
  document.getElementById('pgKnown').textContent = k;
  document.getElementById('pgCorrect').textContent = qScore;
  document.getElementById('pgWrong').textContent = qTotal - qScore;
  document.getElementById('pgStreak').textContent = streak;
  var pct = Math.round((k/HSK1.length)*100);
  document.getElementById('ringChart').style.setProperty('--pct', pct+'%');
  document.getElementById('ringPct').textContent = pct+'%';
}
function resetAll() {
  if (confirm('အားလုံး ပြန်စမည်လား? သင်ကြားပြီးသော စကားလုံးများ ပျောက်သွားမည်')) {
    knownWords={}; writeData={sessions:0,totalReps:0,words:{}}; quizCorrect=0; quizWrong=0; streak=0; qScore=0; qTotal=0; qStreak=0;
    saveAll();
    updateHeaderStats(); updateStats(); updateWriteStats();
  }
}

// ======== WRITING CANVAS ========
var canvas, ctx, isDrawing=false, lastX=0, lastY=0, canvasHasDrawing=false;
var guideOn=false, refOn=false;
var writeIdx=0, writeOrder=[], currentRep=0, audioHeard=0;
var sessionSnaps=[];

function initCanvas() {
  canvas = document.getElementById('writeCanvas');
  if (!canvas) return;
  ctx = canvas.getContext('2d');
  var maxW = Math.min(280, window.innerWidth - 64);
  canvas.width = maxW; canvas.height = maxW;
  canvas.style.width = maxW+'px'; canvas.style.height = maxW+'px';
  clearCanvas();
  // Remove old listeners by cloning
  var nc = canvas.cloneNode(true);
  canvas.parentNode.replaceChild(nc, canvas);
  canvas = nc;
  ctx = canvas.getContext('2d');
  clearCanvas();
  canvas.addEventListener('mousedown', function(e){ isDrawing=true; canvasHasDrawing=true; var p=getPos(e); lastX=p.x; lastY=p.y; });
  canvas.addEventListener('mousemove', function(e){ if(!isDrawing)return; var p=getPos(e); drawStroke(lastX,lastY,p.x,p.y); lastX=p.x; lastY=p.y; });
  canvas.addEventListener('mouseup', function(){ isDrawing=false; });
  canvas.addEventListener('mouseleave', function(){ isDrawing=false; });
  canvas.addEventListener('touchstart', function(e){ e.preventDefault(); isDrawing=true; canvasHasDrawing=true; var p=getTPos(e); lastX=p.x; lastY=p.y; }, {passive:false});
  canvas.addEventListener('touchmove', function(e){ e.preventDefault(); if(!isDrawing)return; var p=getTPos(e); drawStroke(lastX,lastY,p.x,p.y); lastX=p.x; lastY=p.y; }, {passive:false});
  canvas.addEventListener('touchend', function(){ isDrawing=false; });
}
function getPos(e){ var r=canvas.getBoundingClientRect(),sx=canvas.width/r.width,sy=canvas.height/r.height; return {x:(e.clientX-r.left)*sx,y:(e.clientY-r.top)*sy}; }
function getTPos(e){ var r=canvas.getBoundingClientRect(),t=e.touches[0],sx=canvas.width/r.width,sy=canvas.height/r.height; return {x:(t.clientX-r.left)*sx,y:(t.clientY-r.top)*sy}; }
function drawStroke(x1,y1,x2,y2){ ctx.strokeStyle='#FFF'; ctx.lineWidth=Math.max(canvas.width/38,5); ctx.lineCap='round'; ctx.lineJoin='round'; ctx.beginPath(); ctx.moveTo(x1,y1); ctx.lineTo(x2,y2); ctx.stroke(); }
function clearCanvas(){
  if(!canvas||!ctx)return;
  ctx.fillStyle='#0A0018'; ctx.fillRect(0,0,canvas.width,canvas.height);
  if(guideOn) drawGuide();
  canvasHasDrawing=false;
  document.getElementById('writeFeedback').style.display='none';
}
function drawGuide(){
  var w=canvas.width,h=canvas.height;
  ctx.strokeStyle='rgba(255,214,10,0.13)'; ctx.lineWidth=1; ctx.setLineDash([4,6]);
  ctx.beginPath(); ctx.moveTo(w/2,0); ctx.lineTo(w/2,h); ctx.stroke();
  ctx.beginPath(); ctx.moveTo(0,h/2); ctx.lineTo(w,h/2); ctx.stroke();
  ctx.strokeStyle='rgba(191,90,242,0.2)'; ctx.lineWidth=2; ctx.setLineDash([]);
  ctx.strokeRect(3,3,w-6,h-6);
  ctx.setLineDash([]);
}
function toggleGuide(){ guideOn=!guideOn; clearCanvas(); }
function toggleRef(){
  refOn=!refOn;
  var o=document.getElementById('refOverlay');
  o.textContent = document.getElementById('writeChar').textContent;
  o.style.display = refOn?'block':'none';
}

function loadWriteWord(){
  if(writeOrder.length===0) writeOrder=HSK1.map(function(_,i){return i;}).sort(function(){return Math.random()-0.5;});
  currentRep=0; audioHeard=0; sessionSnaps=[];
  refOn=false; guideOn=false;
  document.getElementById('refOverlay').style.display='none';
  var w = HSK1[writeOrder[writeIdx % writeOrder.length]];
  document.getElementById('writeChar').textContent = w.cn;
  document.getElementById('writePy').textContent = w.py;
  document.getElementById('writeMy').textContent = w.my;
  document.getElementById('writeEn').textContent = w.en;
  document.getElementById('refOverlay').textContent = w.cn;
  document.getElementById('sessionDone').style.display='none';
  document.getElementById('writeFeedback').style.display='none';
  // Strokes
  var ss=document.getElementById('writeStrokes'); ss.innerHTML='';
  (w.strokes||[]).forEach(function(s,i){ var d=document.createElement('div'); d.className='stroke-step'; d.innerHTML=s+'<span class="snum">'+(i+1)+'</span>'; ss.appendChild(d); });
  renderRepDots(); renderAudioDots();
  clearCanvas();
  updateWriteStats();
  setTimeout(function(){ speakChinese(w.cn); if(audioHeard<20){audioHeard++;renderAudioDots();document.getElementById('audioLabel').textContent=audioHeard;} },600);
}
function renderRepDots(){
  var d=document.getElementById('repDots'); d.innerHTML='';
  for(var i=0;i<20;i++){
    var dot=document.createElement('div');
    dot.className='rep-dot'+(i<currentRep?' done':i===currentRep?' current':'');
    d.appendChild(dot);
  }
  document.getElementById('repLabel').textContent=currentRep;
  document.getElementById('repCurrent').textContent = currentRep>=20?'✅ ပြည့်ပြီ':'အကြိမ် '+(currentRep+1);
}
function renderAudioDots(){
  var d=document.getElementById('audioDots'); d.innerHTML='';
  for(var i=0;i<20;i++){
    var dot=document.createElement('div');
    dot.className='audio-dot'+(i<audioHeard?' heard':'');
    d.appendChild(dot);
  }
}
function playWriteAudio(){
  speakChinese(document.getElementById('writeChar').textContent);
  if(audioHeard<20){ audioHeard++; renderAudioDots(); document.getElementById('audioLabel').textContent=audioHeard; }
}
function nextWriteWord(){ writeIdx++; loadWriteWord(); }
function skipWrite(){ nextWriteWord(); }

function checkWrite(){
  if(!canvasHasDrawing){ showFb('⚠️','Canvas ပေါ်တွင် ရေးပါ!','var(--orange)'); return; }
  showFb('⏳','AI စစ်ဆေးနေသည်...','var(--muted)');
  var img=canvas.toDataURL('image/png');
  var b64=img.replace('data:image/png;base64,','');
  var ch=document.getElementById('writeChar').textContent;
  var py=document.getElementById('writePy').textContent;
  var my=document.getElementById('writeMy').textContent;
  callAI(b64,ch,py,my);
}
function callAI(b64,ch,py,my){
  var prompt = 'You are a Chinese handwriting teacher. Student wrote: "'+ch+'" ('+py+', '+my+'). White strokes on dark bg. JSON only: {"score":0-100,"recognized":"char or empty","correct":true/false,"feedback_my":"1-2 Myanmar sentences","tip_my":"one Myanmar tip"}';
  fetch('https://api.anthropic.com/v1/messages',{
    method:'POST',
    headers:{'Content-Type':'application/json'},
    body:JSON.stringify({
      model:'claude-sonnet-4-20250514',
      max_tokens:600,
      messages:[{role:'user',content:[
        {type:'image',source:{type:'base64',media_type:'image/png',data:b64}},
        {type:'text',text:prompt}
      ]}]
    })
  })
  .then(function(r){return r.json();})
  .then(function(data){
    if(data.error) throw new Error(data.error.message||'API error');
    var txt=(data.content||[]).map(function(i){return i.text||'';}).join('');
    var s=txt.indexOf('{'), e=txt.lastIndexOf('}')+1;
    if(s<0||e<=s) throw new Error('No JSON');
    var result=JSON.parse(txt.substring(s,e));
    showAIResult(result,ch);
  })
  .catch(function(){
    showManualCheck(ch,py);
  });
}
function showAIResult(r,ch){
  var sc=r.score||0;
  window._lastRepScore=sc;
  var col=sc>=80?'var(--green)':sc>=60?'var(--yellow)':'var(--red)';
  var em=sc>=80?'🌟':sc>=60?'👍':'✏️';
  var html='<div class="feedback-anim">'
    +'<div style="font-size:2rem;margin-bottom:4px">'+em+'</div>'
    +'<div style="font-size:2rem;font-weight:900;color:'+col+';margin-bottom:8px">'+sc+'/100</div>';
  if(r.recognized) html+='<div style="font-size:0.75rem;color:var(--muted);margin-bottom:6px">မြင်သောအက္ခရာ: <span style="font-family:\'Noto Serif SC\',serif;font-size:1.2rem;color:var(--text)">'+r.recognized+'</span> '+(r.recognized===ch?'✅':'')+'</div>';
  html+='<div style="font-size:0.85rem;line-height:1.7;color:var(--text);font-family:\'Noto Sans Myanmar\',sans-serif;margin-bottom:8px">'+(r.feedback_my||'')+'</div>';
  if(r.tip_my) html+='<div style="background:rgba(255,214,10,0.08);border-left:3px solid var(--yellow);padding:8px;border-radius:6px;font-size:0.78rem;color:var(--yellow);text-align:left;margin-bottom:10px">💡 '+r.tip_my+'</div>';
  html+='<div style="display:flex;gap:8px;justify-content:center;flex-wrap:wrap">'
    +'<button class="btn" style="background:rgba(255,45,85,0.15);border:1px solid var(--red);color:var(--red);font-size:0.75rem" onclick="clearCanvas()">🗑️ ထပ်ရေး</button>'
    +'<button class="btn" style="background:linear-gradient(135deg,var(--yellow),var(--orange));color:#000;font-size:0.8rem;font-weight:700" onclick="recordRep()">✅ မှတ်တမ်းတင်၍ ဆက်ရေး</button>'
    +'</div></div>';
  var fb=document.getElementById('writeFeedback');
  fb.innerHTML=html; fb.style.display='block';
  if(sc>=60) speakChinese(document.getElementById('writeChar').textContent);
}
function showManualCheck(ch,py){
  var html='<div style="margin-bottom:8px;font-size:1.1rem">🔍 နမူနာနှင့် နှိုင်းယှဉ်ကြည့်ပါ</div>'
    +'<div style="font-family:\'Noto Serif SC\',serif;font-size:3rem;color:var(--yellow);margin-bottom:8px">'+ch+'</div>'
    +'<div style="font-size:0.78rem;color:var(--muted);margin-bottom:12px">'+py+' - သင်ရေးသောပုံနှင့် နှိုင်းယှဉ်ပါ</div>'
    +'<div style="display:flex;gap:8px;justify-content:center;flex-wrap:wrap">'
    +'<button class="btn" style="background:rgba(48,209,88,0.15);border:1px solid var(--green);color:var(--green);font-size:0.8rem" onclick="window._lastRepScore=85;recordRep()">✅ ကောင်းသည်</button>'
    +'<button class="btn" style="background:rgba(255,214,10,0.15);border:1px solid var(--yellow);color:var(--yellow);font-size:0.8rem" onclick="window._lastRepScore=65;recordRep()">👍 ဆက်ကြိုးစား</button>'
    +'<button class="btn" style="background:rgba(255,45,85,0.15);border:1px solid var(--red);color:var(--red);font-size:0.8rem" onclick="clearCanvas()">↩️ ထပ်ရေး</button>'
    +'</div>';
  var fb=document.getElementById('writeFeedback');
  fb.innerHTML=html; fb.style.display='block';
}
function recordRep(){
  var sc=window._lastRepScore||70;
  sessionSnaps.push({score:sc,snap:canvas.toDataURL('image/png')});
  currentRep++;
  if(audioHeard<20){ audioHeard++; renderAudioDots(); document.getElementById('audioLabel').textContent=audioHeard; speakChinese(document.getElementById('writeChar').textContent); }
  renderRepDots(); clearCanvas();
  document.getElementById('writeFeedback').style.display='none';
  if(currentRep>=20) finishSession();
}
function finishSession(){
  var ch=document.getElementById('writeChar').textContent;
  var avg=sessionSnaps.length?Math.round(sessionSnaps.reduce(function(a,b){return a+b.score;},0)/sessionSnaps.length):0;
  writeData.sessions++;
  writeData.totalReps+=20;
  if(!writeData.words[ch]) writeData.words[ch]={sessions:0,scores:[]};
  writeData.words[ch].sessions++;
  writeData.words[ch].scores.push(avg);
  if(writeData.words[ch].scores.length>10) writeData.words[ch].scores.shift();
  saveAll();
  updateWriteStats();
  document.getElementById('sessionDone').style.display='block';
  document.getElementById('sessionWord').textContent=ch;
  document.getElementById('sessionInfo').textContent='ပျမ်းမျှ: '+avg+'/100 • Pinyin ကြားသော: '+audioHeard+'/20';
  showConfetti();
  var cc=0; var fn=function(){ if(cc>=3)return; speakChinese(document.getElementById('writeChar').textContent); cc++; setTimeout(fn,1800); }; setTimeout(fn,400);
}
function showReview(){
  var fb=document.getElementById('writeFeedback');
  var html='<div style="font-size:0.65rem;color:var(--cyan);letter-spacing:2px;text-transform:uppercase;margin-bottom:10px">📋 ၂၀ ကြိမ် မှတ်တမ်း</div><div style="display:grid;grid-template-columns:repeat(5,1fr);gap:5px;">';
  sessionSnaps.forEach(function(r,i){
    var col=r.score>=80?'#30D158':r.score>=60?'#FFD60A':'#FF2D55';
    html+='<div style="text-align:center"><img src="'+r.snap+'" style="width:100%;border-radius:5px;border:1.5px solid '+col+'"/><div style="font-size:0.6rem;color:'+col+';font-weight:700">'+r.score+'</div></div>';
  });
  html+='</div>';
  fb.innerHTML=html; fb.style.display='block';
}
function updateWriteStats(){
  document.getElementById('wsSessions').textContent=writeData.sessions;
  document.getElementById('wsTotal').textContent=writeData.totalReps;
  document.getElementById('wsWords').textContent=Object.keys(writeData.words).length;
  var list=document.getElementById('practicedList'); list.innerHTML='';
  var keys=Object.keys(writeData.words);
  if(keys.length===0){ list.innerHTML='<div style="font-size:0.72rem;color:var(--muted)">မှတ်တမ်းမရှိသေး</div>'; return; }
  keys.forEach(function(cn){
    var d=document.createElement('span');
    d.className='practiced-chip';
    d.textContent=cn;
    d.title='Session: '+writeData.words[cn].sessions;
    d.onclick=(function(c){ return function(){
      var wi=HSK1.findIndex(function(h){return h.cn===c;});
      if(wi>=0){ var oi=writeOrder.indexOf(wi); if(oi<0){writeOrder.unshift(wi);writeIdx=0;}else{writeIdx=oi;} loadWriteWord(); }
    }; })(cn);
    list.appendChild(d);
  });
}
function showFb(icon,msg,color){
  var fb=document.getElementById('writeFeedback');
  fb.innerHTML='<div style="font-size:1.3rem;margin-bottom:6px">'+icon+'</div><div style="color:'+color+';font-size:0.85rem;font-family:\'Noto Sans Myanmar\',sans-serif;">'+msg+'</div>';
  fb.style.display='block';
}

// ======== CONFETTI ========
function showConfetti(){
  var emojis=['🎉','✨','⭐','🌟','💫','🎊'];
  for(var i=0;i<12;i++){
    (function(){
      var el=document.createElement('div'); el.className='confetti-piece';
      el.textContent=emojis[Math.floor(Math.random()*emojis.length)];
      el.style.left=Math.random()*100+'%'; el.style.top=(40+Math.random()*40)+'%';
      el.style.animationDelay=(Math.random()*0.6)+'s';
      document.body.appendChild(el);
      setTimeout(function(){if(el.parentNode)el.parentNode.removeChild(el);},2000);
    })();
  }
}

// ======== INIT ========
// Show loading state
document.getElementById('knownNum').textContent = '...';
loadAll().then(function() {
  loadWord(0);
  updateHeaderStats();
  updateWriteStats();
  updateStats();
  // Show a toast if data was found
  var k = Object.keys(knownWords).length;
  if (k > 0) {
    var toast = document.createElement('div');
    toast.style.cssText = 'position:fixed;bottom:80px;left:50%;transform:translateX(-50%);background:rgba(48,209,88,0.9);color:#000;padding:10px 20px;border-radius:20px;font-family:\'Noto Sans Myanmar\',sans-serif;font-size:0.82rem;z-index:9999;font-weight:700;';
    toast.textContent = '✓ ' + k + ' စကားလုံး မှတ်တမ်းမှ ပြန်ရယူပြီ';
    document.body.appendChild(toast);
    setTimeout(function(){ if(toast.parentNode) toast.parentNode.removeChild(toast); }, 3000);
  }
});
</script>
</body>
</html>
