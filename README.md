Seoul trip · HTML
<!doctype html>
<html lang="zh-Hant">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>首爾冬日小旅行 2027</title>
<meta name="color-scheme" content="light">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Huninn&display=swap" rel="stylesheet">
<style>
:root{
  --paper:#FBFAFF; --ink:#3D3A5C;
  --pu:#C3B1F0; --li:#E2D8FA; --bl:#A9CEF4; --sk:#CFE6F9;
  --bw:3px; --r:26px;
}
*{box-sizing:border-box;-webkit-tap-highlight-color:transparent}
html{scroll-behavior:smooth;color-scheme:light}
body{
  margin:0;background:var(--paper);color:var(--ink);
  font-family:'Huninn','Noto Sans TC','PingFang TC','Microsoft JhengHei',sans-serif;
  line-height:1.65;font-size:16px;padding-top:72px;-webkit-text-size-adjust:100%;
}
a{color:inherit}
main{max-width:640px;margin:0 auto;padding:14px 16px 100px}
section{scroll-margin-top:82px;margin-top:34px}
h1,h2,h3,p{margin:0}
 
/* ---------- 選單 ---------- */
nav{
  position:fixed;top:0;left:0;right:0;z-index:50;background:var(--paper);
  border-bottom:var(--bw) solid var(--ink);padding-top:env(safe-area-inset-top);
}
.navin{
  display:flex;gap:8px;overflow-x:auto;padding:10px 14px;max-width:760px;margin:0 auto;
  scrollbar-width:none;
}
.navin::-webkit-scrollbar{display:none}
.navin a{
  flex:0 0 auto;text-decoration:none;font-size:15px;padding:4px 14px;
  border:var(--bw) solid var(--ink);border-radius:999px;background:var(--paper);white-space:nowrap;
}
.navin a.on{background:var(--li)}
 
/* ---------- 共用卡片 ---------- */
.card{
  background:var(--paper);border:var(--bw) solid var(--ink);border-radius:var(--r);
  box-shadow:3px 5px 0 var(--ink);overflow:hidden;
}
.pad{padding:16px 18px}
.sec-title{
  display:inline-block;font-size:21px;padding:2px 20px;margin-bottom:16px;
  border:var(--bw) solid var(--ink);border-radius:999px;transform:rotate(-1.5deg);
}
.c-pu{background:var(--pu)}.c-li{background:var(--li)}
.c-bl{background:var(--bl)}.c-sk{background:var(--sk)}
.muted{font-size:14px;opacity:.78}
 
/* ---------- 首頁 ---------- */
.hero svg{display:block;width:100%;height:auto;border-bottom:var(--bw) solid var(--ink)}
.hero .pad{text-align:center;padding:18px 16px 20px}
.hero h1{font-size:clamp(28px,8vw,38px);line-height:1.25;letter-spacing:.04em}
.hero .sub{margin-top:6px;font-size:15px}
.hero .stay{display:inline-block;margin-top:10px;font-size:13px;padding:1px 12px;border:var(--bw) solid var(--ink);border-radius:999px;background:var(--sk)}
.cd-label{margin-top:16px;font-size:15px}
.cd{display:grid;grid-template-columns:repeat(4,1fr);gap:9px;margin-top:8px}
.cd div{border:var(--bw) solid var(--ink);border-radius:18px;padding:6px 0 4px}
.cd div:nth-child(1){background:var(--pu)}.cd div:nth-child(2){background:var(--li)}
.cd div:nth-child(3){background:var(--bl)}.cd div:nth-child(4){background:var(--sk)}
.cd b{display:block;font-size:28px;line-height:1.1;font-weight:400}
.cd span{font-size:12px}
.cd-msg{margin-top:12px;font-size:18px}
 
/* ---------- 航班 ---------- */
.flights{display:grid;gap:16px}
.fl-head{display:flex;justify-content:space-between;align-items:center;padding:8px 18px;border-bottom:var(--bw) solid var(--ink)}
.fl-head b{font-weight:400;font-size:17px}
.route{display:flex;align-items:center;gap:8px;padding:16px 16px 6px}
.route .city{flex:0 0 auto;text-align:center;min-width:64px}
.route .city b{display:block;font-size:22px;font-weight:400;line-height:1.2}
.route .city small{font-size:12px;opacity:.75}
.route .path{flex:1;position:relative;height:36px;overflow:hidden}
.route .path::before{content:'';position:absolute;left:0;right:0;top:50%;border-top:var(--bw) dashed var(--ink)}
.route .path svg{position:absolute;top:2px;left:calc(50% - 18px);width:36px;height:32px;animation:fly 3.2s ease-in-out infinite alternate}
.fl-info{display:grid;grid-template-columns:1fr 1fr;gap:10px;padding:8px 18px 18px}
.fl-info div{border:var(--bw) solid var(--ink);border-radius:16px;padding:6px 12px}
.fl-info small{display:block;font-size:12px;opacity:.75}
.fl-info b{font-weight:400;font-size:17px}
 
/* ---------- 每日行程 ---------- */
.tabs{
  display:flex;gap:8px;overflow-x:auto;padding:4px 4px 12px;margin:0 -4px;
  scrollbar-width:none;scroll-snap-type:x proximity;
}
.tabs::-webkit-scrollbar{display:none}
.tab{
  flex:0 0 auto;scroll-snap-align:center;font:inherit;color:inherit;cursor:pointer;
  width:62px;padding:6px 0 5px;background:var(--paper);
  border:var(--bw) solid var(--ink);border-radius:20px;text-align:center;line-height:1.25;
}
.tab .dd{display:block;font-size:17px}
.tab .ww{display:block;font-size:12px;opacity:.8}
.tab[aria-selected="true"]{background:var(--pu);box-shadow:0 4px 0 var(--ink)}
.tab.bounce{animation:bounce .55s cubic-bezier(.3,1.6,.5,1)}
.panel.pop{animation:pop .5s cubic-bezier(.3,1.5,.5,1)}
.day-head{display:flex;align-items:center;gap:12px;margin:6px 0 18px}
.day-badge{flex:0 0 auto;border:var(--bw) solid var(--ink);border-radius:20px;background:var(--li);padding:2px 12px;font-size:18px}
.day-head h3{font-size:20px;line-height:1.3;font-weight:400}
.day-head p{font-size:13px;opacity:.78}
 
