<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<title>IronEdge | Elite Fitness Faridabad</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Barlow+Condensed:ital,wght@0,300;0,400;0,600;0,700;1,300;1,700&family=Barlow:wght@300;400;500&display=swap" rel="stylesheet"/>
<style>
:root {
  --red: #E8160C;
  --red-dim: rgba(232,22,12,0.15);
  --red-glow: rgba(232,22,12,0.4);
  --black: #050505;
  --deep: #0A0A0A;
  --surface: #111111;
  --surface2: #181818;
  --text: #F0EDE8;
  --text-muted: rgba(240,237,232,0.45);
  --border: rgba(232,22,12,0.15);
  --gold: #C9A84C;
}
*{margin:0;padding:0;box-sizing:border-box;}
html{scroll-behavior:smooth;}
body{font-family:'Barlow',sans-serif;background:var(--black);color:var(--text);overflow-x:hidden;cursor:none;}

/* CURSOR */
.cursor{position:fixed;width:8px;height:8px;background:var(--red);border-radius:50%;pointer-events:none;z-index:9999;transform:translate(-50%,-50%);transition:transform 0.1s;}
.cursor-ring{position:fixed;width:32px;height:32px;border:1px solid rgba(232,22,12,0.6);border-radius:50%;pointer-events:none;z-index:9998;transform:translate(-50%,-50%);transition:transform 0.4s ease,width 0.3s,height 0.3s;}

/* SCROLL REVEAL */
.reveal{opacity:0;transform:translateY(50px);transition:opacity 0.9s ease,transform 0.9s ease;}
.reveal.visible{opacity:1;transform:translateY(0);}
.reveal-left{opacity:0;transform:translateX(-60px);transition:opacity 0.9s ease,transform 0.9s ease;}
.reveal-left.visible{opacity:1;transform:translateX(0);}
.reveal-right{opacity:0;transform:translateX(60px);transition:opacity 0.9s ease,transform 0.9s ease;}
.reveal-right.visible{opacity:1;transform:translateX(0);}

/* NAV */
nav{position:fixed;top:0;left:0;right:0;z-index:500;display:flex;justify-content:space-between;align-items:center;padding:1.6rem 6%;transition:all 0.4s;}
nav.scrolled{background:rgba(5,5,5,0.97);backdrop-filter:blur(20px);padding:1rem 6%;border-bottom:1px solid var(--border);}
.nav-logo{font-family:'Bebas Neue',sans-serif;font-size:2.2rem;color:var(--text);letter-spacing:4px;}
.nav-logo span{color:var(--red);}
nav ul{list-style:none;display:flex;gap:2.5rem;align-items:center;}
nav ul a{text-decoration:none;color:var(--text-muted);font-family:'Barlow Condensed',sans-serif;font-size:0.85rem;font-weight:600;letter-spacing:3px;text-transform:uppercase;transition:color 0.2s;position:relative;}
nav ul a::after{content:'';position:absolute;bottom:-4px;left:0;width:0;height:2px;background:var(--red);transition:width 0.3s;}
nav ul a:hover{color:var(--red);}
nav ul a:hover::after{width:100%;}
.nav-join{background:var(--red)!important;color:var(--text)!important;padding:0.6rem 1.6rem;letter-spacing:2px;transition:background 0.2s!important;}
.nav-join:hover{background:#ff2218!important;}
.nav-join::after{display:none!important;}

/* HERO */
.hero{min-height:100vh;position:relative;display:flex;align-items:center;overflow:hidden;}
.hero-bg{position:absolute;inset:0;background:url('https://images.pexels.com/photos/1552252/pexels-photo-1552252.jpeg?auto=compress&cs=tinysrgb&w=1600') center/cover no-repeat;}
.hero-bg::after{content:'';position:absolute;inset:0;background:linear-gradient(105deg,rgba(5,5,5,0.96) 0%,rgba(5,5,5,0.75) 50%,rgba(5,5,5,0.3) 100%);}
/* Red diagonal slash */
.hero-slash{position:absolute;top:0;right:28%;bottom:0;width:3px;background:linear-gradient(to bottom,transparent,var(--red),transparent);opacity:0.6;transform:skewX(-8deg);}
.hero-content{position:relative;z-index:2;padding:0 6%;padding-top:100px;max-width:900px;}
.hero-eyebrow{display:inline-flex;align-items:center;gap:1rem;font-family:'Barlow Condensed',sans-serif;font-size:0.8rem;letter-spacing:5px;text-transform:uppercase;color:var(--red);margin-bottom:1.8rem;animation:fadeUp 1s 0.2s both;}
.hero-eyebrow::before{content:'';width:40px;height:2px;background:var(--red);}
.hero h1{font-family:'Bebas Neue',sans-serif;font-size:clamp(5rem,10vw,10rem);line-height:0.9;color:var(--text);margin-bottom:2rem;animation:fadeUp 1s 0.35s both;}
.hero h1 span{color:var(--red);display:block;}
.hero-desc{font-size:1.05rem;color:var(--text-muted);line-height:1.8;max-width:480px;margin-bottom:3rem;font-weight:300;animation:fadeUp 1s 0.5s both;}
.hero-actions{display:flex;gap:1.2rem;animation:fadeUp 1s 0.65s both;}
.btn-red{background:var(--red);color:var(--text);padding:1rem 2.8rem;border:none;font-family:'Barlow Condensed',sans-serif;font-size:0.9rem;font-weight:700;letter-spacing:3px;text-transform:uppercase;cursor:pointer;text-decoration:none;display:inline-block;transition:background 0.2s,transform 0.2s;clip-path:polygon(0 0,calc(100% - 12px) 0,100% 100%,12px 100%);}
.btn-red:hover{background:#ff2218;transform:translateY(-2px);}
.btn-outline{border:1px solid rgba(240,237,232,0.25);color:var(--text);padding:1rem 2.8rem;font-family:'Barlow Condensed',sans-serif;font-size:0.9rem;font-weight:600;letter-spacing:3px;text-transform:uppercase;cursor:pointer;text-decoration:none;display:inline-block;transition:border-color 0.2s,color 0.2s;background:transparent;clip-path:polygon(12px 0,100% 0,calc(100% - 12px) 100%,0 100%);}
.btn-outline:hover{border-color:var(--red);color:var(--red);}

/* TICKER */
.ticker{background:var(--red);padding:0.75rem 0;overflow:hidden;white-space:nowrap;}
.ticker-inner{display:inline-block;animation:ticker 18s linear infinite;}
.ticker-inner span{font-family:'Bebas Neue',sans-serif;font-size:1.1rem;letter-spacing:4px;margin:0 3rem;color:var(--text);}
.ticker-inner span::before{content:'✦';margin-right:3rem;opacity:0.6;}
@keyframes ticker{from{transform:translateX(0);}to{transform:translateX(-50%);}}

/* STATS */
.stats{background:var(--deep);border-bottom:1px solid var(--border);padding:5rem 6%;}
.stats-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:1px;background:var(--border);max-width:1200px;margin:0 auto;}
.stat-box{background:var(--deep);padding:3rem 2rem;text-align:center;position:relative;transition:background 0.3s;}
.stat-box:hover{background:var(--surface);}
.stat-box::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;background:var(--red);transform:scaleX(0);transition:transform 0.4s;transform-origin:left;}
.stat-box:hover::before{transform:scaleX(1);}
.stat-num{font-family:'Bebas Neue',sans-serif;font-size:4.5rem;color:var(--red);line-height:1;}
.stat-label{font-family:'Barlow Condensed',sans-serif;font-size:0.78rem;letter-spacing:3px;text-transform:uppercase;color:var(--text-muted);margin-top:0.5rem;}

