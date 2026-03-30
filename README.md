# Tanishka-Gaikwad-portfolio
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>Tanishka Gaikwad — AI & ML Engineer</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=DM+Mono:wght@400;500&family=Syne:wght@300;400;700;800&display=swap" rel="stylesheet"/>
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0;}
:root{--a:#FF7043;--black:#07070A;--white:#F0EEE8;--card:#0F0F14;--mid:#666;--bd:#1a1a22;}
html{scroll-behavior:smooth;}
body{background:var(--black);color:var(--white);font-family:'Syne',sans-serif;overflow-x:hidden;cursor:none;}
#cur{position:fixed;width:10px;height:10px;background:var(--a);border-radius:50%;pointer-events:none;z-index:9999;transform:translate(-50%,-50%);mix-blend-mode:difference;transition:width .2s,height .2s;}
#cur-r{position:fixed;width:36px;height:36px;border:1px solid rgba(255,112,67,.35);border-radius:50%;pointer-events:none;z-index:9998;transform:translate(-50%,-50%);transition:width .3s,height .3s;}
#sb{position:fixed;top:0;left:0;height:2px;background:var(--a);z-index:9999;width:0%;}

/* NAV */
nav{position:fixed;top:0;left:0;right:0;display:flex;justify-content:space-between;align-items:center;padding:1.2rem 3rem;z-index:500;background:rgba(7,7,10,.93);backdrop-filter:blur(14px);border-bottom:1px solid var(--bd);}
.logo{font-family:'Bebas Neue',sans-serif;font-size:1.35rem;letter-spacing:.1em;color:var(--a);}
.nav-links{display:flex;gap:1.8rem;}
.nav-links a{font-family:'DM Mono',monospace;font-size:.65rem;letter-spacing:.15em;text-transform:uppercase;color:var(--mid);text-decoration:none;transition:color .2s;}
.nav-links a:hover{color:var(--a);}

/* HERO */
.hero{min-height:100vh;display:grid;grid-template-columns:1.1fr 0.9fr;padding:8rem 3rem 4rem;align-items:center;gap:3rem;position:relative;overflow:hidden;}
.hero-bg{position:absolute;right:-1rem;top:50%;transform:translateY(-50%);font-family:'Bebas Neue',sans-serif;font-size:clamp(8rem,18vw,15rem);color:rgba(255,112,67,.03);line-height:1;pointer-events:none;user-select:none;white-space:nowrap;}
.htag{font-family:'DM Mono',monospace;font-size:.65rem;letter-spacing:.22em;text-transform:uppercase;color:var(--a);border:1px solid var(--a);display:inline-flex;align-items:center;gap:.5rem;padding:.28rem .8rem;margin-bottom:1.8rem;opacity:0;animation:fadeUp .6s .2s forwards;}
.tdot{width:6px;height:6px;background:var(--a);border-radius:50%;animation:blink 1.4s infinite;}
.hname{font-family:'Bebas Neue',sans-serif;font-size:clamp(3.8rem,8vw,7.5rem);line-height:.88;letter-spacing:.02em;margin-bottom:1.2rem;opacity:0;animation:fadeUp .7s .4s forwards;}
.hname .ac{color:var(--a);}
.hname .out{-webkit-text-stroke:1.5px var(--white);color:transparent;}
.hsub{font-family:'DM Mono',monospace;font-size:.8rem;color:var(--mid);line-height:1.8;margin-bottom:.8rem;opacity:0;animation:fadeUp .6s .55s forwards;}
.hsub em{color:var(--white);font-style:normal;}
.hobj{font-size:.9rem;color:#888;line-height:1.75;max-width:480px;margin-bottom:2.5rem;opacity:0;animation:fadeUp .6s .65s forwards;}
.hobj strong{color:var(--white);font-weight:400;}
.hcta{display:flex;gap:1rem;flex-wrap:wrap;opacity:0;animation:fadeUp .7s .8s forwards;}
.btn-a{background:var(--a);color:var(--black);font-family:'DM Mono',monospace;font-size:.75rem;letter-spacing:.12em;text-transform:uppercase;padding:.88rem 2rem;border:none;cursor:none;font-weight:500;transition:transform .15s,background .15s;}
.btn-a:hover{background:var(--white);transform:translate(-3px,-3px);}
.btn-g{background:transparent;color:var(--white);font-family:'DM Mono',monospace;font-size:.75rem;letter-spacing:.12em;text-transform:uppercase;padding:.88rem 2rem;border:1px solid var(--bd);cursor:none;transition:border-color .2s,color .2s,transform .15s;text-decoration:none;display:inline-block;}
.btn-g:hover{border-color:var(--a);color:var(--a);transform:translate(-3px,-3px);}

/* INFO CARD */
.hero-right{opacity:0;animation:fadeIn 1s 1s forwards;}
.icard{background:var(--card);border:1px solid var(--bd);padding:1.8rem;position:relative;}
.icard::after{content:'';position:absolute;top:-3px;left:-3px;right:3px;bottom:3px;border:1px solid var(--a);pointer-events:none;z-index:-1;}
.ict{font-family:'DM Mono',monospace;font-size:.58rem;letter-spacing:.25em;text-transform:uppercase;color:var(--a);margin-bottom:1.2rem;padding-bottom:.8rem;border-bottom:1px solid var(--bd);}
.icr{display:flex;gap:1rem;padding:.5rem 0;border-bottom:1px solid #111116;font-family:'DM Mono',monospace;font-size:.7rem;}
.icr:last-child{border-bottom:none;}
.ick{color:var(--mid);min-width:85px;flex-shrink:0;}
.icv{color:var(--white);}
.icv.ac{color:var(--a);}
.sbadge{position:absolute;bottom:-1.2rem;right:-1.2rem;background:var(--a);color:var(--black);padding:.45rem 1rem;font-family:'DM Mono',monospace;font-size:.62rem;letter-spacing:.1em;display:flex;align-items:center;gap:.4rem;font-weight:500;}
.sdot{width:5px;height:5px;background:var(--black);border-radius:50%;animation:blink 1.5s infinite;}

/* MARQUEE */
.mq{background:var(--a);color:var(--black);padding:.65rem 0;overflow:hidden;white-space:nowrap;font-family:'Bebas Neue',sans-serif;font-size:.88rem;letter-spacing:.15em;}
.mqi{display:inline-block;animation:marquee 22s linear infinite;}
.mqi span{margin:0 1.6rem;}

/* SECTIONS */
.sec{padding:5rem 3rem;border-top:1px solid var(--bd);}
.sec-eye{font-family:'DM Mono',monospace;font-size:.6rem;letter-spacing:.3em;text-transform:uppercase;color:var(--a);margin-bottom:.5rem;}
.sec-h{font-family:'Bebas Neue',sans-serif;font-size:clamp(2.5rem,5vw,4rem);line-height:1;margin-bottom:2.5rem;}
.sec-h span{color:var(--a);}

/* ABOUT */
.ag{display:grid;grid-template-columns:1fr 1fr;gap:4rem;align-items:start;}
.ap{font-size:.93rem;color:#888;line-height:1.85;margin-bottom:1.4rem;}
.ap strong{color:var(--white);font-weight:400;}
.sr{display:flex;gap:2.5rem;flex-wrap:wrap;padding:1.8rem 0;border-top:1px solid var(--bd);border-bottom:1px solid var(--bd);margin-bottom:2rem;}
.sn{font-family:'Bebas Neue',sans-serif;font-size:2.8rem;color:var(--a);line-height:1;}
.sl{font-family:'DM Mono',monospace;font-size:.58rem;text-transform:uppercase;letter-spacing:.15em;color:var(--mid);}
.now{border-left:2px solid var(--a);padding:1rem 1.4rem;background:var(--card);display:flex;gap:1rem;}
.nl{font-family:'DM Mono',monospace;font-size:.56rem;letter-spacing:.2em;text-transform:uppercase;color:var(--a);white-space:nowrap;margin-top:.15rem;}
.nt{font-size:.85rem;color:#888;line-height:1.65;}
.nt strong{color:var(--white);font-weight:400;}

.skh{font-family:'DM Mono',monospace;font-size:.6rem;letter-spacing:.2em;text-transform:uppercase;color:var(--mid);margin-bottom:.8rem;}
.pills{display:flex;flex-wrap:wrap;gap:.45rem;margin-bottom:1.6rem;}
.pill{font-family:'DM Mono',monospace;font-size:.68rem;padding:.32rem .8rem;border:1px solid #222228;color:var(--mid);transition:all .15s;cursor:default;}
.pill:hover,.pill.on{border-color:var(--a);color:var(--a);}
.langs{display:flex;gap:.45rem;flex-wrap:wrap;}
.lang{font-family:'DM Mono',monospace;font-size:.66rem;padding:.26rem .72rem;background:#111118;color:var(--mid);border:1px solid var(--bd);}

/* EDUCATION */
.elist{display:flex;flex-direction:column;gap:.9rem;}
.ecard{background:var(--card);border:1px solid var(--bd);padding:1.3rem 1.5rem;display:grid;grid-template-columns:1fr auto;gap:.5rem;align-items:start;transition:border-color .2s,transform .15s;position:relative;overflow:hidden;}
.ecard::before{content:'';position:absolute;left:0;top:0;bottom:0;width:2px;background:var(--a);transform:scaleY(0);transform-origin:bottom;transition:transform .3s;}
.ecard:hover::before{transform:scaleY(1);}
.ecard:hover{border-color:#2a2a35;transform:translateX(5px);}
.edeg{font-size:.92rem;font-weight:700;color:var(--white);margin-bottom:.2rem;}
.esch{font-family:'DM Mono',monospace;font-size:.68rem;color:var(--mid);}
.eyr{font-family:'DM Mono',monospace;font-size:.62rem;color:var(--mid);text-align:right;}
.esc{font-family:'Bebas Neue',sans-serif;font-size:1.5rem;color:var(--a);text-align:right;line-height:1;}

/* CERTIFICATIONS */
.certs-grid{display:grid;grid-template-columns:1fr 1fr;gap:1rem;}
.cert-card{background:var(--card);border:1px solid var(--bd);padding:1.2rem 1.4rem;transition:border-color .2s,transform .15s;position:relative;overflow:hidden;}
.cert-card::before{content:'';position:absolute;top:0;left:0;right:0;height:2px;background:var(--a);transform:scaleX(0);transform-origin:left;transition:transform .3s;}
.cert-card:hover::before{transform:scaleX(1);}
.cert-card:hover{border-color:#2a2a35;transform:translateY(-3px);}
.cert-org{font-family:'DM Mono',monospace;font-size:.6rem;letter-spacing:.15em;text-transform:uppercase;color:var(--a);margin-bottom:.4rem;}
.cert-name{font-size:.9rem;color:var(--white);font-weight:700;line-height:1.3;margin-bottom:.3rem;}
.cert-date{font-family:'DM Mono',monospace;font-size:.62rem;color:var(--mid);}

/* CONTACT */
.cgrid{display:grid;grid-template-columns:1fr 1fr;gap:1rem;}
.cc{display:flex;gap:1.2rem;align-items:center;padding:1.2rem 1.5rem;background:var(--card);border:1px solid var(--bd);text-decoration:none;transition:border-color .2s,transform .15s;}
.cc:hover{border-color:var(--a);transform:translateX(5px);}
.cc.full{grid-column:span 2;}
.cci{font-family:'DM Mono',monospace;font-size:.7rem;color:var(--a);width:36px;height:36px;border:1px solid rgba(255,112,67,.3);display:flex;align-items:center;justify-content:center;flex-shrink:0;}
.ccl{font-family:'DM Mono',monospace;font-size:.56rem;text-transform:uppercase;letter-spacing:.2em;color:var(--mid);margin-bottom:.25rem;}
.ccv{font-size:.85rem;color:var(--white);}

/* CURTAIN */
#curtain{position:fixed;inset:0;z-index:850;display:flex;pointer-events:none;}
.cp{flex:1;background:var(--a);transform:scaleY(0);transform-origin:top;}
.co .cp{transform:scaleY(1);transition:transform .35s cubic-bezier(.77,0,.18,1);}
.co .cp:nth-child(2){transition-delay:.05s;transform-origin:bottom;}
.co .cp:nth-child(3){transition-delay:.1s;}
.co .cp:nth-child(4){transition-delay:.08s;transform-origin:bottom;}
.co .cp:nth-child(5){transition-delay:.15s;}
.cr .cp{transform:scaleY(0);transform-origin:bottom;transition:transform .35s .05s cubic-bezier(.77,0,.18,1);}
.cr .cp:nth-child(2){transition-delay:.1s;transform-origin:top;}
.cr .cp:nth-child(3){transition-delay:.15s;}
.cr .cp:nth-child(4){transition-delay:.12s;transform-origin:top;}
.cr .cp:nth-child(5){transition-delay:.2s;}
#clbl{position:fixed;top:50%;left:50%;transform:translate(-50%,-50%);font-family:'Bebas Neue',sans-serif;font-size:clamp(2rem,8vw,5rem);color:var(--black);z-index:860;letter-spacing:.1em;opacity:0;pointer-events:none;transition:opacity .25s;}
#closebtn{position:fixed;top:1.3rem;right:3rem;z-index:900;font-family:'DM Mono',monospace;font-size:.66rem;letter-spacing:.15em;text-transform:uppercase;color:var(--a);background:none;border:1px solid var(--a);padding:.38rem 1rem;cursor:none;transition:all .2s;display:none;}
#closebtn:hover{background:var(--a);color:var(--black);}

/* WORK OVERLAY */
#woverlay{position:fixed;inset:0;z-index:800;background:var(--black);display:none;overflow-y:auto;padding:7rem 3rem 4rem;}
.we{font-family:'DM Mono',monospace;font-size:.6rem;letter-spacing:.3em;text-transform:uppercase;color:var(--a);margin-bottom:.5rem;opacity:0;transform:translateY(16px);transition:all .5s .1s;}
.wt{font-family:'Bebas Neue',sans-serif;font-size:clamp(2.8rem,6vw,5rem);line-height:.95;opacity:0;transform:translateY(24px);transition:all .6s .2s;}
.wt span{color:var(--a);}
.wd{font-family:'DM Mono',monospace;font-size:.76rem;color:var(--mid);margin-top:.8rem;max-width:500px;line-height:1.7;opacity:0;transform:translateY(16px);transition:all .5s .3s;}
#woverlay.rev .we,#woverlay.rev .wt,#woverlay.rev .wd{opacity:1;transform:translateY(0);}
.wh{margin-bottom:3rem;}

/* PROJECT CARDS */
.pgrid{display:grid;grid-template-columns:1fr 1fr;gap:1.5rem;margin-bottom:2.5rem;}
.pcard{background:var(--card);border:1px solid var(--bd);overflow:hidden;cursor:none;opacity:0;transform:translateY(50px) scale(.97);transition:opacity .6s,transform .6s,border-color .2s;}
.pcard.pop{opacity:1;transform:translateY(0) scale(1);}
.pcard:hover{border-color:var(--a);}
.pcard:hover .pimg{transform:scale(1.04);}
.pimg{width:100%;height:180px;background:linear-gradient(135deg,#0d0d14,#14141f);display:flex;align-items:center;justify-content:center;position:relative;overflow:hidden;transition:transform .5s;}
.pghost{position:absolute;font-family:'Bebas Neue',sans-serif;font-size:3.5rem;color:rgba(255,112,67,.06);text-align:center;line-height:1.1;pointer-events:none;}
.pibox{position:relative;z-index:2;width:50px;height:50px;border:1px solid rgba(255,112,67,.2);display:flex;align-items:center;justify-content:center;font-size:1.3rem;}
.pbadge{position:absolute;top:.9rem;right:.9rem;background:var(--a);color:var(--black);font-family:'DM Mono',monospace;font-size:.56rem;padding:.18rem .55rem;letter-spacing:.08em;font-weight:500;}
.pb{padding:1.3rem;}
.pnum{font-family:'DM Mono',monospace;font-size:.56rem;color:#333;letter-spacing:.2em;margin-bottom:.4rem;}
.pname{font-family:'Bebas Neue',sans-serif;font-size:1.4rem;line-height:1;color:var(--white);margin-bottom:.7rem;}
.pname span{color:var(--a);}
.ptags{display:flex;gap:.35rem;flex-wrap:wrap;margin-bottom:.8rem;}
.ptag{font-family:'DM Mono',monospace;font-size:.56rem;background:#111118;color:var(--a);padding:.18rem .52rem;border:1px solid #202028;}
.pp{font-size:.8rem;color:#777;line-height:1.6;}

.bcard{background:var(--card);border:1px solid var(--bd);padding:1.6rem;opacity:0;transform:translateY(30px);transition:opacity .6s .5s,transform .6s .5s;}
.bcard.pop{opacity:1;transform:translateY(0);}
.bct{font-family:'DM Mono',monospace;font-size:.58rem;letter-spacing:.2em;text-transform:uppercase;color:var(--a);margin-bottom:1rem;}
.bgrid{display:grid;grid-template-columns:1fr 1fr;gap:.7rem;}
.bul{display:flex;gap:.7rem;align-items:flex-start;padding:.85rem;background:#0a0a10;border:1px solid var(--bd);transition:border-color .2s;}
.bul:hover{border-color:rgba(255,112,67,.25);}
.barr{color:var(--a);flex-shrink:0;font-size:.82rem;margin-top:2px;}
.bt{font-size:.78rem;color:#888;line-height:1.5;}

.sksec{padding-top:2.5rem;border-top:1px solid var(--bd);margin-top:1rem;}
.skth{font-family:'Bebas Neue',sans-serif;font-size:2rem;margin-bottom:1.5rem;}
.skth span{color:var(--a);}
.skgrid{display:grid;grid-template-columns:repeat(auto-fit,minmax(140px,1fr));gap:.8rem;}
.skc{background:var(--card);border:1px solid var(--bd);padding:1rem;position:relative;overflow:hidden;opacity:0;transform:translateY(18px);transition:opacity .4s,transform .4s,border-color .2s;}
.skc.pop{opacity:1;transform:translateY(0);}
.skc::before{content:'';position:absolute;bottom:0;left:0;width:0;height:2px;background:var(--a);transition:width .3s;}
.skc:hover::before{width:100%;}
.skc:hover{border-color:rgba(255,112,67,.2);}
.skdot{position:absolute;top:.7rem;right:.7rem;width:4px;height:4px;background:var(--a);border-radius:50%;}
.skn{font-family:'DM Mono',monospace;font-size:.7rem;color:var(--white);margin-bottom:.25rem;}
.skt{font-family:'DM Mono',monospace;font-size:.56rem;color:var(--mid);text-transform:uppercase;letter-spacing:.1em;}

footer{border-top:1px solid var(--bd);padding:2rem 3rem;display:flex;justify-content:space-between;align-items:center;font-family:'DM Mono',monospace;font-size:.62rem;letter-spacing:.08em;color:#333;flex-wrap:wrap;gap:.5rem;}
footer a{color:#333;text-decoration:none;transition:color .2s;}
footer a:hover{color:var(--a);}

@keyframes fadeUp{from{opacity:0;transform:translateY(28px);}to{opacity:1;transform:translateY(0);}}
@keyframes fadeIn{from{opacity:0;}to{opacity:1;}}
@keyframes marquee{from{transform:translateX(0);}to{transform:translateX(-50%);}}
@keyframes blink{0%,100%{opacity:1;}50%{opacity:0;}}

@media(max-width:768px){
  nav{padding:1rem 1.5rem;}
  .hero{grid-template-columns:1fr;padding:7rem 1.5rem 3rem;}
  .hero-right{display:none;}
  .ag,.cgrid,.certs-grid,.pgrid,.bgrid{grid-template-columns:1fr;}
  .cc.full{grid-column:span 1;}
  .sec,.sksec{padding:4rem 1.5rem;}
  #woverlay{padding:6rem 1.5rem 3rem;}
  #closebtn{right:1.5rem;}
  footer{flex-direction:column;text-align:center;}
}
</style>
</head>
<body>
<div id="sb"></div>
<div id="cur"></div>
<div id="cur-r"></div>
<div id="curtain"><div class="cp"></div><div class="cp"></div><div class="cp"></div><div class="cp"></div><div class="cp"></div></div>
<div id="clbl">MY WORK</div>
<button id="closebtn">&#10005; Close</button>

<nav>
  <div class="logo">T.GAIKWAD</div>
  <div class="nav-links">
    <a href="#hero">Home</a>
    <a href="#about">About</a>
    <a href="#education">Education</a>
    <a href="#certifications">Certifications</a>
    <a href="#contact">Contact</a>
  </div>
</nav>

<div id="main">

  <!-- HERO -->
  <section class="hero" id="hero">
    <div class="hero-bg">AI&ML</div>
    <div>
      <div class="htag"><div class="tdot"></div>Open to Internships &middot; 2025 Batch</div>
      <h1 class="hname">
        TANISHKA<br/>
        <span class="ac">LILADHAR</span><br/>
        <span class="out">GAIKWAD</span>
      </h1>
      <p class="hsub"><em>Aspiring AI/ML Engineer</em> &middot; Python &middot; IoT &middot; Data Analytics<br/>B.Tech &mdash; AI &amp; ML &middot; Universal AI University</p>
      <p class="hobj">Motivated B.Tech student with hands-on experience in <strong>IoT and machine learning projects</strong>. Skilled in Python, SQL, and data analysis. Seeking <strong>internship opportunities</strong> to apply technical knowledge in real-world AI applications.</p>
      <div class="hcta">
        <button class="btn-a" id="explore-btn">Explore My Work &rarr;</button>
        <a href="#contact" class="btn-g">Get In Touch</a>
      </div>
    </div>
    <div class="hero-right">
      <div class="icard">
        <div class="ict">// tanishka_gaikwad.info</div>
        <div class="icr"><span class="ick">Name</span><span class="icv">Tanishka Liladhar Gaikwad</span></div>
        <div class="icr"><span class="ick">Degree</span><span class="icv ac">B.Tech &middot; AI &amp; ML</span></div>
        <div class="icr"><span class="ick">University</span><span class="icv">Universal AI University</span></div>
        <div class="icr"><span class="ick">Email</span><span class="icv">tanugaikwad017@gmail.com</span></div>
        <div class="icr"><span class="ick">Alt Email</span><span class="icv">Tanishka.gaikwad@universalai.in</span></div>
        <div class="icr"><span class="ick">Phone</span><span class="icv">+91 9209448101</span></div>
        <div class="icr"><span class="ick">Location</span><span class="icv">Karjat, Maharashtra</span></div>
        <div class="icr"><span class="ick">Languages</span><span class="icv">English &middot; Hindi &middot; Marathi</span></div>
        <div class="icr"><span class="ick">Status</span><span class="icv ac">Available &#10003;</span></div>
        <div class="sbadge"><div class="sdot"></div>Open to Internships</div>
      </div>
    </div>
  </section>

  <!-- MARQUEE -->
  <div class="mq">
    <div class="mqi">
      <span>Python</span><span>&middot;</span><span>IoT</span><span>&middot;</span><span>AI/ML</span><span>&middot;</span><span>Arduino</span><span>&middot;</span><span>SQL</span><span>&middot;</span><span>Data Analysis</span><span>&middot;</span><span>ESP8266</span><span>&middot;</span><span>Fraud Detection</span><span>&middot;</span><span>Generative AI</span><span>&middot;</span><span>C/C++</span><span>&middot;</span>
      <span>Python</span><span>&middot;</span><span>IoT</span><span>&middot;</span><span>AI/ML</span><span>&middot;</span><span>Arduino</span><span>&middot;</span><span>SQL</span><span>&middot;</span><span>Data Analysis</span><span>&middot;</span><span>ESP8266</span><span>&middot;</span><span>Fraud Detection</span><span>&middot;</span><span>Generative AI</span><span>&middot;</span><span>C/C++</span><span>&middot;</span>
    </div>
  </div>

  <!-- ABOUT + SKILLS -->
  <section class="sec" id="about">
    <div class="sec-eye">About Me</div>
    <h2 class="sec-h">WHO I <span>AM.</span></h2>
    <div class="ag">
      <div>
        <p class="ap">I'm <strong>Tanishka Liladhar Gaikwad</strong>, a B.Tech student specializing in <strong>Artificial Intelligence &amp; Machine Learning</strong> at Universal AI University. I have hands-on experience in <strong>IoT systems and ML models</strong>.</p>
        <p class="ap">I'm passionate about building <strong>real-world AI applications</strong> — from IoT-based data transmission systems to fraud detection models. I thrive at the intersection of hardware, data, and intelligent software.</p>
        <div class="sr">
          <div><div class="sn">2</div><div class="sl">Projects Built</div></div>
          <div><div class="sn">3</div><div class="sl">Certifications</div></div>
          <div><div class="sn">5+</div><div class="sl">Tech Skills</div></div>
        </div>
        <div class="now">
          <div class="nl">Now</div>
          <div class="nt">Pursuing <strong>B.Tech in AI &amp; ML</strong> and actively seeking <strong>internship opportunities</strong> to apply my skills in AI, IoT, and data analytics.</div>
        </div>
      </div>
      <div>
        <div class="skh">Programming Languages</div>
        <div class="pills">
          <div class="pill on">Python</div><div class="pill on">C / C++</div>
          <div class="pill on">SQL</div><div class="pill">R</div>
        </div>
        <div class="skh" style="margin-top:1.2rem;">AI / ML &amp; Data</div>
        <div class="pills">
          <div class="pill on">Data Preprocessing</div><div class="pill on">Fraud Detection</div>
          <div class="pill">Generative AI</div><div class="pill">Data Analysis</div>
        </div>
        <div class="skh" style="margin-top:1.2rem;">IoT &amp; Hardware</div>
        <div class="pills">
          <div class="pill on">Arduino UNO</div><div class="pill on">ESP8266</div>
          <div class="pill">ThingSpeak</div><div class="pill">VLC</div>
        </div>
        <div class="skh" style="margin-top:1.2rem;">Tools &amp; Platforms</div>
        <div class="pills">
          <div class="pill on">VS Code</div><div class="pill on">Google Colab</div>
          <div class="pill">GitHub Copilot</div><div class="pill">ChatGPT</div>
          <div class="pill">Claude AI</div><div class="pill">Google Gemini</div>
        </div>
        <div class="skh" style="margin-top:1.2rem;">Soft Skills</div>
        <div class="pills">
          <div class="pill on">Analytical Thinking</div><div class="pill on">Teamwork</div>
          <div class="pill">Communication</div><div class="pill">Adaptability</div><div class="pill">Time Management</div>
        </div>
        <div class="skh" style="margin-top:1.2rem;">Languages Known</div>
        <div class="langs">
          <div class="lang">English</div><div class="lang">Hindi</div><div class="lang">Marathi</div>
        </div>
      </div>
    </div>
  </section>

  <!-- EDUCATION -->
  <section class="sec" id="education">
    <div class="sec-eye">Education</div>
    <h2 class="sec-h">MY <span>JOURNEY.</span></h2>
    <div class="elist">
      <div class="ecard">
        <div><div class="edeg">B.Tech in Artificial Intelligence &amp; Machine Learning</div><div class="esch">Universal AI University</div></div>
        <div><div class="eyr">2025 &mdash; Present</div><div class="esc">AI&ML</div></div>
      </div>
      <div class="ecard">
        <div><div class="edeg">12th Grade (HSC) &mdash; Science</div><div class="esch">Orchid College</div></div>
        <div><div class="eyr">2025</div><div class="esc">67.56%</div></div>
      </div>
      <div class="ecard">
        <div><div class="edeg">10th Grade (SSC)</div><div class="esch">Kids Land High School</div></div>
        <div><div class="eyr">2023</div><div class="esc">69%</div></div>
      </div>
    </div>
  </section>

  <!-- CERTIFICATIONS -->
  <section class="sec" id="certifications">
    <div class="sec-eye">Certifications &amp; Workshops</div>
    <h2 class="sec-h">WHAT I'VE <span>EARNED.</span></h2>
    <div class="certs-grid">
      <div class="cert-card">
        <div class="cert-org">Deloitte &middot; Forage</div>
        <div class="cert-name">Data Analytics Job Simulation</div>
        <div class="cert-date">March 2026</div>
      </div>
      <div class="cert-card">
        <div class="cert-org">Universal AI University</div>
        <div class="cert-name">Build Your Own AI Calling Agent</div>
        <div class="cert-date">February 2026</div>
      </div>
      <div class="cert-card">
        <div class="cert-org">Universal AI University</div>
        <div class="cert-name">Introduction to Generative AI Studio</div>
        <div class="cert-date">February 2026</div>
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section class="sec" id="contact">
    <div class="sec-eye">Contact</div>
    <h2 class="sec-h">LET'S <span>CONNECT.</span></h2>
    <div class="cgrid">
      <a href="mailto:tanugaikwad017@gmail.com" class="cc">
        <div class="cci">@</div>
        <div><div class="ccl">Personal Email</div><div class="ccv">tanugaikwad017@gmail.com</div></div>
      </a>
      <a href="mailto:Tanishka.gaikwad@universalai.in" class="cc">
        <div class="cci">@</div>
        <div><div class="ccl">University Email</div><div class="ccv">Tanishka.gaikwad@universalai.in</div></div>
      </a>
      <a href="tel:9209448101" class="cc">
        <div class="cci">#</div>
        <div><div class="ccl">Phone</div><div class="ccv">+91 9209448101</div></div>
      </a>
      <div class="cc">
        <div class="cci">&#128205;</div>
        <div><div class="ccl">Location</div><div class="ccv">Karjat, Maharashtra, India</div></div>
      </div>
    </div>
  </section>

  <footer>
    <span>&copy; 2026 &mdash; Tanishka Liladhar Gaikwad</span>
    <span>B.Tech &middot; AI &amp; ML &middot; Universal AI University</span>
    <a href="mailto:tanugaikwad017@gmail.com">tanugaikwad017@gmail.com</a>
  </footer>
</div>

<!-- WORK OVERLAY -->
<div id="woverlay">
  <div class="wh">
    <div class="we">My Projects</div>
    <h2 class="wt">WHAT I'VE <span>BUILT.</span></h2>
    <p class="wd">Two hands-on projects combining IoT hardware, AI/ML models, Python and real-world data.</p>
  </div>

  <div class="pgrid">
    <!-- Project 1 -->
    <div class="pcard" id="pc1">
      <div class="pimg">
        <div class="pghost">IoT VLC</div>
        <div class="pibox">&#128268;</div>
        <div class="pbadge">IoT &middot; Arduino</div>
      </div>
      <div class="pb">
        <div class="pnum">PROJECT &mdash; 01</div>
        <div class="pname">IoT <span>VISIBLE LIGHT</span> COMMUNICATION</div>
        <div class="ptags"><div class="ptag">Arduino</div><div class="ptag">ESP8266</div><div class="ptag">C/C++</div><div class="ptag">IoT</div><div class="ptag">ThingSpeak</div></div>
        <p class="pp">Wireless data transmission system using LED light pulses (VLC technology) with real-time IoT dashboard monitoring.</p>
      </div>
    </div>

    <!-- Project 2 -->
    <div class="pcard" id="pc2">
      <div class="pimg" style="background:linear-gradient(135deg,#0a0a12,#111120);">
        <div class="pghost">FRAUD AI</div>
        <div class="pibox">&#129302;</div>
        <div class="pbadge">AI &middot; ML</div>
      </div>
      <div class="pb">
        <div class="pnum">PROJECT &mdash; 02</div>
        <div class="pname">MEDICLAIM <span>FRAUD</span> DETECTION</div>
        <div class="ptags"><div class="ptag">Python</div><div class="ptag">ML</div><div class="ptag">SQL</div><div class="ptag">Data Analysis</div></div>
        <p class="pp">Machine learning model to identify fraudulent insurance claims using data preprocessing and classification algorithms.</p>
      </div>
    </div>

    <!-- Bullets -->
    <div class="bcard" id="pbcard" style="grid-column:span 2;">
      <div class="bct">Project Details</div>
      <div class="bgrid">
        <div>
          <div style="font-family:'DM Mono',monospace;font-size:.6rem;color:var(--a);letter-spacing:.15em;text-transform:uppercase;margin-bottom:.6rem;">IoT &mdash; VLC System</div>
          <div class="bul"><div class="barr">&rsaquo;</div><div class="bt">Designed wireless data transmission using LED light pulses (VLC technology)</div></div>
          <div class="bul" style="margin-top:.5rem;"><div class="barr">&rsaquo;</div><div class="bt">Implemented Arduino UNO-based LED transmitter and photodiode receiver</div></div>
          <div class="bul" style="margin-top:.5rem;"><div class="barr">&rsaquo;</div><div class="bt">Uploaded real-time data to ThingSpeak IoT dashboard for monitoring</div></div>
        </div>
        <div>
          <div style="font-family:'DM Mono',monospace;font-size:.6rem;color:var(--a);letter-spacing:.15em;text-transform:uppercase;margin-bottom:.6rem;">AI/ML &mdash; Fraud Detection</div>
          <div class="bul"><div class="barr">&rsaquo;</div><div class="bt">Built ML model to identify fraudulent insurance claims</div></div>
          <div class="bul" style="margin-top:.5rem;"><div class="barr">&rsaquo;</div><div class="bt">Performed data preprocessing and feature engineering</div></div>
          <div class="bul" style="margin-top:.5rem;"><div class="barr">&rsaquo;</div><div class="bt">Applied classification algorithms for fraud prediction</div></div>
        </div>
      </div>
    </div>
  </div>

  <!-- Skills -->
  <div class="sksec">
    <h3 class="skth">SKILLS &amp; <span>TOOLS.</span></h3>
    <div class="skgrid" id="skgrid">
      <div class="skc" data-d="0.05"><div class="skdot"></div><div class="skn">Python</div><div class="skt">Language</div></div>
      <div class="skc" data-d="0.1"><div class="skdot"></div><div class="skn">C / C++</div><div class="skt">Language</div></div>
      <div class="skc" data-d="0.15"><div class="skdot"></div><div class="skn">SQL</div><div class="skt">Database</div></div>
      <div class="skc" data-d="0.2"><div class="skdot"></div><div class="skn">Arduino UNO</div><div class="skt">IoT Hardware</div></div>
      <div class="skc" data-d="0.25"><div class="skdot"></div><div class="skn">ESP8266</div><div class="skt">IoT Hardware</div></div>
      <div class="skc" data-d="0.3"><div class="skdot"></div><div class="skn">AI / ML</div><div class="skt">Specialization</div></div>
      <div class="skc" data-d="0.35"><div class="skdot"></div><div class="skn">Data Analysis</div><div class="skt">Analytics</div></div>
      <div class="skc" data-d="0.4"><div class="skdot"></div><div class="skn">Google Colab</div><div class="skt">Tool</div></div>
      <div class="skc" data-d="0.45"><div class="skdot"></div><div class="skn">Generative AI</div><div class="skt">AI Tools</div></div>
      <div class="skc" data-d="0.5"><div class="skdot"></div><div class="skn">ThingSpeak</div><div class="skt">IoT Platform</div></div>
    </div>
  </div>

  <footer style="margin-top:3rem;">
    <span>&copy; 2026 &mdash; Tanishka Gaikwad</span>
    <span>B.Tech &middot; AI &amp; ML</span>
    <a href="mailto:tanugaikwad017@gmail.com">tanugaikwad017@gmail.com</a>
  </footer>
</div>

<script>
(function(){
  var cur=document.getElementById('cur'), curR=document.getElementById('cur-r');
  var mx=0,my=0,rx=0,ry=0;
  document.addEventListener('mousemove',function(e){mx=e.clientX;my=e.clientY;cur.style.left=mx+'px';cur.style.top=my+'px';});
  function ac(){rx+=(mx-rx)*.12;ry+=(my-ry)*.12;curR.style.left=rx+'px';curR.style.top=ry+'px';requestAnimationFrame(ac);}
  ac();
  document.querySelectorAll('a,button,.pill,.ecard,.pcard,.skc,.cc,.bul,.cert-card').forEach(function(el){
    el.addEventListener('mouseenter',function(){cur.style.width='18px';cur.style.height='18px';curR.style.width='52px';curR.style.height='52px';curR.style.opacity='.2';});
    el.addEventListener('mouseleave',function(){cur.style.width='10px';cur.style.height='10px';curR.style.width='36px';curR.style.height='36px';curR.style.opacity='.35';});
  });
  window.addEventListener('scroll',function(){
    var p=window.scrollY/(document.body.scrollHeight-window.innerHeight)*100;
    document.getElementById('sb').style.width=p+'%';
  });
  document.querySelectorAll('.pill').forEach(function(p){p.addEventListener('click',function(){p.classList.toggle('on');});});

  function reset(){
    ['pc1','pc2','pbcard'].forEach(function(id){var e=document.getElementById(id);if(e)e.classList.remove('pop');});
    document.querySelectorAll('#skgrid .skc').forEach(function(c){c.classList.remove('pop');});
  }

  function openWork(){
    var ct=document.getElementById('curtain'),lb=document.getElementById('clbl');
    var ov=document.getElementById('woverlay'),cb=document.getElementById('closebtn');
    reset(); ov.classList.remove('rev'); lb.textContent='MY WORK';
    ct.className='co'; ct.style.pointerEvents='all';
    setTimeout(function(){lb.style.opacity='1';},200);
    setTimeout(function(){
      ov.style.display='block'; cb.style.display='block';
      ov.scrollTop=0; document.getElementById('main').style.display='none';
      ct.className='cr'; lb.style.opacity='0';
      setTimeout(function(){
        ct.className=''; ct.style.pointerEvents='none';
        ov.classList.add('rev');
        setTimeout(function(){var e=document.getElementById('pc1');if(e)e.classList.add('pop');},300);
        setTimeout(function(){var e=document.getElementById('pc2');if(e)e.classList.add('pop');},440);
        setTimeout(function(){var e=document.getElementById('pbcard');if(e)e.classList.add('pop');},580);
        document.querySelectorAll('#skgrid .skc').forEach(function(c){
          var d=parseFloat(c.getAttribute('data-d')||0)*1000;
          setTimeout(function(){c.classList.add('pop');},640+d);
        });
      },500);
    },480);
  }

  function closeWork(){
    var ct=document.getElementById('curtain'),lb=document.getElementById('clbl');
    var ov=document.getElementById('woverlay'),cb=document.getElementById('closebtn');
    lb.textContent='WELCOME BACK';
    ct.className='co'; ct.style.pointerEvents='all';
    setTimeout(function(){lb.style.opacity='1';},200);
    setTimeout(function(){
      ov.style.display='none'; ov.classList.remove('rev');
      cb.style.display='none'; document.getElementById('main').style.display='block';
      window.scrollTo(0,0); ct.className='cr'; lb.style.opacity='0';
      setTimeout(function(){ct.className='';ct.style.pointerEvents='none';lb.textContent='MY WORK';},500);
    },480);
  }

  document.getElementById('explore-btn').addEventListener('click',openWork);
  document.getElementById('closebtn').addEventListener('click',closeWork);
})();
</script>
</body>
</html>
