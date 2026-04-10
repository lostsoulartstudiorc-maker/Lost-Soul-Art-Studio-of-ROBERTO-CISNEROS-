# Lost-Soul-Art-Studio-of-ROBERTO-CISNEROS-
PORTFOLIO, and Professional Visual Art Services website.
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Lost Soul Art Studio — Roberto Cisneros | San Francisco</title>
<meta name="description" content="Fine art portraiture, surrealist paintings, interior murals, storefront installations, tattoo art and workshops by Roberto Cisneros — Lost Soul Art Studio, San Francisco CA.">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;0,900;1,400;1,700&family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Josefin+Sans:wght@100;300;400&display=swap" rel="stylesheet">

<style>
/* ═══════════════════════════════════════════════════════════
   BRAND TOKENS — Black · Red · Cream · Gold accent
═══════════════════════════════════════════════════════════ */
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
:root{
  /* Core brand */
  --blk:#0A0A0C;
  --deep:#111116;
  --char:#1A1A22;
  --obs:#141418;

  /* Red — primary brand accent */
  --red:#C0271A;
  --red2:#E8321F;
  --red3:#8B1A10;
  --redfade:rgba(192,39,26,.15);
  --redbdr:rgba(192,39,26,.3);

  /* Gold — secondary warm accent */
  --gold:#C8A951;
  --glt:#E2C97E;
  --gdk:#8B6E2A;

  /* Text */
  --crm:#F0E8D8;
  --mst:#9A8878;
  --dim:#6A5A52;

  /* Borders */
  --bdr:rgba(192,39,26,.2);
  --bdr2:rgba(240,232,216,.08);

  /* Live */
  --live:#C0271A;
}

html{scroll-behavior:smooth}
body{
  background:var(--blk);
  color:var(--crm);
  font-family:'Cormorant Garamond',serif;
  font-size:18px;
  line-height:1.7;
  overflow-x:hidden;
  cursor:crosshair;
}

/* Grain texture */
body::before{
  content:'';position:fixed;inset:0;pointer-events:none;z-index:999;opacity:.25;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23n)' opacity='.05'/%3E%3C/svg%3E");
}

/* ═══ ANIMATIONS ═══ */
@keyframes fadeUp{from{opacity:0;transform:translateY(28px)}to{opacity:1;transform:translateY(0)}}
@keyframes fadeIn{from{opacity:0}to{opacity:1}}
@keyframes pulseRed{0%,100%{opacity:1;transform:scale(1)}50%{opacity:.5;transform:scale(.85)}}
@keyframes flutterL{0%,100%{transform:rotateY(0deg) scaleX(1)}50%{transform:rotateY(-18deg) scaleX(.92)}}
@keyframes flutterR{0%,100%{transform:rotateY(0deg) scaleX(1)}50%{transform:rotateY(18deg) scaleX(.92)}}
@keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-8px)}}
@keyframes shimmer{0%{background-position:-200% center}100%{background-position:200% center}}

/* ═══ SCROLLBAR ═══ */
::-webkit-scrollbar{width:3px}
::-webkit-scrollbar-track{background:var(--blk)}
::-webkit-scrollbar-thumb{background:var(--red3)}

/* ═══ PAGES ═══ */
.page{display:none;min-height:100vh}
.page.active{display:block}

/* ═══ NAV ═══ */
nav{
  position:fixed;top:0;left:0;right:0;z-index:800;
  padding:14px 48px;display:flex;justify-content:space-between;align-items:center;
  background:rgba(10,10,12,.97);backdrop-filter:blur(12px);
  border-bottom:1px solid var(--bdr);
}
.nav-logo-wrap{display:flex;align-items:center;gap:14px;cursor:pointer}
.nav-logo-text{font-family:'Playfair Display',serif;font-size:14px;font-weight:700;letter-spacing:.18em;color:var(--crm);text-transform:uppercase;line-height:1.1}
.nav-logo-text em{display:block;font-style:italic;color:var(--red);font-size:11px;letter-spacing:.22em}
.nav-links{display:flex;gap:0;list-style:none}
.nav-links a{
  font-family:'Josefin Sans',sans-serif;font-weight:100;font-size:9px;
  letter-spacing:.38em;text-transform:uppercase;color:var(--mst);
  text-decoration:none;transition:color .3s;cursor:pointer;
  padding:8px 13px;display:block;position:relative;
}
.nav-links a::after{
  content:'';position:absolute;bottom:0;left:13px;right:13px;
  height:1px;background:var(--red);transform:scaleX(0);transition:transform .3s;
}
.nav-links a:hover,.nav-links a.active{color:var(--red2)}
.nav-links a:hover::after,.nav-links a.active::after{transform:scaleX(1)}
.nav-links a.highlight{color:var(--red)!important}
.hamburger{display:none;flex-direction:column;gap:5px;cursor:pointer;padding:4px}
.hamburger span{width:22px;height:1px;background:var(--crm);transition:all .3s}
@media(max-width:900px){
  .nav-links{display:none;position:fixed;top:0;left:0;right:0;bottom:0;background:rgba(10,10,12,.99);flex-direction:column;justify-content:center;align-items:center;gap:6px}
  .nav-links.open{display:flex}
  .nav-links a{font-size:11px;padding:14px 28px}
  .hamburger{display:flex}
  nav{padding:12px 20px}
}

/* ═══ SHARED LAYOUT ═══ */
.wrap{max-width:1200px;margin:0 auto;padding:0 40px}
@media(max-width:600px){.wrap{padding:0 20px}}
section{padding:90px 0}

/* ═══ TYPOGRAPHY HELPERS ═══ */
.eyebrow{
  font-family:'Josefin Sans',sans-serif;font-weight:100;font-size:10px;
  letter-spacing:.55em;color:var(--red);text-transform:uppercase;margin-bottom:28px;
  opacity:0;animation:fadeUp 1s ease forwards .2s;
}
.sec-label{
  font-family:'Josefin Sans',sans-serif;font-weight:100;font-size:10px;
  letter-spacing:.5em;color:var(--red);text-transform:uppercase;
  margin-bottom:16px;display:flex;align-items:center;gap:14px;
}
.sec-label::after{content:'';flex:0 0 48px;height:1px;background:var(--bdr)}
.sh{font-family:'Playfair Display',serif;font-size:clamp(34px,5vw,58px);font-weight:900;line-height:1.05;color:var(--crm);margin-bottom:14px}
.sh em{font-style:italic;color:var(--red)}
.sub{font-size:17px;color:var(--mst);font-style:italic;line-height:1.85;max-width:540px;margin-bottom:48px}

/* ═══ HERO ═══ */
.hero{
  min-height:100vh;display:flex;flex-direction:column;
  align-items:center;justify-content:center;text-align:center;
  padding:120px 40px 80px;position:relative;overflow:hidden;
}
.hero-glow{
  position:absolute;inset:0;pointer-events:none;
  background:
    radial-gradient(ellipse 55% 45% at 20% 80%,rgba(192,39,26,.08),transparent 60%),
    radial-gradient(ellipse 40% 55% at 80% 20%,rgba(192,39,26,.06),transparent 55%),
    radial-gradient(ellipse 30% 40% at 50% 50%,rgba(192,39,26,.04),transparent 70%);
}
.hero-art-bg{
  position:absolute;top:0;right:0;bottom:0;width:42%;
  pointer-events:none;overflow:hidden;opacity:.07;
}
.hero-art-bg img{width:100%;height:100%;object-fit:cover;filter:blur(3px) grayscale(.4)}
.hero h1{
  font-family:'Playfair Display',serif;
  font-size:clamp(58px,12vw,124px);
  font-weight:900;line-height:.88;letter-spacing:-.02em;
  color:var(--crm);opacity:0;animation:fadeUp 1s ease forwards .45s;
}
.hero h1 em{font-style:italic;color:var(--red);display:block}
.hero-sub{
  font-style:italic;font-size:clamp(16px,2.2vw,21px);
  color:var(--mst);margin-top:28px;max-width:540px;
  opacity:0;animation:fadeUp 1s ease forwards .75s;line-height:1.85;
}
.med-tags{display:flex;gap:10px;justify-content:center;flex-wrap:wrap;margin-top:24px;opacity:0;animation:fadeUp 1s ease forwards .95s}
.med-tag{
  font-family:'Josefin Sans',sans-serif;font-weight:300;font-size:9px;
  letter-spacing:.35em;text-transform:uppercase;color:var(--dim);
  border:1px solid var(--bdr2);padding:7px 16px;
}
.hero-socials{display:flex;gap:12px;justify-content:center;flex-wrap:wrap;margin-top:26px;opacity:0;animation:fadeUp 1s ease forwards 1.1s}
.hsoc{
  font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.35em;
  text-transform:uppercase;color:var(--dim);text-decoration:none;
  border:1px solid rgba(192,39,26,.15);padding:7px 16px;
  transition:all .3s;display:inline-block;
}
.hsoc:hover{color:var(--red);border-color:var(--red);background:var(--redfade)}
.hero-line{width:1px;height:72px;background:linear-gradient(to bottom,transparent,var(--red),transparent);margin:44px auto 0;opacity:0;animation:fadeIn 1.8s ease forwards 1.3s}

/* ═══ CARDS ═══ */
.grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(310px,1fr));gap:2px}
.grid2{display:grid;grid-template-columns:1fr 1fr;gap:2px}
.grid3{display:grid;grid-template-columns:repeat(3,1fr);gap:2px}
@media(max-width:900px){.grid3{grid-template-columns:1fr 1fr}}
@media(max-width:600px){.grid2,.grid3{grid-template-columns:1fr}}
.card{
  background:var(--obs);border:1px solid var(--bdr2);
  padding:36px 32px;position:relative;overflow:hidden;
  transition:border-color .4s,transform .4s;display:flex;flex-direction:column;
}
.card::before{
  content:'';position:absolute;top:0;left:0;right:0;height:2px;
  background:linear-gradient(90deg,transparent,var(--red),transparent);
  transform:scaleX(0);transition:transform .5s;
}
.card:hover{border-color:rgba(192,39,26,.4);transform:translateY(-3px)}
.card:hover::before{transform:scaleX(1)}
.card-label{font-family:'Josefin Sans',sans-serif;font-weight:100;font-size:9px;letter-spacing:.4em;text-transform:uppercase;color:var(--red3);margin-bottom:12px}
.card-h{font-family:'Playfair Display',serif;font-size:22px;font-weight:700;color:var(--crm);margin-bottom:10px;line-height:1.2}
.card-body{font-size:15px;color:var(--mst);font-style:italic;line-height:1.75;margin-bottom:24px}
.price-line{border-top:1px solid var(--bdr2);padding-top:20px;margin-top:auto}
.price-from{font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.35em;text-transform:uppercase;color:var(--dim);margin-bottom:4px}
.price-val{font-family:'Playfair Display',serif;font-size:40px;font-weight:900;color:var(--red);line-height:1}
.price-note{font-size:13px;color:var(--mst);margin-top:5px;font-style:italic}

/* ═══ BUTTONS ═══ */
.btn{font-family:'Josefin Sans',sans-serif;font-weight:300;font-size:10px;letter-spacing:.42em;text-transform:uppercase;padding:16px 36px;border:none;cursor:pointer;transition:all .3s;text-decoration:none;display:inline-block;text-align:center}
.btn-red{color:var(--crm);background:var(--red)}
.btn-red:hover{background:var(--red2)}
.btn-out{color:var(--red);background:transparent;border:1px solid var(--bdr)}
.btn-out:hover{border-color:var(--red);color:var(--red2);background:var(--redfade)}
.btn-row{display:flex;gap:12px;flex-wrap:wrap}

/* ═══ SECTIONS ═══ */
.band{background:var(--deep);padding:90px 0;border-top:1px solid var(--bdr2);border-bottom:1px solid var(--bdr2)}
.band-dark{background:var(--char);padding:90px 0}

/* ═══ REVEAL ═══ */
.rev{opacity:0;transform:translateY(20px);transition:opacity .75s,transform .75s}
.rev.vis{opacity:1;transform:translateY(0)}

/* ═══ LIVE BADGE ═══ */
.live-badge{display:inline-flex;align-items:center;gap:8px;background:rgba(192,39,26,.08);border:1px solid rgba(192,39,26,.25);padding:7px 16px;margin-top:18px}
.live-dot{width:6px;height:6px;background:var(--red);border-radius:50%;animation:pulseRed 2s infinite}
.live-txt{font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.35em;text-transform:uppercase;color:var(--red)}

/* ═══ GALLERY ═══ */
.gal-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(260px,1fr));gap:3px}
.gal-item{position:relative;overflow:hidden;aspect-ratio:1;cursor:pointer;background:var(--obs)}
.gal-item img{width:100%;height:100%;object-fit:cover;transition:transform .6s,filter .4s;filter:brightness(.8)}
.gal-item:hover img{transform:scale(1.06);filter:brightness(1)}
.gal-cap{position:absolute;bottom:0;left:0;right:0;padding:18px 14px 12px;background:linear-gradient(to top,rgba(10,10,12,.92),transparent);font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.3em;text-transform:uppercase;color:var(--red);transform:translateY(100%);transition:transform .4s}
.gal-item:hover .gal-cap{transform:translateY(0)}

/* ═══ LIGHTBOX ═══ */
.lb{position:fixed;inset:0;background:rgba(10,10,12,.97);z-index:9000;display:none;align-items:center;justify-content:center;padding:20px}
.lb.open{display:flex}
.lb img{max-width:90vw;max-height:90vh;object-fit:contain}
.lb-close{position:absolute;top:22px;right:24px;font-size:26px;color:var(--mst);cursor:pointer;transition:color .3s;font-family:'Josefin Sans',sans-serif}
.lb-close:hover{color:var(--red)}
.lb-cap{position:absolute;bottom:22px;left:50%;transform:translateX(-50%);font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.4em;text-transform:uppercase;color:var(--red);white-space:nowrap}

/* ═══ TESTIMONIALS ═══ */
.tcards{display:grid;grid-template-columns:repeat(auto-fill,minmax(310px,1fr));gap:2px}
.tcard{background:var(--obs);border:1px solid var(--bdr2);padding:36px 32px}
.tcard-q{font-size:15px;color:var(--mst);font-style:italic;line-height:1.85;margin-bottom:24px}
.tcard-q::before{content:'"';font-family:'Playfair Display',serif;font-size:52px;color:rgba(192,39,26,.2);line-height:1;display:block;margin-bottom:-10px}
.tcard-name{font-family:'Playfair Display',serif;font-size:17px;font-weight:700;color:var(--crm);margin-bottom:4px}
.tcard-role{font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.35em;text-transform:uppercase;color:var(--red3)}

/* ═══ PORTRAIT TABLE ═══ */
.ptable{width:100%;border-collapse:collapse;margin-top:28px}
.ptable th{background:var(--char);font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.4em;text-transform:uppercase;color:var(--red);padding:16px 18px;text-align:left;border:1px solid var(--bdr2)}
.ptable td{padding:14px 18px;border:1px solid var(--bdr2);font-size:16px;color:var(--mst);font-style:italic}
.ptable tr:nth-child(even) td{background:rgba(255,255,255,.02)}
.ptable .tier-h td{background:var(--char);font-family:'Playfair Display',serif;font-size:16px;font-weight:700;color:var(--crm);font-style:normal}
.ptable .pv{color:var(--red);font-family:'Playfair Display',serif;font-weight:700;font-size:19px;font-style:normal}
.ptable .dv{color:var(--red3);font-style:normal}

/* ═══ TATTOO TIER CARDS ═══ */
.tat-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(300px,1fr));gap:2px;margin-top:48px}
.tat-tier{background:var(--obs);border:1px solid var(--bdr2);padding:36px 30px;transition:all .4s}
.tat-tier:hover{border-color:rgba(192,39,26,.4);transform:translateY(-3px)}
.tat-tier.feat{border-color:var(--red)}
.tat-tier.feat::after{content:'MOST POPULAR';position:absolute;top:-1px;left:50%;transform:translateX(-50%);background:var(--red);color:var(--crm);font-family:'Josefin Sans',sans-serif;font-size:8px;letter-spacing:.3em;padding:4px 14px;white-space:nowrap}
.tat-tier{position:relative}
.t-cat{font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.4em;text-transform:uppercase;color:var(--red3);margin-bottom:10px}
.t-name{font-family:'Playfair Display',serif;font-size:22px;font-weight:700;color:var(--crm);margin-bottom:6px}
.t-sz{font-size:14px;color:var(--mst);font-style:italic;margin-bottom:14px}
.t-price{font-family:'Playfair Display',serif;font-size:44px;font-weight:900;color:var(--red);line-height:1;margin-bottom:5px}
.t-time{font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.3em;text-transform:uppercase;color:var(--mst);margin-bottom:14px}
.t-desc{font-size:14px;color:var(--mst);font-style:italic;line-height:1.72;border-top:1px solid var(--bdr2);padding-top:14px;margin-bottom:14px}
.t-incl{list-style:none;display:flex;flex-direction:column;gap:6px}
.t-incl li{font-size:13px;color:var(--mst);display:flex;gap:9px;align-items:flex-start}
.t-incl li::before{content:'✦';color:var(--red3);font-size:8px;margin-top:4px;flex-shrink:0}

/* ═══ CONTRACT FORM ═══ */
.contract-wrap{max-width:820px;margin:0 auto;padding:100px 40px}
.fhdr{text-align:center;padding:60px 0 48px;border-bottom:1px solid var(--bdr2);margin-bottom:56px}
.csec{margin-bottom:44px}
.csec h3{font-family:'Playfair Display',serif;font-size:20px;font-weight:700;color:var(--crm);border-left:3px solid var(--red);padding-left:14px;margin-bottom:16px}
.csec p,.csec li{font-size:16px;color:var(--mst);line-height:1.85;font-style:italic}
.csec ul{padding-left:20px;margin-top:8px}
.csec li{margin-bottom:8px}
.form-g{margin-bottom:20px}
.form-g label{display:block;font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.4em;text-transform:uppercase;color:var(--red3);margin-bottom:8px;font-weight:300}
.form-g input,.form-g select,.form-g textarea{width:100%;background:var(--char);border:1px solid var(--bdr2);color:var(--crm);font-family:'Cormorant Garamond',serif;font-size:17px;padding:13px 16px;outline:none;transition:border-color .3s;resize:vertical}
.form-g input:focus,.form-g select:focus,.form-g textarea:focus{border-color:var(--red)}
.form-g select option{background:var(--char)}
.form-row{display:grid;grid-template-columns:1fr 1fr;gap:18px}
@media(max-width:600px){.form-row{grid-template-columns:1fr}.contract-wrap{padding:80px 20px}}
.chk-item{display:flex;align-items:flex-start;gap:12px;cursor:pointer;margin-bottom:12px}
.chk-item input[type=checkbox]{width:16px;height:16px;accent-color:var(--red);flex-shrink:0;margin-top:3px;cursor:pointer}
.chk-item span{font-size:15px;color:var(--mst);font-style:italic;line-height:1.6}
.sig-input{border:none;border-bottom:1px solid var(--red3);background:transparent;width:100%;color:var(--crm);font-family:'Playfair Display',serif;font-size:22px;font-style:italic;padding:8px 0;outline:none}
.total-box{background:var(--obs);border:1px solid var(--red);padding:22px 26px;margin-top:24px;display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:10px}
.total-label{font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.4em;text-transform:uppercase;color:var(--mst)}
.total-val{font-family:'Playfair Display',serif;font-size:38px;font-weight:900;color:var(--red)}

/* ═══ TERMS ═══ */
.terms-wrap{max-width:780px;margin:0 auto;padding:100px 40px}
.t-sec{margin-bottom:48px;border-bottom:1px solid var(--bdr2);padding-bottom:48px}
.t-sec:last-child{border-bottom:none}
.t-num{font-family:'Playfair Display',serif;font-size:60px;font-weight:900;color:rgba(192,39,26,.08);line-height:1;margin-bottom:6px}
.t-sec h3{font-family:'Playfair Display',serif;font-size:22px;font-weight:700;color:var(--crm);margin-bottom:16px}
.t-sec p{font-size:15px;color:var(--mst);font-style:italic;line-height:1.9;margin-bottom:12px}
.t-sec ul{padding-left:18px}
.t-sec li{font-size:15px;color:var(--mst);font-style:italic;line-height:1.8;margin-bottom:8px}