/* ABOUT */
.about{display:grid;grid-template-columns:1fr 1fr;max-width:100%;min-height:600px;}
.about-visual{position:relative;overflow:hidden;}
.about-visual img{width:100%;height:100%;object-fit:cover;display:block;filter:grayscale(20%);}
.about-visual::after{content:'';position:absolute;inset:0;background:linear-gradient(to right,transparent 60%,var(--black));}
/* Red accent bar */
.about-visual::before{content:'FORGE YOUR BODY';position:absolute;top:50%;left:-30px;transform:translateY(-50%) rotate(-90deg);font-family:'Bebas Neue',sans-serif;font-size:0.9rem;letter-spacing:8px;color:var(--red);opacity:0.5;white-space:nowrap;z-index:2;}
.about-content{background:var(--black);padding:6rem 8%;display:flex;flex-direction:column;justify-content:center;}
.about-tag{font-family:'Barlow Condensed',sans-serif;font-size:0.78rem;letter-spacing:5px;text-transform:uppercase;color:var(--red);margin-bottom:1.2rem;display:flex;align-items:center;gap:0.8rem;}
.about-tag::before{content:'';width:30px;height:2px;background:var(--red);}
.about h2{font-family:'Bebas Neue',sans-serif;font-size:clamp(3rem,5vw,5rem);line-height:1;margin-bottom:1.8rem;letter-spacing:2px;}
.about h2 span{color:var(--red);}
.about p{color:var(--text-muted);line-height:1.9;font-weight:300;margin-bottom:1.2rem;font-size:0.98rem;}
.about-list{list-style:none;margin:2rem 0;display:flex;flex-direction:column;gap:0.8rem;}
.about-list li{display:flex;align-items:center;gap:1rem;font-family:'Barlow Condensed',sans-serif;font-size:1rem;letter-spacing:1px;color:var(--text-muted);}
.about-list li::before{content:'→';color:var(--red);font-size:1.1rem;}

/* PROGRAMS */
.programs{background:var(--deep);padding:8rem 6%;}
.section-header{text-align:center;margin-bottom:5rem;}
.section-tag{font-family:'Barlow Condensed',sans-serif;font-size:0.78rem;letter-spacing:5px;text-transform:uppercase;color:var(--red);margin-bottom:1rem;display:flex;align-items:center;justify-content:center;gap:1.2rem;}
.section-tag::before,.section-tag::after{content:'';width:40px;height:2px;background:var(--red);}
.section-header h2{font-family:'Bebas Neue',sans-serif;font-size:clamp(3rem,6vw,5.5rem);line-height:1;letter-spacing:2px;}
.section-header h2 span{color:var(--red);}
.programs-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1px;background:var(--border);max-width:1200px;margin:0 auto;}
.prog-card{background:var(--deep);overflow:hidden;position:relative;transition:transform 0.4s;}
.prog-card:hover{transform:translateY(-6px);z-index:2;}
.prog-img{width:100%;height:260px;object-fit:cover;display:block;transition:transform 0.5s;filter:grayscale(30%);}
.prog-card:hover .prog-img{transform:scale(1.05);filter:grayscale(0%);}
.prog-overlay{position:absolute;top:0;left:0;right:0;height:260px;background:linear-gradient(to top,rgba(5,5,5,0.9),transparent 50%);}
.prog-label{position:absolute;top:1.2rem;left:1.2rem;font-family:'Barlow Condensed',sans-serif;font-size:0.7rem;letter-spacing:3px;text-transform:uppercase;background:var(--red);color:var(--text);padding:0.3rem 0.8rem;}
.prog-body{padding:1.8rem;}
.prog-name{font-family:'Bebas Neue',sans-serif;font-size:1.8rem;letter-spacing:2px;margin-bottom:0.6rem;}
.prog-desc{font-size:0.85rem;color:var(--text-muted);line-height:1.6;margin-bottom:1.2rem;}
.prog-meta{display:flex;gap:1.5rem;}
.prog-meta span{font-family:'Barlow Condensed',sans-serif;font-size:0.78rem;letter-spacing:2px;text-transform:uppercase;color:var(--red);}

