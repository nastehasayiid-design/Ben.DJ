<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover"/>
<title>Benjamin Muhoya — DJ & Events</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Syncopate:wght@400;700&display=swap" rel="stylesheet"/>
<style>
*,*::before,*::after{margin:0;padding:0;box-sizing:border-box;}
:root{
  --red:#d93a1a;
  --amber:#f0a500;
  --deep:#080503;
  --surface:#0f0b07;
  --panel:#161009;
  --card:#1c1410;
  --border:rgba(240,165,0,.15);
  --border2:rgba(217,58,26,.2);
  --glow-r:rgba(217,58,26,.5);
  --glow-a:rgba(240,165,0,.4);
  --text:#ede8e0;
  --muted:#6b6058;
  --muted2:#9a8f83;
  --ok:#e8b14a;
}
html{scroll-behavior:smooth;-webkit-text-size-adjust:100%;}
body{
  background:var(--deep);
  color:var(--text);
  font-family:'Cormorant Garamond',serif;
  font-weight:300;
  overflow-x:hidden;
  -webkit-font-smoothing:antialiased;
}
body::after{
  content:'';
  position:fixed;inset:0;z-index:9000;
  pointer-events:none;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 512 512' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='0.035'/%3E%3C/svg%3E");
  opacity:.6;
}

/* NAV */
nav{
  position:fixed;top:0;width:100%;z-index:500;
  padding:env(safe-area-inset-top,0) 0 0;
  background:linear-gradient(to bottom,rgba(8,5,3,.97) 0%,transparent 100%);
}
.nav-inner{
  display:flex;align-items:center;justify-content:space-between;
  padding:20px 24px;
}
.nav-logo{
  font-family:'Syncopate',sans-serif;
  font-weight:700;font-size:12px;letter-spacing:.2em;
  color:var(--text);text-decoration:none;
}
.nav-logo em{color:var(--red);font-style:normal;}
.nav-book{
  font-family:'Syncopate',sans-serif;
  font-size:9px;letter-spacing:.2em;text-transform:uppercase;
  padding:9px 20px;
  border:1px solid var(--red);
  color:var(--red);text-decoration:none;
  transition:background .2s,color .2s,box-shadow .2s;
}
.nav-book:hover,.nav-book:active{background:var(--red);color:#fff;box-shadow:0 0 20px var(--glow-r);}

/* HERO */
#hero{
  min-height:100svh;
  display:flex;flex-direction:column;justify-content:flex-end;
  padding:0 24px clamp(60px,12vh,100px);
  position:relative;overflow:hidden;
}
.hero-bg{
  position:absolute;inset:0;
  background:
    linear-gradient(to top,rgba(8,5,3,1) 0%,rgba(8,5,3,.6) 40%,rgba(8,5,3,.1) 100%),
    radial-gradient(ellipse at 65% 35%,rgba(217,58,26,.38) 0%,rgba(240,165,0,.1) 45%,transparent 70%),
    radial-gradient(ellipse at 20% 70%,rgba(217,58,26,.12) 0%,transparent 50%),
    #0f0b07;
}
.hero-rings{
  position:absolute;
  right:-100px;top:50%;transform:translateY(-50%);
  width:500px;height:500px;
  pointer-events:none;
}
.hr{
  position:absolute;border-radius:50%;border:1px solid;
  top:50%;left:50%;transform:translate(-50%,-50%);
}
.hr:nth-child(1){width:100px;height:100px;border-color:rgba(217,58,26,.6);animation:rspin 5s linear infinite;}
.hr:nth-child(2){width:190px;height:190px;border-color:rgba(217,58,26,.25);animation:rspin 9s linear infinite reverse;}
.hr:nth-child(3){width:300px;height:300px;border-color:rgba(240,165,0,.13);animation:rspin 14s linear infinite;}
.hr:nth-child(4){width:420px;height:420px;border-color:rgba(240,165,0,.07);animation:rspin 20s linear infinite reverse;}
.hr-dot{position:absolute;width:8px;height:8px;border-radius:50%;background:var(--red);box-shadow:0 0 14px var(--glow-r);top:50%;left:-4px;transform:translateY(-50%);}
@keyframes rspin{to{transform:translate(-50%,-50%) rotate(360deg);}}

.hero-content{position:relative;z-index:2;}
.hero-tag{
  font-family:'Syncopate',sans-serif;
  font-size:9px;letter-spacing:.35em;text-transform:uppercase;
  color:var(--amber);
  display:flex;align-items:center;gap:10px;
  margin-bottom:20px;opacity:0;
  animation:fadeup .8s .2s forwards;
}
.hero-tag::before{content:'';display:block;width:28px;height:1px;background:var(--amber);}
h1{
  font-family:'Bebas Neue',sans-serif;
  font-size:clamp(72px,20vw,180px);
  line-height:.88;letter-spacing:.02em;
  opacity:0;animation:fadeup .9s .35s forwards;
}
h1 .r{color:var(--red);}
.hero-sub{
  margin-top:22px;
  font-size:clamp(16px,4vw,20px);
  font-style:italic;line-height:1.6;
  color:var(--muted2);max-width:380px;
  opacity:0;animation:fadeup .9s .5s forwards;
}
.hero-cta{
  margin-top:36px;
  display:flex;flex-wrap:wrap;gap:14px;
  opacity:0;animation:fadeup .9s .65s forwards;
}
.btn-fire{
  font-family:'Syncopate',sans-serif;
  font-size:10px;letter-spacing:.2em;text-transform:uppercase;
  padding:15px 32px;
  background:var(--red);color:#fff;
  text-decoration:none;border:none;cursor:pointer;
  transition:box-shadow .3s,transform .2s,opacity .2s;
  -webkit-tap-highlight-color:transparent;display:inline-block;
}
.btn-fire:active{transform:scale(.97);}
.btn-fire:hover{box-shadow:0 0 32px var(--glow-r),0 0 64px rgba(217,58,26,.15);}
.btn-fire:disabled,.btn-next:disabled{opacity:.55;cursor:wait;box-shadow:none;}
.btn-outline{
  font-family:'Syncopate',sans-serif;
  font-size:10px;letter-spacing:.2em;text-transform:uppercase;
  padding:15px 32px;
  border:1px solid var(--border);
  color:var(--text);text-decoration:none;cursor:pointer;
  transition:border-color .25s,color .25s;
  -webkit-tap-highlight-color:transparent;display:inline-block;
}
.btn-outline:hover{border-color:var(--amber);color:var(--amber);}
@keyframes fadeup{from{opacity:0;transform:translateY(24px);}to{opacity:1;transform:translateY(0);}}