/* ═══ WORKSHOP STYLES ═══ */
.ws-filt{font-family:'Josefin Sans',sans-serif;font-weight:300;font-size:10px;letter-spacing:.35em;text-transform:uppercase;padding:9px 20px;border:1px solid var(--bdr2);background:transparent;color:var(--mst);cursor:pointer;transition:all .3s}
.ws-filt.ws-on,.ws-filt:hover{border-color:var(--red);color:var(--red);background:var(--redfade)}
.guide-tab{font-family:'Josefin Sans',sans-serif;font-weight:100;font-size:9px;letter-spacing:.35em;text-transform:uppercase;padding:14px 22px;border:1px solid transparent;border-bottom:none;color:var(--mst);cursor:pointer;transition:all .3s;background:transparent;position:relative;bottom:-1px;white-space:nowrap}
.guide-tab.guide-on{color:var(--red);border-color:var(--bdr2);border-bottom-color:var(--obs);background:var(--obs)}
.guide-panel{display:none;background:var(--obs);border:1px solid var(--bdr2);border-top:none;padding:48px 44px;animation:fadeIn .4s ease}
.guide-panel.guide-panel-on{display:block}
@media(max-width:600px){.guide-panel{padding:24px 18px}}
.chk-row{display:flex;align-items:flex-start;gap:12px;padding:11px 0;border-bottom:1px solid rgba(192,39,26,.06);cursor:pointer}
.chk-box-ws{width:18px;height:18px;border:1px solid var(--bdr2);flex-shrink:0;margin-top:2px;display:flex;align-items:center;justify-content:center;transition:all .3s;font-size:11px;color:var(--blk)}
.chk-box-ws.done{background:var(--red);border-color:var(--red)}
.chk-txt{font-size:15px;color:var(--mst);font-style:italic;line-height:1.6}
.chk-txt b{color:var(--crm);font-style:normal}

/* ═══ BLOG ═══ */
.blog-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(340px,1fr));gap:2px}
.blog-card{background:var(--obs);border:1px solid var(--bdr2);overflow:hidden;transition:all .4s}
.blog-card:hover{border-color:rgba(192,39,26,.35);transform:translateY(-2px)}
.blog-card img{width:100%;height:200px;object-fit:cover;filter:brightness(.72);transition:filter .4s}
.blog-card:hover img{filter:brightness(.9)}
.blog-body{padding:28px 26px}
.blog-date{font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.4em;text-transform:uppercase;color:var(--red3);margin-bottom:10px}
.blog-h{font-family:'Playfair Display',serif;font-size:20px;font-weight:700;color:var(--crm);margin-bottom:10px;line-height:1.25}
.blog-p{font-size:14px;color:var(--mst);font-style:italic;line-height:1.75}

/* ═══ CTA ═══ */
.cta-sec{text-align:center;padding:100px 40px;position:relative;overflow:hidden;background:var(--obs)}
.cta-sec::before{content:'';position:absolute;inset:0;background:radial-gradient(ellipse 70% 60% at 50%,rgba(192,39,26,.06),transparent 70%)}
.cta-h{font-family:'Playfair Display',serif;font-size:clamp(34px,6vw,70px);font-weight:900;color:var(--crm);line-height:1.05;margin-bottom:18px;position:relative}
.cta-h em{color:var(--red);font-style:italic}
.cta-p{font-size:17px;color:var(--mst);font-style:italic;margin-bottom:44px;position:relative;max-width:500px;margin-left:auto;margin-right:auto}

/* ═══ FOOTER ═══ */
footer{background:var(--blk);border-top:1px solid var(--bdr);padding:52px 40px;text-align:center}
.foot-links{display:flex;gap:20px;justify-content:center;flex-wrap:wrap;margin:20px 0}
.foot-links a{font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.3em;text-transform:uppercase;color:var(--mst);text-decoration:none;cursor:pointer;transition:color .3s}
.foot-links a:hover{color:var(--red)}
.foot-social{display:flex;gap:14px;justify-content:center;flex-wrap:wrap;margin-top:20px}
.foot-social a{font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.3em;text-transform:uppercase;color:var(--dim);text-decoration:none;border:1px solid rgba(192,39,26,.15);padding:7px 14px;transition:all .3s}
.foot-social a:hover{color:var(--red);border-color:var(--red)}
.foot-q{font-size:14px;color:var(--dim);font-style:italic;margin-top:16px}

/* ═══ ABOUT GRID ═══ */
.about-grid{display:grid;grid-template-columns:1fr 1fr;gap:64px;align-items:start}
@media(max-width:700px){.about-grid{grid-template-columns:1fr;gap:32px}}
.quote-box{border:1px solid var(--bdr2);padding:36px;background:var(--obs)}
.quote-txt{font-family:'Playfair Display',serif;font-size:20px;font-style:italic;color:var(--crm);line-height:1.45;margin-bottom:20px}
.quote-attr{font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.4em;text-transform:uppercase;color:var(--red3)}