/* MEMBERSHIP */
.membership{padding:8rem 6%;background:var(--black);}
.plans-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1.5rem;max-width:1100px;margin:4rem auto 0;}
.plan-card{border:1px solid var(--border);padding:3rem 2.5rem;position:relative;transition:border-color 0.3s,transform 0.3s;background:var(--surface);}
.plan-card:hover{border-color:var(--red);transform:translateY(-6px);}
.plan-card.featured{border-color:var(--red);background:var(--surface2);}
.plan-badge{position:absolute;top:-1px;left:50%;transform:translateX(-50%);background:var(--red);color:var(--text);font-family:'Barlow Condensed',sans-serif;font-size:0.7rem;letter-spacing:3px;text-transform:uppercase;padding:0.35rem 1.2rem;white-space:nowrap;}
.plan-name{font-family:'Bebas Neue',sans-serif;font-size:1.6rem;letter-spacing:3px;color:var(--text-muted);margin-bottom:1.5rem;}
.plan-price{font-family:'Bebas Neue',sans-serif;font-size:4rem;color:var(--text);line-height:1;}
.plan-price sup{font-size:1.8rem;vertical-align:top;margin-top:0.6rem;color:var(--red);}
.plan-price sub{font-family:'Barlow Condensed',sans-serif;font-size:0.9rem;color:var(--text-muted);letter-spacing:2px;}
.plan-divider{height:1px;background:var(--border);margin:1.5rem 0;}
.plan-features{list-style:none;display:flex;flex-direction:column;gap:0.8rem;margin-bottom:2.5rem;}
.plan-features li{font-size:0.9rem;color:var(--text-muted);display:flex;align-items:center;gap:0.8rem;}
.plan-features li::before{content:'✓';color:var(--red);font-weight:700;flex-shrink:0;}
.plan-features li.no{color:rgba(240,237,232,0.2);}
.plan-features li.no::before{content:'✗';color:rgba(240,237,232,0.15);}

/* TRAINERS */
.trainers{background:var(--deep);padding:8rem 6%;}
.trainers-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:2rem;max-width:1100px;margin:4rem auto 0;}
.trainer-card{position:relative;overflow:hidden;group;}
.trainer-img{width:100%;height:420px;object-fit:cover;object-position:top;display:block;filter:grayscale(40%);transition:filter 0.4s,transform 0.4s;}
.trainer-card:hover .trainer-img{filter:grayscale(0%);transform:scale(1.03);}
.trainer-overlay{position:absolute;bottom:0;left:0;right:0;padding:2rem;background:linear-gradient(to top,rgba(5,5,5,0.98),rgba(5,5,5,0.6),transparent);}
.trainer-name{font-family:'Bebas Neue',sans-serif;font-size:2rem;letter-spacing:3px;}
.trainer-role{font-family:'Barlow Condensed',sans-serif;font-size:0.78rem;letter-spacing:3px;text-transform:uppercase;color:var(--red);margin-top:0.3rem;}
.trainer-exp{font-size:0.82rem;color:var(--text-muted);margin-top:0.6rem;}

/* TRANSFORMATION */
.transformation{padding:8rem 6%;background:var(--black);}
.transform-grid{display:grid;grid-template-columns:repeat(4,1fr);grid-template-rows:240px 240px;gap:4px;margin-top:4rem;}
.tg-item{overflow:hidden;position:relative;}
.tg-item img{width:100%;height:100%;object-fit:cover;display:block;filter:grayscale(40%);transition:filter 0.5s,transform 0.5s;}
.tg-item:hover img{filter:grayscale(0%);transform:scale(1.06);}
.tg-item::after{content:'';position:absolute;inset:0;background:linear-gradient(to top,rgba(5,5,5,0.5),transparent);opacity:0;transition:opacity 0.3s;}
.tg-item:hover::after{opacity:1;}
.tg-item.tall{grid-row:span 2;}
.tg-item.wide{grid-column:span 2;}

/* TESTIMONIALS */
.testimonials{background:var(--deep);padding:8rem 6%;}
.testi-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1.5rem;max-width:1100px;margin:4rem auto 0;}
.testi-card{background:var(--surface);border:1px solid var(--border);padding:2.5rem;position:relative;transition:border-color 0.3s,transform 0.3s;}
.testi-card:hover{border-color:var(--red);transform:translateY(-4px);}
.testi-card::before{content:'"';font-family:'Bebas Neue',sans-serif;font-size:6rem;color:var(--red);line-height:0.7;opacity:0.25;display:block;margin-bottom:1.5rem;}
.testi-text{font-size:0.95rem;color:var(--text-muted);line-height:1.8;font-style:italic;margin-bottom:2rem;font-weight:300;}
.testi-author{display:flex;align-items:center;gap:1rem;}
.testi-avatar{width:44px;height:44px;border-radius:50%;background:var(--red);color:var(--text);display:flex;align-items:center;justify-content:center;font-family:'Bebas Neue',sans-serif;font-size:1.3rem;flex-shrink:0;}
.testi-name{font-family:'Barlow Condensed',sans-serif;font-size:1rem;letter-spacing:1px;font-weight:600;}
.testi-detail{font-size:0.75rem;color:var(--red);letter-spacing:2px;text-transform:uppercase;margin-top:0.2rem;}