/* MARQUEE */
.marquee{
  padding:20px 0;overflow:hidden;white-space:nowrap;
  background:linear-gradient(90deg,var(--red),#b02d12,var(--red));
  background-size:200%;animation:gradshift 4s ease infinite;
}
@keyframes gradshift{0%,100%{background-position:0%;}50%{background-position:100%;}}
.marquee-track{display:inline-flex;animation:mq 20s linear infinite;}
.marquee-track span{font-family:'Bebas Neue',sans-serif;font-size:18px;letter-spacing:.15em;padding:0 28px;color:rgba(255,255,255,.92);}
.marquee-track .dot{color:rgba(255,255,255,.4);}
@keyframes mq{0%{transform:translateX(0);}100%{transform:translateX(-50%);}}

/* SHARED */
section{position:relative;z-index:1;}
.sec-pad{padding:80px 24px;}
.sec-label{
  font-family:'Syncopate',sans-serif;
  font-size:8px;letter-spacing:.4em;text-transform:uppercase;
  color:var(--red);margin-bottom:14px;
  display:flex;align-items:center;gap:10px;
}
.sec-label::before{content:'';display:block;width:24px;height:1px;background:var(--red);}
h2{font-family:'Bebas Neue',sans-serif;font-size:clamp(44px,10vw,88px);line-height:.92;letter-spacing:.02em;}
h2 .r{color:var(--red);}

/* ABOUT */
#about{background:var(--surface);}
.about-grid{display:grid;gap:48px;}
.about-visual{position:relative;aspect-ratio:4/3;background:var(--panel);overflow:hidden;}
.about-visual::before{
  content:'';position:absolute;inset:0;
  background:radial-gradient(ellipse at 60% 40%,rgba(217,58,26,.3) 0%,transparent 60%),
             radial-gradient(ellipse at 20% 80%,rgba(240,165,0,.15) 0%,transparent 50%);
}
.platter-wrap{position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);}
.platter{
  width:clamp(160px,40vw,220px);height:clamp(160px,40vw,220px);
  border-radius:50%;
  background:radial-gradient(circle at 40% 35%,#2a1a0e,#080503);
  border:1px solid rgba(217,58,26,.3);
  position:relative;
  animation:rspin 8s linear infinite;
  box-shadow:0 0 60px rgba(217,58,26,.2),inset 0 0 40px rgba(0,0,0,.8);
}
.platter::before{content:'';position:absolute;inset:20%;border-radius:50%;border:1px solid rgba(217,58,26,.2);}
.platter::after{content:'';position:absolute;width:14px;height:14px;border-radius:50%;top:50%;left:50%;transform:translate(-50%,-50%);background:var(--red);box-shadow:0 0 20px var(--glow-r);}
.groove{position:absolute;border-radius:50%;top:50%;left:50%;transform:translate(-50%,-50%);border:1px solid rgba(255,255,255,.04);}
.about-text h2{margin-bottom:20px;}
.about-text p{font-size:clamp(16px,4vw,18px);line-height:1.75;color:var(--muted2);margin-bottom:16px;}
.about-text p strong{color:var(--text);font-weight:400;}
.stat-row{display:flex;gap:32px;flex-wrap:wrap;margin-top:28px;padding-top:28px;border-top:1px solid var(--border);}
.stat-n{font-family:'Bebas Neue',sans-serif;font-size:44px;line-height:1;color:var(--text);}
.stat-n em{color:var(--red);font-style:normal;}
.stat-l{font-family:'Syncopate',sans-serif;font-size:8px;letter-spacing:.25em;text-transform:uppercase;color:var(--muted);margin-top:2px;}

/* SERVICES */
.svc-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:2px;margin-top:48px;}
.svc-card{
  background:var(--card);
  padding:clamp(24px,6vw,36px) clamp(20px,5vw,28px);
  border-top:2px solid transparent;
  transition:border-color .3s,background .3s;
  position:relative;overflow:hidden;
  -webkit-tap-highlight-color:transparent;
}
.svc-card:active,.svc-card:hover{border-color:var(--red);background:#201510;}
.svc-num{font-family:'Bebas Neue',sans-serif;font-size:56px;color:rgba(217,58,26,.07);position:absolute;top:8px;right:12px;line-height:1;}
.svc-icon{font-size:24px;margin-bottom:14px;}
.svc-card h3{font-family:'Syncopate',sans-serif;font-size:10px;letter-spacing:.12em;text-transform:uppercase;color:var(--text);margin-bottom:10px;}
.svc-card p{font-size:13px;line-height:1.65;color:var(--muted);}

/* LOCATIONS */
#locations{background:var(--surface);}
.loc-list{display:flex;flex-direction:column;gap:10px;margin-top:48px;}
.loc-item{
  background:linear-gradient(180deg,rgba(28,20,16,.96),rgba(22,16,9,.96));
  padding:24px 20px;
  display:flex;align-items:center;justify-content:space-between;
  border-left:2px solid transparent;
  border:1px solid rgba(240,165,0,.08);
  transition:border-color .25s,background .25s,transform .2s;
  -webkit-tap-highlight-color:transparent;
}
.loc-item:hover,.loc-item:active{border-color:var(--amber);background:#1a1608;transform:translateY(-1px);}
.loc-copy{display:flex;flex-direction:column;gap:7px;}
.loc-city{font-family:'Bebas Neue',sans-serif;font-size:clamp(28px,7vw,44px);line-height:1;color:var(--text);}
.loc-meta{display:flex;gap:10px;align-items:center;flex-wrap:wrap;}
.loc-state{font-family:'Syncopate',sans-serif;font-size:8px;letter-spacing:.3em;text-transform:uppercase;color:var(--red);}
.loc-badge{
  font-family:'Syncopate',sans-serif;font-size:7px;letter-spacing:.28em;text-transform:uppercase;
  padding:7px 10px;border:1px solid var(--border);color:var(--muted2);
  background:rgba(255,255,255,.02);
}
.loc-dot{
  width:10px;height:10px;border-radius:50%;background:rgba(240,165,0,.28);flex-shrink:0;
  box-shadow:0 0 0 rgba(240,165,0,0);
}
.loc-item.active-city{
  border-color:rgba(240,165,0,.32);
  box-shadow:inset 0 0 0 1px rgba(240,165,0,.06),0 0 24px rgba(240,165,0,.08);
}
.loc-item.active-city .loc-badge{
  border-color:rgba(240,165,0,.3);
  color:var(--ok);
  background:rgba(240,165,0,.08);
}
.loc-item.active-city .loc-dot{
  background:var(--amber);
  box-shadow:0 0 14px var(--glow-a);
  animation:pulse 2s ease-in-out infinite;
}
.loc-item.pending-city{opacity:.8;}
.loc-item.pending-city .loc-state{color:var(--muted2);}
.loc-item.pending-city .loc-badge{
  border-color:rgba(217,58,26,.14);
  color:#b7aba0;
}
.loc-item.pending-city .loc-dot{background:rgba(154,143,131,.35);}
@keyframes pulse{0%,100%{box-shadow:0 0 8px var(--glow-a);}50%{box-shadow:0 0 22px var(--glow-a);}}

/* BOOKING */
#booking{padding:80px 24px;padding-bottom:calc(80px + env(safe-area-inset-bottom,0));}
.booking-header{margin-bottom:48px;}
.booking-header p{font-size:clamp(17px,4vw,20px);font-style:italic;color:var(--muted2);margin-top:14px;line-height:1.6;max-width:500px;}
.booking-note{
  margin-top:20px;
  padding:14px 16px;
  border:1px solid var(--border);
  background:linear-gradient(180deg,rgba(28,20,16,.75),rgba(15,11,7,.75));
  color:var(--muted2);
  font-size:15px;
  line-height:1.55;
  max-width:620px;
}
.booking-note strong{color:var(--text);font-weight:400;}
.steps-bar{display:flex;gap:8px;margin-bottom:40px;}
.step-pip{flex:1;height:2px;background:var(--border);transition:background .4s;}
.step-pip.active{background:var(--red);}
.step-pip.done{background:var(--amber);}
.step-panel{display:none;animation:fadeup .5s forwards;}
.step-panel.active{display:block;}
.step-title{font-family:'Bebas Neue',sans-serif;font-size:clamp(32px,8vw,52px);line-height:1;margin-bottom:28px;color:var(--text);}
.step-title em{color:var(--red);font-style:normal;}

.event-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:10px;}
.event-card{
  background:var(--card);border:1px solid var(--border);
  padding:20px 16px;
  display:flex;flex-direction:column;align-items:center;gap:10px;
  cursor:pointer;
  transition:border-color .25s,background .25s,transform .15s,box-shadow .2s;
  -webkit-tap-highlight-color:transparent;user-select:none;
}
.event-card:active{transform:scale(.97);}
.event-card.selected{border-color:var(--red);background:#201410;box-shadow:0 0 0 1px rgba(217,58,26,.1);}
.event-card:hover{border-color:rgba(217,58,26,.5);}
.event-emoji{font-size:28px;line-height:1;}
.event-label{font-family:'Syncopate',sans-serif;font-size:8.5px;letter-spacing:.15em;text-transform:uppercase;color:var(--muted2);text-align:center;}
.event-card.selected .event-label{color:var(--text);}

.field-group{display:flex;flex-direction:column;gap:16px;margin-bottom:24px;}
.field{display:flex;flex-direction:column;gap:7px;}
.field label{font-family:'Syncopate',sans-serif;font-size:8px;letter-spacing:.3em;text-transform:uppercase;color:var(--muted);}
.field input,.field select,.field textarea{
  background:var(--panel);border:1px solid var(--border);
  color:var(--text);font-family:'Cormorant Garamond',serif;
  font-size:16px;font-weight:300;padding:14px 16px;
  outline:none;-webkit-appearance:none;
  transition:border-color .25s,box-shadow .25s;
  border-radius:0;width:100%;
}
.field input:focus,.field select:focus,.field textarea:focus{border-color:var(--red);box-shadow:0 0 0 3px rgba(217,58,26,.1);}
.field input::placeholder,.field textarea::placeholder{color:var(--muted);}
.field textarea{resize:vertical;min-height:100px;}
.field select option{background:var(--panel);}
.row2{display:grid;grid-template-columns:1fr 1fr;gap:12px;}
.step-nav{display:flex;gap:12px;margin-top:28px;flex-wrap:wrap;}
.btn-next{
  font-family:'Syncopate',sans-serif;font-size:10px;letter-spacing:.2em;text-transform:uppercase;
  padding:15px 32px;background:var(--red);color:#fff;border:none;cursor:pointer;
  transition:box-shadow .25s,transform .15s,opacity .2s;-webkit-tap-highlight-color:transparent;
}
.btn-next:active{transform:scale(.97);}
.btn-next:hover{box-shadow:0 0 28px var(--glow-r);}
.btn-back{
  font-family:'Syncopate',sans-serif;font-size:10px;letter-spacing:.2em;text-transform:uppercase;
  padding:15px 24px;background:transparent;border:1px solid var(--border);
  color:var(--muted);cursor:pointer;transition:border-color .2s,color .2s;
  -webkit-tap-highlight-color:transparent;
}
.btn-back:hover{border-color:var(--muted);color:var(--text);}
.form-status{
  min-height:24px;
  margin-top:14px;
  font-size:15px;
  color:var(--muted2);
}
.form-status.error{color:#ff9d89;}
.form-status.success{color:var(--ok);}

/* CONFIRMATION */
#confirm{
  display:none;position:fixed;inset:0;z-index:800;
  background:rgba(8,5,3,0);
  align-items:center;justify-content:center;padding:24px;
}
#confirm.show{display:flex;animation:confirmFade .8s forwards;}
@keyframes confirmFade{0%{background:rgba(8,5,3,0);}100%{background:rgba(8,5,3,.97);}}
.confirm-inner{
  text-align:center;max-width:480px;width:100%;
  position:relative;z-index:2;
  opacity:0;transform:translateY(30px);
  transition:opacity .9s .4s,transform .9s .4s;
}
#confirm.show .confirm-inner{opacity:1;transform:translateY(0);}
.confirm-orb{position:relative;width:160px;height:160px;margin:0 auto 36px;}
.c-ring{position:absolute;border-radius:50%;top:50%;left:50%;transform:translate(-50%,-50%);border:1px solid;}
.c-ring:nth-child(1){width:60px;height:60px;border-color:rgba(217,58,26,.8);background:radial-gradient(circle,rgba(217,58,26,.2),transparent);animation:rspin 3s linear infinite;}
.c-ring:nth-child(2){width:100px;height:100px;border-color:rgba(217,58,26,.35);animation:rspin 5s linear infinite reverse;}
.c-ring:nth-child(3){width:140px;height:140px;border-color:rgba(240,165,0,.2);animation:rspin 8s linear infinite;}
.c-ring:nth-child(4){width:160px;height:160px;border-color:rgba(240,165,0,.1);animation:rspin 12s linear infinite reverse;}
.c-center{position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);font-size:28px;animation:pulse 3s ease-in-out infinite;}
.confirm-eyebrow{font-family:'Syncopate',sans-serif;font-size:8px;letter-spacing:.4em;text-transform:uppercase;color:var(--amber);margin-bottom:16px;}
.confirm-title{font-family:'Bebas Neue',sans-serif;font-size:clamp(48px,14vw,80px);line-height:.9;color:var(--text);margin-bottom:6px;}
.confirm-title em{color:var(--red);font-style:normal;}
.confirm-sub{font-family:'Cormorant Garamond',serif;font-size:clamp(18px,5vw,22px);font-style:italic;line-height:1.6;color:var(--muted2);margin:20px auto;max-width:360px;}
.confirm-line{width:60px;height:1px;background:linear-gradient(90deg,transparent,var(--red),transparent);margin:24px auto;}
.confirm-note{font-family:'Syncopate',sans-serif;font-size:8px;letter-spacing:.3em;text-transform:uppercase;color:var(--muted);}
.confirm-close{
  margin-top:36px;font-family:'Syncopate',sans-serif;font-size:9px;letter-spacing:.2em;text-transform:uppercase;
  padding:12px 28px;border:1px solid var(--border2);color:var(--muted2);background:transparent;cursor:pointer;
  transition:border-color .2s,color .2s;-webkit-tap-highlight-color:transparent;
}
.confirm-close:hover{border-color:var(--red);color:var(--red);}
.particle{position:absolute;border-radius:50%;background:var(--red);pointer-events:none;animation:float-p linear infinite;opacity:0;}
@keyframes float-p{0%{transform:translateY(100vh) scale(0);opacity:0;}10%{opacity:.6;}90%{opacity:.3;}100%{transform:translateY(-10vh) scale(1);opacity:0;}}

/* FOOTER */
footer{background:var(--deep);padding:60px 24px calc(40px + env(safe-area-inset-bottom,0));border-top:1px solid var(--border);}
.footer-logo{font-family:'Bebas Neue',sans-serif;font-size:52px;line-height:1;letter-spacing:.04em;margin-bottom:8px;}
.footer-logo em{color:var(--red);font-style:normal;}
.footer-sub{font-size:12px;letter-spacing:.08em;color:var(--muted);margin-bottom:36px;}
.footer-grid{display:grid;grid-template-columns:1fr 1fr;gap:32px;margin-bottom:40px;}
.footer-col h4{font-family:'Syncopate',sans-serif;font-size:8px;letter-spacing:.3em;text-transform:uppercase;color:var(--amber);margin-bottom:14px;}
.footer-col ul{list-style:none;display:flex;flex-direction:column;gap:10px;}
.footer-col a{font-size:14px;color:var(--muted);text-decoration:none;transition:color .2s;}
.footer-col a:hover{color:var(--text);}
.footer-bottom{padding-top:24px;border-top:1px solid var(--border);display:flex;flex-direction:column;gap:16px;}
.footer-bottom p{font-size:11px;color:var(--muted);}
.social-row{display:flex;gap:12px;}
.soc{width:36px;height:36px;border:1px solid var(--border);display:flex;align-items:center;justify-content:center;color:var(--muted);text-decoration:none;font-size:11px;font-family:'Syncopate',sans-serif;transition:border-color .2s,color .2s;}
.soc:hover{border-color:var(--red);color:var(--red);}

/* REVEAL */
.reveal{opacity:0;transform:translateY(28px);transition:opacity .8s cubic-bezier(.23,1,.32,1),transform .8s cubic-bezier(.23,1,.32,1);}
.reveal.on{opacity:1;transform:translateY(0);}

/* DESKTOP */
@media(min-width:768px){
  .nav-inner{padding:24px 60px;}
  .sec-pad{padding:120px 60px;}
  #hero{padding:0 60px clamp(80px,14vh,120px);}
  .about-grid{grid-template-columns:1fr 1fr;align-items:center;gap:80px;}
  .about-visual{aspect-ratio:unset;height:480px;}
  .svc-grid{grid-template-columns:repeat(3,1fr);}
  .event-grid{grid-template-columns:repeat(4,1fr);}
  .footer-grid{grid-template-columns:repeat(4,1fr);}
  .footer-bottom{flex-direction:row;justify-content:space-between;align-items:center;}
  #booking{padding:120px 60px;}
  .hero-rings{right:-40px;}
}
</style>
</head>
<body>

<nav>
  <div class="nav-inner">
    <a href="#" class="nav-logo">B<em>.</em>MUHOYA</a>
    <a href="#booking" class="nav-book">Book Now</a>
  </div>
</nav>

<section id="hero">
  <div class="hero-bg">
    <div class="hero-rings">
      <div class="hr"><div class="hr-dot"></div></div>
      <div class="hr"></div>
      <div class="hr"></div>
      <div class="hr"></div>
    </div>
  </div>
  <div class="hero-content">
    <div class="hero-tag">Princeton, NJ · Nationwide</div>
    <h1><span class="r">Benjamin</span><br>Muhoya</h1>
    <p class="hero-sub">DJ. Event Host. The energy your event has been missing.</p>
    <div class="hero-cta">
      <a href="#booking" class="btn-fire">Book Your Event</a>
      <a href="#about" class="btn-outline">Learn More</a>
    </div>
  </div>
</section>

<div class="marquee">
  <div class="marquee-track">
    <span>DJ SETS</span><span class="dot">✦</span>
    <span>WEDDINGS</span><span class="dot">✦</span>
    <span>CORPORATE</span><span class="dot">✦</span>
    <span>BIRTHDAYS</span><span class="dot">✦</span>
    <span>GRADUATIONS</span><span class="dot">✦</span>
    <span>BABY SHOWERS</span><span class="dot">✦</span>
    <span>CLUB NIGHTS</span><span class="dot">✦</span>
    <span>PRIVATE PARTIES</span><span class="dot">✦</span>
    <span>DJ SETS</span><span class="dot">✦</span>
    <span>WEDDINGS</span><span class="dot">✦</span>
    <span>CORPORATE</span><span class="dot">✦</span>
    <span>BIRTHDAYS</span><span class="dot">✦</span>
    <span>GRADUATIONS</span><span class="dot">✦</span>
    <span>BABY SHOWERS</span><span class="dot">✦</span>
    <span>CLUB NIGHTS</span><span class="dot">✦</span>
    <span>PRIVATE PARTIES</span><span class="dot">✦</span>
  </div>
</div>

<section id="about" class="sec-pad">
  <div class="about-grid">
    <div class="about-visual reveal">
      <div class="platter-wrap">
        <div class="platter">
          <div class="groove" style="width:60%;height:60%"></div>
          <div class="groove" style="width:75%;height:75%"></div>
          <div class="groove" style="width:88%;height:88%"></div>
        </div>
      </div>
    </div>
    <div class="about-text reveal">
      <div class="sec-label">Who We Are</div>
      <h2>The Man<br>Behind the<br><span class="r">Decks</span></h2>
      <p>Based out of <strong>Princeton, NJ</strong>, Benjamin Muhoya has spent over a decade commanding dancefloors and curating moments people never forget.</p>
      <p>With a roster of elite DJs across <strong>New York, LA, San Diego, Berkeley, and Oakland</strong> — we match every event with exactly the right energy.</p>
      <div class="stat-row">
        <div class="stat-box">
          <div class="stat-n">500<em>+</em></div>
          <div class="stat-l">Events</div>
        </div>
        <div class="stat-box">
          <div class="stat-n">6<em>+</em></div>
          <div class="stat-l">Cities</div>
        </div>
        <div class="stat-box">
          <div class="stat-n">10<em>yr</em></div>
          <div class="stat-l">Experience</div>
        </div>
      </div>
    </div>
  </div>
</section>

<section id="services" class="sec-pad">
  <div class="sec-label">What We Do</div>
  <h2>Our <span class="r">Services</span></h2>
  <div class="svc-grid">
    <div class="svc-card reveal"><div class="svc-num">01</div><div class="svc-icon">🎛️</div><h3>Live DJ Sets</h3><p>Tailored sets for your crowd — hip-hop, Afrobeats, house, R&B, top 40 and everything between.</p></div>
    <div class="svc-card reveal"><div class="svc-num">02</div><div class="svc-icon">🎤</div><h3>Event Hosting</h3><p>Charismatic MC services to anchor your event and keep energy at its peak all night.</p></div>
    <div class="svc-card reveal"><div class="svc-num">03</div><div class="svc-icon">💼</div><h3>Corporate Events</h3><p>Product launches, galas, brand activations — professional sound that impresses every guest.</p></div>
    <div class="svc-card reveal"><div class="svc-num">04</div><div class="svc-icon">💍</div><h3>Weddings</h3><p>From first dance to last song — every musical moment handled with heart and precision.</p></div>
    <div class="svc-card reveal"><div class="svc-num">05</div><div class="svc-icon">🎂</div><h3>Celebrations</h3><p>Birthdays, graduations, baby showers — we make every milestone hit different.</p></div>
    <div class="svc-card reveal"><div class="svc-num">06</div><div class="svc-icon">🔊</div><h3>DJ Bookings</h3><p>Tap into our nationwide roster. We find the perfect DJ for your budget and city.</p></div>
  </div>
</section>

<section id="locations" class="sec-pad">
  <div class="sec-label">Where We Are</div>
  <h2>Our <span class="r">Locations</span></h2>
  <div class="loc-list">
    <div class="loc-item active-city reveal">
      <div class="loc-copy">
        <div class="loc-city">New York</div>
        <div class="loc-meta">
          <div class="loc-state">New York · Flagship City</div>
          <div class="loc-badge">Active</div>
        </div>
      </div>
      <div class="loc-dot" aria-hidden="true"></div>
    </div>
    <div class="loc-item pending-city reveal">
      <div class="loc-copy">
        <div class="loc-city">Los Angeles</div>
        <div class="loc-meta">
          <div class="loc-state">California</div>
          <div class="loc-badge">Pending</div>
        </div>
      </div>
      <div class="loc-dot" aria-hidden="true"></div>
    </div>
    <div class="loc-item pending-city reveal">
      <div class="loc-copy">
        <div class="loc-city">San Diego</div>
        <div class="loc-meta">
          <div class="loc-state">California</div>
          <div class="loc-badge">Pending</div>
        </div>
      </div>
      <div class="loc-dot" aria-hidden="true"></div>
    </div>
    <div class="loc-item pending-city reveal">
      <div class="loc-copy">
        <div class="loc-city">Berkeley</div>
        <div class="loc-meta">
          <div class="loc-state">California · Bay Area</div>
          <div class="loc-badge">Pending</div>
        </div>
      </div>
      <div class="loc-dot" aria-hidden="true"></div>
    </div>
    <div class="loc-item pending-city reveal">
      <div class="loc-copy">
        <div class="loc-city">Oakland</div>
        <div class="loc-meta">
          <div class="loc-state">California · East Bay</div>
          <div class="loc-badge">Pending</div>
        </div>
      </div>
      <div class="loc-dot" aria-hidden="true"></div>
    </div>
  </div>
</section>

<section id="booking">
  <div class="booking-header reveal">
    <div class="sec-label">Let's Make It Happen</div>
    <h2>Book Your <span class="r">Event</span></h2>
    <p>Tell us about your vibe and we'll take it from there.</p>
    <div class="booking-note">
      <strong>Supabase-ready intake:</strong> submissions from this form will be sent into your database and also saved locally in the browser as a backup.
    </div>
  </div>

  <div class="steps-bar">
    <div class="step-pip active" id="pip1"></div>
    <div class="step-pip" id="pip2"></div>
    <div class="step-pip" id="pip3"></div>
  </div>

  <div class="step-panel active" id="step1">
    <div class="step-title">What's the <em>occasion?</em></div>
    <div class="event-grid">
      <div class="event-card" data-val="Birthday"><div class="event-emoji">🎂</div><div class="event-label">Birthday</div></div>
      <div class="event-card" data-val="Wedding"><div class="event-emoji">💍</div><div class="event-label">Wedding</div></div>
      <div class="event-card" data-val="Graduation"><div class="event-emoji">🎓</div><div class="event-label">Graduation</div></div>
      <div class="event-card" data-val="Baby Shower"><div class="event-emoji">🍼</div><div class="event-label">Baby Shower</div></div>
      <div class="event-card" data-val="Corporate"><div class="event-emoji">💼</div><div class="event-label">Corporate</div></div>
      <div class="event-card" data-val="Club Night"><div class="event-emoji">🔊</div><div class="event-label">Club Night</div></div>
      <div class="event-card" data-val="House Party"><div class="event-emoji">🏠</div><div class="event-label">House Party</div></div>
      <div class="event-card" data-val="Other"><div class="event-emoji">✨</div><div class="event-label">Other</div></div>
    </div>
    <div class="step-nav">
      <button class="btn-next" type="button" onclick="goStep(2)">Next →</button>
    </div>
  </div>

  <div class="step-panel" id="step2">
    <div class="step-title">Tell us the <em>details</em></div>
    <div class="field-group">
      <div class="row2">
        <div class="field"><label for="fname">First Name</label><input type="text" id="fname" placeholder="Your name" autocomplete="given-name"/></div>
        <div class="field"><label for="lname">Last Name</label><input type="text" id="lname" placeholder="Last name" autocomplete="family-name"/></div>
      </div>
      <div class="field"><label for="email">Email</label><input type="email" id="email" placeholder="your@email.com" autocomplete="email"/></div>
      <div class="field"><label for="phone">Phone</label><input type="tel" id="phone" placeholder="+1 (000) 000-0000" autocomplete="tel"/></div>
      <div class="row2">
        <div class="field"><label for="edate">Event Date</label><input type="date" id="edate"/></div>
        <div class="field"><label for="guests">Guest Count</label><input type="number" id="guests" placeholder="e.g. 80"/></div>
      </div>
      <div class="field">
        <label for="city">City</label>
        <select id="city">
          <option value="" disabled selected>Select a city</option>
          <option>New York, NY</option>
          <option>Los Angeles, CA</option>
          <option>San Diego, CA</option>
          <option>Berkeley, CA</option>
          <option>Oakland, CA</option>
          <option>Princeton, NJ</option>
          <option>Other</option>
        </select>
      </div>
    </div>
    <div class="step-nav">
      <button class="btn-back" type="button" onclick="goStep(1)">← Back</button>
      <button class="btn-next" type="button" onclick="goStep(3)">Next →</button>
    </div>
  </div>

  <div class="step-panel" id="step3">
    <div class="step-title">Almost <em>there...</em></div>
    <div class="field-group">
      <div class="field">
        <label for="vibe">Music Vibe</label>
        <select id="vibe">
          <option value="" disabled selected>What's the energy?</option>
          <option>Hip-Hop / Rap</option>
          <option>Afrobeats / Dancehall</option>
          <option>R&B / Soul</option>
          <option>House / Electronic</option>
          <option>Top 40 / Pop</option>
          <option>Latin / Reggaeton</option>
          <option>Mixed / Surprise Me</option>
        </select>
      </div>
      <div class="field">
        <label for="budget">Budget Range</label>
        <select id="budget">
          <option value="" disabled selected>Approximate budget</option>
          <option>Under $500</option>
          <option>$500 - $1,000</option>
          <option>$1,000 - $2,500</option>
          <option>$2,500 - $5,000</option>
          <option>$5,000+</option>
        </select>
      </div>
      <div class="field">
        <label for="notes">Anything else we should know?</label>
        <textarea id="notes" placeholder="Venue, special requests, themes..."></textarea>
      </div>
    </div>
    <div class="step-nav">
      <button class="btn-back" type="button" onclick="goStep(2)">← Back</button>
      <button class="btn-next" type="button" id="submitBtn" onclick="submitBooking()">Send It</button>
    </div>
    <div class="form-status" id="formStatus" aria-live="polite"></div>
  </div>
</section>

<div id="confirm">
  <div class="confirm-inner">
    <div class="confirm-orb">
      <div class="c-ring"></div>
      <div class="c-ring"></div>
      <div class="c-ring"></div>
      <div class="c-ring"></div>
      <div class="c-center">🎛️</div>
    </div>
    <div class="confirm-eyebrow">Transmission Received</div>
    <div class="confirm-title">We'll be<br>in <em>touch.</em></div>
    <div class="confirm-line"></div>
    <p class="confirm-sub">Something is already in motion. Benjamin will reach out to you personally within 24 hours.</p>
    <div class="confirm-note">Watch your inbox. Good things are coming.</div>
    <button class="confirm-close" type="button" onclick="closeConfirm()">Return to the site</button>
  </div>
</div>

<footer>
  <div class="footer-logo">B<em>.</em>MUHOYA</div>
  <div class="footer-sub">DJ · Event Host · Booking Service · Princeton, NJ</div>
  <div class="footer-grid">
    <div class="footer-col"><h4>Navigate</h4><ul><li><a href="#about">About</a></li><li><a href="#services">Services</a></li><li><a href="#locations">Locations</a></li><li><a href="#booking">Booking</a></li></ul></div>
    <div class="footer-col"><h4>Services</h4><ul><li><a href="#">Live DJ Sets</a></li><li><a href="#">Weddings</a></li><li><a href="#">Corporate</a></li><li><a href="#">Celebrations</a></li></ul></div>
    <div class="footer-col"><h4>Cities</h4><ul><li><a href="#">New York</a></li><li><a href="#">Los Angeles</a></li><li><a href="#">San Diego</a></li><li><a href="#">Oakland</a></li></ul></div>
    <div class="footer-col"><h4>Contact</h4><ul><li><a href="mailto:bookings@benjaminmuhoya.com">Email Us</a></li><li><a href="tel:+16095550182">+1 (609) 555-0182</a></li></ul></div>
  </div>
  <div class="footer-bottom">
    <p>© 2025 Benjamin Muhoya. All Rights Reserved.</p>
    <div class="social-row">
      <a class="soc" href="#">IG</a>
      <a class="soc" href="#">X</a>
      <a class="soc" href="#">SC</a>
      <a class="soc" href="#">TT</a>
    </div>
  </div>
</footer>

<script type="module">
import { createClient } from 'https://cdn.jsdelivr.net/npm/@supabase/supabase-js/+esm';

const STORAGE_KEY = 'bm_bookings';
const SUPABASE_CONFIG = {
  url: 'https://mcuswctumkazxdrcgzfq.supabase.co',
  anonKey: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Im1jdXN3Y3R1bWthenhkcmNnemZxIiwicm9sZSI6ImFub24iLCJpYXQiOjE3NzY4MzMyMzUsImV4cCI6MjA5MjQwOTIzNX0.gDXVTmGAvvS8tWyXbENcOHn-N_aAe3NJcBL97tFGwxM',
  table: 'booking_requests'
};

const formStatus = document.getElementById('formStatus');
const submitBtn = document.getElementById('submitBtn');
let selectedEvent = '';
let supabase = null;

function getBookings(){
  try{return JSON.parse(localStorage.getItem(STORAGE_KEY)||'[]');}
  catch(e){return[];}
}

function saveBookingLocal(booking){
  const all = getBookings();
  all.unshift(booking);
  localStorage.setItem(STORAGE_KEY, JSON.stringify(all));
}

function getSupabaseClient(){
  if(!supabase){
    supabase = createClient(SUPABASE_CONFIG.url, SUPABASE_CONFIG.anonKey);
  }
  return supabase;
}

function setStatus(message, type=''){
  formStatus.textContent = message;
  formStatus.className = 'form-status' + (type ? ' ' + type : '');
}

function resetStatus(){
  setStatus('');
}

document.querySelectorAll('.event-card').forEach(card=>{
  card.addEventListener('click',()=>{
    document.querySelectorAll('.event-card').forEach(c=>c.classList.remove('selected'));
    card.classList.add('selected');
    selectedEvent = card.dataset.val;
    resetStatus();
  });
});

window.goStep = function goStep(n){
  if(n===2 && !selectedEvent){
    alert('Please choose an event type first.');
    return;
  }
  document.querySelectorAll('.step-panel').forEach(p=>p.classList.remove('active'));
  document.getElementById('step'+n).classList.add('active');
  for(let i=1;i<=3;i++){
    const pip = document.getElementById('pip'+i);
    pip.classList.remove('active','done');
    if(i===n) pip.classList.add('active');
    if(i<n) pip.classList.add('done');
  }
  resetStatus();
  document.getElementById('booking').scrollIntoView({behavior:'smooth',block:'start'});
};

function collectBooking(){
  return {
    submitted_at: new Date().toISOString(),
    event_type: selectedEvent,
    first_name: document.getElementById('fname').value.trim(),
    last_name: document.getElementById('lname').value.trim(),
    email: document.getElementById('email').value.trim(),
    phone: document.getElementById('phone').value.trim(),
    event_date: document.getElementById('edate').value || null,
    guest_count: document.getElementById('guests').value ? Number(document.getElementById('guests').value) : null,
    city: document.getElementById('city').value,
    vibe: document.getElementById('vibe').value,
    budget: document.getElementById('budget').value,
    notes: document.getElementById('notes').value.trim()
  };
}

function validateBooking(booking){
  if(!booking.event_type) return { ok:false, message:'Please choose an event type first.', step:1 };
  if(!booking.first_name || !booking.email) return { ok:false, message:'Please fill in at least your first name and email.', step:2 };
  return { ok:true };
}

async function saveBookingToSupabase(booking){
  const client = getSupabaseClient();
  const payload = {
    ...booking,
    status: 'new',
    source: 'website'
  };
  const { error } = await client.from(SUPABASE_CONFIG.table).insert(payload);
  if(error) throw error;
}

window.submitBooking = async function submitBooking(){
  const booking = collectBooking();
  const validation = validateBooking(booking);

  if(!validation.ok){
    setStatus(validation.message, 'error');
    goStep(validation.step);
    return;
  }

  submitBtn.disabled = true;
  setStatus('Sending your request...');

  const localBackup = {
    id: Date.now(),
    ...booking,
    submitted: new Date().toLocaleString()
  };

  try{
    saveBookingLocal(localBackup);
    await saveBookingToSupabase(booking);
    setStatus('Request sent successfully.', 'success');
    showConfirm();
  }catch(error){
    console.error('Booking submission failed:', error);
    setStatus('Submission failed. Check the browser console for the exact error.', 'error');
  }finally{
    submitBtn.disabled = false;
  }
};

function showConfirm(){
  const el = document.getElementById('confirm');
  el.classList.add('show');
  document.body.style.overflow = 'hidden';
  spawnParticles();
}

window.closeConfirm = function closeConfirm(){
  document.getElementById('confirm').classList.remove('show');
  document.body.style.overflow = '';
  goStep(1);
  selectedEvent = '';
  resetStatus();
  document.querySelectorAll('.event-card').forEach(c=>c.classList.remove('selected'));
  document.querySelectorAll('input,textarea').forEach(i=>i.value='');
  document.querySelectorAll('select').forEach(s=>s.selectedIndex=0);
};

function spawnParticles(){
  const el = document.getElementById('confirm');
  for(let i=0;i<20;i++){
    const p = document.createElement('div');
    p.classList.add('particle');
    const size = Math.random()*6+3;
    p.style.cssText = `width:${size}px;height:${size}px;left:${Math.random()*100}%;bottom:0;animation-duration:${Math.random()*3+2.5}s;animation-delay:${Math.random()*2}s;background:${Math.random()>.5?'var(--red)':'var(--amber)'};`;
    el.appendChild(p);
    setTimeout(()=>p.remove(),6000);
  }
}

const io = new IntersectionObserver(entries=>{
  entries.forEach(e=>{
    if(e.isIntersecting){
      e.target.classList.add('on');
      io.unobserve(e.target);
    }
  });
},{threshold:.1});

document.querySelectorAll('.reveal').forEach(el=>io.observe(el));

window.viewBookings = function(){
  const b = getBookings();
  if(!b.length){
    console.log('No bookings yet.');
    return;
  }
  console.table(b);
  console.log('\nFull data:\n',JSON.stringify(b,null,2));
};
</script>
</body>
</html>    first_name: document.getElementById('fname').value.trim(),
    last_name: document.getElementById('lname').value.trim(),
    email: document.getElementById('email').value.trim(),
    phone: document.getElementById('phone').value.trim(),
    event_date: document.getElementById('edate').value || null,
    guest_count: document.getElementById('guests').value ? Number(document.getElementById('guests').value) : null,
    city: document.getElementById('city').value,
    vibe: document.getElementById('vibe').value,
    budget: document.getElementById('budget').value,
    notes: document.getElementById('notes').value.trim()
  };
}