.tl{list-style:none;margin:0;padding:0 0 0 32px;position:relative}
.tl::before{content:'';position:absolute;left:11px;top:10px;bottom:14px;border-left:var(--bw) dashed var(--ink)}
.tli{position:relative;margin-bottom:14px}
.tli::before{
  content:'';position:absolute;left:-32px;top:12px;width:24px;height:24px;border-radius:50%;
  border:var(--bw) solid var(--ink);background:var(--dot,var(--pu));
}
.tc{background:var(--paper);border:var(--bw) solid var(--ink);border-radius:22px;padding:10px 14px 12px}
.tc-top{display:flex;flex-wrap:wrap;align-items:center;gap:6px 8px}
.time{font-size:13px;padding:0 10px;border:var(--bw) solid var(--ink);border-radius:999px;background:var(--bl)}
.time.none{background:var(--paper);opacity:.85}
.must{
  display:inline-flex;align-items:center;gap:3px;font-size:13px;padding:0 10px 0 6px;
  border:var(--bw) solid var(--ink);border-radius:999px;background:var(--pu);
  animation:wiggle 2.8s ease-in-out infinite;transform-origin:center;
}
.must svg{width:14px;height:14px}
.tc h4{margin:6px 0 0;font-size:18px;font-weight:400;line-height:1.4;width:100%}
.tags{display:flex;flex-wrap:wrap;gap:6px;margin-top:6px}
.tag{font-size:12px;padding:0 10px;border:var(--bw) solid var(--ink);border-radius:999px}
.tag.fly{background:var(--pu)}.tag.metro{background:var(--bl)}
.tag.walk{background:var(--sk)}.tag.taxi{background:var(--li)}
.notes{margin:8px 0 0;padding:0;list-style:none;font-size:14px}
.notes li{position:relative;padding-left:16px;margin-top:2px}
.notes li::before{content:'';position:absolute;left:2px;top:.62em;width:7px;height:7px;border-radius:50%;background:var(--li);border:2px solid var(--ink)}
.places{display:grid;gap:8px;margin-top:10px}
.place{border:var(--bw) solid var(--ink);border-radius:16px;padding:5px 12px;background:var(--paper)}
.place:nth-child(4n+1){background:#F3EEFD}.place:nth-child(4n+2){background:#EAF3FC}
.place:nth-child(4n+3){background:#F8F5FE}.place:nth-child(4n+4){background:#EFF6FD}
.place b{display:block;font-weight:400;font-size:15px}
.place small{display:block;font-size:13px;opacity:.8;line-height:1.5}
.link{
  display:inline-block;margin-top:10px;font-size:14px;text-decoration:none;
  padding:2px 14px;border:var(--bw) solid var(--ink);border-radius:999px;background:var(--sk);
}
 
/* ---------- 清單 ---------- */
.prog{margin-bottom:14px}
.prog-top{display:flex;justify-content:space-between;font-size:14px;margin-bottom:4px}
.bar{height:16px;border:var(--bw) solid var(--ink);border-radius:999px;overflow:hidden;background:var(--paper)}
.fill{height:100%;width:0;background:var(--pu);border-right:var(--bw) solid var(--ink);transition:width .35s cubic-bezier(.3,1.4,.5,1)}
.fill[style*="width: 0%"]{border-right:0}
.group{margin-bottom:14px}
.group h3{display:inline-block;font-size:16px;font-weight:400;padding:0 14px;border:var(--bw) solid var(--ink);border-radius:999px;margin-bottom:8px}
.chk{
  display:flex;align-items:flex-start;gap:12px;padding:9px 12px;margin-bottom:8px;cursor:pointer;
  border:var(--bw) solid var(--ink);border-radius:18px;background:var(--paper);
}
.chk input,.cbx{
  appearance:none;-webkit-appearance:none;flex:0 0 auto;width:26px;height:26px;margin:1px 0 0;
  border:var(--bw) solid var(--ink);border-radius:9px;background:var(--paper);cursor:pointer;position:relative;
}
.chk input:checked,.cbx:checked{background:var(--sk)}
.chk input:checked::after,.cbx:checked::after{
  content:'';position:absolute;left:6px;top:1px;width:7px;height:13px;
  border:solid var(--ink);border-width:0 3px 3px 0;transform:rotate(45deg);
  animation:tick .3s cubic-bezier(.3,1.6,.5,1);
}
.chk input:focus-visible,.tab:focus-visible,.navin a:focus-visible,.btn:focus-visible,.link:focus-visible{outline:3px solid #7C66CC;outline-offset:2px}
.chk span{flex:1;font-size:16px;line-height:1.5}
.chk span small{display:block;font-size:13px;opacity:.75}
.chk input:checked + span{text-decoration:line-through;text-decoration-thickness:2px;opacity:.55}
 
/* ---------- 住宿 ---------- */
.hotel svg{display:block;width:100%;height:auto;border-bottom:var(--bw) solid var(--ink)}
.hotel h3{font-size:21px;font-weight:400;line-height:1.35}
.grid2{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-top:14px}
.grid2 div{border:var(--bw) solid var(--ink);border-radius:16px;padding:6px 12px}
.grid2 small{display:block;font-size:12px;opacity:.75}
.grid2 b{font-weight:400;font-size:16px;word-break:break-all}
.grid2 .wide{grid-column:1/-1}
.btns{display:flex;flex-wrap:wrap;gap:10px;margin-top:14px}
.btn{
  font:inherit;font-size:15px;color:inherit;text-decoration:none;cursor:pointer;
  padding:5px 16px;border:var(--bw) solid var(--ink);border-radius:999px;background:var(--li);
}
.btn:active{transform:translateY(2px)}
.btn.alt{background:var(--bl)}
 
footer{text-align:center;font-size:14px;margin-top:38px;opacity:.85}
footer svg{width:90px;height:auto;display:block;margin:0 auto 6px}
 
/* ---------- 動畫 ---------- */
@keyframes bob{0%,100%{transform:translateY(0)}50%{transform:translateY(-5px)}}
@keyframes cloud{0%{transform:translateX(0)}100%{transform:translateX(34px)}}
@keyframes drift{0%{transform:translate(-14px,6px)}100%{transform:translate(26px,-8px)}}
@keyframes snow{0%{transform:translate(0,-12px);opacity:0}10%{opacity:1}100%{transform:translate(14px,262px);opacity:1}}
@keyframes train{0%{transform:translateX(-140px)}100%{transform:translateX(380px)}}
@keyframes fly{0%{transform:translateX(-52px)}100%{transform:translateX(52px)}}
@keyframes wiggle{0%,86%,100%{transform:rotate(0)}90%{transform:rotate(-6deg)}94%{transform:rotate(5deg)}97%{transform:rotate(-3deg)}}
@keyframes pop{0%{transform:translateY(16px) scale(.94);opacity:0}55%{transform:translateY(-6px) scale(1.015);opacity:1}100%{transform:none;opacity:1}}
@keyframes bounce{0%{transform:translateY(0)}35%{transform:translateY(-9px)}65%{transform:translateY(2px)}100%{transform:none}}
@keyframes tick{0%{transform:rotate(45deg) scale(0)}100%{transform:rotate(45deg) scale(1)}}
.sun{animation:bob 4s ease-in-out infinite}
.cloud1{animation:cloud 9s ease-in-out infinite alternate}
.cloud2{animation:cloud 12s ease-in-out infinite alternate-reverse}
.plane{animation:drift 6s ease-in-out infinite alternate}
.flake{animation:snow 9s linear infinite}
.f2{animation-duration:11s;animation-delay:-3s}.f3{animation-duration:8s;animation-delay:-6s}
.f4{animation-duration:12s;animation-delay:-1s}.f5{animation-duration:10s;animation-delay:-8s}
.f6{animation-duration:9.5s;animation-delay:-4.5s}.f7{animation-duration:13s;animation-delay:-10s}
.f8{animation-duration:8.5s;animation-delay:-2s}
.trainmove{animation:train 20s linear infinite}
 
@media (prefers-reduced-motion: reduce){
  html{scroll-behavior:auto}
  *,*::before,*::after{animation:none!important;transition:none!important;scroll-behavior:auto!important}
  .flake{opacity:1;transform:translate(0,0)}
  .flake:not(.f1):not(.f3):not(.f6){display:none}
  .f1{transform:translate(0,60px)}.f3{transform:translate(0,120px)}.f6{transform:translate(0,40px)}
  .trainmove{transform:translateX(30px)}
}
@media (min-width:600px){
  .places{grid-template-columns:1fr 1fr}
}
 
/* ---------- 編輯功能 ---------- */
[hidden]{display:none!important}
body.lock{overflow:hidden}
.btn.sm{font-size:14px;padding:3px 14px}
.mini{font:inherit;font-size:14px;color:inherit;cursor:pointer;padding:1px 13px;border:var(--bw) solid var(--ink);border-radius:999px;background:var(--li)}
.mini:disabled{opacity:.35;cursor:default}
.mini.del,.btn.del{background:var(--paper);border-style:dashed}
.mini:focus-visible{outline:3px solid #7C66CC;outline-offset:2px}
.edit-bar{margin-bottom:16px;padding:12px 16px;background:var(--li)}
.edit-bar b{font-weight:400;font-size:18px}
.edit-bar .btns{margin-top:10px}
body.editing [data-f]{outline:3px dashed #7C66CC;outline-offset:3px;border-radius:6px;display:inline-block;min-width:1.6em;cursor:text}
[data-f]:empty::before{content:'—';opacity:.45}
.fab{position:fixed;right:16px;bottom:calc(16px + env(safe-area-inset-bottom));z-index:40;font:inherit;font-size:16px;color:inherit;cursor:pointer;padding:8px 20px;border:var(--bw) solid var(--ink);border-radius:999px;background:var(--pu);box-shadow:2px 4px 0 var(--ink)}
.fab:active{transform:translateY(2px);box-shadow:2px 2px 0 var(--ink)}
.fab:focus-visible{outline:3px solid #7C66CC;outline-offset:3px}
body.editing .fab{background:var(--bl)}
.toast{position:fixed;left:50%;bottom:calc(78px + env(safe-area-inset-bottom));transform:translateX(-50%);z-index:70;max-width:86vw;padding:6px 18px;border-radius:999px;background:var(--ink);color:var(--paper);font-size:14px;text-align:center;opacity:0;pointer-events:none;transition:opacity .25s}
.toast.show{opacity:1}
.overlay{position:fixed;inset:0;z-index:60;display:flex;align-items:flex-end;justify-content:center;padding:12px;background:rgba(61,58,92,.38)}
@media (min-width:600px){.overlay{align-items:center}}
.sheet{width:100%;max-width:520px;max-height:92vh;overflow:auto;background:var(--paper);border:var(--bw) solid var(--ink);border-radius:var(--r);box-shadow:3px 5px 0 var(--ink);padding:18px;animation:sheet .35s cubic-bezier(.3,1.5,.5,1)}
@keyframes sheet{0%{transform:translateY(26px) scale(.96);opacity:0}100%{transform:none;opacity:1}}
.sheet h3{font-size:20px;font-weight:400;margin-bottom:12px}
.sheet p{margin:0 0 10px;font-size:15px}
.m-btns{display:flex;justify-content:flex-end;gap:10px;margin-top:16px}
.fld{display:block;margin-bottom:12px;font-size:15px}
.fld small{display:block;font-size:12px;opacity:.72}
.sheet input:not([type=checkbox]):not([type=radio]),.sheet textarea,.sheet select{display:block;width:100%;margin-top:4px;font:inherit;font-size:16px;color:var(--ink);padding:7px 12px;background:var(--paper);border:var(--bw) solid var(--ink);border-radius:16px}
.sheet textarea{border-radius:18px;resize:vertical;line-height:1.5}
.sheet input:focus,.sheet textarea:focus,.sheet select:focus{outline:3px solid #7C66CC;outline-offset:1px}
#bkText{font-size:13px}
.chk-inline{display:flex;align-items:center;gap:10px}
.chips{display:flex;flex-wrap:wrap;gap:8px;margin-top:6px}
.chip{position:relative;cursor:pointer}
.chip input{position:absolute;inset:0;width:100%;height:100%;margin:0;opacity:0;cursor:pointer}
.chip .tag{display:inline-block;font-size:14px;padding:1px 14px}
.chip input:not(:checked)+.tag{background:var(--paper);opacity:.55}
.chip input:checked+.tag{box-shadow:0 3px 0 var(--ink)}
.chip input:focus-visible+.tag{outline:3px solid #7C66CC;outline-offset:2px}
.swatches{display:flex;gap:12px;margin-top:6px}
.swatches label{position:relative;cursor:pointer}
.swatches input{position:absolute;inset:0;width:100%;height:100%;margin:0;opacity:0;cursor:pointer}
.sw{display:block;width:38px;height:38px;border-radius:50%;border:var(--bw) solid var(--ink)}
.swatches input:checked+.sw{box-shadow:0 0 0 3px var(--paper),0 0 0 6px var(--ink)}
.swatches input:focus-visible+.sw{outline:3px solid #7C66CC;outline-offset:6px}
.ed-row{display:flex;flex-wrap:wrap;gap:8px;margin-top:10px;padding-top:10px;border-top:var(--bw) dashed var(--ink)}
.ed-day{margin:-8px 0 16px}
.addbtn{width:100%;font:inherit;font-size:16px;color:inherit;cursor:pointer;padding:10px;border:var(--bw) dashed var(--ink);border-radius:22px;background:var(--paper)}
.addbtn:focus-visible{outline:3px solid #7C66CC;outline-offset:2px}
.tli.add::before{background:var(--paper);border-style:dashed}
.tab.add{border-style:dashed;font-size:22px;padding:0;min-height:56px;display:flex;align-items:center;justify-content:center}
.empty{text-align:center;padding:18px 0;opacity:.75}
.chk-ed{display:flex;gap:8px;margin-bottom:8px}
.ed-in{flex:1;min-width:0;font:inherit;font-size:16px;color:var(--ink);padding:7px 12px;border:var(--bw) solid var(--ink);border-radius:16px;background:var(--paper)}
.ed-in:focus{outline:3px solid #7C66CC;outline-offset:1px}
.chk-ed.add .ed-in{border-style:dashed}
</style>
</head>
<body>
 
<nav aria-label="頁面選單">
  <div class="navin" id="navin">
    <a href="#top" class="on">首頁</a>
    <a href="#flight">航班</a>
    <a href="#itinerary">行程</a>
    <a href="#todo">待辦</a>
    <a href="#stay">住宿</a>
    <a href="#prep">出發前</a>
    <a href="#pack">行李</a>
  </div>
</nav>
 
<main>
 
<div class="card edit-bar" id="editBar" hidden>
  <b>編輯模式</b>
  <p class="muted">點虛線框的文字就能直接改；行程可新增、排序、刪除；清單可新增或刪除項目。修改會自動存在這支瀏覽器裡。</p>
  <p class="muted" id="noStore" hidden>注意：目前的環境無法儲存變更，關掉頁面後會消失，請改用瀏覽器直接開啟這個檔案。</p>
  <div class="btns"><button class="btn sm" id="bkBtn" type="button">備份／匯入</button><button class="btn alt sm" id="rstBtn" type="button">還原預設</button></div>
</div>
 
<!-- ================= 首頁 ================= -->
<section id="top" style="margin-top:0;scroll-margin-top:90px">
  <div class="card hero">
    <svg viewBox="0 0 360 250" role="img" aria-label="繪本風首爾插圖：南山塔、韓屋城門、飛機與地鐵">
      <rect width="360" height="250" fill="#A9CEF4"/>
 
      <!-- 太陽 -->
      <g class="sun"><circle cx="292" cy="56" r="24" fill="#E2D8FA" stroke="#3D3A5C" stroke-width="3"/>
        <circle cx="284" cy="52" r="2.5" fill="#3D3A5C"/><circle cx="300" cy="52" r="2.5" fill="#3D3A5C"/>
        <path d="M285 62 q7 6 14 0" fill="none" stroke="#3D3A5C" stroke-width="2.5" stroke-linecap="round"/>
        <circle cx="280" cy="60" r="3.5" fill="#C3B1F0"/><circle cx="304" cy="60" r="3.5" fill="#C3B1F0"/>
      </g>
 
      <!-- 雲 -->
      <g class="cloud1"><g transform="translate(14 14)">
        <path d="M30 90 h70 a14 14 0 0 0 0 -28 a20 20 0 0 0 -38 -4 a16 16 0 0 0 -32 14 a9 9 0 0 0 0 18z" fill="#FBFAFF" stroke="#3D3A5C" stroke-width="3" stroke-linejoin="round"/></g></g>
      <g class="cloud2"><g transform="translate(180 -4) scale(.62)">
        <path d="M30 90 h70 a14 14 0 0 0 0 -28 a20 20 0 0 0 -38 -4 a16 16 0 0 0 -32 14 a9 9 0 0 0 0 18z" fill="#FBFAFF" stroke="#3D3A5C" stroke-width="4.5" stroke-linejoin="round"/></g></g>
 
      <!-- 飛機 -->
      <g class="plane"><g transform="translate(130 36)">
        <path d="M-34 4 H-92" stroke="#FBFAFF" stroke-width="3" stroke-dasharray="5 7" stroke-linecap="round"/>
        <path d="M-20 -2 L-30 -16 L-21 -16 L-8 -2 Z" fill="#C3B1F0" stroke="#3D3A5C" stroke-width="3" stroke-linejoin="round"/>
        <ellipse cx="0" cy="3" rx="24" ry="9" fill="#FBFAFF" stroke="#3D3A5C" stroke-width="3"/>
        <path d="M-6 6 L-16 20 L-6 20 L8 6 Z" fill="#E2D8FA" stroke="#3D3A5C" stroke-width="3" stroke-linejoin="round"/>
        <circle cx="6" cy="1" r="2" fill="#3D3A5C"/><circle cx="13" cy="1" r="2" fill="#3D3A5C"/>
      </g></g>
 
      <!-- 雪山 -->
      <path d="M150 175 L205 108 L250 160 L292 122 L360 180 V215 H150Z" fill="#FBFAFF" stroke="#3D3A5C" stroke-width="3" stroke-linejoin="round"/>
      <path d="M190 128 L205 108 L220 130 L211 126 L205 134 L198 126Z" fill="#A9CEF4" stroke="#3D3A5C" stroke-width="2.5" stroke-linejoin="round"/>
 
      <!-- 南山（綠丘）＋ 南山塔 -->
      <path d="M-10 218 Q30 150 120 148 Q200 148 245 218 Z" fill="#D9CEF7" stroke="#3D3A5C" stroke-width="3" stroke-linejoin="round"/>
      <path d="M40 190 q10 -6 18 0 M150 178 q10 -6 18 0 M82 200 q8 -5 15 0" fill="none" stroke="#3D3A5C" stroke-width="2.5" stroke-linecap="round"/>
      <rect x="108" y="138" width="24" height="12" rx="4" fill="#FBFAFF" stroke="#3D3A5C" stroke-width="3"/>
      <rect x="117" y="98" width="6" height="42" fill="#FBFAFF" stroke="#3D3A5C" stroke-width="3"/>
      <rect x="103" y="86" width="34" height="13" rx="6.5" fill="#C3B1F0" stroke="#3D3A5C" stroke-width="3"/>
      <rect x="110" y="77" width="20" height="9" rx="4.5" fill="#E2D8FA" stroke="#3D3A5C" stroke-width="3"/>
      <path d="M120 77 V54" stroke="#3D3A5C" stroke-width="3" stroke-linecap="round"/>
      <circle cx="120" cy="52" r="3.5" fill="#C3B1F0" stroke="#3D3A5C" stroke-width="2.5"/>
 
      <!-- 韓屋城門 -->
      <rect x="216" y="168" width="118" height="48" fill="#FBFAFF" stroke="#3D3A5C" stroke-width="3"/>
      <path d="M232 216 v-16 a10 10 0 0 1 20 0 v16Z M265 216 v-22 a15 15 0 0 1 30 0 v22Z M308 216 v-16 a10 10 0 0 1 20 0 v16Z" fill="#3D3A5C"/>
      <rect x="228" y="152" width="94" height="16" fill="#C3B1F0" stroke="#3D3A5C" stroke-width="3"/>
      <path d="M200 146 Q222 158 234 136 H316 Q328 158 350 146 L340 156 Q326 166 318 152 H232 Q224 166 210 156Z" fill="#3D3A5C" stroke="#3D3A5C" stroke-width="3" stroke-linejoin="round"/>
      <rect x="246" y="124" width="58" height="12" fill="#E2D8FA" stroke="#3D3A5C" stroke-width="3"/>
      <path d="M240 126 Q258 126 262 110 H288 Q292 126 310 126 Q300 132 290 126 H260 Q250 132 240 126Z" fill="#3D3A5C" stroke="#3D3A5C" stroke-width="3" stroke-linejoin="round"/>
 
      <!-- 雪地 -->
      <rect x="-2" y="212" width="364" height="40" fill="#FBFAFF" stroke="#3D3A5C" stroke-width="3"/>
      <path d="M20 232 h28 M120 238 h34 M230 233 h26 M300 240 h30" stroke="#A9CEF4" stroke-width="3" stroke-linecap="round"/>
 
      <!-- 地鐵 -->
      <g class="trainmove">
        <rect x="0" y="192" width="112" height="28" rx="10" fill="#E2D8FA" stroke="#3D3A5C" stroke-width="3"/>
        <rect x="10" y="199" width="22" height="11" rx="3" fill="#A9CEF4" stroke="#3D3A5C" stroke-width="2.5"/>
        <rect x="40" y="199" width="22" height="11" rx="3" fill="#A9CEF4" stroke="#3D3A5C" stroke-width="2.5"/>
        <rect x="70" y="199" width="22" height="11" rx="3" fill="#A9CEF4" stroke="#3D3A5C" stroke-width="2.5"/>
        <path d="M2 214 H110" stroke="#C3B1F0" stroke-width="3"/>
        <circle cx="24" cy="222" r="5" fill="#3D3A5C"/><circle cx="88" cy="222" r="5" fill="#3D3A5C"/>
      </g>
 
      <!-- 雪花 -->
      <g fill="#FBFAFF">
        <circle class="flake f1" cx="24" cy="0" r="3"/><circle class="flake f2" cx="70" cy="0" r="2.5"/>
        <circle class="flake f3" cx="118" cy="0" r="3.2"/><circle class="flake f4" cx="170" cy="0" r="2.4"/>
        <circle class="flake f5" cx="214" cy="0" r="3"/><circle class="flake f6" cx="262" cy="0" r="2.6"/>
        <circle class="flake f7" cx="310" cy="0" r="3.2"/><circle class="flake f8" cx="344" cy="0" r="2.4"/>
      </g>
    </svg>
    <div class="pad">
      <h1>首爾冬日小旅行</h1>
      <p class="sub">2027.1.18（一）— 1.25（一）・7 晚 8 天</p>
      <span class="stay">大韓航空 KE2026 ／ KE2029</span>
      <p class="cd-label" id="cdLabel">距離出發還有</p>
      <div class="cd" id="cd" aria-live="off">
        <div><b id="cdD">--</b><span>天</span></div>
        <div><b id="cdH">--</b><span>小時</span></div>
        <div><b id="cdM">--</b><span>分鐘</span></div>
        <div><b id="cdS">--</b><span>秒</span></div>
      </div>
      <p class="cd-msg" id="cdMsg" hidden></p>
    </div>
  </div>
</section>
 
<!-- ================= 航班 ================= -->
<section id="flight">
  <h2 class="sec-title c-pu">航班</h2>
  <div class="flights">
    <article class="card">
      <div class="fl-head c-pu"><b>去程 ・ 1/18（一）</b><span>大韓航空</span></div>
      <div class="route">
        <div class="city"><b>台灣</b><small>出發</small></div>
        <div class="path"><svg viewBox="0 0 36 32" aria-hidden="true"><path d="M2 17 L10 14 L18 4 L23 4 L19 14 L30 13 L34 16 L30 19 L19 18 L23 28 L18 28 L10 18 L2 15Z" fill="#FBFAFF" stroke="#3D3A5C" stroke-width="2.5" stroke-linejoin="round"/></svg></div>
        <div class="city"><b>仁川</b><small>ICN</small></div>
      </div>
      <div class="fl-info">
        <div><small>航班</small><b data-f="f1no">KE2026</b></div>
        <div><small>抵達仁川</small><b data-f="f1arr">15:50</b></div>
        <div><small>入境完成</small><b data-f="f1ent">約 17:30</b></div>
        <div><small>起飛時間</small><b data-f="f1dep">— 待補</b></div>
      </div>
    </article>
    <article class="card">
      <div class="fl-head c-bl"><b>回程 ・ 1/25（一）</b><span>大韓航空</span></div>
      <div class="route">
        <div class="city"><b>仁川</b><small>ICN</small></div>
        <div class="path"><svg viewBox="0 0 36 32" aria-hidden="true"><path d="M2 17 L10 14 L18 4 L23 4 L19 14 L30 13 L34 16 L30 19 L19 18 L23 28 L18 28 L10 18 L2 15Z" fill="#FBFAFF" stroke="#3D3A5C" stroke-width="2.5" stroke-linejoin="round"/></svg></div>
        <div class="city"><b>台灣</b><small>回家</small></div>
      </div>
      <div class="fl-info">
        <div><small>航班</small><b data-f="f2no">KE2029</b></div>
        <div><small>抵達機場</small><b data-f="f2arr">14:20</b></div>
        <div class="wide" style="grid-column:1/-1"><small>起飛時間</small><b data-f="f2dep">— 待補</b></div>
      </div>
    </article>
  </div>
</section>
 
<!-- ================= 每日行程 ================= -->
<section id="itinerary">
  <h2 class="sec-title c-li">每日行程</h2>
  <div class="tabs" id="tabs" role="tablist" aria-label="選擇日期"></div>
  <div class="panel" id="panel" role="tabpanel"></div>
</section>
 
<!-- ================= 待辦 ================= -->
<section id="todo">
  <h2 class="sec-title c-sk">待辦清單</h2>
  <div class="card pad">
    <div class="prog"><div class="prog-top"><span>預約與確認</span><span id="todoCnt">0 / 0</span></div><div class="bar"><div class="fill" id="todoBar" style="width:0%"></div></div></div>
    <div id="todoList"></div>
  </div>
</section>
 
<!-- ================= 住宿 ================= -->
<section id="stay">
  <h2 class="sec-title c-bl">住宿資訊</h2>
  <div class="card hotel">
    <svg viewBox="0 0 360 130" role="img" aria-label="飯店插圖">
      <rect width="360" height="130" fill="#A9CEF4"/>
      <circle cx="40" cy="34" r="16" fill="#E2D8FA" stroke="#3D3A5C" stroke-width="3"/>
      <rect x="-2" y="104" width="364" height="30" fill="#FBFAFF" stroke="#3D3A5C" stroke-width="3"/>
      <rect x="110" y="30" width="140" height="76" rx="6" fill="#FBFAFF" stroke="#3D3A5C" stroke-width="3"/>
      <rect x="100" y="22" width="160" height="12" rx="6" fill="#C3B1F0" stroke="#3D3A5C" stroke-width="3"/>
      <g fill="#E2D8FA" stroke="#3D3A5C" stroke-width="3">
        <rect x="124" y="46" width="22" height="18" rx="4"/><rect x="169" y="46" width="22" height="18" rx="4"/><rect x="214" y="46" width="22" height="18" rx="4"/>
        <rect x="124" y="74" width="22" height="18" rx="4"/><rect x="214" y="74" width="22" height="18" rx="4"/>
      </g>
      <path d="M168 106 v-22 a12 12 0 0 1 24 0 v22Z" fill="#3D3A5C"/>
      <path d="M270 106 v-30 M270 76 q-14 -4 -14 -18 q16 0 14 18 M270 84 q14 -2 16 -16 q-16 -2 -16 16" fill="none" stroke="#3D3A5C" stroke-width="3" stroke-linecap="round"/>
      <path d="M270 76 q-14 -4 -14 -18 q16 0 14 18Z M270 84 q14 -2 16 -16 q-16 -2 -16 16Z" fill="#D9CEF7" stroke="#3D3A5C" stroke-width="3" stroke-linejoin="round"/>
    </svg>
    <div class="pad">
      <h3 data-f="hname">Dongdaemun Inspiroom Hotel</h3>
      <p class="muted" data-f="harea">東廟站附近</p>
      <div class="grid2">
        <div><small>入住</small><b data-f="hin">1/18（一）16:00 起</b></div>
        <div><small>退房</small><b data-f="hout">1/25（一）11:00 前</b></div>
        <div><small>住宿天數</small><b data-f="hnights">7 晚</b></div>
        <div><small>訂房平台</small><b data-f="hsite">Agoda</b></div>
        <div class="wide"><small>Agoda 訂單編號</small><b id="orderNo" data-f="horder">1791231431</b></div>
      </div>
      <div class="btns">
        <button class="btn" type="button" id="copyBtn">複製訂單編號</button>
        <a class="btn alt" target="_blank" rel="noopener" href="https://www.google.com/maps/search/?api=1&amp;query=Dongdaemun+Inspiroom+Hotel">在地圖開啟</a>
      </div>
    </div>
  </div>
</section>
 
<!-- ================= 出發前清單 ================= -->
<section id="prep">
  <h2 class="sec-title c-pu">出發前清單</h2>
  <div class="card pad">
    <div class="prog"><div class="prog-top"><span>出發前準備</span><span id="prepCnt">0 / 0</span></div><div class="bar"><div class="fill" id="prepBar" style="width:0%"></div></div></div>
    <div id="prepList"></div>
  </div>
</section>
 
<!-- ================= 行李清單 ================= -->
<section id="pack">
  <h2 class="sec-title c-li">行李清單</h2>
  <div class="card pad">
    <p class="muted" style="margin-bottom:12px">一月的首爾常在零下，早晚特別冷，記得多帶保暖小物。</p>
    <div class="prog"><div class="prog-top"><span>打包進度</span><span id="packCnt">0 / 0</span></div><div class="bar"><div class="fill" id="packBar" style="width:0%"></div></div></div>
    <div id="packList"></div>
  </div>
</section>
 
<footer>
  <svg viewBox="0 0 90 60" aria-hidden="true"><path d="M8 52 Q45 6 82 52Z" fill="#D9CEF7" stroke="#3D3A5C" stroke-width="3" stroke-linejoin="round"/><circle cx="45" cy="30" r="9" fill="#C3B1F0" stroke="#3D3A5C" stroke-width="3"/><path d="M4 54 H86" stroke="#3D3A5C" stroke-width="3" stroke-linecap="round"/></svg>
  路上平安，玩得開心！
</footer>
 
</main>
 
<button type="button" class="fab" id="editFab">✎ 編輯</button>
<div class="toast" id="toast" role="status" aria-live="polite"></div>
<div class="overlay" id="modal" hidden>
  <div class="sheet" role="dialog" aria-modal="true" aria-labelledby="mTitle">
    <h3 id="mTitle"></h3>
    <div id="mBody"></div>
    <div class="m-btns"><button type="button" class="btn alt" id="mCancel">取消</button><button type="button" class="btn" id="mOk">儲存</button></div>
  </div>
</div>
 
<script>
(function(){
'use strict';
var $ = function(s,r){return (r||document).querySelector(s)};
var $$ = function(s,r){return Array.prototype.slice.call((r||document).querySelectorAll(s))};
var esc = function(s){return String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;')};
var reduce = window.matchMedia('(prefers-reduced-motion: reduce)');
var has = function(o,k){return Object.prototype.hasOwnProperty.call(o,k)};
var clone = function(o){return JSON.parse(JSON.stringify(o))};
 
/* ---------- 儲存 ---------- */
var storeOK = true;
try{ localStorage.setItem('seoul27:t','1'); localStorage.removeItem('seoul27:t'); }catch(e){ storeOK = false; }
var store = {
  get:function(k){try{return JSON.parse(localStorage.getItem(k)||'null')}catch(e){return null}},
  set:function(k,v){try{localStorage.setItem(k,JSON.stringify(v))}catch(e){storeOK=false}},
  del:function(k){try{localStorage.removeItem(k)}catch(e){}}
};
 
/* ---------- 小提示 ---------- */
var toastEl = $('#toast'), toastT;
function toast(msg){
  toastEl.textContent = msg; toastEl.classList.add('show');
  clearTimeout(toastT); toastT = setTimeout(function(){toastEl.classList.remove('show')},2200);
}
 
/* ---------- 出發倒數 ---------- */
var DEP = new Date('2027-01-18T00:00:00+08:00');
var END = new Date('2027-01-26T00:00:00+08:00');
function pad(n){return n<10?'0'+n:''+n}
function tick(){
  var now = new Date(), diff = DEP - now;
  var cd = $('#cd'), msg = $('#cdMsg'), lab = $('#cdLabel');
  if(diff > 0){
    var s = Math.floor(diff/1000);
    $('#cdD').textContent = Math.floor(s/86400);
    $('#cdH').textContent = pad(Math.floor(s%86400/3600));
    $('#cdM').textContent = pad(Math.floor(s%3600/60));
    $('#cdS').textContent = pad(s%60);
  }else if(now < END){
    cd.hidden = true; lab.hidden = true; msg.hidden = false;
    msg.textContent = '旅程進行中，今天是第 '+(Math.floor((now-DEP)/86400000)+1)+' 天，玩得開心！';
  }else{
    cd.hidden = true; lab.hidden = true; msg.hidden = false;
    msg.textContent = '平安回到家，旅行回憶滿滿！';
  }
}
tick(); setInterval(tick,1000);
 
/* ---------- 資料清理（讀取、匯入共用） ---------- */
var COLORS = ['pu','li','bl','sk'];
var LEGACY = {coral:'pu',yellow:'li',water:'bl',green:'sk'};
var STD_TAGS = ['飛機','機場鐵路','地鐵','步行','計程車','公車'];
var TAGCLS = {'飛機':'fly','機場鐵路':'metro','地鐵':'metro','步行':'walk','計程車':'taxi','公車':'taxi'};
function str(v,max){return typeof v==='string'?v.slice(0,max||300):''}
function okUrl(u){return /^https?:\/\//i.test(u)?u:''}
function cleanItem(it){
  if(!it||typeof it!=='object') return null;
  var c = LEGACY[it.c]||it.c; if(COLORS.indexOf(c)<0) c = 'pu';
  var o = {t:str(it.t,20).trim(),title:str(it.title,120).trim()||'（未命名）',tags:[],c:c,must:!!it.must,notes:[],places:[],
           link:okUrl(str(it.link,1000).trim()),linkText:str(it.linkText,40).trim()};
  (Array.isArray(it.tags)?it.tags:[]).slice(0,10).forEach(function(t){t=str(t,10).trim(); if(t&&o.tags.indexOf(t)<0) o.tags.push(t)});
  (Array.isArray(it.notes)?it.notes:[]).slice(0,20).forEach(function(n){n=str(n,200).trim(); if(n) o.notes.push(n)});
  (Array.isArray(it.places)?it.places:[]).slice(0,20).forEach(function(p){
    if(!p||typeof p!=='object') return;
    var n = str(p.n,100).trim(); if(n) o.places.push({n:n,s:str(p.s,200).trim()});
  });
  return o;
}
function cleanDays(arr){
  if(!Array.isArray(arr)||!arr.length||arr.length>40) return null;
  var out = [];
  for(var i=0;i<arr.length;i++){
    var d = arr[i];
    if(!d||typeof d!=='object'||!Array.isArray(d.items)) return null;
    out.push({d:str(d.d,10).trim(),w:str(d.w,2).trim(),title:str(d.title,60).trim(),sub:str(d.sub,120).trim(),
              items:d.items.slice(0,60).map(cleanItem).filter(Boolean)});
  }
  return out;
}
function cleanLists(gs){
  if(!Array.isArray(gs)||!gs.length||gs.length>30) return null;
  var out = [];
  for(var i=0;i<gs.length;i++){
    var g = gs[i];
    if(!g||typeof g!=='object'||!Array.isArray(g.items)) return null;
    var seen = {}, items = [];
    g.items.slice(0,100).forEach(function(it,j){
      if(!it||typeof it!=='object') return;
      var t = str(it.t,80).trim(); if(!t) return;
      var id = str(it.id,40)||('x'+i+'-'+j); if(seen[id]) id = id+'-'+j; seen[id] = 1;
      items.push({id:id,t:t,s:str(it.s,120).trim()});
    });
    out.push({id:str(g.id,30)||('g'+i),title:str(g.title,30),color:COLORS.indexOf(g.color)>=0?g.color:'pu',items:items});
  }
  return out;
}
 
/* ---------- 預設行程 ---------- */
var NAVER = 'https://map.naver.com/p/entry/place/1655852311?c=15.00,0,0,0,dh&placePath=%2Fhome%3Ffrom%3Dmap%26fromPanelNum%3D1%26additionalHeight%3D76%26timestamp%3D202611082009%26locale%3Dko%26svcName%3Dmap_pcv5';
var DEFAULT_DAYS = [
  {d:'1/18',w:'一',title:'抵達首爾',sub:'入境、入住、汗蒸幕與東大門夜遊',items:[
    {t:'15:50',title:'仁川機場落地',tags:['飛機'],c:'pu',notes:['KE2026 抵達仁川國際機場']},
    {t:'17:30',title:'入境完成',tags:['步行'],c:'bl',notes:['準備前往飯店']},
    {t:'',title:'飯店 CHECK-IN',tags:['機場鐵路','地鐵'],c:'li',notes:['Dongdaemun Inspiroom Hotel（東廟站附近）','16:00 起可入住']},
    {t:'',title:'晚餐：陳玉華奶奶一隻雞',tags:['步行'],c:'li',must:true},
    {t:'',title:'汗蒸幕：SPAREX 東廟店',tags:['步行'],c:'sk'},
    {t:'',title:'逛東大門',tags:['步行'],c:'pu'}
  ]},
  {d:'1/19',w:'二',title:'美髮日・弘大與延南洞',sub:'上午美髮，下午逛選品店與森林公園',items:[
    {t:'',title:'早餐',c:'li'},
    {t:'10:00',title:'美髮：SOONSIKI',tags:['地鐵'],c:'pu',notes:['預計 4–6 小時']},
    {t:'',title:'弘大商圈',tags:['地鐵'],c:'sk',places:[{n:'as”on'},{n:'Understar 選品店'},{n:'Oyoi 選品店'},{n:'chung chung 牛仔褲'}]},
    {t:'',title:'延南洞',tags:['步行'],c:'bl',places:[{n:'延南洞森林公園'}]},
    {t:'18:30',title:'晚餐：NO烤肉',c:'li'}
  ]},
  {d:'1/20',w:'三',title:'廣藏市場',sub:'市場小吃日',items:[
    {t:'',title:'廣藏市場',tags:['地鐵'],c:'li',must:true}
  ]},
  {d:'1/21',w:'四',title:'聖水洞',sub:'潮流選品與烤肉晚餐',items:[
    {t:'',title:'聖水',tags:['地鐵'],c:'sk'},
    {t:'',title:'聖水洞 / hype2k（하입투케이）',tags:['步行'],c:'pu',must:true,notes:['樓層：B1－ROUGHNECK 韓國實體販售據點'],link:NAVER,linkText:'在 Naver 地圖開啟'},
    {t:'',title:'晚餐：韓式烤肉',c:'li'}
  ]},
  {d:'1/22',w:'五',title:'西村・景福宮韓服日',sub:'早午餐、韓服拍攝、下午茶與安國散步',items:[
    {t:'',title:'早餐（西村）',tags:['地鐵','步行'],c:'li',places:[
      {n:'As Like 애즈라이크 서촌',s:'推薦：開放式三明治、沙拉、湯品、咖啡'},
      {n:'Respirer 레스피레베이커리카페 서촌',s:'推薦：鹽可頌、歐姆蛋三明治、法式吐司'}]},
    {t:'9:00',title:'景福宮韓服拍攝：한복STAR',tags:['步行'],c:'pu',must:true,notes:['預計 4–6 小時']},
    {t:'15:00',title:'下午茶：Onion 安國店 / 3 號店',tags:['步行'],c:'li',notes:['韓屋風格']},
    {t:'',title:'韓國茶',tags:['步行'],c:'sk',places:[
      {n:'Pyunkang Yul Tea House（편강 율 티하우스）'},
      {n:'Chamasineun Tteul（차마시는뜰）'}]},
    {t:'',title:'安國站小店逛逛',tags:['步行'],c:'bl'}
  ]},
  {d:'1/23',w:'六',title:'汝矣島',sub:'百貨、商場與漢江夕陽',items:[
    {t:'',title:'現代百貨首爾店（The Hyundai Seoul）',tags:['地鐵'],c:'pu',places:[
      {n:'3F',s:'KREAM－ROUGHNECK 實體據點'},
      {n:'B2',s:'潮流、時尚、快閃店'},
      {n:'B1',s:'美食、甜點'},
      {n:'5F',s:'Sounds Forest 室內森林'}]},
    {t:'',title:'IFC Mall',tags:['步行'],c:'bl'},
    {t:'',title:'汝矣島漢江公園',tags:['步行'],c:'sk',must:true,notes:['欣賞漢江景色','拍攝首爾城市天際線','散步、看夕陽']},
    {t:'',title:'汝矣島公園',tags:['步行'],c:'sk',notes:['都市森林與步道，適合散步、休息','可以和漢江公園擇一，不必兩個都去']},
    {t:'',title:'晚餐',c:'li'}
  ]},
  {d:'1/24',w:'日',title:'狎鷗亭',sub:'最後一個完整的玩樂日',items:[
    {t:'',title:'狎鷗亭羅德奧站',tags:['地鐵'],c:'pu'}
  ]},
  {d:'1/25',w:'一',title:'回家囉',sub:'早餐、退房、前往機場',items:[
    {t:'',title:'早餐',c:'li'},
    {t:'',title:'退房（11:00 前）',tags:['步行'],c:'bl',notes:['Dongdaemun Inspiroom Hotel']},
    {t:'14:20',title:'抵達機場',tags:['機場鐵路'],c:'sk'},
    {t:'',title:'搭乘 KE2029 返台',tags:['飛機'],c:'pu'}
  ]}
];
var days = cleanDays(store.get('seoul27:days')) || cleanDays(clone(DEFAULT_DAYS));
function saveDays(){ store.set('seoul27:days',days); }
 
/* ---------- 預設清單 ---------- */
function mk(groups){
  return groups.map(function(g){
    return {id:g.id,title:g.title,color:g.color,items:g.items.map(function(it,j){return {id:g.id+'-'+j,t:it[0],s:it[1]||''}})};
  });
}
var DEFAULT_LISTS = {
  todo: mk([{id:'todo',title:'',color:'pu',items:[
    ['預約美髮 SOONSIKI','1/19 10:00 開始，預計 4–6 小時'],
    ['預約景福宮韓服拍攝 한복STAR','1/22 9:00 開始，預計 4–6 小時'],
    ['預約晚餐 NO烤肉','1/19 18:30'],
    ['預約晚餐 陳玉華奶奶一隻雞','1/18 抵達當晚，確認是否需要訂位'],
    ['確認汗蒸幕 SPAREX 東廟店營業時間','1/18 入住後前往'],
    ['確認選品店與百貨營業日','hype2k、Oyoi、Understar、現代百貨等'],
    ['截圖保存 Agoda 訂單','訂單編號 1791231431']
  ]}]),
  prep: mk([{id:'prep',title:'',color:'pu',items:[
    ['確認護照效期','建議出發日起還有 6 個月以上'],
    ['確認最新入境規定','含 K-ETA 等是否需要事先申請'],
    ['大韓航空線上報到、選位','KE2026（1/18）／ KE2029（1/25）'],
    ['買網卡或 eSIM',''],
    ['準備韓元現金與海外刷卡','確認信用卡海外手續費與額度'],
    ['下載 App','Naver Map、Papago、Subway Korea、KakaoT'],
    ['下載離線地圖與訂單截圖','飯店、機票、預約確認信'],
    ['確認旅平險、行李託運規定','']
  ]}]),
  pack: mk([
    {id:'p1',title:'證件與金錢',color:'pu',items:[['護照',''],['機票電子檔／登機證',''],['韓元現金、信用卡',''],['T-money 交通卡（可到韓國再買）','']]},
    {id:'p2',title:'保暖衣物',color:'bl',items:[['羽絨外套或厚大衣',''],['發熱衣、發熱褲',''],['毛衣、針織衫',''],['手套、帽子、圍巾',''],['厚襪、備用襪',''],['防滑好走的鞋','走路多，雪地要防滑'],['睡衣、內衣褲','']]},
    {id:'p3',title:'暖身與保濕',color:'li',items:[['暖暖包',''],['護唇膏、護手霜、乳液',''],['保濕面膜','']]},
    {id:'p4',title:'3C 用品',color:'sk',items:[['手機、充電線',''],['行動電源','需隨身帶上機，不可託運'],['轉接頭','韓國插座為圓孔，記得確認充電器電壓'],['耳機','']]},
    {id:'p5',title:'盥洗與藥品',color:'pu',items:[['牙刷牙膏、盥洗用品',''],['個人藥品、感冒藥、腸胃藥',''],['卸妝與保養品',''],['口罩、衛生用品','']]},
    {id:'p6',title:'這趟特別帶',color:'bl',items:[['美髮參考照片','給 SOONSIKI 設計師看'],['韓服拍照用的小飾品、髮飾','依預約內容準備'],['折疊購物袋','選品店與市場採買用'],['空間留給戰利品','回程行李預留空位']]}
  ])
};
var LIST_CFG = {
  todo:{root:'#todoList',cnt:'#todoCnt',bar:'#todoBar'},
  prep:{root:'#prepList',cnt:'#prepCnt',bar:'#prepBar'},
  pack:{root:'#packList',cnt:'#packCnt',bar:'#packBar'}
};
var LIST_KEYS = ['todo','prep','pack'];
var lists = {}, checks = {};
(function(){
  var saved = store.get('seoul27:lists') || {};
  LIST_KEYS.forEach(function(k){
    lists[k] = cleanLists(saved[k]) || clone(DEFAULT_LISTS[k]);
    var c = store.get('seoul27:'+k); checks[k] = (c&&typeof c==='object'&&!Array.isArray(c)) ? c : {};
  });
})();
function saveLists(){ store.set('seoul27:lists',lists); }
 
/* ---------- 可編輯欄位（航班、住宿） ---------- */
var fieldEls = $$('[data-f]'), defFields = {};
fieldEls.forEach(function(el){ defFields[el.dataset.f] = el.textContent; });
var fields = (function(){
  var f = store.get('seoul27:fields'), o = {};
  if(f&&typeof f==='object') Object.keys(defFields).forEach(function(k){ if(typeof f[k]==='string') o[k] = f[k].slice(0,80); });
  return o;
})();
function applyFields(){
  fieldEls.forEach(function(el){ var k = el.dataset.f; el.textContent = has(fields,k) ? fields[k] : defFields[k]; });
}
applyFields();
var editing = false;
function setFieldsEditable(on){
  fieldEls.forEach(function(el){
    if(on){
      try{ el.contentEditable = 'plaintext-only'; }catch(e){}
      if(el.contentEditable !== 'plaintext-only') el.contentEditable = 'true';
      el.setAttribute('role','textbox'); el.spellcheck = false;
      var lab = el.previousElementSibling;
      if(lab && lab.tagName === 'SMALL') el.setAttribute('aria-label',lab.textContent);
    }else{
      el.removeAttribute('contenteditable'); el.removeAttribute('role'); el.removeAttribute('aria-label');
    }
  });
}
fieldEls.forEach(function(el){
  el.addEventListener('input',function(){
    fields[el.dataset.f] = el.textContent.replace(/\s+/g,' ').trim().slice(0,80);
    store.set('seoul27:fields',fields);
  });
  el.addEventListener('keydown',function(e){ if(e.key==='Enter'){ e.preventDefault(); el.blur(); } });
  el.addEventListener('blur',function(){ var v = el.textContent.replace(/\s+/g,' ').trim(); if(el.textContent !== v) el.textContent = v; });
  el.addEventListener('paste',function(e){
    if(!editing) return;
    e.preventDefault();
    var t = ((e.clipboardData||window.clipboardData).getData('text')||'').replace(/\s+/g,' ');
    document.execCommand('insertText',false,t);
  });
});
 
/* ---------- 對話視窗 ---------- */
var modal = $('#modal'), mTitle = $('#mTitle'), mBody = $('#mBody'), mOk = $('#mOk'), mCancel = $('#mCancel');
var mOnOk = null, lastFocus = null;
function openModal(opt){
  mTitle.textContent = opt.title;
  mBody.innerHTML = opt.html;
  mOk.textContent = opt.ok || '儲存';
  mOnOk = opt.onOk || null;
  lastFocus = document.activeElement;
  modal.hidden = false;
  document.body.classList.add('lock');
  var f = mBody.querySelector('input:not([type=checkbox]):not([type=radio]),textarea,select');
  (f || mCancel).focus({preventScroll:true});
}
function closeModal(){
  modal.hidden = true; document.body.classList.remove('lock'); mOnOk = null;
  if(lastFocus && lastFocus.focus){ try{ lastFocus.focus({preventScroll:true}); }catch(e){} }
}
function confirmBox(title,text,onYes){
  openModal({title:title,html:'<p>'+esc(text)+'</p>',ok:'確定',onOk:onYes});
}
mOk.addEventListener('click',function(){ if(mOnOk && mOnOk() === false) return; closeModal(); });
mCancel.addEventListener('click',closeModal);
modal.addEventListener('click',function(e){ if(e.target === modal) closeModal(); });
document.addEventListener('keydown',function(e){
  if(modal.hidden) return;
  if(e.key === 'Escape'){ closeModal(); return; }
  if(e.key === 'Enter' && e.target.tagName === 'INPUT' && e.target.type !== 'checkbox' && e.target.type !== 'radio'){ e.preventDefault(); mOk.click(); return; }
  if(e.key === 'Tab'){
    var fs = $$('button:not([disabled]),input:not([disabled]),textarea,select',modal);
    if(!fs.length) return;
    var first = fs[0], last = fs[fs.length-1];
    if(e.shiftKey && document.activeElement === first){ e.preventDefault(); last.focus(); }
    else if(!e.shiftKey && document.activeElement === last){ e.preventDefault(); first.focus(); }
  }
});
 
/* ---------- 每日行程 ---------- */
var STAR = '<svg viewBox="0 0 24 24" aria-hidden="true"><path d="M12 2.5l2.9 6 6.6.8-4.9 4.6 1.3 6.5L12 17.1 6.1 20.4l1.3-6.5L2.5 9.3l6.6-.8z" fill="#E2D8FA" stroke="#3D3A5C" stroke-width="2.4" stroke-linejoin="round"/></svg>';
var tabs = $('#tabs'), panel = $('#panel'), cur = 0;
function restart(el,cls){ el.classList.remove(cls); void el.offsetWidth; el.classList.add(cls); }
 
function itemHtml(it,idx,len){
  var h = '<li class="tli" style="--dot:var(--'+it.c+')"><div class="tc"><div class="tc-top">';
  h += it.t ? '<span class="time">'+esc(it.t)+'</span>' : '<span class="time none">接著</span>';
  if(it.must) h += '<span class="must">'+STAR+'必去</span>';
  h += '<h4>'+esc(it.title)+'</h4></div>';
  if(it.tags.length) h += '<div class="tags">'+it.tags.map(function(t){return '<span class="tag '+(TAGCLS[t]||'walk')+'">'+esc(t)+'</span>'}).join('')+'</div>';
  if(it.notes.length) h += '<ul class="notes">'+it.notes.map(function(n){return '<li>'+esc(n)+'</li>'}).join('')+'</ul>';
  if(it.places.length) h += '<div class="places">'+it.places.map(function(p){
    return '<div class="place"><b>'+esc(p.n)+'</b>'+(p.s?'<small>'+esc(p.s)+'</small>':'')+'</div>'}).join('')+'</div>';
  if(it.link) h += '<a class="link" target="_blank" rel="noopener" href="'+esc(it.link)+'">'+esc(it.linkText||'開啟連結')+'</a>';
  if(editing){
    h += '<div class="ed-row">'
      + '<button type="button" class="mini" data-a="up" data-i="'+idx+'"'+(idx===0?' disabled':'')+' aria-label="上移">↑ 上移</button>'
      + '<button type="button" class="mini" data-a="down" data-i="'+idx+'"'+(idx===len-1?' disabled':'')+' aria-label="下移">↓ 下移</button>'
      + '<button type="button" class="mini" data-a="edit" data-i="'+idx+'">編輯</button>'
      + '<button type="button" class="mini del" data-a="del" data-i="'+idx+'">刪除</button></div>';
  }
  return h + '</div></li>';
}
function dayTitle(d){ return (d.d||'')+(d.w?'（'+d.w+'）':'')+d.title; }
function renderPanel(i){
  var d = days[i];
  panel.setAttribute('aria-labelledby','tab'+i);
  var h = '<div class="day-head"><span class="day-badge">Day '+(i+1)+'</span><div><h3>'+esc(dayTitle(d)||'（未命名）')+'</h3>'+(d.sub?'<p>'+esc(d.sub)+'</p>':'')+'</div></div>';
  if(editing) h += '<div class="ed-day"><button type="button" class="mini" data-a="editday">編輯日期與標題</button></div>';
  if(d.items.length || editing){
    h += '<ol class="tl">'+d.items.map(function(it,k){return itemHtml(it,k,d.items.length)}).join('');
    if(editing) h += '<li class="tli add"><button type="button" class="addbtn" data-a="add">＋ 新增行程</button></li>';
    h += '</ol>';
  }else{
    h += '<p class="empty">這天還沒有安排行程。</p>';
  }
  panel.innerHTML = h;
}
function renderTabs(){
  tabs.innerHTML = '';
  days.forEach(function(d,i){
    var b = document.createElement('button');
    b.type = 'button'; b.className = 'tab'; b.id = 'tab'+i; b.dataset.i = i;
    b.setAttribute('role','tab'); b.setAttribute('aria-selected','false'); b.tabIndex = -1;
    b.innerHTML = '<span class="dd">'+esc(d.d||'新')+'</span><span class="ww">'+(d.w?'週'+esc(d.w):'&nbsp;')+'</span>';
    tabs.appendChild(b);
  });
  if(editing){
    var a = document.createElement('button');
    a.type = 'button'; a.className = 'tab add'; a.setAttribute('aria-label','新增一天'); a.textContent = '＋';
    tabs.appendChild(a);
  }
}
function show(i,anim,focus){
  if(i < 0) i = 0; if(i >= days.length) i = days.length-1;
  cur = i;
  var btns = $$('.tab[role=tab]',tabs);
  btns.forEach(function(b,k){ var on = k===i; b.setAttribute('aria-selected',on?'true':'false'); b.tabIndex = on?0:-1; });
  renderPanel(i);
  var b = btns[i];
  if(anim && !reduce.matches){ restart(panel,'pop'); restart(b,'bounce'); }
  tabs.scrollTo({left:b.offsetLeft-(tabs.clientWidth-b.offsetWidth)/2,behavior:reduce.matches?'auto':'smooth'});
  if(focus) b.focus({preventScroll:true});
}
tabs.addEventListener('click',function(e){
  var b = e.target.closest('.tab'); if(!b) return;
  if(b.classList.contains('add')){ addDay(); return; }
  show(+b.dataset.i,true);
});
tabs.addEventListener('keydown',function(e){
  var b = e.target.closest('.tab[role=tab]'); if(!b) return;
  var i = +b.dataset.i;
  if(e.key === 'ArrowRight'){ e.preventDefault(); show(Math.min(days.length-1,i+1),true,true); }
  if(e.key === 'ArrowLeft'){ e.preventDefault(); show(Math.max(0,i-1),true,true); }
});
 
/* 行程表單 */
function itemForm(it){
  it = it || {t:'',title:'',tags:[],c:'pu',must:false,notes:[],places:[],link:'',linkText:''};
  var tags = STD_TAGS.slice();
  it.tags.forEach(function(t){ if(tags.indexOf(t) < 0) tags.push(t); });
  return ''
  + '<label class="fld">時間<small>可留空，例：10:00</small><input id="fT" maxlength="20" value="'+esc(it.t)+'"></label>'
  + '<label class="fld">標題<input id="fTitle" maxlength="120" value="'+esc(it.title)+'"></label>'
  + '<div class="fld">交通方式<small>點一下開關</small><div class="chips" id="fTags">'+tags.map(function(t){
      return '<label class="chip"><input type="checkbox" value="'+esc(t)+'"'+(it.tags.indexOf(t)>=0?' checked':'')+'><span class="tag '+(TAGCLS[t]||'walk')+'">'+esc(t)+'</span></label>';
    }).join('')+'</div></div>'
  + '<label class="fld chk-inline"><input type="checkbox" class="cbx" id="fMust"'+(it.must?' checked':'')+'><span>標為「必去」</span></label>'
  + '<label class="fld">備註<small>每行一則</small><textarea id="fNotes" rows="3">'+esc(it.notes.join('\n'))+'</textarea></label>'
  + '<label class="fld">地點清單<small>每行一個，要加說明就用「｜」隔開，例：3F｜KREAM 據點</small><textarea id="fPlaces" rows="3">'
      +esc(it.places.map(function(p){return p.s?p.n+'｜'+p.s:p.n}).join('\n'))+'</textarea></label>'
  + '<label class="fld">連結網址<small>可留空，需以 http:// 或 https:// 開頭</small><input id="fLink" type="url" inputmode="url" value="'+esc(it.link)+'"></label>'
  + '<label class="fld">連結按鈕文字<input id="fLinkT" maxlength="40" value="'+esc(it.linkText)+'"></label>'
  + '<div class="fld">標記顏色<div class="swatches" id="fColor">'+COLORS.map(function(c){
      return '<label><input type="radio" name="fc" value="'+c+'"'+(it.c===c?' checked':'')+' aria-label="顏色 '+c+'"><span class="sw" style="background:var(--'+c+')"></span></label>';
    }).join('')+'</div></div>';
}
function readItem(){
  var title = $('#fTitle').value.trim();
  if(!title){ toast('請輸入標題'); $('#fTitle').focus(); return null; }
  var link = $('#fLink').value.trim();
  if(link && !okUrl(link)){ toast('連結請以 http:// 或 https:// 開頭'); $('#fLink').focus(); return null; }
  var lines = function(id){ return $('#'+id).value.split('\n').map(function(s){return s.trim()}).filter(Boolean); };
  var places = lines('fPlaces').map(function(s){
    var p = s.split(/[｜|]/); var n = (p.shift()||'').trim();
    return {n:n,s:p.join('｜').trim()};
  }).filter(function(p){return p.n});
  var ch = $('#fColor input:checked');
  return cleanItem({
    t:$('#fT').value, title:title,
    tags:$$('#fTags input:checked').map(function(x){return x.value}),
    c:ch?ch.value:'pu', must:$('#fMust').checked,
    notes:lines('fNotes'), places:places, link:link, linkText:$('#fLinkT').value
  });
}
function editItem(i){
  var d = days[cur], it = i >= 0 ? d.items[i] : null;
  openModal({title:it?'編輯行程':'新增行程',html:itemForm(it),ok:'儲存',onOk:function(){
    var o = readItem(); if(!o) return false;
    if(it) d.items[i] = o; else d.items.push(o);
    saveDays(); renderPanel(cur); toast('已儲存');
  }});
}
/* 日期表單 */
var WEEK = ['','一','二','三','四','五','六','日'];
function dayForm(d){
  d = d || {d:'',w:'',title:'',sub:''};
  return ''
  + '<label class="fld">日期<small>例：1/26</small><input id="dD" maxlength="10" value="'+esc(d.d)+'"></label>'
  + '<label class="fld">星期<select id="dW">'+WEEK.map(function(w){return '<option value="'+w+'"'+(w===d.w?' selected':'')+'>'+(w?'週'+w:'不顯示')+'</option>'}).join('')+'</select></label>'
  + '<label class="fld">這天的主題<input id="dTitle" maxlength="60" value="'+esc(d.title)+'"></label>'
  + '<label class="fld">一句話說明<input id="dSub" maxlength="120" value="'+esc(d.sub)+'"></label>';
}
function readDay(){
  var date = $('#dD').value.trim();
  if(!date){ toast('請輸入日期'); $('#dD').focus(); return null; }
  return {d:date.slice(0,10),w:$('#dW').value,title:$('#dTitle').value.trim(),sub:$('#dSub').value.trim()};
}
function editDay(i){
  var d = days[i];
  var extra = days.length > 1 ? '<div class="fld"><button type="button" class="btn del sm" id="delDay">刪除這一天</button></div>' : '';
  openModal({title:'編輯這一天',html:dayForm(d)+extra,ok:'儲存',onOk:function(){
    var o = readDay(); if(!o) return false;
    d.d = o.d; d.w = o.w; d.title = o.title; d.sub = o.sub;
    saveDays(); renderTabs(); show(i,false); toast('已儲存');
  }});
  var del = $('#delDay');
  if(del) del.addEventListener('click',function(){
    closeModal();
    confirmBox('刪除這一天？','「'+(dayTitle(d)||'這一天')+'」與裡面的 '+d.items.length+' 個行程都會被刪除。',function(){
      days.splice(i,1); saveDays(); renderTabs(); show(Math.min(i,days.length-1),true); toast('已刪除');
    });
  });
}
function addDay(){
  openModal({title:'新增一天',html:dayForm(null),ok:'新增',onOk:function(){
    var o = readDay(); if(!o) return false;
    days.push({d:o.d,w:o.w,title:o.title,sub:o.sub,items:[]});
    saveDays(); renderTabs(); show(days.length-1,true); toast('已新增，接著加入行程吧');
  }});
}
/* 行程卡片上的按鈕 */
panel.addEventListener('click',function(e){
  if(!editing) return;
  var b = e.target.closest('[data-a]'); if(!b || b.disabled) return;
  var a = b.dataset.a, i = +b.dataset.i, d = days[cur];
  if(a === 'up' || a === 'down'){
    var j = a === 'up' ? i-1 : i+1;
    if(j < 0 || j >= d.items.length) return;
    var tmp = d.items[i]; d.items[i] = d.items[j]; d.items[j] = tmp;
    saveDays(); renderPanel(cur);
    var nb = panel.querySelector('[data-a="'+a+'"][data-i="'+j+'"]');
    if(nb && !nb.disabled) nb.focus({preventScroll:true});
  }else if(a === 'edit'){ editItem(i); }
  else if(a === 'add'){ editItem(-1); }
  else if(a === 'del'){
    var it = d.items[i];
    confirmBox('刪除這個行程？','「'+it.title+'」會被刪除。',function(){
      d.items.splice(i,1); saveDays(); renderPanel(cur); toast('已刪除');
    });
  }else if(a === 'editday'){ editDay(cur); }
});
 
/* ---------- 可打勾／可編輯清單 ---------- */
function updProg(key){
  var cfg = LIST_CFG[key], total = 0, n = 0;
  lists[key].forEach(function(g){ g.items.forEach(function(it){ total++; if(checks[key][it.id]) n++; }); });
  $(cfg.cnt).textContent = n+' / '+total;
  $(cfg.bar).style.width = (total ? Math.round(n/total*100) : 0)+'%';
}
function drawList(key){
  var root = $(LIST_CFG[key].root), h = '';
  lists[key].forEach(function(g,gi){
    h += '<div class="group">'+(g.title?'<h3 class="c-'+g.color+'">'+esc(g.title)+'</h3>':'');
    g.items.forEach(function(it){
      if(editing){
        h += '<div class="chk-ed"><input class="ed-in" data-g="'+gi+'" data-id="'+esc(it.id)+'" value="'+esc(it.t)+'" maxlength="80" aria-label="項目名稱">'
          + '<button type="button" class="mini del" data-act="rm" data-g="'+gi+'" data-id="'+esc(it.id)+'" aria-label="刪除項目">✕</button></div>';
      }else{
        h += '<label class="chk"><input type="checkbox" data-id="'+esc(it.id)+'"'+(checks[key][it.id]?' checked':'')+'><span>'+esc(it.t)+(it.s?'<small>'+esc(it.s)+'</small>':'')+'</span></label>';
      }
    });
    if(editing){
      h += '<div class="chk-ed add"><input class="ed-in" data-isnew="1" data-g="'+gi+'" placeholder="新增項目…" maxlength="80" aria-label="新增項目">'
        + '<button type="button" class="mini" data-act="add" data-g="'+gi+'" aria-label="加入項目">＋</button></div>';
    }
    h += '</div>';
  });
  root.innerHTML = h;
  updProg(key);
}
function bindList(key){
  var root = $(LIST_CFG[key].root);
  root.addEventListener('change',function(e){
    var t = e.target;
    if(t.type !== 'checkbox') return;
    if(t.checked) checks[key][t.dataset.id] = 1; else delete checks[key][t.dataset.id];
    store.set('seoul27:'+key,checks[key]); updProg(key);
  });
  root.addEventListener('input',function(e){
    var t = e.target;
    if(!t.classList.contains('ed-in') || t.dataset.isnew) return;
    var g = lists[key][+t.dataset.g]; if(!g) return;
    g.items.forEach(function(it){ if(it.id === t.dataset.id) it.t = t.value.slice(0,80); });
    saveLists();
  });
  root.addEventListener('click',function(e){
    var b = e.target.closest('[data-act]'); if(!b) return;
    var gi = +b.dataset.g, g = lists[key][gi]; if(!g) return;
    if(b.dataset.act === 'rm'){
      g.items = g.items.filter(function(it){ return it.id !== b.dataset.id; });
      delete checks[key][b.dataset.id];
      saveLists(); store.set('seoul27:'+key,checks[key]); drawList(key); toast('已刪除');
    }else if(b.dataset.act === 'add'){
      var inp = b.parentNode.querySelector('.ed-in'), v = inp.value.trim();
      if(!v){ inp.focus(); return; }
      g.items.push({id:'u'+Date.now().toString(36)+Math.random().toString(36).slice(2,5),t:v.slice(0,80),s:''});
      saveLists(); drawList(key);
      var nx = root.querySelector('.chk-ed.add .ed-in[data-g="'+gi+'"]'); if(nx) nx.focus({preventScroll:true});
    }
  });
  root.addEventListener('keydown',function(e){
    if(e.key !== 'Enter' || !e.target.classList.contains('ed-in')) return;
    e.preventDefault();
    if(e.target.dataset.isnew){ var btn = e.target.parentNode.querySelector('[data-act="add"]'); if(btn) btn.click(); }
    else e.target.blur();
  });
}
LIST_KEYS.forEach(function(k){ bindList(k); drawList(k); });
 
/* ---------- 編輯模式 ---------- */
var fab = $('#editFab'), editBar = $('#editBar');
function setEditing(on){
  editing = on;
  document.body.classList.toggle('editing',on);
  editBar.hidden = !on;
  fab.textContent = on ? '✓ 完成' : '✎ 編輯';
  setFieldsEditable(on);
  renderTabs(); show(cur,false);
  LIST_KEYS.forEach(drawList);
  if(on){ $('#noStore').hidden = storeOK; toast(storeOK ? '編輯模式：點虛線框或按鈕即可修改' : '目前無法儲存變更，請改用瀏覽器開啟'); }
  else toast('已完成編輯');
}
fab.addEventListener('click',function(){ setEditing(!editing); });
 
/* 備份、匯入、還原 */
function collectFields(){ var o = {}; fieldEls.forEach(function(el){ o[el.dataset.f] = el.textContent; }); return o; }
function backupText(){ return JSON.stringify({v:2,days:days,lists:lists,checks:checks,fields:collectFields()},null,1); }
function redrawAll(){
  applyFields(); renderTabs(); show(Math.min(cur,days.length-1),false); LIST_KEYS.forEach(drawList);
}
function applyBackup(txt){
  var obj; try{ obj = JSON.parse(txt); }catch(e){ return false; }
  if(!obj || typeof obj !== 'object') return false;
  var nd = cleanDays(obj.days); if(!nd) return false;
  days = nd;
  LIST_KEYS.forEach(function(k){
    var cl = obj.lists ? cleanLists(obj.lists[k]) : null;
    if(cl) lists[k] = cl;
    var c = {};
    if(obj.checks && obj.checks[k] && typeof obj.checks[k] === 'object') Object.keys(obj.checks[k]).forEach(function(id){ if(obj.checks[k][id]) c[id] = 1; });
    checks[k] = c; store.set('seoul27:'+k,c);
  });
  fields = {};
  if(obj.fields && typeof obj.fields === 'object') Object.keys(defFields).forEach(function(k){ if(typeof obj.fields[k] === 'string') fields[k] = obj.fields[k].slice(0,80); });
  saveDays(); saveLists(); store.set('seoul27:fields',fields);
  redrawAll();
  return true;
}
$('#bkBtn').addEventListener('click',function(){
  openModal({title:'備份／匯入',ok:'匯入',html:
    '<p>按「複製備份」把內容貼到備忘錄存起來。要還原或搬到別的裝置，就把備份文字貼回下面的框，再按「匯入」。</p>'
    +'<textarea id="bkText" rows="8" spellcheck="false"></textarea>'
    +'<div class="btns"><button type="button" class="btn sm" id="bkCopy">複製備份</button></div>',
    onOk:function(){
      if(!applyBackup($('#bkText').value)){ toast('這段文字不是有效的備份'); return false; }
      toast('已匯入備份');
    }});
  var ta = $('#bkText'); ta.value = backupText();
  $('#bkCopy').addEventListener('click',function(){
    function done(ok){ toast(ok ? '已複製備份' : '請長按文字框手動複製'); }
    if(navigator.clipboard && navigator.clipboard.writeText){
      navigator.clipboard.writeText(ta.value).then(function(){done(true)},function(){ ta.select(); done(false); });
    }else{
      ta.select(); try{ done(document.execCommand('copy')); }catch(e){ done(false); }
    }
  });
});
$('#rstBtn').addEventListener('click',function(){
  confirmBox('還原成預設內容？','你修改過的行程、清單、航班與住宿資訊都會回到最初版本，打勾紀錄也會清除。',function(){
    days = cleanDays(clone(DEFAULT_DAYS));
    LIST_KEYS.forEach(function(k){ lists[k] = clone(DEFAULT_LISTS[k]); checks[k] = {}; store.del('seoul27:'+k); });
    fields = {};
    ['seoul27:days','seoul27:lists','seoul27:fields'].forEach(store.del);
    cur = 0; redrawAll(); toast('已還原預設內容');
  });
});
 
/* ---------- 起始日期：旅程期間自動選當天 ---------- */
(function(){
  var n = new Date(), start = 0;
  if(n.getFullYear() === 2027){
    for(var i=0;i<days.length;i++){
      var m = /^(\d+)\/(\d+)$/.exec(days[i].d);
      if(m && +m[1] === n.getMonth()+1 && +m[2] === n.getDate()) start = i;
    }
  }
  renderTabs(); show(start,false);
})();
 
/* ---------- 複製訂單編號 ---------- */
$('#copyBtn').addEventListener('click',function(){
  var btn = this, el = $('#orderNo'), txt = el.textContent;
  function done(ok){ btn.textContent = ok ? '已複製！' : '請長按數字手動複製'; setTimeout(function(){btn.textContent='複製訂單編號'},1800); }
  if(navigator.clipboard && navigator.clipboard.writeText){
    navigator.clipboard.writeText(txt).then(function(){done(true)},function(){done(false)});
  }else{
    try{
      var r = document.createRange(); r.selectNodeContents(el);
      var s = window.getSelection(); s.removeAllRanges(); s.addRange(r);
      done(document.execCommand('copy'));
    }catch(e){ done(false); }
  }
});
 
/* ---------- 選單高亮 ---------- */
var links = $$('#navin a'), secs = [];
links.forEach(function(a){ var s = document.getElementById(a.getAttribute('href').slice(1)); if(s) secs.push(s); });
function setOn(id){
  links.forEach(function(a){
    var on = a.getAttribute('href') === '#'+id;
    a.classList.toggle('on',on);
    if(on){ var nv = $('#navin'); nv.scrollTo({left:a.offsetLeft-(nv.clientWidth-a.offsetWidth)/2,behavior:reduce.matches?'auto':'smooth'}); }
  });
}
if('IntersectionObserver' in window){
  var io = new IntersectionObserver(function(es){
    es.forEach(function(e){ if(e.isIntersecting) setOn(e.target.id); });
  },{rootMargin:'-35% 0px -60% 0px'});
  secs.forEach(function(s){ io.observe(s); });
}
})();
 
</script>
</body>
</html>