/* LOCATION */
.location-section{display:grid;grid-template-columns:1fr 1fr;max-width:100%;}
.location-info{background:var(--surface);padding:7rem 8%;display:flex;flex-direction:column;justify-content:center;}
.location-info h2{font-family:'Bebas Neue',sans-serif;font-size:clamp(2.5rem,4vw,4rem);line-height:1;margin-bottom:1.5rem;}
.location-info h2 span{color:var(--red);}
.location-info p{color:var(--text-muted);line-height:1.9;font-weight:300;margin-bottom:2.5rem;}
.info-items{display:flex;flex-direction:column;gap:1.4rem;margin-bottom:3rem;}
.info-item{display:flex;align-items:flex-start;gap:1.2rem;}
.info-icon{width:42px;height:42px;border:1px solid var(--border);display:flex;align-items:center;justify-content:center;font-size:1rem;flex-shrink:0;color:var(--red);}
.info-label{font-family:'Barlow Condensed',sans-serif;font-size:0.7rem;letter-spacing:3px;text-transform:uppercase;color:var(--red);margin-bottom:0.3rem;}
.info-val{font-size:0.95rem;color:var(--text-muted);}
.map-embed{position:relative;height:100%;min-height:500px;}
.map-embed iframe{width:100%;height:100%;border:none;filter:grayscale(1) invert(0.9) contrast(0.8);}

/* JOIN SECTION */
.join-section{background:var(--red);padding:7rem 6%;text-align:center;position:relative;overflow:hidden;}
.join-section::before{content:'IRONEDGE';position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);font-family:'Bebas Neue',sans-serif;font-size:20rem;color:rgba(0,0,0,0.1);line-height:1;pointer-events:none;white-space:nowrap;}
.join-section h2{font-family:'Bebas Neue',sans-serif;font-size:clamp(3.5rem,7vw,7rem);line-height:0.9;margin-bottom:1.5rem;position:relative;z-index:2;}
.join-section p{font-size:1.1rem;color:rgba(240,237,232,0.7);max-width:500px;margin:0 auto 3rem;font-weight:300;line-height:1.8;position:relative;z-index:2;}
.btn-black{background:var(--black);color:var(--text);padding:1.1rem 3rem;border:none;font-family:'Barlow Condensed',sans-serif;font-size:0.9rem;font-weight:700;letter-spacing:4px;text-transform:uppercase;cursor:pointer;text-decoration:none;display:inline-block;transition:transform 0.2s;clip-path:polygon(0 0,calc(100% - 12px) 0,100% 100%,12px 100%);position:relative;z-index:2;}
.btn-black:hover{transform:scale(1.05);}

/* FOOTER */
footer{background:var(--surface);border-top:1px solid var(--border);padding:4rem 6% 2rem;}
.footer-top{display:grid;grid-template-columns:1.5fr 1fr 1fr 1fr;gap:3rem;margin-bottom:3rem;}
.footer-logo{font-family:'Bebas Neue',sans-serif;font-size:2rem;letter-spacing:4px;display:block;margin-bottom:1rem;}
.footer-logo span{color:var(--red);}
.footer-brand p{font-size:0.85rem;color:var(--text-muted);line-height:1.8;font-weight:300;}
.footer-col h4{font-family:'Barlow Condensed',sans-serif;font-size:0.7rem;letter-spacing:4px;text-transform:uppercase;color:var(--red);margin-bottom:1.5rem;}
.footer-col ul{list-style:none;display:flex;flex-direction:column;gap:0.7rem;}
.footer-col ul a{text-decoration:none;color:var(--text-muted);font-size:0.88rem;transition:color 0.2s;}
.footer-col ul a:hover{color:var(--red);}
.footer-bottom{border-top:1px solid var(--border);padding-top:2rem;display:flex;justify-content:space-between;align-items:center;font-size:0.78rem;color:var(--text-muted);}
.social-links{display:flex;gap:1rem;}
.social-link{width:36px;height:36px;border:1px solid var(--border);display:flex;align-items:center;justify-content:center;color:var(--text-muted);text-decoration:none;font-size:0.85rem;transition:border-color 0.2s,color 0.2s;font-family:'Barlow Condensed',sans-serif;font-weight:700;}
.social-link:hover{border-color:var(--red);color:var(--red);}