/* ═══ TATTOO STRIP ═══ */
.tattoo-strip{background:linear-gradient(135deg,#1A0508 0%,#0D0305 100%);border-top:1px solid rgba(192,39,26,.4);border-bottom:1px solid rgba(192,39,26,.4);padding:64px 40px;text-align:center;position:relative;overflow:hidden}
.tattoo-strip::before{content:'TATTOO';font-family:'Playfair Display',serif;font-size:200px;font-weight:900;color:rgba(192,39,26,.04);position:absolute;right:-20px;top:50%;transform:translateY(-50%);pointer-events:none;line-height:1}
.new-pill{display:inline-block;font-family:'Josefin Sans',sans-serif;font-size:8px;letter-spacing:.45em;text-transform:uppercase;color:var(--red);background:rgba(192,39,26,.1);border:1px solid rgba(192,39,26,.3);padding:5px 18px;margin-bottom:20px}
.ts-h{font-family:'Playfair Display',serif;font-size:clamp(26px,4vw,50px);font-weight:900;color:var(--crm);margin-bottom:12px}
.ts-h em{color:var(--red);font-style:italic}
.ts-p{font-size:17px;color:rgba(240,232,216,.6);font-style:italic;max-width:560px;margin:0 auto 28px;line-height:1.8}

/* ═══ WORKSHOP PKG PAYPAL ═══ */
.pp-btn{display:block;width:100%;background:var(--red);color:var(--crm);font-family:'Josefin Sans',sans-serif;font-weight:400;font-size:11px;letter-spacing:.42em;text-transform:uppercase;padding:20px;border:none;cursor:pointer;transition:background .3s;text-align:center}
.pp-btn:hover{background:var(--red2)}
.pp-sub{font-size:13px;color:var(--mst);font-style:italic;text-align:center;margin-top:8px}
</style>
</head>
<body>

<!-- ═══ SVG LOGO DEFS (embedded, reusable) ═══ -->
<!-- The butterfly-soul logo: wings formed from the letter S curves,
     a skull-moth hybrid at center, thorax becomes the word "LOST" -->
<svg width="0" height="0" style="position:absolute;overflow:hidden">
  <defs>
    <linearGradient id="wing-grad-l" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%" style="stop-color:#C0271A;stop-opacity:1"/>
      <stop offset="60%" style="stop-color:#8B1A10;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#3A0808;stop-opacity:1"/>
    </linearGradient>
    <linearGradient id="wing-grad-r" x1="100%" y1="0%" x2="0%" y2="100%">
      <stop offset="0%" style="stop-color:#C0271A;stop-opacity:1"/>
      <stop offset="60%" style="stop-color:#8B1A10;stop-opacity:1"/>
      <stop offset="100%" style="stop-color:#3A0808;stop-opacity:1"/>
    </linearGradient>
    <filter id="glow">
      <feGaussianBlur stdDeviation="2.5" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
    <symbol id="logo-mark" viewBox="0 0 200 160">
      <!-- Left upper wing -->
      <path d="M100,80 C85,65 55,50 30,38 C15,30 8,20 12,10 C16,2 30,0 48,8 C70,18 90,45 100,80Z"
        fill="url(#wing-grad-l)" opacity="0.95"/>
      <!-- Left lower wing -->
      <path d="M100,80 C88,95 65,110 40,122 C22,130 12,138 15,148 C18,156 32,158 52,148 C76,136 92,112 100,80Z"
        fill="url(#wing-grad-l)" opacity="0.75"/>
      <!-- Right upper wing -->
      <path d="M100,80 C115,65 145,50 170,38 C185,30 192,20 188,10 C184,2 170,0 152,8 C130,18 110,45 100,80Z"
        fill="url(#wing-grad-r)" opacity="0.95"/>
      <!-- Right lower wing -->
      <path d="M100,80 C112,95 135,110 160,122 C178,130 188,138 185,148 C182,156 168,158 148,148 C124,136 108,112 100,80Z"
        fill="url(#wing-grad-r)" opacity="0.75"/>
      <!-- Wing veins left upper -->
      <path d="M100,80 C88,68 72,55 52,42 M100,80 C84,70 65,58 44,50"
        stroke="#1A0508" stroke-width="1" fill="none" opacity="0.6"/>
      <!-- Wing veins right upper -->
      <path d="M100,80 C112,68 128,55 148,42 M100,80 C116,70 135,58 156,50"
        stroke="#1A0508" stroke-width="1" fill="none" opacity="0.6"/>
      <!-- Wing dots left -->
      <circle cx="62" cy="44" r="4" fill="#F0E8D8" opacity="0.25"/>
      <circle cx="48" cy="72" r="3" fill="#F0E8D8" opacity="0.2"/>
      <circle cx="58" cy="118" r="5" fill="#F0E8D8" opacity="0.2"/>
      <!-- Wing dots right -->
      <circle cx="138" cy="44" r="4" fill="#F0E8D8" opacity="0.25"/>
      <circle cx="152" cy="72" r="3" fill="#F0E8D8" opacity="0.2"/>
      <circle cx="142" cy="118" r="5" fill="#F0E8D8" opacity="0.2"/>
      <!-- Body / thorax -->
      <ellipse cx="100" cy="80" rx="7" ry="22" fill="#0A0A0C" stroke="#C0271A" stroke-width="1.5"/>
      <!-- Soul orb at center -->
      <circle cx="100" cy="80" r="5" fill="#C0271A" opacity="0.9" filter="url(#glow)"/>
      <!-- Antennae -->
      <line x1="100" y1="58" x2="85" y2="34" stroke="#C0271A" stroke-width="1.2" stroke-linecap="round"/>
      <line x1="100" y1="58" x2="115" y2="34" stroke="#C0271A" stroke-width="1.2" stroke-linecap="round"/>
      <circle cx="84" cy="33" r="2.5" fill="#C0271A"/>
      <circle cx="116" cy="33" r="2.5" fill="#C0271A"/>
    </symbol>
  </defs>
</svg>

<!-- ═══ LIGHTBOX ═══ -->
<div class="lb" id="lb" onclick="closeLB(event)">
  <span class="lb-close" onclick="closeLB()">✕</span>
  <img id="lb-img" src="" alt="">
  <span class="lb-cap" id="lb-cap"></span>
</div>

<!-- ═══ NAV ═══ -->
<nav id="main-nav">
  <div class="nav-logo-wrap" onclick="go('home')">
    <!-- Inline logo mark small -->
    <svg width="36" height="30" viewBox="0 0 200 160" style="flex-shrink:0">
      <use href="#logo-mark"/>
    </svg>
    <div class="nav-logo-text">
      Lost Soul<em>Art Studio</em>
    </div>
  </div>
  <ul class="nav-links" id="nav-links">
    <li><a onclick="go('home')" id="n-home" class="active">Home</a></li>
    <li><a onclick="go('gallery')" id="n-gallery">Gallery</a></li>
    <li><a onclick="go('portraits')" id="n-portraits">Portraits</a></li>
    <li><a onclick="go('murals')" id="n-murals">Murals</a></li>
    <li><a onclick="go('storefronts')" id="n-storefronts">Storefronts</a></li>
    <li><a onclick="go('tattoo')" id="n-tattoo" class="highlight">✦ Tattoo</a></li>
    <li><a onclick="go('workshops')" id="n-workshops" class="highlight">✦ Workshops</a></li>
    <li><a onclick="go('contract')" id="n-contract">Commission</a></li>
    <li><a onclick="go('blog')" id="n-blog">Blog</a></li>
    <li><a onclick="go('terms')" id="n-terms">Terms</a></li>
  </ul>
  <div class="hamburger" id="ham" onclick="toggleMenu()">
    <span></span><span></span><span></span>
  </div>
</nav>

<!-- ══════════════════════════════════════
     HOME PAGE
══════════════════════════════════════ -->
<div id="page-home" class="page active">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-glow"></div>
    <div class="hero-art-bg">
      <img src="https://lostsoulart.simdif.com/images/public/sd_69611b5fd49f1.jpg?no_cache=1767971699" alt="">
    </div>
    <p class="eyebrow">Roberto Cisneros &nbsp;·&nbsp; San Francisco, CA</p>

    <!-- LARGE LOGO MARK in hero -->
    <div style="opacity:0;animation:fadeIn 1.4s ease forwards .3s;margin-bottom:20px;animation-fill-mode:both">
      <svg width="110" height="88" viewBox="0 0 200 160" style="filter:drop-shadow(0 0 20px rgba(192,39,26,.4));animation:float 4s ease-in-out infinite">
        <use href="#logo-mark"/>
      </svg>
    </div>

    <h1>Lost Soul<br><em>Art Studio</em></h1>
    <div class="med-tags">
      <span class="med-tag">Acrylic</span>
      <span class="med-tag">Ballpoint Pen</span>
      <span class="med-tag">Watercolor</span>
      <span class="med-tag" style="color:var(--red);border-color:rgba(192,39,26,.3)">✦ Now Tattooing</span>
    </div>
    <p class="hero-sub">Fine art portraiture and contemporary surrealism. Custom murals, storefront installations, workshops — and now, original tattoo art. Getting lost in imagination.</p>

    <!-- SOCIAL LINKS -->
    <div class="hero-socials">
      <a href="https://www.facebook.com/lostsoulart" target="_blank" rel="noopener" class="hsoc">Facebook</a>
      <a href="https://www.instagram.com/lostsoulart" target="_blank" rel="noopener" class="hsoc">Instagram</a>
      <a href="https://www.tiktok.com/@lostsoulart" target="_blank" rel="noopener" class="hsoc">TikTok</a>
      <a href="https://www.youtube.com/@lostsoulart" target="_blank" rel="noopener" class="hsoc">YouTube</a>
    </div>
    <div class="hero-line"></div>
  </div>

  <!-- FEATURED ARTWORKS -->
  <div style="background:var(--blk)">
    <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:2px">
      <div style="position:relative;overflow:hidden;aspect-ratio:4/3;cursor:pointer" onclick="go('gallery')">
        <img src="https://lostsoulart.simdif.com/images/public/sd_69611b5fd49f1.jpg?no_cache=1767971699" alt="Transcend to Your Highest Vibrational Self" loading="lazy" style="width:100%;height:100%;object-fit:cover;filter:brightness(.72);transition:transform .7s,filter .5s" onmouseover="this.style.transform='scale(1.06)';this.style.filter='brightness(1)'" onmouseout="this.style.transform='scale(1)';this.style.filter='brightness(.72)'">
        <div style="position:absolute;bottom:0;left:0;right:0;padding:20px 16px 14px;background:linear-gradient(to top,rgba(10,10,12,.92),transparent)">
          <p style="font-family:'Josefin Sans',sans-serif;font-size:8px;letter-spacing:.35em;text-transform:uppercase;color:var(--red);margin-bottom:3px">Signature Work</p>
          <p style="font-family:'Playfair Display',serif;font-size:15px;font-weight:700;color:var(--crm)">Transcend to Your Highest Vibrational Self</p>
        </div>
      </div>
      <div style="position:relative;overflow:hidden;aspect-ratio:4/3;cursor:pointer" onclick="go('gallery')">
        <img src="https://lostsoulart.simdif.com/images/public/sd_696119a390eed.jpg?no_cache=1767971257" alt="The Duality of it All" loading="lazy" style="width:100%;height:100%;object-fit:cover;filter:brightness(.72);transition:transform .7s,filter .5s" onmouseover="this.style.transform='scale(1.06)';this.style.filter='brightness(1)'" onmouseout="this.style.transform='scale(1)';this.style.filter='brightness(.72)'">
        <div style="position:absolute;bottom:0;left:0;right:0;padding:20px 16px 14px;background:linear-gradient(to top,rgba(10,10,12,.92),transparent)">
          <p style="font-family:'Josefin Sans',sans-serif;font-size:8px;letter-spacing:.35em;text-transform:uppercase;color:var(--red);margin-bottom:3px">Signature Work</p>
          <p style="font-family:'Playfair Display',serif;font-size:15px;font-weight:700;color:var(--crm)">The Duality of It All</p>
        </div>
      </div>
      <div style="position:relative;overflow:hidden;aspect-ratio:4/3;cursor:pointer" onclick="go('gallery')">
        <img src="https://lostsoulart.simdif.com/images/public/sd_69611addad79a.jpg?no_cache=1767975164" alt="Butterfly Spirit" loading="lazy" style="width:100%;height:100%;object-fit:cover;filter:brightness(.72);transition:transform .7s,filter .5s" onmouseover="this.style.transform='scale(1.06)';this.style.filter='brightness(1)'" onmouseout="this.style.transform='scale(1)';this.style.filter='brightness(.72)'">
        <div style="position:absolute;bottom:0;left:0;right:0;padding:20px 16px 14px;background:linear-gradient(to top,rgba(10,10,12,.92),transparent)">
          <p style="font-family:'Josefin Sans',sans-serif;font-size:8px;letter-spacing:.35em;text-transform:uppercase;color:var(--red);margin-bottom:3px">Signature Work</p>
          <p style="font-family:'Playfair Display',serif;font-size:15px;font-weight:700;color:var(--crm)">Butterfly Spirit</p>
        </div>
      </div>
    </div>
    <div style="text-align:center;padding:18px;background:var(--obs);border-top:1px solid var(--bdr2)">
      <button onclick="go('gallery')" style="font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.42em;text-transform:uppercase;color:var(--red);background:transparent;border:none;cursor:pointer;transition:color .3s" onmouseover="this.style.color='var(--red2)'" onmouseout="this.style.color='var(--red)'">View Full Portfolio — 31 Original Works →</button>
    </div>
  </div>

  <!-- TATTOO STRIP -->
  <div class="tattoo-strip">
    <div class="new-pill">Now Available · April 2026</div>
    <h2 class="ts-h">Introducing <em>Tattoo Art</em><br>by Lost Soul Art Studio</h2>
    <p class="ts-p">Roberto Cisneros is now accepting custom tattoo commissions — bringing the same surrealist, fine-line vision that defines the studio's paintings directly onto skin. Original flash designs revealed every Wednesday at 5 PM.</p>
    <button class="btn btn-red" onclick="go('tattoo')">View Tattoo Services &amp; Pricing</button>
  </div>

  <!-- ARTIST STATEMENT -->
  <section style="background:var(--obs);border-bottom:1px solid var(--bdr2)">
    <div class="wrap">
      <div style="display:grid;grid-template-columns:1fr 1fr;gap:80px;align-items:center" class="rev">
        <div>
          <p class="sec-label">Artist Statement</p>
          <h2 class="sh">The Philosophy<br><em>Behind the Work</em></h2>
          <div style="width:48px;height:2px;background:var(--red);margin:0 0 32px"></div>
          <p style="font-size:19px;color:var(--crm);line-height:1.9;margin-bottom:20px;font-style:italic">"I have always believed that art is not something you make. It is something you find — in the space between what you planned to paint and what the brush actually does when you stop controlling it."</p>
          <p style="font-size:16px;color:var(--mst);line-height:1.9;margin-bottom:20px;font-style:italic">My work lives in the territory between classical fine art and surrealist expressionism. I am drawn to the faces people make when they think no one is watching, to the objects that accumulate meaning without anyone deciding they should, to the colors that exist only in the moments between waking and sleep.</p>
          <p style="font-size:16px;color:var(--mst);line-height:1.9;margin-bottom:20px;font-style:italic">I work in acrylic, ballpoint pen, and watercolor — three mediums that could not be more different from each other, and that combination is deliberate. Acrylic is bold and declarative. Watercolor is patient and surrendered. Ballpoint pen is obsessive and precise.</p>
          <p style="font-size:16px;color:var(--mst);line-height:1.9;margin-bottom:32px;font-style:italic">My mission with Lost Soul Art Studio has always been the same: to create work that makes someone stop. Not just look — stop. Feel something shift. Recognize something in the image that they had not been able to name before they saw it.</p>
          <p style="font-family:'Playfair Display',serif;font-size:20px;font-style:italic;color:var(--red)">"The labyrinth of the creative mind is where the soul goes to find itself."</p>
          <p style="font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.4em;text-transform:uppercase;color:var(--red3);margin-top:8px">— Roberto Cisneros</p>
        </div>
        <div>
          <div style="display:grid;grid-template-columns:1fr 1fr;gap:2px">
            <div style="position:relative;overflow:hidden;aspect-ratio:3/4;cursor:pointer" onclick="go('gallery')">
              <img src="https://lostsoulart.simdif.com/images/public/sd_6960b6bc6042c.jpg?no_cache=1767949552" alt="The Lost Soul" loading="lazy" style="width:100%;height:100%;object-fit:cover;filter:brightness(.8);transition:all .6s" onmouseover="this.style.filter='brightness(1)';this.style.transform='scale(1.04)'" onmouseout="this.style.filter='brightness(.8)';this.style.transform='scale(1)'">
              <div style="position:absolute;bottom:0;left:0;right:0;padding:12px;background:linear-gradient(to top,rgba(10,10,12,.88),transparent)"><p style="font-family:'Playfair Display',serif;font-size:13px;color:var(--crm)">The Lost Soul</p></div>
            </div>
            <div style="position:relative;overflow:hidden;aspect-ratio:3/4;cursor:pointer" onclick="go('gallery')">
              <img src="https://lostsoulart.simdif.com/images/public/sd_6960b6eda8c79.jpg?no_cache=1767949611" alt="Rebellious" loading="lazy" style="width:100%;height:100%;object-fit:cover;filter:brightness(.8);transition:all .6s" onmouseover="this.style.filter='brightness(1)';this.style.transform='scale(1.04)'" onmouseout="this.style.filter='brightness(.8)';this.style.transform='scale(1)'">
              <div style="position:absolute;bottom:0;left:0;right:0;padding:12px;background:linear-gradient(to top,rgba(10,10,12,.88),transparent)"><p style="font-family:'Playfair Display',serif;font-size:13px;color:var(--crm)">Rebellious</p></div>
            </div>
            <div style="position:relative;overflow:hidden;cursor:pointer;grid-column:1/-1" onclick="go('gallery')">
              <img src="https://lostsoulart.simdif.com/images/public/sd_6960b75a5f55d.jpg?no_cache=1767949704" alt="Opening the 3rd Eye" loading="lazy" style="width:100%;height:190px;object-fit:cover;filter:brightness(.8);transition:all .6s" onmouseover="this.style.filter='brightness(1)'" onmouseout="this.style.filter='brightness(.8)'">
              <div style="position:absolute;bottom:0;left:0;right:0;padding:12px;background:linear-gradient(to top,rgba(10,10,12,.88),transparent)"><p style="font-family:'Playfair Display',serif;font-size:13px;color:var(--crm)">Opening the 3rd Eye</p></div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- SERVICES -->
  <div class="band">
    <div class="wrap">
      <div class="rev">
        <p class="sec-label">Professional Services</p>
        <h2 class="sh">Fine Art Portraiture &amp;<br><em>Contemporary Surrealism</em></h2>
        <p class="sub">One artist. Every medium. A complete creative practice built around the belief that art should challenge the viewer to find beauty within the shadows of the psyche.</p>
      </div>
      <div class="grid rev">
        <div class="card" style="cursor:pointer" onclick="go('portraits')"><p class="card-label">Fine Art</p><h3 class="card-h">Portraits of People &amp; Pets</h3><p class="card-body">Hand-painted portraits in acrylic, watercolor, or ballpoint pen. Each one built from your reference photos — capturing personality, not just likeness.</p><div class="price-line"><p class="price-from">Starting from</p><div class="price-val">$150</div><p class="price-note">5×7 small · Up to 24×36 statement pieces</p></div></div>
        <div class="card" style="cursor:pointer" onclick="go('murals')"><p class="card-label">Interior Murals</p><h3 class="card-h">Residential &amp; Commercial</h3><p class="card-body">Acrylic murals that transform a space into something people remember and photograph. Homes, cafés, restaurants, offices, hotel lobbies.</p><div class="price-line"><p class="price-from">Starting from</p><div class="price-val">$500</div><p class="price-note">Quoted by square footage and complexity</p></div></div>
        <div class="card" style="cursor:pointer" onclick="go('storefronts')"><p class="card-label">Storefront Art</p><h3 class="card-h">Window Installations</h3><p class="card-body">Seasonal and custom window painting for businesses. Halloween, Christmas, summer themes, branded permanent pieces — completed in one day.</p><div class="price-line"><p class="price-from">Starting from</p><div class="price-val">$200</div><p class="price-note">Up to 15 sq ft · Larger tiers available</p></div></div>
        <div class="card" style="border-color:rgba(192,39,26,.4);cursor:pointer" onclick="go('tattoo')"><p class="card-label" style="color:var(--red)">✦ New — Now Booking</p><h3 class="card-h">Custom Tattoo Art</h3><p class="card-body">Original custom tattoos and flash designs rooted in surrealist fine-line imagery. The same vision that defines the paintings — now permanent on skin.</p><div class="price-line"><p class="price-from">Studio minimum</p><div class="price-val">$150</div><p class="price-note">Custom, flash &amp; friend rates available</p></div><div class="live-badge"><div class="live-dot"></div><span class="live-txt">Flash drops · Wednesday Lives · 5 PM</span></div></div>
        <div class="card" onclick="go('workshops')" style="cursor:pointer"><p class="card-label">Workshops</p><h3 class="card-h">Studio Workshops</h3><p class="card-body">Every Saturday 10 AM. Guided 90-minute surrealist painting sessions. All materials included. Max 6 students. Book and pay directly online.</p><div class="price-line"><p class="price-from">Group sessions from</p><div class="price-val">$100</div><p class="price-note">Per student · Private sessions $180</p></div></div>
        <div class="card" onclick="go('gallery')" style="cursor:pointer"><p class="card-label">Originals &amp; Prints</p><h3 class="card-h">Own a Lost Soul Work</h3><p class="card-body">Original acrylic paintings, watercolor studies, and ballpoint pen works. Fine art prints from $50. Wednesday Live drops — first access to new work.</p><div class="price-line"><p class="price-from">Prints from</p><div class="price-val">$50</div><p class="price-note">Originals from $150 · Ships nationwide</p></div><div class="live-badge"><div class="live-dot"></div><span class="live-txt">Live drops every Wednesday · 5 PM</span></div></div>
      </div>
    </div>
  </div>

  <!-- ABOUT -->
  <section>
    <div class="wrap">
      <div class="about-grid rev">
        <div>
          <p class="sec-label">The Artist</p>
          <h2 class="sh">Roberto<br><em>Cisneros</em></h2>
          <p style="font-size:17px;color:var(--mst);font-style:italic;line-height:1.85;margin-bottom:18px">Roberto Cisneros is a multidisciplinary artist whose work bridges the gap between classical fine-art technique and contemporary graphic expressionism. Under the banner of Lost Soul Art Studio, he creates works that challenge the viewer to find beauty within the shadows of the psyche.</p>
          <p style="font-size:17px;color:var(--mst);font-style:italic;line-height:1.85;margin-bottom:32px">Working in acrylic, ballpoint pen, and watercolor from his San Francisco studio, Roberto brings a surrealist's eye to every commission — and now extends that same creative vision into original tattoo art.</p>
          <div class="btn-row">
            <button class="btn btn-red" onclick="go('gallery')">View Portfolio</button>
            <button class="btn btn-out" onclick="go('contract')">Start a Commission</button>
          </div>
        </div>
        <div>
          <div class="quote-box">
            <img src="https://lostsoulart.simdif.com/images/th/sd_69c862b26dc86.png?no_cache=1774740168" alt="Roberto Cisneros" style="width:100%;margin-bottom:28px;filter:brightness(.88)">
            <p class="quote-txt">"The labyrinth of the creative mind is where the soul goes to find itself."</p>
            <p class="quote-attr">— Roberto Cisneros, Lost Soul Art Studio</p>
            <div style="margin-top:24px;padding-top:24px;border-top:1px solid var(--bdr2)">
              <p style="font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.35em;text-transform:uppercase;color:var(--mst);margin-bottom:12px">Watch Live Every Wednesday at 5 PM</p>
              <div class="live-badge"><div class="live-dot"></div><span class="live-txt">Facebook · Instagram · TikTok · YouTube</span></div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- TESTIMONIALS -->
  <div class="band">
    <div class="wrap">
      <div class="rev"><p class="sec-label">Client Words</p><h2 class="sh">What People<br><em>Are Saying</em></h2></div>
      <div class="tcards rev">
        <div class="tcard"><p class="tcard-q">Working with Lost Soul Art was an incredible experience. The custom piece created for our home perfectly captures my innovative spirit and has become a conversation starter with every person who visits. The attention to detail and Roberto's process exceeded our expectations.</p><p class="tcard-name">Jojo Collins</p><p class="tcard-role">San Francisco, CA Resident</p></div>
        <div class="tcard"><p class="tcard-q">I commissioned a piece for my home and was blown away by the result. The artist truly listened to what I wanted and delivered something even better than I imagined. The colors, energy, and emotion in the work make it the centerpiece of my living room.</p><p class="tcard-name">Lawrence Renfield</p><p class="tcard-role">Interior Designer</p></div>
        <div class="tcard"><p class="tcard-q">The mural painted for our Mission District café has transformed the entire atmosphere of our space. Customers constantly ask about it and it's become a signature part of our brand identity. Professional, creative, and completed on time — couldn't ask for more.</p><p class="tcard-name">David Park</p><p class="tcard-role">Owner, Ritual Coffee Collective</p></div>
      </div>
    </div>
  </div>

  <!-- SOCIAL / FOLLOW -->
  <section style="background:var(--char);border-top:1px solid var(--bdr2)">
    <div class="wrap" style="text-align:center">
      <div class="rev">
        <p class="sec-label" style="justify-content:center">Follow the Studio</p>
        <h2 class="sh" style="max-width:500px;margin:0 auto 14px">Find Lost Soul Art<br><em>On Every Platform</em></h2>
        <p class="sub" style="max-width:440px;margin:0 auto 40px">New work drops every Wednesday at 5 PM on all four platforms simultaneously. Follow to catch live painting sessions, flash tattoo reveals, workshop announcements, and original art drops.</p>
        <div style="display:grid;grid-template-columns:repeat(4,1fr);gap:2px;max-width:800px;margin:0 auto">
          <a href="https://www.facebook.com/lostsoulart" target="_blank" rel="noopener" style="background:var(--obs);border:1px solid var(--bdr2);padding:32px 20px;text-decoration:none;transition:all .4s;display:block" onmouseover="this.style.borderColor='var(--red)';this.style.background='var(--redfade)'" onmouseout="this.style.borderColor='var(--bdr2)';this.style.background='var(--obs)'">
            <div style="font-size:32px;margin-bottom:12px">f</div>
            <p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.4em;text-transform:uppercase;color:var(--red);margin-bottom:6px">Facebook</p>
            <p style="font-size:13px;color:var(--mst);font-style:italic">Live every Wednesday</p>
          </a>
          <a href="https://www.instagram.com/lostsoulart" target="_blank" rel="noopener" style="background:var(--obs);border:1px solid var(--bdr2);padding:32px 20px;text-decoration:none;transition:all .4s;display:block" onmouseover="this.style.borderColor='var(--red)';this.style.background='var(--redfade)'" onmouseout="this.style.borderColor='var(--bdr2)';this.style.background='var(--obs)'">
            <div style="font-size:32px;margin-bottom:12px">◎</div>
            <p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.4em;text-transform:uppercase;color:var(--red);margin-bottom:6px">Instagram</p>
            <p style="font-size:13px;color:var(--mst);font-style:italic">Process &amp; portfolio drops</p>
          </a>
          <a href="https://www.tiktok.com/@lostsoulart" target="_blank" rel="noopener" style="background:var(--obs);border:1px solid var(--bdr2);padding:32px 20px;text-decoration:none;transition:all .4s;display:block" onmouseover="this.style.borderColor='var(--red)';this.style.background='var(--redfade)'" onmouseout="this.style.borderColor='var(--bdr2)';this.style.background='var(--obs)'">
            <div style="font-size:32px;margin-bottom:12px">♪</div>
            <p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.4em;text-transform:uppercase;color:var(--red);margin-bottom:6px">TikTok</p>
            <p style="font-size:13px;color:var(--mst);font-style:italic">Studio life &amp; technique</p>
          </a>
          <a href="https://www.youtube.com/@lostsoulart" target="_blank" rel="noopener" style="background:var(--obs);border:1px solid var(--bdr2);padding:32px 20px;text-decoration:none;transition:all .4s;display:block" onmouseover="this.style.borderColor='var(--red)';this.style.background='var(--redfade)'" onmouseout="this.style.borderColor='var(--bdr2)';this.style.background='var(--obs)'">
            <div style="font-size:32px;margin-bottom:12px">▶</div>
            <p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.4em;text-transform:uppercase;color:var(--red);margin-bottom:6px">YouTube</p>
            <p style="font-size:13px;color:var(--mst);font-style:italic">Full Lives &amp; tutorials</p>
          </a>
        </div>
        <div style="margin-top:32px">
          <div class="live-badge" style="display:inline-flex"><div class="live-dot"></div><span class="live-txt">Live every Wednesday at 5:00 PM · All platforms simultaneously</span></div>
        </div>
      </div>
    </div>
  </section>

  <!-- CONTACT STRIP -->
  <section style="background:linear-gradient(135deg,#1A0508,#0A0A0C);border-top:1px solid var(--bdr)">
    <div class="wrap" style="text-align:center">
      <div class="rev">
        <p class="sec-label" style="justify-content:center">Get in Touch</p>
        <h2 class="sh" style="margin-bottom:14px">Ready to Begin<br><em>Something Real?</em></h2>
        <p class="sub" style="max-width:440px;margin:0 auto 40px">Every commission starts with a conversation. Three ways to reach Roberto directly — choose the one that works best for you.</p>
        <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:2px;max-width:700px;margin:0 auto 32px">
          <div style="background:var(--obs);border:1px solid var(--bdr2);padding:28px 20px">
            <p style="font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.4em;text-transform:uppercase;color:var(--red);margin-bottom:10px">Online Form</p>
            <p style="font-size:15px;color:var(--mst);font-style:italic;line-height:1.65;margin-bottom:16px">Fill out the commission agreement with your project details.</p>
            <button onclick="go('contract')" style="font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.35em;text-transform:uppercase;color:var(--red);background:transparent;border:1px solid var(--bdr);padding:8px 16px;cursor:pointer;transition:all .3s" onmouseover="this.style.borderColor='var(--red)'" onmouseout="this.style.borderColor='var(--bdr)'">Start Here →</button>
          </div>
          <div style="background:var(--obs);border:1px solid var(--red);padding:28px 20px">
            <p style="font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.4em;text-transform:uppercase;color:var(--red);margin-bottom:10px">WhatsApp</p>
            <p style="font-size:15px;color:var(--mst);font-style:italic;line-height:1.65;margin-bottom:16px">The fastest way to get a real answer from Roberto directly.</p>
            <a href="https://wa.me/13412539299" target="_blank" style="font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.35em;text-transform:uppercase;color:var(--crm);background:var(--red);border:none;padding:9px 18px;cursor:pointer;text-decoration:none;display:inline-block;transition:background .3s" onmouseover="this.style.background='var(--red2)'" onmouseout="this.style.background='var(--red)'">+1 (341) 253-9299</a>
          </div>
          <div style="background:var(--obs);border:1px solid var(--bdr2);padding:28px 20px">
            <p style="font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.4em;text-transform:uppercase;color:var(--red);margin-bottom:10px">PayPal Deposit</p>
            <p style="font-size:15px;color:var(--mst);font-style:italic;line-height:1.65;margin-bottom:16px">Ready to commit? Pay your deposit directly to secure your spot.</p>
            <a href="https://www.paypal.com/ncp/payment/8LZGEN2GHFUMU" target="_blank" style="font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.35em;text-transform:uppercase;color:var(--red);background:transparent;border:1px solid var(--bdr);padding:8px 16px;text-decoration:none;display:inline-block;transition:all .3s" onmouseover="this.style.borderColor='var(--red)'" onmouseout="this.style.borderColor='var(--bdr)'">Pay via PayPal</a>
          </div>
        </div>
      </div>
    </div>
  </section>

  <footer>
    <!-- Footer logo -->
    <div style="display:flex;align-items:center;justify-content:center;gap:16px;margin-bottom:18px">
      <svg width="48" height="38" viewBox="0 0 200 160" style="opacity:.8"><use href="#logo-mark"/></svg>
      <div style="text-align:left">
        <p style="font-family:'Playfair Display',serif;font-size:18px;font-weight:700;color:var(--crm)">Lost Soul Art Studio</p>
        <p style="font-family:'Josefin Sans',sans-serif;font-size:8px;letter-spacing:.4em;text-transform:uppercase;color:var(--red)">Roberto Cisneros · San Francisco, CA</p>
      </div>
    </div>
    <div class="foot-links">
      <a onclick="go('home')">Home</a><a onclick="go('gallery')">Gallery</a><a onclick="go('portraits')">Portraits</a><a onclick="go('murals')">Murals</a><a onclick="go('storefronts')">Storefronts</a><a onclick="go('tattoo')">Tattoo</a><a onclick="go('workshops')">Workshops</a><a onclick="go('contract')">Commission</a><a onclick="go('blog')">Blog</a><a onclick="go('terms')">Terms</a>
    </div>
    <div class="foot-social">
      <a href="https://www.facebook.com/lostsoulart" target="_blank" rel="noopener">Facebook</a>
      <a href="https://www.instagram.com/lostsoulart" target="_blank" rel="noopener">Instagram</a>
      <a href="https://www.tiktok.com/@lostsoulart" target="_blank" rel="noopener">TikTok</a>
      <a href="https://www.youtube.com/@lostsoulart" target="_blank" rel="noopener">YouTube</a>
      <a href="https://wa.me/13412539299" target="_blank" rel="noopener">WhatsApp</a>
    </div>
    <p class="foot-q">"The labyrinth of the creative mind is where the soul goes to find itself." © 2026 Lost Soul Art Studio. All Rights Reserved.</p>
  </footer>
</div>

<!-- ══════════════════════════════════════
     GALLERY
══════════════════════════════════════ -->
<div id="page-gallery" class="page">
  <div class="hero" style="min-height:50vh;padding:130px 40px 60px">
    <div class="hero-glow"></div>
    <p class="eyebrow">Lost Soul Art Studio</p>
    <svg width="60" height="48" viewBox="0 0 200 160" style="opacity:0;animation:fadeIn 1s ease forwards .3s;margin-bottom:16px"><use href="#logo-mark"/></svg>
    <h1 style="font-size:clamp(44px,8vw,88px)">SF <em>Gallery</em></h1>
    <p class="hero-sub">Original works in acrylic, ballpoint pen, and watercolor. Thirty-one pieces of surrealist portraiture and contemporary expressionism.</p>
  </div>
  <div style="padding:60px 40px 100px"><div class="gal-grid" id="gallery-grid"></div></div>
  <div class="cta-sec">
    <h2 class="cta-h">Own a Piece of<br><em>Lost Soul Art</em></h2>
    <p class="cta-p">Commission an original or enquire about a print. Every piece is available as a limited edition giclée print.</p>
    <div class="btn-row" style="justify-content:center">
      <button class="btn btn-red" onclick="go('contract')">Commission Your Piece</button>
      <a href="https://wa.me/13412539299" target="_blank" class="btn btn-out">Ask About Prints</a>
    </div>
  </div>
  <footer>
    <div style="display:flex;align-items:center;justify-content:center;gap:14px;margin-bottom:16px"><svg width="40" height="32" viewBox="0 0 200 160" style="opacity:.7"><use href="#logo-mark"/></svg><p style="font-family:'Playfair Display',serif;font-size:16px;font-weight:700;color:var(--crm)">Lost Soul Art Studio</p></div>
    <p class="foot-q">"The labyrinth of the creative mind is where the soul goes to find itself." © 2026</p>
  </footer>
</div>

<!-- ══════════════════════════════════════
     PORTRAITS
══════════════════════════════════════ -->
<div id="page-portraits" class="page">
  <div class="hero" style="min-height:55vh;padding:130px 40px 60px">
    <div class="hero-glow"></div>
    <p class="eyebrow">Fine Art Portraiture</p>
    <h1 style="font-size:clamp(44px,8vw,90px)">Portraits of<br><em>People &amp; Pets</em></h1>
    <p class="hero-sub">Hand-painted portraits in acrylic, watercolor, or ballpoint pen. Each one a singular piece built around your reference and shaped by your story.</p>
  </div>
  <section>
    <div class="wrap rev">
      <p class="sec-label">Official Pricing Scale</p>
      <h2 class="sh">Portrait<br><em>Pricing</em></h2>
      <p class="sub">A 30% non-refundable deposit secures your spot. The remaining 70% is due upon completion.</p>
      <table class="ptable">
        <thead><tr><th>Tier</th><th>Size</th><th>Total Price</th><th>30% Deposit</th><th>Pay</th></tr></thead>
        <tbody>
          <tr class="tier-h"><td colspan="5">SMALL PORTRAITS</td></tr>
          <tr><td>Small</td><td>5×7</td><td class="pv">$150</td><td class="dv">$45</td><td rowspan="3" style="vertical-align:middle;text-align:center"><a href="https://www.paypal.com/ncp/payment/8LZGEN2GHFUMU" target="_blank" class="btn btn-red" style="font-size:8px;padding:10px 16px">Pay Deposit</a></td></tr>
          <tr><td>Small</td><td>8×8</td><td class="pv">$200</td><td class="dv">$60</td></tr>
          <tr><td>Small</td><td>8×10</td><td class="pv">$275</td><td class="dv">$82.50</td></tr>
          <tr class="tier-h"><td colspan="5">MEDIUM PORTRAITS</td></tr>
          <tr><td>Medium</td><td>11×14</td><td class="pv">$400</td><td class="dv">$120</td><td rowspan="3" style="vertical-align:middle;text-align:center"><a href="https://www.paypal.com/ncp/payment/8LZGEN2GHFUMU" target="_blank" class="btn btn-red" style="font-size:8px;padding:10px 16px">Pay Deposit</a></td></tr>
          <tr><td>Medium</td><td>12×12</td><td class="pv">$525</td><td class="dv">$157.50</td></tr>
          <tr><td>Medium</td><td>12×16</td><td class="pv">$650</td><td class="dv">$195</td></tr>
          <tr class="tier-h"><td colspan="5">LARGE PORTRAITS</td></tr>
          <tr><td>Large</td><td>16×20</td><td class="pv">$850</td><td class="dv">$255</td><td rowspan="3" style="vertical-align:middle;text-align:center"><a href="https://www.paypal.com/ncp/payment/8LZGEN2GHFUMU" target="_blank" class="btn btn-red" style="font-size:8px;padding:10px 16px">Pay Deposit</a></td></tr>
          <tr><td>Large</td><td>18×24</td><td class="pv">$1,100</td><td class="dv">$330</td></tr>
          <tr><td>Statement</td><td>24×36</td><td class="pv">$1,500+</td><td class="dv">$450</td></tr>
        </tbody>
      </table>
      <div style="margin-top:22px;background:var(--obs);border:1px solid var(--bdr2);padding:18px 22px"><p style="font-size:16px;color:var(--mst);font-style:italic"><strong style="color:var(--crm);font-style:normal">Extra subjects:</strong> +30% per additional person or pet. &nbsp;·&nbsp; <strong style="color:var(--crm);font-style:normal">Medium:</strong> Acrylic, watercolor, or ballpoint pen. &nbsp;·&nbsp; <strong style="color:var(--crm);font-style:normal">Balance:</strong> 70% due on completion.</p></div>
    </div>
  </section>
  <div class="cta-sec">
    <h2 class="cta-h">Commission<br><em>Your Portrait</em></h2>
    <div class="btn-row" style="justify-content:center"><button class="btn btn-red" onclick="go('contract')">Commission Now</button><a href="https://wa.me/13412539299" target="_blank" class="btn btn-out">WhatsApp Roberto</a></div>
  </div>
  <footer><div style="display:flex;align-items:center;justify-content:center;gap:14px;margin-bottom:14px"><svg width="40" height="32" viewBox="0 0 200 160" style="opacity:.7"><use href="#logo-mark"/></svg><p style="font-family:'Playfair Display',serif;font-size:16px;font-weight:700;color:var(--crm)">Lost Soul Art Studio</p></div><p class="foot-q">"The labyrinth of the creative mind is where the soul goes to find itself." © 2026</p></footer>
</div>

<!-- ══════════════════════════════════════
     MURALS
══════════════════════════════════════ -->
<div id="page-murals" class="page">
  <div class="hero" style="min-height:55vh;padding:130px 40px 60px"><div class="hero-glow"></div><p class="eyebrow">Interior Murals</p><h1 style="font-size:clamp(44px,8vw,90px)">Walls That<br><em>Remember You</em></h1><p class="hero-sub">Custom acrylic murals for residential and commercial interiors. Work that transforms a space rather than merely decorating it.</p></div>
  <section><div class="wrap rev"><p class="sec-label">Services &amp; Pricing</p><h2 class="sh">Mural<br><em>Commissions</em></h2><div class="grid" style="margin-bottom:28px"><div class="card"><p class="card-label">Residential</p><h3 class="card-h">Home Murals</h3><p class="card-body">Living rooms, bedrooms, nurseries, entryways, stairwells. Spaces where you live should carry the work that reflects how you see the world.</p><div class="price-line"><p class="price-from">Starting from</p><div class="price-val">$500</div><p class="price-note">Priced by square footage · In-home consultation required</p></div></div><div class="card"><p class="card-label">Commercial</p><h3 class="card-h">Business Murals</h3><p class="card-body">Cafés, restaurants, offices, retail, hotel lobbies. Work that becomes part of your brand identity and gives your customers something worth photographing.</p><div class="price-line"><p class="price-from">Starting from</p><div class="price-val">$1,500</div><p class="price-note">Priced per project · Scheduled around your business hours</p></div></div></div><div style="background:var(--obs);border:1px solid var(--bdr2);padding:28px"><p style="font-size:16px;color:var(--mst);font-style:italic;line-height:1.8"><strong style="color:var(--crm);font-style:normal">To get a quote:</strong> Provide your address, wall dimensions (W×H), desired theme or visual direction, and target completion date.</p></div></div></section>
  <div class="cta-sec"><h2 class="cta-h">Transform<br><em>Your Space</em></h2><div class="btn-row" style="justify-content:center"><button class="btn btn-red" onclick="go('contract')">Request a Quote</button><a href="https://wa.me/13412539299" target="_blank" class="btn btn-out">WhatsApp Roberto</a></div></div>
  <footer><div style="display:flex;align-items:center;justify-content:center;gap:14px;margin-bottom:14px"><svg width="40" height="32" viewBox="0 0 200 160" style="opacity:.7"><use href="#logo-mark"/></svg><p style="font-family:'Playfair Display',serif;font-size:16px;font-weight:700;color:var(--crm)">Lost Soul Art Studio</p></div><p class="foot-q">"The labyrinth of the creative mind is where the soul goes to find itself." © 2026</p></footer>
</div>

<!-- ══════════════════════════════════════
     STOREFRONTS
══════════════════════════════════════ -->
<div id="page-storefronts" class="page">
  <div class="hero" style="min-height:55vh;padding:130px 40px 60px"><div class="hero-glow"></div><p class="eyebrow">Storefront Installations</p><h1 style="font-size:clamp(44px,8vw,90px)">Windows That<br><em>Stop People Cold</em></h1><p class="hero-sub">Professional hand-painted window illustrations for businesses. High-impact seasonal and branded displays that command attention.</p></div>
  <section><div class="wrap rev"><p class="sec-label">Tiers &amp; Pricing</p><h2 class="sh">Storefront<br><em>Packages</em></h2><div class="grid"><div class="card"><p class="card-label">Tier I</p><h3 class="card-h">Minimalist / Line Work</h3><p class="card-body">Clean branding and line illustration. Up to 15 sq ft. Elegant seasonal touch for boutiques and professional spaces.</p><div class="price-line"><p class="price-from">Starting from</p><div class="price-val">$200</div><p class="price-note">Deposit: $50 · Timeline: 4–6 hours</p></div></div><div class="card"><p class="card-label">Tier II</p><h3 class="card-h">Standard / Seasonal</h3><p class="card-body">Mid-detail seasonal illustration — Halloween scenes, Christmas tableaux, spring florals, summer themes. Most popular tier for repeat seasonal clients.</p><div class="price-line"><p class="price-from">Starting from</p><div class="price-val">$450</div><p class="price-note">Deposit: $100 · 15–40 sq ft coverage</p></div></div><div class="card"><p class="card-label">Tier III</p><h3 class="card-h">Signature / Full Mural</h3><p class="card-body">Highly detailed full storefront murals — 40+ sq ft of original hand-painted illustration. Branded permanent installations and large statement seasonal displays.</p><div class="price-line"><p class="price-from">Starting from</p><div class="price-val">$800</div><p class="price-note">Quoted individually · 40+ sq ft</p></div></div></div></div></section>
  <div class="cta-sec"><h2 class="cta-h">Book Your<br><em>Storefront</em></h2><div class="btn-row" style="justify-content:center"><button class="btn btn-red" onclick="go('contract')">Request a Quote</button><a href="https://wa.me/13412539299" target="_blank" class="btn btn-out">WhatsApp Roberto</a></div></div>
  <footer><div style="display:flex;align-items:center;justify-content:center;gap:14px;margin-bottom:14px"><svg width="40" height="32" viewBox="0 0 200 160" style="opacity:.7"><use href="#logo-mark"/></svg><p style="font-family:'Playfair Display',serif;font-size:16px;font-weight:700;color:var(--crm)">Lost Soul Art Studio</p></div><p class="foot-q">"The labyrinth of the creative mind is where the soul goes to find itself." © 2026</p></footer>
</div>

<!-- ══════════════════════════════════════
     TATTOO
══════════════════════════════════════ -->
<div id="page-tattoo" class="page">
  <div class="hero" style="background:linear-gradient(180deg,#0A0A0C,#1A0508 100%);min-height:60vh;padding:130px 40px 60px">
    <div class="hero-glow"></div>
    <p class="eyebrow">✦ Now Accepting Bookings · San Francisco</p>
    <svg width="80" height="64" viewBox="0 0 200 160" style="opacity:0;animation:fadeIn 1s ease forwards .3s;margin-bottom:16px;filter:drop-shadow(0 0 16px rgba(192,39,26,.5))"><use href="#logo-mark"/></svg>
    <h1 style="font-size:clamp(52px,9vw,100px)">Tattoo<br><em>Art</em></h1>
    <div class="med-tags"><span class="med-tag">Custom Design</span><span class="med-tag">Flash Available</span><span class="med-tag">Surrealist Fine Line</span><span class="med-tag">Portrait Tattoos</span></div>
    <p class="hero-sub">The same visual language that defines Lost Soul Art's paintings — now permanent. Surrealist imagery, fine-line portraiture, and original flash art rooted in fine art tradition.</p>
  </div>
  <section><div class="wrap rev"><p class="sec-label">The Style</p><h2 class="sh">Fine Art<br><em>Made Permanent</em></h2><p class="sub">Every tattoo design is original. Nothing is repeated. Ballpoint-pen precision meets skin — dreamlike imagery you carry with you always.</p><div class="grid3" style="margin-bottom:0"><div class="card"><h3 class="card-h">Surrealist</h3><p class="card-body">Dreamlike imagery, symbolic objects, figures caught between worlds. Work that means something beyond surface decoration.</p></div><div class="card"><h3 class="card-h">Fine Line</h3><p class="card-body">Precise linework informed by years of ballpoint pen illustration. Clean, controlled, built to age beautifully on skin.</p></div><div class="card"><h3 class="card-h">Portrait</h3><p class="card-body">People, pets, loved ones — the same fine art portraiture sensibility. Now something you carry with you always.</p></div></div></div></section>
  <div class="band"><div class="wrap"><div class="rev"><p class="sec-label">Honest Pricing · San Francisco 2026</p><h2 class="sh">Tattoo<br><em>Pricing</em></h2><p class="sub">Grounded in current SF market rates for independent fine-art tattoo work. A deposit holds every appointment.</p></div>
  <div class="tat-grid rev">
    <div class="tat-tier"><p class="t-cat">Studio Minimum</p><h3 class="t-name">Flash &amp; Micro</h3><p class="t-sz">Up to 2 inches · Simple linework</p><div class="t-price">$150</div><p class="t-time">30–60 minutes</p><p class="t-desc">Small flash designs, minimal linework, single words or symbols. The studio minimum covers sterile setup, materials, and your artist's time.</p><ul class="t-incl"><li>Pre-designed flash from current sheet</li><li>Single needle or fine line</li><li>Placement consultation included</li><li>Aftercare instructions provided</li></ul></div>
    <div class="tat-tier feat"><p class="t-cat">Custom Small</p><h3 class="t-name">Custom Small</h3><p class="t-sz">2–4 inches · Original design</p><div class="t-price">$250</div><p class="t-time">1–2 hours</p><p class="t-desc">Original custom design created specifically for you. Never repeated. Surrealist motifs, small portraits, animal studies, botanical imagery.</p><ul class="t-incl"><li>Original design consultation</li><li>Custom artwork created before session</li><li>One revision round on design</li><li>Placement guidance and sizing</li><li>Aftercare kit included</li></ul></div>
    <div class="tat-tier"><p class="t-cat">Custom Medium</p><h3 class="t-name">Custom Medium</h3><p class="t-sz">4–6 inches · Detailed work</p><div class="t-price">$400</div><p class="t-time">2–4 hours</p><p class="t-desc">Ideal for detailed portraits, surrealist scenes, and fine-line compositions that need room to breathe. Most collectors' favorite size.</p><ul class="t-incl"><li>Full custom design session</li><li>Portrait or scene composition</li><li>Two revision rounds on design</li><li>Aftercare kit and follow-up</li></ul></div>
    <div class="tat-tier"><p class="t-cat">Large Piece</p><h3 class="t-name">Large &amp; Statement</h3><p class="t-sz">6–10 inches · Statement work</p><div class="t-price">$700<span style="font-size:18px;color:var(--mst)">+</span></div><p class="t-time">4–6+ hours · May be multi-session</p><p class="t-desc">Sleeve sections, back pieces, thigh work, large-format surrealist compositions. Quoted individually based on complexity and placement.</p><ul class="t-incl"><li>Comprehensive design consultation</li><li>Multi-session planning if needed</li><li>Touch-up included within 60 days</li></ul></div>
    <div class="tat-tier"><p class="t-cat">Special Rate</p><h3 class="t-name">Friend &amp; Loyalty</h3><p class="t-sz">Friends · Returning clients · Referrals</p><div class="t-price" style="font-size:28px;padding:6px 0">Ask Roberto</div><p class="t-time">Discussed at consultation</p><p class="t-desc">Roberto takes care of the people who believe in him. Friends, returning collectors, and referrals are always welcomed with a rate that reflects the relationship.</p><ul class="t-incl"><li>Discounted rate on any service</li><li>Discussed privately and honestly</li><li>Applies to tattoo and fine art work</li></ul></div>
    <div class="tat-tier"><p class="t-cat">Hourly Rate</p><h3 class="t-name">Large Custom / Hourly</h3><p class="t-sz">Complex large-format &amp; multi-session</p><div class="t-price">$150<span style="font-size:18px;color:var(--mst)">/hr</span></div><p class="t-time">Quoted per project at consultation</p><p class="t-desc">For projects better scoped hourly — full sleeves, detailed portraiture spanning multiple sessions. Transparent time tracking throughout.</p><ul class="t-incl"><li>Project quote before booking</li><li>Deposit applied toward total</li><li>Session breaks included in timing</li></ul></div>
  </div></div></div>
  <section><div class="wrap rev"><div style="background:var(--obs);border:1px solid rgba(192,39,26,.4);padding:36px;text-align:center;margin-top:32px"><p style="font-family:'Playfair Display',serif;font-size:20px;font-style:italic;color:var(--crm);margin-bottom:8px">Flash designs revealed every Wednesday at 5 PM</p><p style="font-size:15px;color:var(--mst);font-style:italic;margin-bottom:18px">Watch live on Facebook, Instagram, TikTok, and YouTube — claim a flash design in real time.</p><div class="live-badge" style="display:inline-flex"><div class="live-dot"></div><span class="live-txt">Wednesday Lives · 5:00 PM · All Platforms</span></div></div></div></section>
  <div class="cta-sec"><h2 class="cta-h">Book Your<br><em>Tattoo Consultation</em></h2><p class="cta-p">Free consultation — no pressure, just a conversation about your vision.</p><div class="btn-row" style="justify-content:center"><button class="btn btn-red" onclick="go('contract')">Book a Consultation</button><a href="https://wa.me/13412539299" target="_blank" class="btn btn-out">WhatsApp Roberto</a></div></div>
  <footer><div style="display:flex;align-items:center;justify-content:center;gap:14px;margin-bottom:14px"><svg width="40" height="32" viewBox="0 0 200 160" style="opacity:.7"><use href="#logo-mark"/></svg><p style="font-family:'Playfair Display',serif;font-size:16px;font-weight:700;color:var(--crm)">Lost Soul Art Studio</p></div><p class="foot-q">"The labyrinth of the creative mind is where the soul goes to find itself." © 2026</p></footer>
</div>

<!-- ══════════════════════════════════════
     WORKSHOPS
══════════════════════════════════════ -->
<div id="page-workshops" class="page">
  <div class="hero" style="background:linear-gradient(180deg,#0A0A0C,#1A0A0A 100%);min-height:100vh;padding:130px 40px 80px">
    <div class="hero-glow"></div>
    <p class="eyebrow">Lost Soul Art Studio · San Francisco</p>
    <svg width="80" height="64" viewBox="0 0 200 160" style="opacity:0;animation:fadeIn 1s ease forwards .35s;margin-bottom:16px;filter:drop-shadow(0 0 16px rgba(192,39,26,.4))"><use href="#logo-mark"/></svg>
    <h1 style="font-size:clamp(52px,11vw,116px)">Workshops<br><em>with Roberto</em></h1>
    <div class="med-tags"><span class="med-tag">Every Saturday</span><span class="med-tag">10:00 AM PST</span><span class="med-tag">90 Minutes</span><span class="med-tag">Max 6 Students</span></div>
    <p class="hero-sub">Every Saturday morning Roberto opens his studio to a small group of creatives for a guided 90-minute painting session rooted in surrealist themes. No experience required. All materials included. Just show up and get lost.</p>
    <div style="display:inline-flex;align-items:center;gap:12px;margin-top:28px;background:rgba(192,39,26,.08);border:1px solid rgba(192,39,26,.25);padding:14px 32px;opacity:0;animation:fadeUp 1s ease forwards 1.1s">
      <div class="live-dot"></div>
      <span style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.42em;text-transform:uppercase;color:var(--red)">Saturdays · 10:00 AM – 11:30 AM · Book Below</span>
    </div>
    <div class="hero-line"></div>
  </div>

  <!-- TIMING -->
  <div style="background:linear-gradient(135deg,#0D1A2E,#1A0808);padding:64px 40px;border-top:1px solid rgba(192,39,26,.3);border-bottom:1px solid rgba(192,39,26,.3)">
    <div style="max-width:1100px;margin:0 auto">
      <div class="rev" style="text-align:center;margin-bottom:40px">
        <h2 style="font-family:'Playfair Display',serif;font-size:clamp(26px,4vw,48px);font-weight:900;color:var(--crm)">Why Saturday at <em style="color:var(--red);font-style:italic">10:00 AM</em></h2>
        <p style="font-size:16px;color:rgba(240,232,216,.55);font-style:italic;max-width:500px;margin:12px auto 0;line-height:1.8">Instagram and TikTok peak for creative content on Saturday mornings — so every photo you post during or after the session lands at maximum reach.</p>
      </div>
      <div style="display:grid;grid-template-columns:repeat(5,1fr);gap:2px" class="rev">
        <div style="background:rgba(255,255,255,.03);border:1px solid rgba(192,39,26,.1);padding:20px 12px;text-align:center"><div style="font-family:'Playfair Display',serif;font-size:22px;font-weight:900;color:var(--mst);line-height:1;margin-bottom:5px">9 AM</div><div style="font-family:'Josefin Sans',sans-serif;font-size:8px;letter-spacing:.3em;text-transform:uppercase;color:var(--mst);margin-bottom:6px">Pre-Workshop</div><div style="font-size:12px;color:rgba(154,136,120,.7);font-style:italic;line-height:1.5">Post "doors open" story. Audience checking phones.</div></div>
        <div style="background:rgba(192,39,26,.1);border:1px solid rgba(192,39,26,.4);padding:20px 12px;text-align:center"><div style="font-family:'Josefin Sans',sans-serif;font-size:7px;letter-spacing:.3em;text-transform:uppercase;color:var(--crm);background:var(--red);padding:3px 8px;display:inline-block;margin-bottom:8px">PEAK</div><div style="font-family:'Playfair Display',serif;font-size:22px;font-weight:900;color:var(--red);line-height:1;margin-bottom:5px">10 AM</div><div style="font-family:'Josefin Sans',sans-serif;font-size:8px;letter-spacing:.3em;text-transform:uppercase;color:var(--mst);margin-bottom:6px">Workshop Starts</div><div style="font-size:12px;color:rgba(154,136,120,.7);font-style:italic;line-height:1.5">Highest creative engagement window on all platforms.</div></div>
        <div style="background:rgba(192,39,26,.1);border:1px solid rgba(192,39,26,.4);padding:20px 12px;text-align:center"><div style="font-family:'Josefin Sans',sans-serif;font-size:7px;letter-spacing:.3em;text-transform:uppercase;color:var(--crm);background:var(--red);padding:3px 8px;display:inline-block;margin-bottom:8px">PEAK</div><div style="font-family:'Playfair Display',serif;font-size:22px;font-weight:900;color:var(--red);line-height:1;margin-bottom:5px">11:30</div><div style="font-family:'Josefin Sans',sans-serif;font-size:8px;letter-spacing:.3em;text-transform:uppercase;color:var(--mst);margin-bottom:6px">Workshop Ends</div><div style="font-size:12px;color:rgba(154,136,120,.7);font-style:italic;line-height:1.5">Post finished pieces at prime Saturday scroll time.</div></div>
        <div style="background:rgba(255,255,255,.03);border:1px solid rgba(192,39,26,.1);padding:20px 12px;text-align:center"><div style="font-family:'Playfair Display',serif;font-size:22px;font-weight:900;color:var(--mst);line-height:1;margin-bottom:5px">12 PM</div><div style="font-family:'Josefin Sans',sans-serif;font-size:8px;letter-spacing:.3em;text-transform:uppercase;color:var(--mst);margin-bottom:6px">Content Post</div><div style="font-size:12px;color:rgba(154,136,120,.7);font-style:italic;line-height:1.5">Process photos, student work, next week's topic.</div></div>
        <div style="background:rgba(255,255,255,.03);border:1px solid rgba(192,39,26,.1);padding:20px 12px;text-align:center"><div style="font-family:'Playfair Display',serif;font-size:22px;font-weight:900;color:var(--mst);line-height:1;margin-bottom:5px">1–3 PM</div><div style="font-family:'Josefin Sans',sans-serif;font-size:8px;letter-spacing:.3em;text-transform:uppercase;color:var(--mst);margin-bottom:6px">Engagement</div><div style="font-size:12px;color:rgba(154,136,120,.7);font-style:italic;line-height:1.5">Reply to comments, DM inquiries, build community.</div></div>
      </div>
    </div>
  </div>

  <!-- PRICING -->
  <section>
    <div class="wrap">
      <div class="rev"><p class="sec-label">Packages &amp; Pricing</p><h2 class="sh">Book Your<br><em>Workshop Spot</em></h2><p class="sub">Payment goes directly to Roberto's PayPal the moment you click — your spot is instantly confirmed. No email chains, no waiting.</p></div>
      <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:2px" class="rev">

        <!-- SINGLE -->
        <div class="card" style="padding:44px 36px">
          <p class="card-label">Drop-In</p><h3 class="card-h">Single Session</h3>
          <p class="card-body" style="min-height:56px">One Saturday, one topic, one finished piece.</p>
          <div style="font-family:'Playfair Display',serif;font-size:68px;font-weight:900;color:var(--red);line-height:1"><sup style="font-size:26px;vertical-align:top;margin-top:14px;color:var(--red3)">$</sup>100</div>
          <p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.35em;text-transform:uppercase;color:var(--mst);margin-bottom:24px">Per student · One session</p>
          <div style="border-top:1px solid var(--bdr2);padding-top:22px;margin-bottom:26px">
            <ul style="list-style:none;display:flex;flex-direction:column;gap:10px">
              <li style="font-size:16px;color:var(--mst);display:flex;gap:10px;font-style:italic"><span style="color:var(--red);font-size:10px;margin-top:4px;flex-shrink:0">✦</span>90-minute guided painting session</li>
              <li style="font-size:16px;color:var(--mst);display:flex;gap:10px;font-style:italic"><span style="color:var(--red);font-size:10px;margin-top:4px;flex-shrink:0">✦</span>All materials and supplies included</li>
              <li style="font-size:16px;color:var(--mst);display:flex;gap:10px;font-style:italic"><span style="color:var(--red);font-size:10px;margin-top:4px;flex-shrink:0">✦</span>Finished original piece to take home</li>
              <li style="font-size:16px;color:var(--mst);display:flex;gap:10px;font-style:italic"><span style="color:var(--red);font-size:10px;margin-top:4px;flex-shrink:0">✦</span>Maximum 6 students per session</li>
              <li style="font-size:16px;color:var(--mst);display:flex;gap:10px;font-style:italic"><span style="color:var(--red);font-size:10px;margin-top:4px;flex-shrink:0">✦</span>Spot confirmed instantly on payment</li>
            </ul>
          </div>
          <div style="margin-top:auto">
            <form action="https://www.paypal.com/cgi-bin/webscr" method="post" target="_blank">
              <input type="hidden" name="cmd" value="_xclick">
              <input type="hidden" name="business" value="8LZGEN2GHFUMU">
              <input type="hidden" name="item_name" value="Lost Soul Art Studio — Saturday Workshop Single Session">
              <input type="hidden" name="amount" value="100.00">
              <input type="hidden" name="currency_code" value="USD">
              <input type="hidden" name="no_shipping" value="1">
              <button type="submit" class="pp-btn">Book &amp; Pay $100 via PayPal</button>
            </form>
            <p class="pp-sub">Secure · PayPal · Cards · Venmo</p>
          </div>
        </div>

        <!-- MONTHLY — FEATURED -->
        <div class="card" style="padding:44px 36px;border-color:var(--red);position:relative">
          <div style="position:absolute;top:-1px;left:50%;transform:translateX(-50%);background:var(--red);color:var(--crm);font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.3em;padding:5px 16px;white-space:nowrap">MOST POPULAR</div>
          <p class="card-label">Best Value</p><h3 class="card-h">Monthly Pass</h3>
          <p class="card-body" style="min-height:56px">All four Saturdays in a month. Build a real practice. Save $50.</p>
          <div style="font-family:'Playfair Display',serif;font-size:68px;font-weight:900;color:var(--red);line-height:1"><sup style="font-size:26px;vertical-align:top;margin-top:14px;color:var(--red3)">$</sup>350</div>
          <p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.35em;text-transform:uppercase;color:var(--mst);margin-bottom:24px">Per student · 4 sessions · saves $50</p>
          <div style="border-top:1px solid var(--bdr2);padding-top:22px;margin-bottom:26px">
            <ul style="list-style:none;display:flex;flex-direction:column;gap:10px">
              <li style="font-size:16px;color:var(--mst);display:flex;gap:10px;font-style:italic"><span style="color:var(--red);font-size:10px;margin-top:4px;flex-shrink:0">✦</span>All 4 Saturday sessions in the month</li>
              <li style="font-size:16px;color:var(--mst);display:flex;gap:10px;font-style:italic"><span style="color:var(--red);font-size:10px;margin-top:4px;flex-shrink:0">✦</span>All materials every session</li>
              <li style="font-size:16px;color:var(--mst);display:flex;gap:10px;font-style:italic"><span style="color:var(--red);font-size:10px;margin-top:4px;flex-shrink:0">✦</span>4 original finished pieces</li>
              <li style="font-size:16px;color:var(--mst);display:flex;gap:10px;font-style:italic"><span style="color:var(--red);font-size:10px;margin-top:4px;flex-shrink:0">✦</span>Priority spot — never wait-listed</li>
              <li style="font-size:16px;color:var(--mst);display:flex;gap:10px;font-style:italic"><span style="color:var(--red);font-size:10px;margin-top:4px;flex-shrink:0">✦</span>Early topic announcements</li>
              <li style="font-size:16px;color:var(--mst);display:flex;gap:10px;font-style:italic"><span style="color:var(--red);font-size:10px;margin-top:4px;flex-shrink:0">✦</span>10% off any commission inquiry</li>
            </ul>
          </div>
          <div style="margin-top:auto">
            <form action="https://www.paypal.com/cgi-bin/webscr" method="post" target="_blank">
              <input type="hidden" name="cmd" value="_xclick">
              <input type="hidden" name="business" value="8LZGEN2GHFUMU">
              <input type="hidden" name="item_name" value="Lost Soul Art Studio — Monthly Workshop Pass (4 Sessions)">
              <input type="hidden" name="amount" value="350.00">
              <input type="hidden" name="currency_code" value="USD">
              <input type="hidden" name="no_shipping" value="1">
              <button type="submit" class="pp-btn">Book &amp; Pay $350 via PayPal</button>
            </form>
            <p class="pp-sub">Secure · PayPal · Cards · Venmo</p>
          </div>
        </div>

        <!-- PRIVATE -->
        <div class="card" style="padding:44px 36px">
          <p class="card-label">One-on-One</p><h3 class="card-h">Private Instruction</h3>
          <p class="card-body" style="min-height:56px">Two hours of dedicated instruction built entirely around your goals.</p>
          <div style="font-family:'Playfair Display',serif;font-size:68px;font-weight:900;color:var(--red);line-height:1"><sup style="font-size:26px;vertical-align:top;margin-top:14px;color:var(--red3)">$</sup>180</div>
          <p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.35em;text-transform:uppercase;color:var(--mst);margin-bottom:24px">Per session · 2 hours · Weekdays</p>
          <div style="border-top:1px solid var(--bdr2);padding-top:22px;margin-bottom:26px">
            <ul style="list-style:none;display:flex;flex-direction:column;gap:10px">
              <li style="font-size:16px;color:var(--mst);display:flex;gap:10px;font-style:italic"><span style="color:var(--red);font-size:10px;margin-top:4px;flex-shrink:0">✦</span>2-hour private session with Roberto</li>
              <li style="font-size:16px;color:var(--mst);display:flex;gap:10px;font-style:italic"><span style="color:var(--red);font-size:10px;margin-top:4px;flex-shrink:0">✦</span>Custom curriculum for your goals</li>
              <li style="font-size:16px;color:var(--mst);display:flex;gap:10px;font-style:italic"><span style="color:var(--red);font-size:10px;margin-top:4px;flex-shrink:0">✦</span>Your choice of medium</li>
              <li style="font-size:16px;color:var(--mst);display:flex;gap:10px;font-style:italic"><span style="color:var(--red);font-size:10px;margin-top:4px;flex-shrink:0">✦</span>All materials included</li>
              <li style="font-size:16px;color:var(--mst);display:flex;gap:10px;font-style:italic"><span style="color:var(--red);font-size:10px;margin-top:4px;flex-shrink:0">✦</span>Written technique notes after session</li>
            </ul>
          </div>
          <div style="margin-top:auto">
            <form action="https://www.paypal.com/cgi-bin/webscr" method="post" target="_blank">
              <input type="hidden" name="cmd" value="_xclick">
              <input type="hidden" name="business" value="8LZGEN2GHFUMU">
              <input type="hidden" name="item_name" value="Lost Soul Art Studio — Private Instruction Session (2 Hours)">
              <input type="hidden" name="amount" value="180.00">
              <input type="hidden" name="currency_code" value="USD">
              <input type="hidden" name="no_shipping" value="1">
              <button type="submit" class="pp-btn" style="background:transparent;color:var(--red);border:1px solid rgba(192,39,26,.3)" onmouseover="this.style.background='var(--redfade)';this.style.borderColor='var(--red)'" onmouseout="this.style.background='transparent';this.style.borderColor='rgba(192,39,26,.3)'">Book &amp; Pay $180 via PayPal</button>
            </form>
            <p class="pp-sub">Contact via WhatsApp to schedule time</p>
          </div>
        </div>

      </div><!-- end pricing grid -->

      <!-- AFTER PAYMENT -->
      <div style="margin-top:28px;background:var(--obs);border:1px solid var(--red);padding:32px 36px" class="rev">
        <p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.45em;text-transform:uppercase;color:var(--red3);margin-bottom:16px">What Happens After You Pay</p>
        <div style="display:grid;grid-template-columns:repeat(4,1fr);gap:20px">
          <div><div style="font-family:'Playfair Display',serif;font-size:32px;font-weight:900;color:rgba(192,39,26,.15);line-height:1;margin-bottom:6px">01</div><p style="font-size:15px;color:var(--mst);font-style:italic;line-height:1.65">PayPal receipt arrives immediately. Your spot is confirmed.</p></div>
          <div><div style="font-family:'Playfair Display',serif;font-size:32px;font-weight:900;color:rgba(192,39,26,.15);line-height:1;margin-bottom:6px">02</div><p style="font-size:15px;color:var(--mst);font-style:italic;line-height:1.65">Roberto sends the studio address, what to bring (nothing), and that week's topic.</p></div>
          <div><div style="font-family:'Playfair Display',serif;font-size:32px;font-weight:900;color:rgba(192,39,26,.15);line-height:1;margin-bottom:6px">03</div><p style="font-size:15px;color:var(--mst);font-style:italic;line-height:1.65">Show up Saturday at 10:00 AM. Everything is ready. Doors open 9:45 AM.</p></div>
          <div><div style="font-family:'Playfair Display',serif;font-size:32px;font-weight:900;color:rgba(192,39,26,.15);line-height:1;margin-bottom:6px">04</div><p style="font-size:15px;color:var(--mst);font-style:italic;line-height:1.65">Leave at 11:30 AM with a finished original in your hands.</p></div>
        </div>
      </div>
    </div>
  </section>

  <!-- 50 TOPICS -->
  <div class="band-dark">
    <div class="wrap">
      <div class="rev"><p class="sec-label">The Complete Schedule</p><h2 class="sh">50 Saturday<br><em>Workshop Topics</em></h2><p class="sub">One topic every Saturday. Five categories rotating throughout the year. Drop in on any Saturday — every session stands alone.</p>
        <div style="display:flex;gap:8px;flex-wrap:wrap;margin-bottom:36px">
          <button onclick="filterTopics('all')" class="ws-filt ws-on" data-cat="all">All 50</button>
          <button onclick="filterTopics('surr')" class="ws-filt" data-cat="surr">Surrealism</button>
          <button onclick="filterTopics('port')" class="ws-filt" data-cat="port">Portraiture</button>
          <button onclick="filterTopics('expr')" class="ws-filt" data-cat="expr">Expressionism</button>
          <button onclick="filterTopics('mix')" class="ws-filt" data-cat="mix">Mixed Media</button>
          <button onclick="filterTopics('soul')" class="ws-filt" data-cat="soul">Soul Work</button>
        </div>
      </div>
      <div style="display:grid;grid-template-columns:repeat(auto-fill,minmax(290px,1fr));gap:3px" id="topics-container" class="rev"></div>
    </div>
  </div>

  <!-- GUIDE TABS -->
  <section>
    <div class="wrap">
      <div class="rev"><p class="sec-label">Internal Production Guide</p><h2 class="sh">The Complete<br><em>Workshop Playbook</em></h2><p class="sub">Step-by-step guide covering everything from setup to social media — so Saturday runs on autopilot while you focus on teaching.</p></div>
      <div style="display:flex;border-bottom:1px solid var(--bdr2);margin-bottom:0;overflow-x:auto" class="rev">
        <button onclick="showGuide('runsheet')" id="gt-runsheet" class="guide-tab guide-on">90-Min Runsheet</button>
        <button onclick="showGuide('script')" id="gt-script" class="guide-tab">Scripts</button>
        <button onclick="showGuide('camera')" id="gt-camera" class="guide-tab">Camera Angles</button>
        <button onclick="showGuide('setup')" id="gt-setup" class="guide-tab">Studio Setup</button>
        <button onclick="showGuide('social')" id="gt-social" class="guide-tab">Social Media</button>
      </div>
      <div id="gp-runsheet" class="guide-panel guide-panel-on">
        <h3 style="font-family:'Playfair Display',serif;font-size:22px;font-weight:700;color:var(--crm);margin-bottom:28px">Saturday 10:00 AM — 90-Minute Runsheet</h3>
        <div style="position:relative;padding-left:38px"><div style="position:absolute;left:10px;top:0;bottom:0;width:1px;background:var(--bdr2)"></div>
          <div style="position:relative;margin-bottom:32px"><div style="position:absolute;left:-32px;top:6px;width:10px;height:10px;border-radius:50%;background:var(--red);border:2px solid var(--blk);box-shadow:0 0 0 2px var(--red)"></div><p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.4em;text-transform:uppercase;color:var(--red);margin-bottom:5px">9:45 AM — Doors Open</p><p style="font-family:'Playfair Display',serif;font-size:18px;font-weight:700;color:var(--crm);margin-bottom:7px">Welcome &amp; Setup</p><p style="font-size:16px;color:var(--mst);font-style:italic;line-height:1.78">Students arrive and find their station already set. Music on (lo-fi jazz or ambient, no lyrics). Roberto greets each student by name. Camera #1 (wide, overhead) recording ambient setup footage.</p><p style="font-size:13px;color:var(--red3);margin-top:7px">📷 CAMERA: Wide overhead capturing full studio space and arrivals.</p></div>
          <div style="position:relative;margin-bottom:32px"><div style="position:absolute;left:-32px;top:6px;width:10px;height:10px;border-radius:50%;background:var(--red);border:2px solid var(--blk);box-shadow:0 0 0 2px var(--red)"></div><p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.4em;text-transform:uppercase;color:var(--red);margin-bottom:5px">10:00 – 10:10 AM — Minutes 1–10</p><p style="font-family:'Playfair Display',serif;font-size:18px;font-weight:700;color:var(--crm);margin-bottom:7px">Introduction &amp; Topic Reveal</p><p style="font-size:16px;color:var(--mst);font-style:italic;line-height:1.78">Roberto stands at the front, makes eye contact with every student, delivers the opening. Set the theme, the feeling, and the creative permission they need. Show 2–3 reference images. Do not tell them what to paint — tell them how to feel while they paint.</p><p style="font-size:13px;color:var(--red3);margin-top:7px">📷 CAMERA: Medium shot, Roberto at front. Clip this 60-second intro for TikTok/Reels.</p></div>
          <div style="position:relative;margin-bottom:32px"><div style="position:absolute;left:-32px;top:6px;width:10px;height:10px;border-radius:50%;background:var(--red);border:2px solid var(--blk);box-shadow:0 0 0 2px var(--red)"></div><p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.4em;text-transform:uppercase;color:var(--red);margin-bottom:5px">10:10 – 10:25 AM — Minutes 10–25</p><p style="font-family:'Playfair Display',serif;font-size:18px;font-weight:700;color:var(--crm);margin-bottom:7px">Live Demo — Roberto Paints First</p><p style="font-size:16px;color:var(--mst);font-style:italic;line-height:1.78">Roberto demonstrates the first 15 minutes narrating every decision out loud. Students watch, not yet painting. This is when the phone on tripod captures the most shareable footage of the session — skilled hands in active creation mode.</p><p style="font-size:13px;color:var(--red3);margin-top:7px">📷 CAMERA: Close-up on hands and canvas. Your best content clip of the day.</p></div>
          <div style="position:relative;margin-bottom:32px"><div style="position:absolute;left:-32px;top:6px;width:10px;height:10px;border-radius:50%;background:var(--red);border:2px solid var(--blk);box-shadow:0 0 0 2px var(--red)"></div><p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.4em;text-transform:uppercase;color:var(--red);margin-bottom:5px">10:25 – 11:00 AM — Minutes 25–60</p><p style="font-family:'Playfair Display',serif;font-size:18px;font-weight:700;color:var(--crm);margin-bottom:7px">Student Work — Roberto Circulates</p><p style="font-size:16px;color:var(--mst);font-style:italic;line-height:1.78">Students begin. Roberto circulates clockwise, 3–5 minutes per station. He asks questions, not commands: "What are you feeling in this?" "What would happen if you pushed that color darker?" Photograph each canvas at the halfway mark for content.</p><p style="font-size:13px;color:var(--red3);margin-top:7px">📷 CAMERA: Handheld wander shot. Individual student canvases with permission.</p></div>
          <div style="position:relative;margin-bottom:32px"><div style="position:absolute;left:-32px;top:6px;width:10px;height:10px;border-radius:50%;background:var(--red);border:2px solid var(--blk);box-shadow:0 0 0 2px var(--red)"></div><p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.4em;text-transform:uppercase;color:var(--red);margin-bottom:5px">11:00 – 11:20 AM — Minutes 60–80</p><p style="font-family:'Playfair Display',serif;font-size:18px;font-weight:700;color:var(--crm);margin-bottom:7px">Finishing &amp; Refinement</p><p style="font-size:16px;color:var(--mst);font-style:italic;line-height:1.78">Students focus on completing their pieces. Roberto offers one-on-one finishing guidance — "What's the one thing this piece still needs?" The room is usually in full flow state here. Ambient audio of brush strokes is powerful content on its own.</p><p style="font-size:13px;color:var(--red3);margin-top:7px">📷 CAMERA: Close-ups of detail work. Capture the finishing moment — brush lifting for the last time.</p></div>
          <div style="position:relative"><div style="position:absolute;left:-32px;top:6px;width:10px;height:10px;border-radius:50%;background:var(--red);border:2px solid var(--blk);box-shadow:0 0 0 2px var(--red)"></div><p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.4em;text-transform:uppercase;color:var(--red);margin-bottom:5px">11:20 – 11:30 AM — Minutes 80–90</p><p style="font-family:'Playfair Display',serif;font-size:18px;font-weight:700;color:var(--crm);margin-bottom:7px">Gallery Moment &amp; Close</p><p style="font-size:16px;color:var(--mst);font-style:italic;line-height:1.78">Everyone holds up their finished piece. Roberto takes a group photo of all works together — this is the weekly social media post. He gives one genuine, specific observation about each piece. Invites students to follow on all platforms and notes next Saturday's topic drops Wednesday at 5 PM Live.</p><p style="font-size:13px;color:var(--red3);margin-top:7px">📷 CAMERA: Wide group shot of all finished pieces. Individual shots for the portfolio archive.</p></div>
        </div>
      </div>
      <div id="gp-script" class="guide-panel">
        <h3 style="font-family:'Playfair Display',serif;font-size:22px;font-weight:700;color:var(--crm);margin-bottom:28px">Word-for-Word Scripts</h3>
        <div style="margin-bottom:36px"><p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.42em;text-transform:uppercase;color:var(--red);margin-bottom:12px">Opening (say this every Saturday)</p><div style="background:var(--char);border-left:3px solid var(--red);padding:22px 26px"><p style="font-size:18px;color:var(--crm);font-style:italic;line-height:1.8">"Welcome. I'm Roberto. This is Lost Soul Art Studio. For the next 90 minutes this room belongs to you — and to the work. There's no right way to do this. There's no wrong piece at the end. The only rule is that you stay curious. Today we're working on [TOPIC]. Before you touch your brush, I want to tell you what this topic means to me — and then I want you to forget what I said and make it mean something to you."</p></div></div>
        <div style="margin-bottom:36px"><p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.42em;text-transform:uppercase;color:var(--red);margin-bottom:12px">Demo Narration</p><div style="background:var(--char);border-left:3px solid var(--red);padding:22px 26px"><p style="font-size:18px;color:var(--crm);font-style:italic;line-height:1.8">"I'm starting with the darkest tone because in surrealist work you always build from shadow outward — the light only means something when the dark defines it. Watch this edge here. I'm not blending it smoothly — I want that tension. Surrealism lives in tension."</p></div></div>
        <div style="margin-bottom:36px"><p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.42em;text-transform:uppercase;color:var(--red);margin-bottom:12px">Individual Feedback Lines</p>
          <div style="display:grid;grid-template-columns:1fr 1fr;gap:2px">
            <div style="background:var(--char);padding:18px 20px"><p style="font-size:9px;font-family:'Josefin Sans',sans-serif;letter-spacing:.3em;text-transform:uppercase;color:var(--red3);margin-bottom:7px">When someone is stuck:</p><p style="font-size:16px;color:var(--crm);font-style:italic;line-height:1.7">"What are you afraid this piece is going to become? Paint that instead."</p></div>
            <div style="background:var(--char);padding:18px 20px"><p style="font-size:9px;font-family:'Josefin Sans',sans-serif;letter-spacing:.3em;text-transform:uppercase;color:var(--red3);margin-bottom:7px">When overworking:</p><p style="font-size:16px;color:var(--crm);font-style:italic;line-height:1.7">"Put the brush down for 30 seconds and look at it from across the room. Tell me what you see."</p></div>
            <div style="background:var(--char);padding:18px 20px"><p style="font-size:9px;font-family:'Josefin Sans',sans-serif;letter-spacing:.3em;text-transform:uppercase;color:var(--red3);margin-bottom:7px">When they like what they made:</p><p style="font-size:16px;color:var(--crm);font-style:italic;line-height:1.7">"Good. Now do the thing you don't want to do to it. Trust me."</p></div>
            <div style="background:var(--char);padding:18px 20px"><p style="font-size:9px;font-family:'Josefin Sans',sans-serif;letter-spacing:.3em;text-transform:uppercase;color:var(--red3);margin-bottom:7px">When they say they can't draw:</p><p style="font-size:16px;color:var(--crm);font-style:italic;line-height:1.7">"Surrealism was invented by people who refused to draw correctly. You're in the right place."</p></div>
          </div>
        </div>
        <div><p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.42em;text-transform:uppercase;color:var(--red);margin-bottom:12px">Closing Script</p><div style="background:var(--char);border-left:3px solid var(--red);padding:22px 26px"><p style="font-size:18px;color:var(--crm);font-style:italic;line-height:1.8">"Brushes down. Hold up what you made. [Pause.] Look at that. Six different people, one theme, six completely different pieces. You each made something that didn't exist 90 minutes ago. That's not small. Next week's topic drops Wednesday at 5 PM on the Live — follow me on Instagram, TikTok, Facebook, YouTube. See you next Saturday."</p></div></div>
      </div>
      <div id="gp-camera" class="guide-panel">
        <h3 style="font-family:'Playfair Display',serif;font-size:22px;font-weight:700;color:var(--crm);margin-bottom:16px">Camera Angles &amp; Shot Guide</h3>
        <p style="font-size:16px;color:var(--mst);font-style:italic;line-height:1.8;margin-bottom:28px">One phone, one tripod, a full week of content. Set up the primary angle before students arrive and leave it running.</p>
        <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:2px">
          <div style="background:var(--char);border:1px solid var(--bdr2);padding:24px"><h4 style="font-family:'Playfair Display',serif;font-size:18px;font-weight:700;color:var(--red);margin-bottom:7px">Angle 1 — Wide Studio</h4><p style="font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.3em;text-transform:uppercase;color:var(--red3);margin-bottom:8px">Tripod · Run all session</p><p style="font-size:14px;color:var(--mst);font-style:italic;line-height:1.7">Back corner of room, capturing full studio space. Time-lapses from this angle perform extremely well. Shoot vertical 9:16 for Reels and TikTok.</p><p style="font-size:13px;color:var(--red);margin-top:10px">TikTok time-lapse · Instagram Reel · YouTube thumbnail</p></div>
          <div style="background:var(--char);border:1px solid var(--bdr2);padding:24px"><h4 style="font-family:'Playfair Display',serif;font-size:18px;font-weight:700;color:var(--red);margin-bottom:7px">Angle 2 — Close Hands</h4><p style="font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.3em;text-transform:uppercase;color:var(--red3);margin-bottom:8px">Handheld · During demo</p><p style="font-size:14px;color:var(--mst);font-style:italic;line-height:1.7">Overhead or side of canvas during demo. Brush touching surface, color mixing, gestural strokes. Your highest-engagement content — people cannot look away from skilled hands.</p><p style="font-size:13px;color:var(--red);margin-top:10px">TikTok · Instagram Reel close-up · Story highlights</p></div>
          <div style="background:var(--char);border:1px solid var(--bdr2);padding:24px"><h4 style="font-family:'Playfair Display',serif;font-size:18px;font-weight:700;color:var(--red);margin-bottom:7px">Angle 3 — Face &amp; Voice</h4><p style="font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.3em;text-transform:uppercase;color:var(--red3);margin-bottom:8px">Tripod · Opening 10 min</p><p style="font-size:14px;color:var(--mst);font-style:italic;line-height:1.7">Eye level facing Roberto from the front during intro. This medium shot — artist addressing students — is the content that brings new workshop sign-ups.</p><p style="font-size:13px;color:var(--red);margin-top:10px">Workshop promo posts · Facebook · YouTube intro</p></div>
          <div style="background:var(--char);border:1px solid var(--bdr2);padding:24px"><h4 style="font-family:'Playfair Display',serif;font-size:18px;font-weight:700;color:var(--red);margin-bottom:7px">Angle 4 — Student Work</h4><p style="font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.3em;text-transform:uppercase;color:var(--red3);margin-bottom:8px">Handheld · Mid-session</p><p style="font-size:14px;color:var(--mst);font-style:italic;line-height:1.7">Individual student canvases at halfway point and near end. Before/after canvas shots are powerful proof of what happens in 90 minutes.</p><p style="font-size:13px;color:var(--red);margin-top:10px">Student showcase posts · Commission inquiries</p></div>
          <div style="background:var(--char);border:1px solid var(--bdr2);padding:24px"><h4 style="font-family:'Playfair Display',serif;font-size:18px;font-weight:700;color:var(--red);margin-bottom:7px">Angle 5 — The Reveal</h4><p style="font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.3em;text-transform:uppercase;color:var(--red3);margin-bottom:8px">Handheld · Final 10 min</p><p style="font-size:14px;color:var(--mst);font-style:italic;line-height:1.7">Each finished piece photographed individually, then the group shot of all six pieces held up together. Primary weekly post — shows range and community.</p><p style="font-size:13px;color:var(--red);margin-top:10px">Weekly wrap post · Workshop promotion · Portfolio</p></div>
          <div style="background:var(--char);border:1px solid var(--bdr2);padding:24px"><h4 style="font-family:'Playfair Display',serif;font-size:18px;font-weight:700;color:var(--red);margin-bottom:7px">Angle 6 — Setup ASMR</h4><p style="font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.3em;text-transform:uppercase;color:var(--red3);margin-bottom:8px">Before students arrive</p><p style="font-size:14px;color:var(--mst);font-style:italic;line-height:1.7">Arrive 20 min early. Film the studio setup — laying out canvases, squeezing paint, arranging brushes. Record with ambient sound only. Performs very well on TikTok.</p><p style="font-size:13px;color:var(--red);margin-top:10px">Saturday morning teaser posts · Story content</p></div>
        </div>
      </div>
      <div id="gp-setup" class="guide-panel">
        <h3 style="font-family:'Playfair Display',serif;font-size:22px;font-weight:700;color:var(--crm);margin-bottom:16px">Studio Setup Checklist</h3>
        <p style="font-size:16px;color:var(--mst);font-style:italic;line-height:1.8;margin-bottom:28px">Complete Friday evening so Saturday morning is effortless. Click each item to check it off.</p>
        <div style="display:grid;grid-template-columns:1fr 1fr;gap:32px">
          <div><p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.42em;text-transform:uppercase;color:var(--red);margin-bottom:14px">Friday Evening Prep</p><div id="friday-list"></div></div>
          <div><p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.42em;text-transform:uppercase;color:var(--red);margin-bottom:14px">Saturday Morning (9:30 AM)</p><div id="saturday-list"></div></div>
        </div>
      </div>
      <div id="gp-social" class="guide-panel">
        <h3 style="font-family:'Playfair Display',serif;font-size:22px;font-weight:700;color:var(--crm);margin-bottom:16px">Saturday Social Media Playbook</h3>
        <p style="font-size:16px;color:var(--mst);font-style:italic;line-height:1.8;margin-bottom:28px">One workshop generates an entire week of content if you capture it right.</p>
        <div style="display:flex;flex-direction:column;gap:2px">
          <div style="background:var(--char);border:1px solid var(--bdr2);padding:22px 26px;display:grid;grid-template-columns:150px 1fr;gap:20px"><div><p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.4em;text-transform:uppercase;color:var(--red);margin-bottom:4px">9:00 AM</p><p style="font-size:13px;color:var(--mst);font-style:italic">All 4 platforms</p></div><div><p style="font-family:'Playfair Display',serif;font-size:17px;font-weight:700;color:var(--crm);margin-bottom:5px">Workshop Day Announcement</p><p style="font-size:15px;color:var(--mst);font-style:italic;line-height:1.7">Post the studio setup ASMR clip. Caption: "Doors open in 1 hour. Saturday workshop — [TOPIC]. 6 seats, all filled. Watch what happens. 📍Lost Soul Art Studio, SF 🎨"</p></div></div>
          <div style="background:var(--obs);border:1px solid var(--bdr2);padding:22px 26px;display:grid;grid-template-columns:150px 1fr;gap:20px"><div><p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.4em;text-transform:uppercase;color:var(--red);margin-bottom:4px">10:15 AM</p><p style="font-size:13px;color:var(--mst);font-style:italic">Instagram + TikTok</p></div><div><p style="font-family:'Playfair Display',serif;font-size:17px;font-weight:700;color:var(--crm);margin-bottom:5px">Live Demo Clip (60–90 sec)</p><p style="font-size:15px;color:var(--mst);font-style:italic;line-height:1.7">Post the close-up hands clip from the demo. No filter, no music — just brush on canvas. Caption: "15 minutes in. Today's topic: [TOPIC]. This is what surrealism sounds like. 🎨"</p></div></div>
          <div style="background:var(--char);border:1px solid var(--bdr2);padding:22px 26px;display:grid;grid-template-columns:150px 1fr;gap:20px"><div><p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.4em;text-transform:uppercase;color:var(--red);margin-bottom:4px">12:00 PM</p><p style="font-size:13px;color:var(--mst);font-style:italic">All 4 platforms</p></div><div><p style="font-family:'Playfair Display',serif;font-size:17px;font-weight:700;color:var(--crm);margin-bottom:5px">The Reveal — All Finished Pieces</p><p style="font-size:15px;color:var(--mst);font-style:italic;line-height:1.7">Post the group photo. Caption: "Today's workshop: [TOPIC]. 6 students. 6 completely different pieces. One theme, infinite interpretations. Next Saturday open — link in bio. 🎨 #LostSoulArt #SFArtist"</p></div></div>
          <div style="background:var(--obs);border:1px solid var(--bdr2);padding:22px 26px;display:grid;grid-template-columns:150px 1fr;gap:20px"><div><p style="font-family:'Josefin Sans',sans-serif;font-size:10px;letter-spacing:.4em;text-transform:uppercase;color:var(--red);margin-bottom:4px">Wednesday 5 PM</p><p style="font-size:13px;color:var(--mst);font-style:italic">Live Stream</p></div><div><p style="font-family:'Playfair Display',serif;font-size:17px;font-weight:700;color:var(--crm);margin-bottom:5px">Announce Next Saturday's Topic</p><p style="font-size:15px;color:var(--mst);font-style:italic;line-height:1.7">During Wednesday Live at 5 PM, reveal next Saturday's topic. Open booking link live: "Saturday is [TOPIC] — spots are live right now, link in bio, first six in are confirmed."</p></div></div>
        </div>
      </div>
    </div>
  </section>

  <div class="cta-sec">
    <h2 class="cta-h">Ready for<br><em>This Saturday?</em></h2>
    <p class="cta-p">Six seats. 10:00 AM. Your finished piece is waiting to be made.</p>
    <div class="btn-row" style="justify-content:center">
      <form action="https://www.paypal.com/cgi-bin/webscr" method="post" target="_blank" style="display:inline">
        <input type="hidden" name="cmd" value="_xclick">
        <input type="hidden" name="business" value="8LZGEN2GHFUMU">
        <input type="hidden" name="item_name" value="Lost Soul Art Studio — Saturday Workshop Single Session">
        <input type="hidden" name="amount" value="100.00">
        <input type="hidden" name="currency_code" value="USD">
        <input type="hidden" name="no_shipping" value="1">
        <button type="submit" class="btn btn-red">Book Single Session — $100</button>
      </form>
      <form action="https://www.paypal.com/cgi-bin/webscr" method="post" target="_blank" style="display:inline">
        <input type="hidden" name="cmd" value="_xclick">
        <input type="hidden" name="business" value="8LZGEN2GHFUMU">
        <input type="hidden" name="item_name" value="Lost Soul Art Studio — Monthly Workshop Pass (4 Sessions)">
        <input type="hidden" name="amount" value="350.00">
        <input type="hidden" name="currency_code" value="USD">
        <input type="hidden" name="no_shipping" value="1">
        <button type="submit" class="btn btn-out">Monthly Pass — $350</button>
      </form>
    </div>
    <a href="https://wa.me/13412539299" target="_blank" style="display:inline-block;margin-top:18px;font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.38em;text-transform:uppercase;color:var(--mst);text-decoration:none;transition:color .3s" onmouseover="this.style.color='var(--red)'" onmouseout="this.style.color='var(--mst)'">Questions? WhatsApp Roberto directly</a>
  </div>

  <footer>
    <div style="display:flex;align-items:center;justify-content:center;gap:14px;margin-bottom:14px"><svg width="40" height="32" viewBox="0 0 200 160" style="opacity:.7"><use href="#logo-mark"/></svg><p style="font-family:'Playfair Display',serif;font-size:16px;font-weight:700;color:var(--crm)">Lost Soul Art Studio</p></div>
    <div class="foot-links"><a onclick="go('home')">Home</a><a onclick="go('gallery')">Gallery</a><a onclick="go('portraits')">Portraits</a><a onclick="go('murals')">Murals</a><a onclick="go('storefronts')">Storefronts</a><a onclick="go('tattoo')">Tattoo</a><a onclick="go('workshops')">Workshops</a><a onclick="go('contract')">Commission</a><a onclick="go('blog')">Blog</a><a onclick="go('terms')">Terms</a></div>
    <p class="foot-q">"The labyrinth of the creative mind is where the soul goes to find itself." © 2026</p>
  </footer>
</div>

<!-- ══════════════════════════════════════
     CONTRACT
══════════════════════════════════════ -->
<div id="page-contract" class="page">
  <div style="padding-top:80px;background:var(--char);border-bottom:1px solid var(--bdr2)">
    <div style="text-align:center;padding:60px 40px 48px">
      <svg width="60" height="48" viewBox="0 0 200 160" style="opacity:.8;margin-bottom:20px"><use href="#logo-mark"/></svg>
      <h1 style="font-family:'Playfair Display',serif;font-size:clamp(36px,6vw,64px);font-weight:900;color:var(--crm);margin-bottom:14px">Commission Agreement</h1>
      <p style="font-size:17px;color:var(--mst);font-style:italic;max-width:560px;margin:0 auto;line-height:1.8">This agreement is between you and Roberto Cisneros, the independent artist behind Lost Soul Art Studio. Please read every section before signing.</p>
      <div style="margin-top:20px;display:inline-block;background:rgba(192,39,26,.06);border:1px solid var(--bdr2);padding:14px 22px"><p style="font-size:14px;color:var(--mst);font-style:italic">Note: Lost Soul Art Studio is an independent artist practice operated by Roberto Cisneros as a sole creative professional — not a registered LLC or incorporated business.</p></div>
    </div>
  </div>
  <div class="contract-wrap">
    <div class="csec">
      <h3>Services Covered by This Agreement</h3>
      <ul>
        <li><strong style="color:var(--crm);font-style:normal">Fine Art Portrait</strong> — Original hand-painted portrait in acrylic, watercolor, or ballpoint pen. Includes reference consultation, work-in-progress updates, and delivery of the physical original.</li>
        <li><strong style="color:var(--crm);font-style:normal">Interior Mural</strong> — Custom acrylic mural painted on-site. Includes consultation, concept sketches, wall preparation, painting, and protective sealant.</li>
        <li><strong style="color:var(--crm);font-style:normal">Storefront Installation</strong> — Seasonal or custom window painting. Includes design concept, one day of on-site work, and clean removal when the season ends.</li>
        <li><strong style="color:var(--crm);font-style:normal">Original Artwork Purchase</strong> — Purchase of an existing studio work. Includes signed certificate of authenticity and protective packaging.</li>
        <li><strong style="color:var(--crm);font-style:normal">Workshop / Instruction</strong> — Group or private instruction session. Includes all materials and a finished piece to take home.</li>
        <li><strong style="color:var(--crm);font-style:normal">Tattoo — Custom Design</strong> — Original tattoo design created for you, tattooed by Roberto. Includes design consultation, one revision round, and the session itself.</li>
        <li><strong style="color:var(--crm);font-style:normal">Tattoo — Flash Design</strong> — Pre-designed original from the current flash sheet. Done once, never repeated. Deposit holds your design.</li>
      </ul>
    </div>
    <div class="csec">
      <h3>Your Information</h3>
      <div class="form-row"><div class="form-g"><label>First Name</label><input type="text" placeholder="First name"></div><div class="form-g"><label>Last Name</label><input type="text" placeholder="Last name"></div></div>
      <div class="form-row"><div class="form-g"><label>Email Address</label><input type="email" placeholder="your@email.com"></div><div class="form-g"><label>Phone Number</label><input type="tel" placeholder="(415) 000-0000"></div></div>
      <div class="form-g"><label>City / Neighborhood</label><input type="text" placeholder="e.g. Mission District, SF"></div>
    </div>
    <div class="csec">
      <h3>Service Selection</h3>
      <div class="form-g"><label>Which service are you commissioning?</label>
        <select id="svc-select" onchange="calcTotal()">
          <option value="">— Select a service —</option>
          <optgroup label="Fine Art Portraits"><option value="150">Portrait — Small 5×7 ($150)</option><option value="200">Portrait — Small 8×8 ($200)</option><option value="275">Portrait — Small 8×10 ($275)</option><option value="400">Portrait — Medium 11×14 ($400)</option><option value="525">Portrait — Medium 12×12 ($525)</option><option value="650">Portrait — Medium 12×16 ($650)</option><option value="850">Portrait — Large 16×20 ($850)</option><option value="1100">Portrait — Large 18×24 ($1,100)</option><option value="1500">Portrait — Statement 24×36 ($1,500+)</option></optgroup>
          <optgroup label="Murals"><option value="500">Interior Mural — Residential (starting $500)</option><option value="1500">Interior Mural — Commercial (starting $1,500)</option></optgroup>
          <optgroup label="Storefronts"><option value="200">Storefront — Tier I Minimalist ($200+)</option><option value="450">Storefront — Tier II Standard/Seasonal ($450+)</option><option value="800">Storefront — Tier III Signature/Full ($800+)</option></optgroup>
          <optgroup label="Workshops"><option value="100">Workshop — Group Studio Saturday ($100/student)</option><option value="180">Workshop — Private One-on-One ($180)</option></optgroup>
          <optgroup label="Tattoo"><option value="150">Tattoo — Flash &amp; Micro ($150 minimum)</option><option value="250">Tattoo — Custom Small 2–4 inches ($250)</option><option value="400">Tattoo — Custom Medium 4–6 inches ($400)</option><option value="700">Tattoo — Large &amp; Statement 6–10 inches ($700+)</option><option value="0">Tattoo — Friend / Loyalty Rate (discuss with Roberto)</option></optgroup>
        </select>
      </div>
      <div class="form-g"><label>Describe your subject, idea, or project</label><textarea rows="4" placeholder="For portraits: subject, mood, story. For murals/storefronts: space and theme. For tattoos: placement and design vision."></textarea></div>
      <div class="form-g"><label>Preferred medium — portraits only (optional)</label><select><option>— Leave to Roberto's judgment —</option><option>Acrylic</option><option>Watercolor</option><option>Ballpoint Pen</option><option>Mixed</option></select></div>
      <div class="form-row"><div class="form-g"><label>Desired size or dimensions</label><input type="text" placeholder='e.g. 11×14 or "as large as works"'></div><div class="form-g"><label>Preferred timeline or deadline</label><input type="text" placeholder='"Before the holidays" or "No rush"'></div></div>
      <div class="total-box"><span class="total-label">Starting Price Estimate</span><span class="total-val" id="t-val">Select a service above</span></div>
      <div style="margin-top:14px;padding:14px 18px;background:var(--obs);border:1px solid var(--bdr2)"><p style="font-size:14px;color:var(--mst);font-style:italic">Deposit required via <a href="https://www.paypal.com/ncp/payment/8LZGEN2GHFUMU" target="_blank" style="color:var(--red)">PayPal</a> or <a href="https://wa.me/13412539299" target="_blank" style="color:var(--red)">WhatsApp</a>. Roberto confirms details and sends deposit instructions within 48 hours.</p></div>
    </div>
    <div class="csec">
      <h3>What Roberto Agrees To</h3>
      <ul><li>To create original work in the style and medium described, using acrylic, ballpoint pen, or watercolor as appropriate.</li><li>To communicate at key stages so you are never surprised by the direction of the work.</li><li>To deliver within the agreed timeline, or notify you promptly if circumstances require a change.</li><li>To keep your personal information and reference photos private.</li></ul>
    </div>
    <div class="csec">
      <h3>What You Are Agreeing To</h3>
      <ul><li>To pay the required deposit before any work begins. No work starts without a confirmed deposit.</li><li>To pay the remaining balance when the work is complete and approved — or for tattoos, on the day of your session.</li><li>To provide clear reference materials in a timely manner.</li><li>To communicate concerns during the work-in-progress phase — changes after completion may incur additional fees.</li><li>For tattoo clients: to follow all aftercare instructions provided.</li><li>To allow Roberto Cisneros to photograph and share the completed work on his portfolio and social media unless you request otherwise in writing before work begins.</li></ul>
    </div>
    <div class="csec">
      <h3>Refund &amp; Cancellation</h3>
      <ul><li>Deposits are non-refundable under all circumstances, except if Roberto is unable to complete the commission — in which case the deposit is returned in full within 14 days.</li><li>Refunds are not issued for completed work.</li><li>Murals/storefronts cancelled after on-site work has begun: a 25% kill fee applies in addition to the deposit.</li><li>Tattoo cancellations under 48 hours: deposit is forfeited. Over 48 hours: may roll to a rescheduled appointment at Roberto's discretion.</li></ul>
    </div>
    <div class="csec">
      <h3>Copyright &amp; Ownership</h3>
      <ul><li>Roberto Cisneros retains full copyright and reproduction rights to all original works.</li><li>You receive the physical artwork and the right to display and enjoy it personally.</li><li>You may not reproduce, sell, or use images commercially without written permission.</li><li>For tattoo designs: your custom design will not be tattooed on anyone else.</li><li>Personal social media sharing is welcome. Please tag @lostsoulart.</li></ul>
    </div>
    <div class="csec">
      <h3>Please Confirm the Following</h3>
      <div>
        <label class="chk-item"><input type="checkbox"><span>I have read and understood the full description of the service I am commissioning.</span></label>
        <label class="chk-item"><input type="checkbox"><span>I understand that a deposit is required before work begins and is non-refundable.</span></label>
        <label class="chk-item"><input type="checkbox"><span>I understand that Roberto Cisneros retains copyright to all original work created.</span></label>
        <label class="chk-item"><input type="checkbox"><span>I agree to the refund and cancellation policy described above.</span></label>
        <label class="chk-item"><input type="checkbox"><span>I consent to Roberto photographing and sharing the completed work on his portfolio and social media.</span></label>
        <label class="chk-item" id="tat-chk" style="display:none"><input type="checkbox"><span>For tattoo services: I confirm I am 18 years of age or older.</span></label>
      </div>
    </div>
    <div class="csec">
      <h3>Signature &amp; Agreement</h3>
      <p style="font-size:16px;color:var(--mst);font-style:italic;line-height:1.85">By typing your name below, you confirm that you have read this agreement in full and agree to all terms. This is a personal agreement between you and Roberto Cisneros, entered into voluntarily by both parties.</p>
      <div class="form-row" style="margin-top:28px"><div><label style="font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.4em;text-transform:uppercase;color:var(--red3);display:block;margin-bottom:8px">Your Full Name (typed signature)</label><input type="text" class="sig-input" placeholder="Type your full name to sign"></div><div class="form-g"><label>Date</label><input type="date" id="sig-date"></div></div>
      <div style="margin-top:40px;text-align:center">
        <button class="btn btn-red" style="width:100%;max-width:380px" onclick="submitForm()">Submit Commission Agreement</button>
        <p style="font-size:13px;color:var(--mst);font-style:italic;margin-top:12px">Roberto will contact you within 48 hours to confirm details and arrange your deposit.</p>
        <div style="display:flex;gap:12px;justify-content:center;margin-top:18px;flex-wrap:wrap">
          <a href="https://www.paypal.com/ncp/payment/8LZGEN2GHFUMU" target="_blank" class="btn btn-out" style="font-size:8px;padding:10px 20px">Pay via PayPal</a>
          <a href="https://wa.me/13412539299" target="_blank" class="btn btn-out" style="font-size:8px;padding:10px 20px">WhatsApp Roberto</a>
        </div>
      </div>
    </div>
  </div>
  <footer><div style="display:flex;align-items:center;justify-content:center;gap:14px;margin-bottom:14px"><svg width="40" height="32" viewBox="0 0 200 160" style="opacity:.7"><use href="#logo-mark"/></svg><p style="font-family:'Playfair Display',serif;font-size:16px;font-weight:700;color:var(--crm)">Lost Soul Art Studio</p></div><p class="foot-q">"The labyrinth of the creative mind is where the soul goes to find itself." © 2026</p></footer>
</div>

<!-- ══════════════════════════════════════
     BLOG
══════════════════════════════════════ -->
<div id="page-blog" class="page">
  <div class="hero" style="min-height:50vh;padding:130px 40px 60px"><div class="hero-glow"></div><p class="eyebrow">Lost Soul Art Studio</p><h1 style="font-size:clamp(44px,8vw,88px)">Creative<br><em>Art Blog</em></h1><p class="hero-sub">Thoughts on the creative process, the artist's journey, and the ongoing conversation between art, identity, and imagination.</p></div>
  <section><div class="wrap"><div class="blog-grid rev">
    <div class="blog-card"><img src="https://lostsoulart.simdif.com/images/th/sd_6969c62e7f820.jpg?no_cache=1768543300" alt="Lost Soul Art Blog" loading="lazy"><div class="blog-body"><p class="blog-date">January 15, 2026</p><h3 class="blog-h">Lost Soul: The Artist, The Creativity &amp; The Brand</h3><p class="blog-p">In a world that demands we fit into neat, labeled boxes, there is a profound power in being "lost." For the creator, being a Lost Soul isn't about being aimless — it is the raw, unpolished space where the artist, the creative process, and the brand identity finally collide. Stay lost. Keep creating. Find yourself in the work.</p></div></div>
    <div class="blog-card"><img src="https://lostsoulart.simdif.com/images/th/sd_696ce60557266.jpg?no_cache=1768748102" alt="Creative Block" loading="lazy"><div class="blog-body"><p class="blog-date">January 18, 2026</p><h3 class="blog-h">The Creative Block: When the Well Runs Dry</h3><p class="blog-p">Every artist, no matter how seasoned, has faced it — the dreaded creative block. True innovation happens in the Lost State, where time disappears and you aren't just making art, you are letting the art happen through you. It's about curiosity over ego.</p></div></div>
    <div class="blog-card"><img src="https://lostsoulart.simdif.com/images/th/sd_698d319f2190a.png?no_cache=1770864584" alt="Pre Renewal Phase" loading="lazy"><div class="blog-body"><p class="blog-date">February 12, 2026</p><h3 class="blog-h">Pre Renewal Phase: The Journey Behind the Brush Stroke</h3><p class="blog-p">"The labyrinth of the creative mind is where the soul goes to find itself." This quote is the heartbeat of every morning I spend in the studio. In my Renewal Collection, I've been leaning into the chaos of the line — exploring the bridge between classical training and urgent contemporary expressionism.</p></div></div>
  </div>
  <div style="margin-top:56px;text-align:center" class="rev"><p style="font-size:17px;color:var(--mst);font-style:italic;margin-bottom:24px">New blog posts published monthly. Follow along for weekly creative updates and live painting sessions every Wednesday at 5 PM.</p><div class="live-badge" style="display:inline-flex"><div class="live-dot"></div><span class="live-txt">Watch Live Every Wednesday · 5 PM · All Platforms</span></div></div>
  </div></section>
  <footer><div style="display:flex;align-items:center;justify-content:center;gap:14px;margin-bottom:14px"><svg width="40" height="32" viewBox="0 0 200 160" style="opacity:.7"><use href="#logo-mark"/></svg><p style="font-family:'Playfair Display',serif;font-size:16px;font-weight:700;color:var(--crm)">Lost Soul Art Studio</p></div><p class="foot-q">"The labyrinth of the creative mind is where the soul goes to find itself." © 2026</p></footer>
</div>

<!-- ══════════════════════════════════════
     TERMS
══════════════════════════════════════ -->
<div id="page-terms" class="page">
  <div style="padding-top:100px;background:var(--char);border-bottom:1px solid var(--bdr2);text-align:center;padding-bottom:56px">
    <svg width="60" height="48" viewBox="0 0 200 160" style="opacity:.8;margin-bottom:20px"><use href="#logo-mark"/></svg>
    <h1 style="font-family:'Playfair Display',serif;font-size:clamp(34px,6vw,62px);font-weight:900;color:var(--crm);margin-bottom:12px">Terms of Service</h1>
    <p style="font-size:17px;color:var(--mst);font-style:italic;max-width:540px;margin:0 auto;line-height:1.8">These terms govern all services provided by Roberto Cisneros under the Lost Soul Art Studio name.</p>
    <p style="font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.3em;text-transform:uppercase;color:var(--mst);margin-top:16px">Last Updated: April 2026</p>
  </div>
  <div class="terms-wrap">
    <div class="t-sec"><div class="t-num">01</div><h3>Who These Terms Apply To</h3><p>These Terms of Service apply to anyone who commissions, purchases, or engages any service offered by Roberto Cisneros operating as Lost Soul Art Studio — including fine art portrait commissions, interior murals, storefront window installations, studio workshops, original artwork purchases, print sales, and tattoo services.</p><p>Lost Soul Art Studio is an independent artist practice. Roberto Cisneros operates as a sole creative professional and is not a registered LLC, corporation, or formally licensed business entity.</p></div>
    <div class="t-sec"><div class="t-num">02</div><h3>Payment Terms</h3><p>Portrait commissions require a 30% non-refundable deposit. All other commissions require a 50% non-refundable deposit before work begins. No work commences until the deposit is received. The remaining balance is due upon completion and your approval — or for tattoos, on the day of your appointment.</p><p>Accepted payment methods: PayPal, Venmo, cash, and bank transfer. Payment plans for commissions over $1,000 may be arranged at Roberto's discretion.</p></div>
    <div class="t-sec"><div class="t-num">03</div><h3>Deposits &amp; Refund Policy</h3><p>Deposits are non-refundable under all circumstances, except in the case where Roberto Cisneros is unable to fulfill the commission — in which case the deposit is returned in full within 14 days. Refunds are not issued for completed work. For murals and large-scale commercial projects cancelled after on-site work has commenced, a kill fee of 25% of the total quoted price applies.</p></div>
    <div class="t-sec"><div class="t-num">04</div><h3>Timelines &amp; Delivery</h3><p>Estimated timelines are provided in good faith but are not guaranteed. Standard timelines: portrait commissions 2–4 weeks from deposit; mural projects 1–5 days on-site; storefront installations one day; tattoo sessions scheduled at time of booking. Rush portrait commissions (under 10 days) available at a 25% surcharge if capacity allows.</p></div>
    <div class="t-sec"><div class="t-num">05</div><h3>Copyright &amp; Intellectual Property</h3><p>Roberto Cisneros retains full copyright and reproduction rights to all original works created, including portrait commissions, mural designs, tattoo designs, flash sheets, and any preparatory sketches. Clients receive the physical artwork and the right to display and enjoy it personally and non-commercially. Clients may not reproduce, sell, license, or use images commercially without prior written permission. For tattoo clients: custom designs will not be repeated on another person, but the design copyright remains with the artist.</p></div>
    <div class="t-sec"><div class="t-num">06</div><h3>Reference Materials &amp; Privacy</h3><p>Reference photos and any personal information shared for your commission are kept private and used solely for that purpose. Completed commissions may be photographed and shared on Roberto's portfolio and social media unless you notify Roberto in writing before your deposit is placed.</p></div>
    <div class="t-sec"><div class="t-num">07</div><h3>Workshops &amp; Events</h3><p>Workshop fees are non-refundable within 48 hours of the scheduled session. Cancellations with more than 48 hours notice may receive a studio credit at Roberto's discretion. All materials included. Students take home their completed work.</p></div>
    <div class="t-sec"><div class="t-num">08</div><h3>Tattoo Services</h3><p>A non-refundable deposit of $50–$100 is required to hold your tattoo appointment. Cancellations under 48 hours forfeit the deposit entirely. One complimentary touch-up included within 60 days for properly cared-for work. All tattoo clients must be 18 years of age or older.</p></div>
    <div class="t-sec"><div class="t-num">09</div><h3>Limitation of Liability</h3><p>Roberto Cisneros's total liability for any claim arising from services provided under the Lost Soul Art Studio name shall not exceed the total amount paid by the client for that specific service.</p></div>
    <div class="t-sec"><div class="t-num">10</div><h3>Contact</h3><p>For questions, concerns, or to start a commission: reach Roberto Cisneros via <a href="https://wa.me/13412539299" target="_blank" style="color:var(--red)">WhatsApp</a> or through the Commission page on this site. All communications are responded to within 48 hours.</p></div>
    <div style="margin-top:48px;text-align:center"><button class="btn btn-red" onclick="go('contract')">Start a Commission</button></div>
  </div>
  <footer><div style="display:flex;align-items:center;justify-content:center;gap:14px;margin-bottom:14px"><svg width="40" height="32" viewBox="0 0 200 160" style="opacity:.7"><use href="#logo-mark"/></svg><p style="font-family:'Playfair Display',serif;font-size:16px;font-weight:700;color:var(--crm)">Lost Soul Art Studio</p></div><p class="foot-q">"The labyrinth of the creative mind is where the soul goes to find itself." © 2026 Lost Soul Art Studio. All Rights Reserved.</p></footer>
</div>

<script>
/* ═══ GALLERY DATA ═══ */
const ARTWORKS=[
  {s:"sd_6960b6bc6042c",t:"The Lost Soul"},{s:"sd_6960b6eda8c79",t:"Rebellious"},
  {s:"sd_6960b75a5f55d",t:"Opening the 3rd Eye"},{s:"sd_6961163e36540",t:"A Child of Rebellion"},
  {s:"sd_6961186390c3d",t:"Lost Skull"},{s:"sd_6961187a8cb70",t:"Sunset Watercolor"},
  {s:"sd_696118a09104f",t:"Beautiful Angel"},{s:"sd_696118bd8d258",t:"Bang Bang"},
  {s:"sd_696118d7d2eb0",t:"Before"},{s:"sd_696118f828591",t:"After"},
  {s:"sd_69611906c780c",t:"Inside My Head"},{s:"sd_6961191f78095",t:"Down the Rabbit Hole"},
  {s:"sd_69611934e540a",t:"Flip Through the Pages"},{s:"sd_6961194839a6d",t:"10 Min Portrait of Cameron"},
  {s:"sd_6961195f6b077",t:"Heart of Gold"},{s:"sd_6961197b527e1",t:"Princess of Hearts"},
  {s:"sd_696119a390eed",t:"The Duality of It All"},{s:"sd_69611a0f8684c",t:"Is That Britney?"},
  {s:"sd_69611a7e7297a",t:"Rose on Thigh"},{s:"sd_69611a40a03b1",t:"Thizz Face"},
  {s:"sd_69611a908cb77",t:"Pop Art"},{s:"sd_69611ac43e283",t:"Ball Point Pen Self Portrait"},
  {s:"sd_69611addad79a",t:"Butterfly Spirit"},{s:"sd_69611ab210abb",t:"Alien"},
  {s:"sd_69611b4ec3b48",t:"Aaaahhhhh"},{s:"sd_69611b5fd49f1",t:"Transcend to Your Highest Vibrational Self"},
  {s:"sd_69611b937b7d9",t:"Self"},{s:"sd_69611af573cff",t:"Ariel / Alter Ego"},
  {s:"sd_69611b2f1ba4f",t:"Blue Rose"},{s:"sd_69611b17a8d28",t:"My Grandpa"},
  {s:"sd_69ac0471e561f",t:"Childlike Wonder"},
];

function buildGallery(){
  const g=document.getElementById('gallery-grid');
  if(!g)return;
  ARTWORKS.forEach(a=>{
    const thumb=`https://lostsoulart.simdif.com/images/th/${a.s}.jpg?no_cache=1767949552`;
    const big=`https://lostsoulart.simdif.com/images/public/${a.s}.jpg?no_cache=1767949552`;
    const el=document.createElement('div');
    el.className='gal-item';
    el.innerHTML=`<img src="${thumb}" alt="${a.t}" loading="lazy"><div class="gal-cap">${a.t}</div>`;
    el.onclick=()=>openLB(big,a.t);
    g.appendChild(el);
  });
}

function openLB(src,cap){
  document.getElementById('lb-img').src=src;
  document.getElementById('lb-cap').textContent=cap;
  document.getElementById('lb').classList.add('open');
  document.body.style.overflow='hidden';
}
function closeLB(e){
  if(!e||e.target===document.getElementById('lb')||e.currentTarget.classList.contains('lb-close')){
    document.getElementById('lb').classList.remove('open');
    document.body.style.overflow='';
  }
}

/* ═══ PAGE NAVIGATION ═══ */
function go(page){
  document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));
  document.querySelectorAll('.nav-links a').forEach(a=>a.classList.remove('active'));
  const pg=document.getElementById('page-'+page);
  const nv=document.getElementById('n-'+page);
  if(pg)pg.classList.add('active');
  if(nv)nv.classList.add('active');
  window.scrollTo({top:0,behavior:'instant'});
  document.getElementById('nav-links').classList.remove('open');
  if(page==='contract'){
    const d=document.getElementById('sig-date');
    if(d)d.valueAsDate=new Date();
  }
  setTimeout(activateReveal,80);
}