function validateBooking(booking){
  if(!booking.event_type) return { ok:false, message:'Please choose an event type first.', step:1 };
  if(!booking.first_name || !booking.email) return { ok:false, message:'Please fill in at least your first name and email.', step:2 };
  return { ok:true };
}

async function saveBookingToSupabase(booking){
  const client = getSupabaseClient();
  if(!client) return { saved:false, mode:'local-only' };

  const payload = {
    ...booking,
    status: 'new',
    source: 'website'
  };

  const { error } = await client.from(SUPABASE_CONFIG.table).insert(payload);
  if(error) throw error;
  return { saved:true, mode:'supabase' };
}

window.submitBooking = async function submitBooking(){
  const booking = collectBooking();
  const validation = validateBooking(booking);

  if(!validation.ok){
    setStatus(validation.message, 'error');
    goStep(validation.step);
    return;
  }

  submitBtn.disabled = true;
  setStatus('Sending your request...', '');

  const localBackup = {
    id: Date.now(),
    ...booking,
    submitted: new Date().toLocaleString()
  };

  try{
    saveBookingLocal(localBackup);
    const result = await saveBookingToSupabase(booking);
    setStatus(
      result.mode === 'supabase'
        ? 'Request sent successfully.'
        : 'Saved locally for now. Add your Supabase keys to start collecting live submissions.',
      'success'
    );
    showConfirm();
  }catch(error){
    console.error('Booking submission failed:', error);
    setStatus('Your request was saved locally, but the live database connection needs attention.', 'error');
    showConfirm();
  }finally{
    submitBtn.disabled = false;
  }
};