/* WHATSAPP */
.whatsapp-float{position:fixed;bottom:2.5rem;right:2.5rem;z-index:600;width:56px;height:56px;background:#25D366;border-radius:50%;display:flex;align-items:center;justify-content:center;box-shadow:0 4px 20px rgba(37,211,102,0.4);text-decoration:none;transition:transform 0.3s;}
.whatsapp-float:hover{transform:scale(1.1);}
.whatsapp-float svg{width:26px;height:26px;fill:white;}

/* VERDANT CREDIT */
.verdant-credit{position:fixed;bottom:2.5rem;left:2.5rem;z-index:600;font-family:'Barlow Condensed',sans-serif;font-size:0.65rem;letter-spacing:2px;text-transform:uppercase;color:rgba(232,22,12,0.4);}
.verdant-credit a{color:inherit;text-decoration:none;}
.verdant-credit a:hover{color:var(--red);}

@keyframes fadeUp{from{opacity:0;transform:translateY(30px);}to{opacity:1;transform:translateY(0);}}

@media(max-width:1000px){
  .about{grid-template-columns:1fr;}
  .programs-grid,.plans-grid,.trainers-grid,.testi-grid{grid-template-columns:1fr 1fr;}
  .stats-grid{grid-template-columns:1fr 1fr;}
  .transform-grid{grid-template-columns:1fr 1fr;grid-template-rows:auto;}
  .tg-item.tall,.tg-item.wide{grid-row:auto;grid-column:auto;}
  .location-section{grid-template-columns:1fr;}
  .footer-top{grid-template-columns:1fr 1fr;}
  nav ul{display:none;}
}
@media(max-width:700px){
  .programs-grid,.plans-grid,.trainers-grid,.testi-grid,.stats-grid{grid-template-columns:1fr;}
  .transform-grid{grid-template-columns:1fr 1fr;}
  .footer-top{grid-template-columns:1fr;}
}
</style>
</head>
<body>

<div class="cursor" id="cursor"></div>
<div class="cursor-ring" id="cursorRing"></div>

<a href="https://wa.me/919999999999" class="whatsapp-float" target="_blank">
  <svg viewBox="0 0 24 24"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347z"/><path d="M12 0C5.373 0 0 5.373 0 12c0 2.127.558 4.121 1.532 5.855L.057 23.885a.5.5 0 00.611.61l6.101-1.569A11.94 11.94 0 0012 24c6.627 0 12-5.373 12-12S18.627 0 12 0zm0 22c-1.891 0-3.66-.524-5.172-1.435l-.371-.221-3.845.988.997-3.77-.242-.389A9.96 9.96 0 012 12C2 6.477 6.477 2 12 2s10 4.477 10 10-4.477 10-10 10z"/></svg>
</a>

<div class="verdant-credit">Built by <a href="https://www.instagram.com/verdant.studio" target="_blank">@verdant.studio</a></div>

<!-- NAV -->
<nav id="navbar">
  <div class="nav-logo">IRON<span>EDGE</span></div>
  <ul>
    <li><a href="#about">About</a></li>
    <li><a href="#programs">Programs</a></li>
    <li><a href="#membership">Pricing</a></li>
    <li><a href="#trainers">Trainers</a></li>
    <li><a href="#location">Visit</a></li>
    <li><a href="#join" class="nav-join">Join Now</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-slash"></div>
  <div class="hero-content">
    <div class="hero-eyebrow">Elite Fitness · Faridabad · Est. 2018</div>
    <h1>FORGE<span>YOUR BEST</span>SELF.</h1>
    <p class="hero-desc">No excuses. No shortcuts. Just raw dedication, elite coaching, and a community that pushes you beyond every limit you thought you had.</p>
    <div class="hero-actions">
      <a href="#join" class="btn-red">Start Today</a>
      <a href="#programs" class="btn-outline">View Programs</a>
    </div>
  </div>
</section>

<!-- TICKER -->
<div class="ticker">
  <div class="ticker-inner">
    <span>Strength Training</span><span>Personal Training</span><span>CrossFit</span><span>Nutrition Coaching</span><span>Cardio Zone</span><span>Yoga & Recovery</span><span>Body Transformation</span><span>Strength Training</span><span>Personal Training</span><span>CrossFit</span><span>Nutrition Coaching</span><span>Cardio Zone</span><span>Yoga & Recovery</span><span>Body Transformation</span>
  </div>
</div>

<!-- STATS -->
<section class="stats">
  <div class="stats-grid">
    <div class="stat-box reveal"><div class="stat-num">2500+</div><div class="stat-label">Active Members</div></div>
    <div class="stat-box reveal"><div class="stat-num">12+</div><div class="stat-label">Expert Trainers</div></div>
    <div class="stat-box reveal"><div class="stat-num">6</div><div class="stat-label">Years of Excellence</div></div>
    <div class="stat-box reveal"><div class="stat-num">98%</div><div class="stat-label">Member Satisfaction</div></div>
  </div>
</section>

<!-- ABOUT -->
<section class="about" id="about">
  <div class="about-visual reveal-left">
    <img src="https://images.pexels.com/photos/1552252/pexels-photo-1552252.jpeg?auto=compress&cs=tinysrgb&w=900" alt="IronEdge Gym"/>
  </div>
  <div class="about-content reveal-right">
    <div class="about-tag">Who We Are</div>
    <h2>NOT JUST A GYM.<br/><span>A MOVEMENT.</span></h2>
    <p>IronEdge was built for people who are serious about results. Not the ones who show up twice in January and disappear — the ones who show up every single day and demand the best from themselves.</p>
    <p>Our facility in Faridabad is equipped with premium imported equipment, certified coaches with national-level experience, and a community culture that holds you accountable.</p>
    <ul class="about-list">
      <li>10,000 sq ft of premium training space</li>
      <li>Imported Hammer Strength & Life Fitness equipment</li>
      <li>Dedicated zones: Weights · Cardio · Functional · Yoga</li>
      <li>Open 5 AM – 11 PM, 365 days a year</li>
      <li>Separate men's & women's sections available</li>
    </ul>
    <a href="#join" class="btn-red">Join IronEdge</a>
  </div>
</section>

<!-- PROGRAMS -->
<section class="programs" id="programs">
  <div class="section-header reveal">
    <div class="section-tag">What We Offer</div>
    <h2>ELITE <span>PROGRAMS</span></h2>
  </div>
  <div class="programs-grid reveal">
    <div class="prog-card">
      <img class="prog-img" src="https://images.pexels.com/photos/1552249/pexels-photo-1552249.jpeg?auto=compress&cs=tinysrgb&w=600" alt="Strength"/>
      <div class="prog-overlay"></div>
      <div class="prog-label">Most Popular</div>
      <div class="prog-body">
        <div class="prog-name">Strength & Muscle</div>
        <p class="prog-desc">Progressive overload training designed to maximize muscle growth and raw power. Structured 5-day splits with trainer-guided programming.</p>
        <div class="prog-meta"><span>5 Days/Week</span><span>All Levels</span></div>
      </div>
    </div>
    <div class="prog-card">
      <img class="prog-img" src="https://images.pexels.com/photos/2827400/pexels-photo-2827400.jpeg?auto=compress&cs=tinysrgb&w=600" alt="CrossFit"/>
      <div class="prog-overlay"></div>
      <div class="prog-label">High Intensity</div>
      <div class="prog-body">
        <div class="prog-name">CrossFit & HIIT</div>
        <p class="prog-desc">Functional movements at high intensity. Build conditioning, endurance, and athleticism with our certified CrossFit coaches. 45-minute sessions.</p>
        <div class="prog-meta"><span>6 Batches/Day</span><span>Intermediate+</span></div>
      </div>
    </div>
    <div class="prog-card">
      <img class="prog-img" src="https://images.pexels.com/photos/1431282/pexels-photo-1431282.jpeg?auto=compress&cs=tinysrgb&w=600" alt="Personal Training"/>
      <div class="prog-overlay"></div>
      <div class="prog-label">Premium</div>
      <div class="prog-body">
        <div class="prog-name">Personal Training</div>
        <p class="prog-desc">1-on-1 sessions with your dedicated coach. Custom program, nutrition plan, and weekly check-ins. The fastest path to your goal.</p>
        <div class="prog-meta"><span>Flexible Schedule</span><span>All Levels</span></div>
      </div>
    </div>
    <div class="prog-card">
      <img class="prog-img" src="https://images.pexels.com/photos/4056723/pexels-photo-4056723.jpeg?auto=compress&cs=tinysrgb&w=600" alt="Weight Loss"/>
      <div class="prog-overlay"></div>
      <div class="prog-body">
        <div class="prog-name">Fat Loss Program</div>
        <p class="prog-desc">Scientifically structured 12-week transformation program combining resistance training, cardio periodization, and a customized diet plan.</p>
        <div class="prog-meta"><span>12 Weeks</span><span>Beginners Welcome</span></div>
      </div>
    </div>
    <div class="prog-card">
      <img class="prog-img" src="https://images.pexels.com/photos/3822864/pexels-photo-3822864.jpeg?auto=compress&cs=tinysrgb&w=600" alt="Yoga"/>
      <div class="prog-overlay"></div>
      <div class="prog-body">
        <div class="prog-name">Yoga & Recovery</div>
        <p class="prog-desc">Power yoga, flexibility training, and active recovery sessions. Essential for injury prevention and long-term athletic performance.</p>
        <div class="prog-meta"><span>Morning & Evening</span><span>All Levels</span></div>
      </div>
    </div>
    <div class="prog-card">
      <img class="prog-img" src="https://images.pexels.com/photos/1640768/pexels-photo-1640768.jpeg?auto=compress&cs=tinysrgb&w=600" alt="Nutrition"/>
      <div class="prog-overlay"></div>
      <div class="prog-label">Add-On</div>
      <div class="prog-body">
        <div class="prog-name">Nutrition Coaching</div>
        <p class="prog-desc">Custom meal plans, macro tracking, and ongoing support from our certified sports nutritionist. Training is 40% — diet is 60%.</p>
        <div class="prog-meta"><span>Monthly Plans</span><span>Online + Offline</span></div>
      </div>
    </div>
  </div>
</section>

<!-- MEMBERSHIP -->
<section class="membership" id="membership">
  <div class="section-header reveal">
    <div class="section-tag">Membership Plans</div>
    <h2>INVEST IN <span>YOURSELF</span></h2>
  </div>
  <div class="plans-grid">
    <div class="plan-card reveal">
      <div class="plan-name">Starter</div>
      <div class="plan-price"><sup>₹</sup>1,499<sub>/mo</sub></div>
      <div class="plan-divider"></div>
      <ul class="plan-features">
        <li>Full gym access</li>
        <li>Cardio & weights zone</li>
        <li>Locker room access</li>
        <li>1 free orientation session</li>
        <li class="no">Group classes</li>
        <li class="no">Personal trainer</li>
        <li class="no">Nutrition plan</li>
      </ul>
      <a href="#join" class="btn-outline" style="width:100%;text-align:center;display:block;padding:0.9rem;">Get Started</a>
    </div>
    <div class="plan-card featured reveal">
      <div class="plan-badge">Most Popular</div>
      <div class="plan-name">Pro</div>
      <div class="plan-price"><sup>₹</sup>2,499<sub>/mo</sub></div>
      <div class="plan-divider"></div>
      <ul class="plan-features">
        <li>Full gym access</li>
        <li>All group classes</li>
        <li>Yoga & recovery sessions</li>
        <li>Monthly fitness assessment</li>
        <li>Basic nutrition guidance</li>
        <li>2 PT sessions/month</li>
        <li class="no">Custom nutrition plan</li>
      </ul>
      <a href="#join" class="btn-red" style="width:100%;text-align:center;display:block;padding:0.9rem;">Join Pro</a>
    </div>
    <div class="plan-card reveal">
      <div class="plan-name">Elite</div>
      <div class="plan-price"><sup>₹</sup>4,999<sub>/mo</sub></div>
      <div class="plan-divider"></div>
      <ul class="plan-features">
        <li>Unlimited everything</li>
        <li>Dedicated personal trainer</li>
        <li>Custom workout program</li>
        <li>Full nutrition plan</li>
        <li>Weekly body composition check</li>
        <li>Priority booking</li>
        <li>Free guest passes (2/mo)</li>
      </ul>
      <a href="#join" class="btn-outline" style="width:100%;text-align:center;display:block;padding:0.9rem;">Go Elite</a>
    </div>
  </div>
</section>

<!-- TRAINERS -->
<section class="trainers" id="trainers">
  <div class="section-header reveal">
    <div class="section-tag">The Coaches</div>
    <h2>TRAINED BY <span>THE BEST</span></h2>
  </div>
  <div class="trainers-grid">
    <div class="trainer-card reveal">
      <img class="trainer-img" src="https://images.pexels.com/photos/1547248/pexels-photo-1547248.jpeg?auto=compress&cs=tinysrgb&w=600" alt="Coach Vikram"/>
      <div class="trainer-overlay">
        <div class="trainer-name">VIKRAM SINGH</div>
        <div class="trainer-role">Head Strength Coach</div>
        <div class="trainer-exp">8 years · National Powerlifting Champion 2021</div>
      </div>
    </div>
    <div class="trainer-card reveal">
      <img class="trainer-img" src="https://images.pexels.com/photos/3757376/pexels-photo-3757376.jpeg?auto=compress&cs=tinysrgb&w=600" alt="Coach Priya"/>
      <div class="trainer-overlay">
        <div class="trainer-name">PRIYA SHARMA</div>
        <div class="trainer-role">Yoga & Recovery Specialist</div>
        <div class="trainer-exp">6 years · RYT-500 Certified · Women's Fitness Expert</div>
      </div>
    </div>
    <div class="trainer-card reveal">
      <img class="trainer-img" src="https://images.pexels.com/photos/1431283/pexels-photo-1431283.jpeg?auto=compress&cs=tinysrgb&w=600" alt="Coach Rahul"/>
      <div class="trainer-overlay">
        <div class="trainer-name">RAHUL KHANNA</div>
        <div class="trainer-role">CrossFit & HIIT Coach</div>
        <div class="trainer-exp">5 years · Level 2 CrossFit Certified · Sports Nutritionist</div>
      </div>
    </div>
  </div>
</section>

<!-- TRANSFORMATION GALLERY -->
<section class="transformation" id="gallery">
  <div class="section-header reveal">
    <div class="section-tag">Real Results</div>
    <h2>THE <span>IRONEDGE</span> TRANSFORMATION</h2>
  </div>
  <div class="transform-grid">
    <div class="tg-item tall"><img src="https://images.pexels.com/photos/1552252/pexels-photo-1552252.jpeg?auto=compress&cs=tinysrgb&w=700" alt="Gym"/></div>
    <div class="tg-item"><img src="https://images.pexels.com/photos/1552249/pexels-photo-1552249.jpeg?auto=compress&cs=tinysrgb&w=700" alt="Training"/></div>
    <div class="tg-item"><img src="https://images.pexels.com/photos/2827400/pexels-photo-2827400.jpeg?auto=compress&cs=tinysrgb&w=700" alt="CrossFit"/></div>
    <div class="tg-item tall"><img src="https://images.pexels.com/photos/3822864/pexels-photo-3822864.jpeg?auto=compress&cs=tinysrgb&w=700" alt="Yoga"/></div>
    <div class="tg-item wide"><img src="https://images.pexels.com/photos/1431282/pexels-photo-1431282.jpeg?auto=compress&cs=tinysrgb&w=900" alt="Equipment"/></div>
  </div>
</section>

<!-- TESTIMONIALS -->
<section class="testimonials">
  <div class="section-header reveal">
    <div class="section-tag">Member Stories</div>
    <h2>REAL PEOPLE. <span>REAL RESULTS.</span></h2>
  </div>
  <div class="testi-grid">
    <div class="testi-card reveal">
      <p class="testi-text">Lost 18 kg in 5 months with Rahul's guidance. I've tried 3 gyms before this — IronEdge is on a completely different level. The coaches actually care.</p>
      <div class="testi-author">
        <div class="testi-avatar">A</div>
        <div><div class="testi-name">Amit Verma</div><div class="testi-detail">Lost 18 kg · Fat Loss Program</div></div>
      </div>
    </div>
    <div class="testi-card reveal">
      <p class="testi-text">As a woman I was nervous about gyms. IronEdge made me feel safe, respected, and incredibly strong. Priya ma'am changed my life in ways I can't fully explain.</p>
      <div class="testi-author">
        <div class="testi-avatar">S</div>
        <div><div class="testi-name">Sneha Gupta</div><div class="testi-detail">6 months · Elite Member</div></div>
      </div>
    </div>
    <div class="testi-card reveal">
      <p class="testi-text">Joined for CrossFit, stayed for the community. These people push you to your absolute limit and celebrate every single milestone. Worth every rupee.</p>
      <div class="testi-author">
        <div class="testi-avatar">R</div>
        <div><div class="testi-name">Rohan Malhotra</div><div class="testi-detail">1 year · CrossFit Member</div></div>
      </div>
    </div>
  </div>
</section>

<!-- LOCATION -->
<div class="location-section" id="location">
  <div class="location-info reveal-left">
    <div class="about-tag">Find Us</div>
    <h2>WE'RE IN THE <span>HEART OF FARIDABAD</span></h2>
    <p>Easily accessible from the metro, with free parking. Open early, close late — because your schedule shouldn't stop you.</p>
    <div class="info-items">
      <div class="info-item">
        <div class="info-icon">📍</div>
        <div><div class="info-label">Address</div><div class="info-val">Plot 45, Sector 12, Near Crown Interiorz Mall, Faridabad, Haryana 121007</div></div>
      </div>
      <div class="info-item">
        <div class="info-icon">🕐</div>
        <div><div class="info-label">Hours</div><div class="info-val">Mon–Sat: 5 AM – 11 PM<br/>Sunday: 6 AM – 9 PM</div></div>
      </div>
      <div class="info-item">
        <div class="info-icon">📞</div>
        <div><div class="info-label">Call / WhatsApp</div><div class="info-val">+91 XXXXX XXXXX</div></div>
      </div>
      <div class="info-item">
        <div class="info-icon">🅿️</div>
        <div><div class="info-label">Parking</div><div class="info-val">Free parking for 100+ vehicles</div></div>
      </div>
    </div>
    <a href="#join" class="btn-red">Get a Free Trial</a>
  </div>
  <div class="map-embed">
    <iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3509.3!2d77.3178!3d28.4089!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0x0!2sSector+12+Faridabad!5e0!3m2!1sen!2sin!4v1234567890" allowfullscreen="" loading="lazy"></iframe>
  </div>
</div>

<!-- JOIN CTA -->
<section class="join-section" id="join">
  <h2>WHAT ARE YOU<br/>WAITING FOR?</h2>
  <p>Your first trial session is on us. Come in, feel the energy, meet the coaches. No commitment. No pressure. Just results.</p>
  <a href="https://wa.me/919999999999?text=Hi%20IronEdge!%20I%20want%20a%20free%20trial%20session." class="btn-black" target="_blank">CLAIM FREE TRIAL →</a>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-top">
    <div class="footer-brand">
      <span class="footer-logo">IRON<span>EDGE</span></span>
      <p>Faridabad's premier fitness destination. Built for the serious. Open for everyone. Your transformation starts here.</p>
    </div>
    <div class="footer-col">
      <h4>Navigate</h4>
      <ul>
        <li><a href="#about">About Us</a></li>
        <li><a href="#programs">Programs</a></li>
        <li><a href="#membership">Membership</a></li>
        <li><a href="#trainers">Trainers</a></li>
        <li><a href="#location">Visit Us</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Programs</h4>
      <ul>
        <li><a href="#programs">Strength Training</a></li>
        <li><a href="#programs">CrossFit & HIIT</a></li>
        <li><a href="#programs">Personal Training</a></li>
        <li><a href="#programs">Yoga & Recovery</a></li>
        <li><a href="#programs">Nutrition Coaching</a></li>
      </ul>
    </div>
    <div class="footer-col">
      <h4>Contact</h4>
      <ul>
        <li><a href="tel:+919999999999">+91 XXXXX XXXXX</a></li>
        <li><a href="https://wa.me/919999999999">WhatsApp Us</a></li>
        <li><a href="#">Sector 12, Faridabad</a></li>
        <li><a href="#">Mon–Sun: 5AM–11PM</a></li>
      </ul>
    </div>
  </div>
  <div class="footer-bottom">
    <span>© 2026 IronEdge Gym · All Rights Reserved · Website by <a href="https://www.instagram.com/verdant.studio" target="_blank" style="color:var(--red);text-decoration:none;">Verdant Studio</a></span>
    <div class="social-links">
      <a href="#" class="social-link">in</a>
      <a href="#" class="social-link">ig</a>
      <a href="#" class="social-link">fb</a>
    </div>
  </div>
</footer>

<script>
// CURSOR
var cursor=document.getElementById('cursor'),ring=document.getElementById('cursorRing'),mx=0,my=0,rx=0,ry=0;
document.addEventListener('mousemove',function(e){mx=e.clientX;my=e.clientY;cursor.style.left=mx+'px';cursor.style.top=my+'px';});
function animRing(){rx+=(mx-rx)*0.12;ry+=(my-ry)*0.12;ring.style.left=rx+'px';ring.style.top=ry+'px';requestAnimationFrame(animRing);}
animRing();
document.querySelectorAll('a,button,.prog-card,.plan-card,.trainer-card').forEach(function(el){
  el.addEventListener('mouseenter',function(){cursor.style.transform='translate(-50%,-50%) scale(2.5)';ring.style.width='56px';ring.style.height='56px';});
  el.addEventListener('mouseleave',function(){cursor.style.transform='translate(-50%,-50%) scale(1)';ring.style.width='32px';ring.style.height='32px';});
});
// NAV
window.addEventListener('scroll',function(){document.getElementById('navbar').classList.toggle('scrolled',window.scrollY>60);});
// REVEAL
var obs=new IntersectionObserver(function(entries){entries.forEach(function(e){if(e.isIntersecting)e.target.classList.add('visible');});},{threshold:0.1});
document.querySelectorAll('.reveal,.reveal-left,.reveal-right').forEach(function(el){obs.observe(el);});
// STAGGER
document.querySelectorAll('.stats-grid .stat-box,.plans-grid .plan-card,.testi-grid .testi-card').forEach(function(el,i){el.style.transitionDelay=(i*0.1)+'s';});
</script>
</body>
</html>