function toggleMenu(){
  document.getElementById('nav-links').classList.toggle('open');
}

/* ═══ CONTRACT ═══ */
function calcTotal(){
  const s=document.getElementById('svc-select');
  const tv=document.getElementById('t-val');
  const tc=document.getElementById('tat-chk');
  if(!s.value){tv.textContent='Select a service above';return;}
  if(s.value==='0'){tv.textContent='Discuss with Roberto';if(tc)tc.style.display='flex';return;}
  const isTat=s.options[s.selectedIndex]?.parentElement?.label==='Tattoo';
  if(tc)tc.style.display=isTat?'flex':'none';
  const v=parseInt(s.value)||0;
  const dep=v>=400?Math.round(v*.3):Math.round(v*.5);
  tv.textContent=`$${v.toLocaleString()} · Deposit: $${dep.toLocaleString()}`;
}

function submitForm(){
  const checks=document.querySelectorAll('.chk-item input[type=checkbox]');
  let allChecked=true;
  checks.forEach(c=>{if(c.closest('label').style.display!=='none'&&!c.checked)allChecked=false;});
  const sig=document.querySelector('.sig-input')?.value?.trim();
  if(!sig){alert('Please type your full name to sign the agreement.');return;}
  if(!allChecked){alert('Please check all confirmation boxes before submitting.');return;}
  if(!document.getElementById('svc-select').value){alert('Please select a service.');return;}
  alert('Thank you! Roberto will contact you within 48 hours to confirm your commission details and arrange the deposit. You can also reach him directly via WhatsApp: +1 (341) 253-9299');
}