function showConfirm(){
  const el=document.getElementById('confirm');
  el.classList.add('show');
  document.body.style.overflow='hidden';
  spawnParticles();
}

window.closeConfirm = function closeConfirm(){
  document.getElementById('confirm').classList.remove('show');
  document.body.style.overflow='';
  goStep(1);
  selectedEvent='';
  resetStatus();
  document.querySelectorAll('.event-card').forEach(c=>c.classList.remove('selected'));
  document.querySelectorAll('input,textarea').forEach(i=>i.value='');
  document.querySelectorAll('select').forEach(s=>s.selectedIndex=0);
};

function spawnParticles(){
  const el=document.getElementById('confirm');
  for(let i=0;i<20;i++){
    const p=document.createElement('div');
    p.classList.add('particle');
    const size=Math.random()*6+3;
    p.style.cssText=`width:${size}px;height:${size}px;left:${Math.random()*100}%;bottom:0;animation-duration:${Math.random()*3+2.5}s;animation-delay:${Math.random()*2}s;background:${Math.random()>.5?'var(--red)':'var(--amber)'};`;
    el.appendChild(p);
    setTimeout(()=>p.remove(),6000);
  }
}

const io=new IntersectionObserver(entries=>{
  entries.forEach(e=>{
    if(e.isIntersecting){
      e.target.classList.add('on');
      io.unobserve(e.target);
    }
  });
},{threshold:.1});

document.querySelectorAll('.reveal').forEach(el=>io.observe(el));

window.viewBookings=function(){
  const b=getBookings();
  if(!b.length){
    console.log('No bookings yet.');
    return;
  }
  console.table(b);
  console.log('\nFull data:\n',JSON.stringify(b,null,2));
};

window.supabaseSetupHelp = function supabaseSetupHelp(){
  console.log(`1. Create a table named "${SUPABASE_CONFIG.table}" in Supabase.
2. Add columns that match the booking payload fields:
   submitted_at, event_type, first_name, last_name, email, phone,
   event_date, guest_count, city, vibe, budget, notes, status, source
3. Replace SUPABASE_CONFIG.url and SUPABASE_CONFIG.anonKey in this file.
4. Enable an insert policy for anonymous users if you're using Row Level Security.`);
};
</script>
</body>
</html>