/* ═══ 50 WORKSHOP TOPICS ═══ */
const TOPICS=[
  {n:1,cat:'surr',title:'The Dreaming Eye',medium:'Acrylic',date:'Apr 5',desc:'We explore the surrealist obsession with the eye as a portal — a single oversized eye set inside an impossible landscape. Focus on contrast between hyper-realistic rendering and loose, dreamlike surroundings.'},
  {n:2,cat:'port',title:'Shadow Self Portrait',medium:'Ballpoint Pen',date:'Apr 12',desc:'You draw the version of yourself you think nobody else can see. Using cross-hatching and pressure variation unique to ballpoint pen, we build a portrait that captures psychology, not just appearance.'},
  {n:3,cat:'expr',title:'The Color of Rage',medium:'Acrylic',date:'Apr 19',desc:'An expressionist deep dive into emotional color theory. Students choose an emotion and translate it into pure abstraction — color field, mark-making, texture. No representational forms allowed.'},
  {n:4,cat:'mix',title:'Paper + Paint + Pen',medium:'Mixed Media',date:'Apr 26',desc:'We collage, paint, and draw on a single surface — tearing magazine pages, layering watercolor washes over them, then drawing over both with ballpoint pen. All three mediums in one session.'},
  {n:5,cat:'soul',title:'What Lives in the Dark',medium:'Acrylic',date:'May 3',desc:'A meditation on the shadow self. We work almost entirely with dark tones, pulling figures and forms from near-black backgrounds using lighter marks. Technically demanding and emotionally revealing.'},
  {n:6,cat:'surr',title:'Objects Out of Context',medium:'Watercolor',date:'May 10',desc:'The surrealist principle of displacement — taking ordinary objects and placing them in environments where they absolutely do not belong. Precise watercolor rendering inside impossible spaces.'},
  {n:7,cat:'port',title:'Pet Portrait — Surrealist Style',medium:'Acrylic',date:'May 17',desc:'Bring a photo of your pet. We paint them with photorealistic accuracy from the neck up — then let the rest of the body dissolve into surrealist abstraction.'},
  {n:8,cat:'expr',title:'Non-Dominant Hand Only',medium:'Acrylic',date:'May 24',desc:'Every student paints exclusively with their non-dominant hand for the entire session. The goal is not a perfect painting — it is the liberation that comes from forced imperfection.'},
  {n:9,cat:'soul',title:'The Ancestor',medium:'Ballpoint Pen',date:'May 31',desc:'We paint someone from our family history — real or imagined. Using ballpoint pen\'s unique capacity for dense, patient mark-making, we build portraits that carry the weight of time and blood and memory.'},
  {n:10,cat:'surr',title:'Gravity Does Not Apply Here',medium:'Acrylic',date:'Jun 7',desc:'Everything floats in today\'s composition. Figures drift upward. Furniture hangs from ceilings. Oceans levitate above deserts. We study Chagall and Magritte then build our own gravity-free worlds.'},
  {n:11,cat:'mix',title:'The Torn Portrait',medium:'Mixed Media',date:'Jun 14',desc:'We begin with a watercolor face, let it dry, then tear it into strips and reassemble it — slightly misaligned — on a new surface. The fractured portrait says something no intact portrait ever could.'},
  {n:12,cat:'expr',title:'Van Gogh\'s Sky Technique',medium:'Acrylic',date:'Jun 21',desc:'A close study of Van Gogh\'s swirling, kinetic mark-making. Students paint a turbulent sky using his specific technique — short curved strokes, heavy impasto, visible brushwork.'},
  {n:13,cat:'soul',title:'Grief Is a Color',medium:'Watercolor',date:'Jun 28',desc:'A gentle but powerful session about translating difficult emotion into watercolor. We explore how loss and longing have specific visual equivalents in color temperature and wash technique.'},
  {n:14,cat:'surr',title:'The Clock Melts',medium:'Acrylic',date:'Jul 5',desc:'Inspired by Dalí but not derivative of it. Students paint melting, warping representations of time — clocks, calendars, hourglasses — combined with personal symbols from their own lives.'},
  {n:15,cat:'port',title:'The Eyes Have It',medium:'Ballpoint Pen',date:'Jul 12',desc:'An entire 90-minute session dedicated to drawing one pair of eyes with absolute precision. Students learn how the iris catches light, how shadows define the socket, and why the eyes determine whether the entire portrait lives or dies.'},
  {n:16,cat:'expr',title:'Abstract Expressionism — Drip Method',medium:'Acrylic',date:'Jul 19',desc:'Action painting in the spirit of Pollock — but with intention behind every movement. Students learn to use the canvas horizontally, to drip and pour with controlled abandon. The hardest part is knowing when to stop.'},
  {n:17,cat:'mix',title:'Word + Image',medium:'Mixed Media',date:'Jul 26',desc:'We write words — poem fragments, memories, single charged words — in watercolor on the surface, then paint over them. The relationship between visible and hidden text becomes the meaning of the piece.'},
  {n:18,cat:'soul',title:'The Childhood Room',medium:'Acrylic',date:'Aug 2',desc:'Students paint a room from their childhood but populate it with objects that did not belong there. A tiger under the bed. A moon in the closet. Autobiographical surrealism meets deep memory work.'},
  {n:19,cat:'surr',title:'The Internal Map',medium:'Ballpoint Pen',date:'Aug 9',desc:'We draw maps — not of places, but of internal states. What does anxiety look like as a geography? What are the borders of love? Students create cartographic drawings of their own emotional interior.'},
  {n:20,cat:'port',title:'The Stranger in the Mirror',medium:'Watercolor',date:'Aug 16',desc:'Loose, impressionistic self-portraiture in watercolor. No tight rendering — students suggest a face with minimal marks, letting water and pigment make decisions alongside the artist.'},
  {n:21,cat:'expr',title:'One Color, One Hour',medium:'Acrylic',date:'Aug 23',desc:'Students choose one color and mix every variation possible — tints, shades, tones — then build a monochromatic painting of startling depth and range. This session teaches more about color than any multi-color session.'},
  {n:22,cat:'soul',title:'The Letter You Never Sent',medium:'Mixed Media',date:'Aug 30',desc:'Students write a letter to a person, a past self, or something lost — in watercolor on the surface, then paint over it completely with an emotional abstract response. What remains visible between layers becomes the piece.'},
  {n:23,cat:'surr',title:'Animals That Do Not Exist',medium:'Acrylic',date:'Sep 6',desc:'Students design and paint a creature that has never existed — hybrid, impossible, entirely their own. We study how surrealism and mythology both create creatures that feel emotionally real even when physically impossible.'},
  {n:24,cat:'mix',title:'The Cut-Up',medium:'Mixed Media',date:'Sep 13',desc:'Inspired by William S. Burroughs. Students create three small works, cut them into strips, and weave them together. The resulting piece is always stranger and more interesting than any single image could be.'},
  {n:25,cat:'port',title:'Hands',medium:'Ballpoint Pen',date:'Sep 20',desc:'A session dedicated entirely to drawing hands — the most expressive and technically demanding subject in portraiture. Students use ballpoint pen\'s density to build three-dimensional rendered hands from their own references.'},
  {n:26,cat:'soul',title:'What I Am Made Of',medium:'Acrylic',date:'Sep 27',desc:'Students paint a self-portrait where the body is transparent — made of the things that define them. A body filled with ocean, or fire, or birds, or books. Always the most personally revealing session of the year.'},
  {n:27,cat:'surr',title:'The Double',medium:'Acrylic',date:'Oct 4',desc:'Inspired by Magritte\'s identical figures. Students paint two versions of the same person — identical in pose, different in essence. What does one know that the other does not?'},
  {n:28,cat:'expr',title:'Music as Canvas',medium:'Acrylic',date:'Oct 11',desc:'Roberto plays one piece of music on repeat while students paint. The music is the only instruction. Students translate sound into visual rhythm, tempo into mark-making speed, melody into line.'},
  {n:29,cat:'mix',title:'The Photograph Reimagined',medium:'Mixed Media',date:'Oct 18',desc:'Students bring one photograph and reproduce it in watercolor — then overwrite it with acrylic abstraction and ballpoint pen marks until the original image is transformed into something entirely new.'},
  {n:30,cat:'soul',title:'The Fear',medium:'Ballpoint Pen',date:'Oct 25',desc:'Students draw their most persistent fear — not literally, but symbolically. Using ballpoint pen\'s capacity for obsessive detail, they build an image that holds the fear at arm\'s length, making it visible and therefore smaller.'},
  {n:31,cat:'surr',title:'Skies That Cannot Exist',medium:'Watercolor',date:'Nov 1',desc:'We paint impossible skies — two suns, inverted lightning, clouds that form recognizable shapes, moons during the day. Watercolor\'s translucency makes it perfect for luminous, impossible atmospheric paintings.'},
  {n:32,cat:'port',title:'The Old Face',medium:'Acrylic',date:'Nov 8',desc:'Students paint the face of someone old with particular attention to the way age lives in the skin. Wrinkles are not flaws to minimize — they are the most interesting lines in any portrait.'},
  {n:33,cat:'expr',title:'Anger Is Beautiful',medium:'Acrylic',date:'Nov 15',desc:'A session built around the premise that anger, properly channeled into paint, produces some of the most alive and energetic work an artist ever makes. Students access an authentic emotional state and paint from inside it.'},
  {n:34,cat:'mix',title:'The Altar',medium:'Mixed Media',date:'Nov 22',desc:'Inspired by traditional ofrendas. Students build a small painted altar — layered, symbolic, personal — using all three mediums. This Thanksgiving session asks students to put what they are grateful for into a visual form.'},
  {n:35,cat:'soul',title:'The Dream I Keep Having',medium:'Acrylic',date:'Nov 29',desc:'A recurring dream — painted. Students describe or paint directly from a dream they have returned to multiple times. We work with the logic of dream imagery: space doesn\'t follow rules and meaning lives in strange details.'},
  {n:36,cat:'surr',title:'Scale Games',medium:'Acrylic',date:'Dec 6',desc:'Magritte\'s apple. A giant chess piece in a city square. Students paint one large object and one small object in impossible proportion — breaking scale relationships and exploring what that rupture communicates.'},
  {n:37,cat:'port',title:'The Child',medium:'Watercolor',date:'Dec 13',desc:'Students paint a child in loose, tender watercolor. Children require different attention than adults in portraiture: softer edges, less contrast, and a quality of presence that watercolor communicates perfectly.'},
  {n:38,cat:'expr',title:'The Last Day of the Year',medium:'Acrylic',date:'Dec 20',desc:'End-of-year session. Students paint what this year felt like — not its events, but its emotional texture. Color, mark, atmosphere. This piece is their annual record of themselves as an artist and a person.'},
  {n:39,cat:'soul',title:'Beginning Again',medium:'Watercolor',date:'Dec 27',desc:'The final session of the year and the first of the next. A session about beginnings — painted in the most forgiving, flow-following medium we have. Students set one visual intention for the coming year.'},
  {n:40,cat:'surr',title:'The Room Inside the Room',medium:'Acrylic',date:'Jan 3',desc:'A room that contains another room that is impossible to reach. Doors that lead to ceilings. Staircases inside mirrors. The impossible architecture of the interior world.'},
  {n:41,cat:'mix',title:'Blind Contour + Color',medium:'Mixed Media',date:'Jan 10',desc:'We begin with blind contour drawing — pen never leaving the page, eyes never leaving the subject — then flood the resulting drawing with expressive watercolor washes. Involuntary accuracy plus deliberate color.'},
  {n:42,cat:'port',title:'The Silhouette',medium:'Acrylic',date:'Jan 17',desc:'Students paint one figure as a pure silhouette — no facial features, no detail — then fill the interior with the most complex imagery they can build. What is inside a person that they cannot show on the outside?'},
  {n:43,cat:'expr',title:'Fast Painting — 10-Minute Studies',medium:'Acrylic',date:'Jan 24',desc:'Instead of one 90-minute piece, students complete nine 10-minute paintings. Speed forces decisions and eliminates overthinking. Students almost always find their ninth piece is their best — and the least precious.'},
  {n:44,cat:'soul',title:'The Wound That Became a Garden',medium:'Watercolor',date:'Jan 31',desc:'A session about transformation — specifically how pain and difficulty can become the source of the most beautiful work. Students paint an image that holds both the wound and the growth that emerged from it simultaneously.'},
  {n:45,cat:'surr',title:'The Hand That Reaches',medium:'Ballpoint Pen',date:'Feb 7',desc:'A disembodied hand — reaching, grasping, offering, releasing — rendered in precise ballpoint pen and placed in an impossible context. Hands in surrealist work carry extraordinary symbolic weight.'},
  {n:46,cat:'mix',title:'The Layered Self',medium:'Mixed Media',date:'Feb 14',desc:'Students build a self-portrait in three layers: watercolor underpainting, acrylic layer over it, and ballpoint pen details across the surface. Three different versions of the self inhabiting one piece.'},
  {n:47,cat:'port',title:'The Eyes Closed',medium:'Acrylic',date:'Feb 21',desc:'We paint faces with closed eyes. Something specific happens to a portrait when the subject is turned inward — the viewer is forced into a different relationship. The psychological difference between a face that looks back and one that does not.'},
  {n:48,cat:'expr',title:'Palette Knife Only',medium:'Acrylic',date:'Feb 28',desc:'No brushes. Students work exclusively with palette knives — scraping, spreading, layering, and lifting acrylic. The resulting textures are unavailable to any brush and produce paintings of startling physicality.'},
  {n:49,cat:'soul',title:'The Message in a Bottle',medium:'Mixed Media',date:'Mar 7',desc:'Students paint a message inside a visual container of their own design. The container protects the message. The message gives the container its reason for existing.'},
  {n:50,cat:'surr',title:'Getting Lost in Imagination',medium:'Acrylic',date:'Mar 14',desc:'The final topic in the cycle and the one the studio is named for. Students paint what it means to them to get lost in their own imagination. Free medium choice, free format, no instruction beyond the title. Always the most surprising session of the year.'},
];

const CAT_COLORS={
  surr:{bg:'rgba(139,92,246,.07)',bc:'rgba(139,92,246,.3)',tc:'rgba(180,140,255,.85)',label:'Surrealism'},
  port:{bg:'rgba(192,39,26,.07)',bc:'rgba(192,39,26,.3)',tc:'rgba(220,80,60,.85)',label:'Portraiture'},
  expr:{bg:'rgba(16,185,129,.07)',bc:'rgba(16,185,129,.3)',tc:'rgba(16,185,129,.85)',label:'Expressionism'},
  mix:{bg:'rgba(245,158,11,.07)',bc:'rgba(245,158,11,.3)',tc:'rgba(245,158,11,.85)',label:'Mixed Media'},
  soul:{bg:'rgba(192,39,26,.07)',bc:'rgba(192,39,26,.25)',tc:'rgba(240,100,80,.85)',label:'Soul Work'},
};

function buildTopics(){
  const c=document.getElementById('topics-container');
  if(!c)return;
  c.innerHTML='';
  TOPICS.forEach(t=>{
    const cc=CAT_COLORS[t.cat];
    const el=document.createElement('div');
    el.dataset.cat=t.cat;
    el.style.cssText=`background:#131318;border:1px solid rgba(240,232,216,.06);padding:26px 24px;position:relative;overflow:hidden;transition:all .35s;cursor:default`;
    el.innerHTML=`
      <div style="display:flex;align-items:center;gap:10px;margin-bottom:12px">
        <span style="font-family:'Josefin Sans',sans-serif;font-size:8px;letter-spacing:.38em;text-transform:uppercase;padding:3px 10px;border:1px solid ${cc.bc};background:${cc.bg};color:${cc.tc}">${cc.label}</span>
        <span style="font-family:'Josefin Sans',sans-serif;font-size:8px;letter-spacing:.3em;text-transform:uppercase;color:#6A5A52">${t.date}</span>
      </div>
      <div style="font-family:'Playfair Display',serif;font-size:20px;font-weight:700;color:#F0E8D8;margin-bottom:8px;line-height:1.22">${t.title}</div>
      <div style="font-size:14px;color:#9A8878;font-style:italic;line-height:1.7;margin-bottom:14px">${t.desc}</div>
      <div style="font-family:'Josefin Sans',sans-serif;font-size:9px;letter-spacing:.3em;text-transform:uppercase;color:#8B1A10">Medium: ${t.medium}</div>
      <div style="font-family:'Playfair Display',serif;font-size:52px;font-weight:900;color:rgba(192,39,26,.07);position:absolute;bottom:2px;right:10px;line-height:1;pointer-events:none">${t.n}</div>
    `;
    el.addEventListener('mouseenter',()=>{el.style.borderColor='rgba(192,39,26,.35)';el.style.transform='translateY(-2px)'});
    el.addEventListener('mouseleave',()=>{el.style.borderColor='rgba(240,232,216,.06)';el.style.transform='translateY(0)'});
    c.appendChild(el);
  });
}

function filterTopics(cat){
  document.querySelectorAll('.ws-filt').forEach(b=>b.classList.remove('ws-on'));
  document.querySelector(`.ws-filt[data-cat="${cat}"]`)?.classList.add('ws-on');
  document.querySelectorAll('#topics-container>div').forEach(el=>{
    el.style.display=(cat==='all'||el.dataset.cat===cat)?'':'none';
  });
}

/* ═══ GUIDE TABS ═══ */
function showGuide(id){
  document.querySelectorAll('.guide-tab').forEach(t=>t.classList.remove('guide-on'));
  document.querySelectorAll('.guide-panel').forEach(p=>p.classList.remove('guide-panel-on'));
  const tab=document.getElementById('gt-'+id);
  const panel=document.getElementById('gp-'+id);
  if(tab)tab.classList.add('guide-on');
  if(panel)panel.classList.add('guide-panel-on');
}

/* ═══ CHECKLISTS ═══ */
const FRIDAY_ITEMS=[
  {b:'Set up 6 student stations',t:'Canvas or paper, palette, brushes, water cup at each station.'},
  {b:'Squeeze paints',t:'Fill each palette with the colors needed for this week\'s medium and topic.'},
  {b:'Charge phone and set up tripod',t:'Phone must be at 100% before the session.'},
  {b:'Confirm all 6 registrations',t:'Check PayPal for 6 confirmed payments.'},
  {b:'Prepare 2–3 reference images',t:'Have them on your phone, ready to show during the intro.'},
  {b:'Set up music playlist',t:'Lo-fi jazz or ambient instrumental, no lyrics.'},
  {b:'Announce topic on socials tonight',t:'"Tomorrow\'s workshop: [TOPIC]. Doors open 9:45 AM."'},
  {b:'Review the topic description',t:'Read it out loud to yourself once. Know what you\'re going to say.'},
];
const SATURDAY_ITEMS=[
  {b:'Arrive by 9:30 AM',t:'30 minutes to set up ambient camera, light a candle, final station check.'},
  {b:'Film setup ASMR clip',t:'Record 60–90 seconds of the studio setup for your 9:00 AM post.'},
  {b:'Post Instagram/TikTok Story at 9 AM',t:'"Doors open in 30 minutes. Saturday workshop — [TOPIC]."'},
  {b:'Check sound levels',t:'Music at comfortable background level, not too loud to talk over.'},
  {b:'Open the door at 9:45 AM',t:'Greet each student by name if possible.'},
  {b:'Begin at 10:00 AM exactly',t:'Start on time every time. This builds the reputation for a professional studio.'},
  {b:'Film the demo close-up (10:10 AM)',t:'Ensure the close-up angle is capturing your hands clearly during demo.'},
  {b:'Photograph student work at 10:45 AM',t:'Canvas-only shots are always fine without asking permission.'},
  {b:'Close at 11:30 AM exactly',t:'Group shot of all pieces. Sign pieces if requested.'},
  {b:'Post the reveal by 12:00 PM',t:'All 6 pieces in one post. Caption with topic, hashtags, and booking link.'},
];

function buildChecklists(){
  const fl=document.getElementById('friday-list');
  const sl=document.getElementById('saturday-list');
  if(!fl||!sl)return;
  function makeList(container,items){
    items.forEach((item,i)=>{
      const d=document.createElement('div');
      d.className='chk-row';
      d.innerHTML=`<div class="chk-box-ws" id="cb-${container.id}-${i}"></div><p class="chk-txt"><b>${item.b}</b> — ${item.t}</p>`;
      d.querySelector('.chk-box-ws').onclick=function(){
        this.classList.toggle('done');
        this.textContent=this.classList.contains('done')?'✓':'';
      };
      container.appendChild(d);
    });
  }
  makeList(fl,FRIDAY_ITEMS);
  makeList(sl,SATURDAY_ITEMS);
}

/* ═══ SCROLL REVEAL ═══ */
const ro=new IntersectionObserver(entries=>{
  entries.forEach((e,i)=>{
    if(e.isIntersecting){
      setTimeout(()=>e.target.classList.add('vis'),i*60);
      ro.unobserve(e.target);
    }
  });
},{threshold:.07});
function activateReveal(){document.querySelectorAll('.rev').forEach(el=>ro.observe(el));}

/* ═══ INIT ═══ */
document.addEventListener('DOMContentLoaded',()=>{
  buildGallery();
  buildTopics();
  buildChecklists();
  activateReveal();
  const sd=document.getElementById('sig-date');
  if(sd)sd.valueAsDate=new Date();
});
</script>
</body>
</html>
