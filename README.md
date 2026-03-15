# Youbeengassed
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"><meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>YouBeEngassed — Platform Blueprint</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Rajdhani:wght@300;400;600;700&family=Space+Mono:ital,wght@0,400;0,700;1,400&display=swap" rel="stylesheet">
<style>
:root{--bg:#060010;--bg2:#0d0020;--bg3:#110030;--g:#39FF14;--p:#FF2D78;--v:#9B30FF;--c:#00F5FF;--y:#FFE600;--o:#FF7700;--dim:rgba(255,255,255,0.06);--border:rgba(153,48,255,0.35);--text:#e8e0ff;--muted:rgba(232,224,255,0.5)}
*{margin:0;padding:0;box-sizing:border-box}
body{background:var(--bg);color:var(--text);font-family:'Rajdhani',sans-serif;font-size:16px;line-height:1.6;min-height:100vh;overflow-x:hidden}
.cosmos{position:fixed;inset:0;z-index:0;pointer-events:none;overflow:hidden}
.cosmos::before{content:'';position:absolute;inset:0;background:radial-gradient(ellipse 80% 50% at 20% 0%,rgba(153,48,255,0.18) 0%,transparent 60%),radial-gradient(ellipse 60% 40% at 80% 100%,rgba(0,245,255,0.12) 0%,transparent 60%),radial-gradient(ellipse 50% 60% at 50% 50%,rgba(57,255,20,0.06) 0%,transparent 70%);animation:cosmosDrift 20s ease-in-out infinite alternate}
@keyframes cosmosDrift{0%{opacity:0.7;transform:scale(1)}100%{opacity:1;transform:scale(1.08)}}
.star{position:absolute;width:2px;height:2px;background:#fff;border-radius:50%;animation:twinkle var(--d,3s) ease-in-out infinite alternate;opacity:var(--o2,0.6)}
@keyframes twinkle{0%{opacity:0.1;transform:scale(0.5)}100%{opacity:1;transform:scale(1.5)}}
.floater{position:absolute;border-radius:50%;filter:blur(60px);animation:float var(--fd,15s) ease-in-out infinite alternate;pointer-events:none}
@keyframes float{0%{transform:translateY(0) translateX(0) scale(1)}100%{transform:translateY(var(--fy,-40px)) translateX(var(--fx,30px)) scale(var(--fs,1.1))}}
nav{position:sticky;top:0;z-index:100;background:rgba(6,0,16,0.85);backdrop-filter:blur(20px);border-bottom:1px solid var(--border);display:flex;align-items:center;justify-content:space-between;padding:0 2rem;height:64px}
.logo{font-family:'Orbitron',monospace;font-weight:900;font-size:1.1rem;color:var(--g);text-shadow:0 0 20px rgba(57,255,20,0.6);letter-spacing:2px;cursor:pointer}
.logo span{color:var(--p)}
.nav-tabs{display:flex;gap:0;list-style:none}
.nav-tabs li{font-family:'Orbitron',monospace;font-size:0.6rem;font-weight:700;letter-spacing:1.5px;padding:0.5rem 1rem;cursor:pointer;color:var(--muted);border-bottom:2px solid transparent;transition:all 0.2s;white-space:nowrap}
.nav-tabs li:hover{color:var(--text)} .nav-tabs li.active{color:var(--g);border-bottom-color:var(--g)}
.gas-meter{font-family:'Orbitron',monospace;font-size:0.65rem;color:var(--y);display:flex;align-items:center;gap:8px}
.gas-meter .pts{font-size:1rem;font-weight:900;color:var(--g);text-shadow:0 0 15px rgba(57,255,20,0.8);animation:countUp 0.5s ease-out}
@keyframes countUp{from{transform:translateY(8px);opacity:0}to{transform:translateY(0);opacity:1}}
.section{display:none;position:relative;z-index:1;min-height:calc(100vh - 64px);animation:fadeIn 0.4s ease-out}
.section.active{display:block}
@keyframes fadeIn{from{opacity:0;transform:translateY(16px)}to{opacity:1;transform:translateY(0)}}
.hero{display:flex;flex-direction:column;align-items:center;justify-content:center;min-height:calc(100vh - 64px);text-align:center;padding:4rem 2rem;position:relative}
.hero-eyebrow{font-family:'Space Mono',monospace;font-size:0.7rem;color:var(--v);letter-spacing:4px;text-transform:uppercase;margin-bottom:1.5rem;animation:pulse 2s ease-in-out infinite}
@keyframes pulse{0%,100%{opacity:0.7}50%{opacity:1}}
.hero-title{font-family:'Orbitron',monospace;font-weight:900;font-size:clamp(3rem,8vw,6.5rem);line-height:0.95;margin-bottom:1rem;letter-spacing:-2px}
.ht1{color:var(--g);display:block;text-shadow:0 0 60px rgba(57,255,20,0.5),0 0 120px rgba(57,255,20,0.2);animation:glitch 6s infinite}
@keyframes glitch{0%,90%,100%{text-shadow:0 0 60px rgba(57,255,20,0.5),0 0 120px rgba(57,255,20,0.2);transform:translate(0)}91%{transform:translate(-2px,1px);text-shadow:3px 0 var(--p),-3px 0 var(--c)}93%{transform:translate(2px,-1px);text-shadow:-3px 0 var(--p),3px 0 var(--c)}95%{transform:translate(0)}}
.ht2{color:var(--p);display:block;text-shadow:0 0 60px rgba(255,45,120,0.5)}
.hero-sub{font-family:'Rajdhani',sans-serif;font-size:1.3rem;color:var(--muted);max-width:600px;margin:1.5rem auto 2.5rem;line-height:1.5}
.hero-ctas{display:flex;gap:1rem;flex-wrap:wrap;justify-content:center;margin-bottom:4rem}
.btn{font-family:'Orbitron',monospace;font-weight:700;font-size:0.7rem;letter-spacing:2px;padding:0.9rem 2rem;border:none;cursor:pointer;transition:all 0.2s;text-transform:uppercase;position:relative;overflow:hidden}
.btn::before{content:'';position:absolute;inset:0;background:rgba(255,255,255,0.15);transform:translateX(-100%);transition:transform 0.3s}
.btn:hover::before{transform:translateX(0)}
.btn-primary{background:var(--g);color:#000;clip-path:polygon(8px 0,100% 0,calc(100% - 8px) 100%,0 100%)}
.btn-primary:hover{box-shadow:0 0 40px rgba(57,255,20,0.6);transform:translateY(-2px)}
.btn-secondary{background:transparent;color:var(--p);border:1px solid var(--p);clip-path:polygon(8px 0,100% 0,calc(100% - 8px) 100%,0 100%)}
.btn-secondary:hover{background:rgba(255,45,120,0.15);box-shadow:0 0 30px rgba(255,45,120,0.4)}
.stats-row{display:grid;grid-template-columns:repeat(4,1fr);gap:1px;width:100%;max-width:900px;background:var(--border);border:1px solid var(--border)}
.stat-cell{background:var(--bg2);padding:1.5rem;text-align:center;transition:background 0.2s}
.stat-cell:hover{background:var(--bg3)}
.stat-num{font-family:'Orbitron',monospace;font-size:2rem;font-weight:900;line-height:1;display:block}
.stat-label{font-size:0.75rem;color:var(--muted);letter-spacing:1px;text-transform:uppercase;margin-top:0.3rem}
.feature-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1px;background:var(--border);border:1px solid var(--border);margin:4rem 0}
.feature-card{background:var(--bg2);padding:2rem;cursor:pointer;transition:background 0.2s;border-bottom:3px solid transparent;position:relative;overflow:hidden}
.feature-card::after{content:'';position:absolute;bottom:0;left:0;right:0;height:3px;background:var(--accent,var(--g));transform:scaleX(0);transition:transform 0.3s;transform-origin:left}
.feature-card:hover{background:var(--bg3)} .feature-card:hover::after{transform:scaleX(1)}
.fc-icon{font-size:2rem;margin-bottom:0.75rem;display:block}
.fc-title{font-family:'Orbitron',monospace;font-size:0.8rem;font-weight:700;color:var(--accent,var(--g));letter-spacing:1px;margin-bottom:0.5rem}
.fc-desc{font-size:0.9rem;color:var(--muted)}
.lab-layout{display:grid;grid-template-columns:340px 1fr;gap:1px;background:var(--border);min-height:calc(100vh - 64px)}
.lab-panel{background:var(--bg2);padding:2rem;border-right:1px solid var(--border);overflow-y:auto}
.lab-preview{background:var(--bg);padding:2rem;display:flex;flex-direction:column;align-items:center;justify-content:flex-start;gap:2rem}
.panel-title{font-family:'Orbitron',monospace;font-size:0.7rem;font-weight:700;color:var(--v);letter-spacing:3px;text-transform:uppercase;margin-bottom:1.5rem;padding-bottom:0.75rem;border-bottom:1px solid var(--border)}
.form-group{margin-bottom:1.5rem}
.form-label{display:flex;justify-content:space-between;font-size:0.75rem;color:var(--muted);letter-spacing:1px;text-transform:uppercase;margin-bottom:0.5rem}
.form-label span{color:var(--y);font-weight:700}
input[type="range"]{-webkit-appearance:none;width:100%;height:3px;background:var(--bg3);outline:none;cursor:pointer}
input[type="range"]::-webkit-slider-thumb{-webkit-appearance:none;width:16px;height:16px;border-radius:50%;background:var(--g);box-shadow:0 0 10px rgba(57,255,20,0.6);cursor:pointer;transition:transform 0.1s}
input[type="range"]::-webkit-slider-thumb:active{transform:scale(1.3)}
.tag-group{display:flex;flex-wrap:wrap;gap:0.4rem;margin-top:0.5rem}
.tag{font-size:0.7rem;padding:0.25rem 0.6rem;border:1px solid var(--border);color:var(--muted);cursor:pointer;transition:all 0.15s;letter-spacing:0.5px;border-radius:2px}
.tag:hover,.tag.sel{border-color:var(--g);color:var(--g);background:rgba(57,255,20,0.08)}
.tag.sel-p{border-color:var(--p);color:var(--p);background:rgba(255,45,120,0.08)}
.tag.sel-c{border-color:var(--c);color:var(--c);background:rgba(0,245,255,0.08)}
.strain-card{width:100%;max-width:400px;background:var(--bg2);border:1px solid var(--border);position:relative;overflow:hidden}
.strain-card::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;background:linear-gradient(90deg,var(--strain-c1,#39FF14),var(--strain-c2,#FF2D78),var(--strain-c3,#9B30FF))}
.strain-visual{height:200px;background:radial-gradient(ellipse at 50% 60%,var(--strain-glow,rgba(153,48,255,0.3)),transparent 70%),linear-gradient(135deg,var(--strain-c1,#0d0020) 0%,var(--strain-c2,#1a0040) 100%);display:flex;align-items:center;justify-content:center;font-size:5rem;position:relative;overflow:hidden;animation:strainPulse 3s ease-in-out infinite}
@keyframes strainPulse{0%,100%{filter:brightness(1)}50%{filter:brightness(1.2)}}
.strain-body{padding:1.25rem}
.strain-name{font-family:'Orbitron',monospace;font-size:1.1rem;font-weight:900;color:var(--g);margin-bottom:0.25rem}
.strain-lineage{font-size:0.8rem;color:var(--muted);margin-bottom:1rem}
.strain-stats{display:grid;grid-template-columns:repeat(3,1fr);gap:0.5rem;margin-bottom:1rem}
.ss-cell{text-align:center;background:var(--bg3);padding:0.5rem}
.ss-val{font-family:'Orbitron',monospace;font-size:1rem;font-weight:700;display:block}
.ss-label{font-size:0.6rem;color:var(--muted);text-transform:uppercase;letter-spacing:1px}
.effects-bar{display:flex;flex-wrap:wrap;gap:0.3rem}
.effect-pill{font-size:0.65rem;padding:0.2rem 0.5rem;border-radius:12px;letter-spacing:0.5px;font-weight:600}
.dna-meter{width:100%;max-width:400px;background:var(--bg2);border:1px solid var(--border);padding:1.25rem}
.dna-title{font-family:'Orbitron',monospace;font-size:0.65rem;color:var(--c);letter-spacing:2px;margin-bottom:1rem}
.dna-row{display:flex;align-items:center;gap:0.75rem;margin-bottom:0.6rem}
.dna-label{font-size:0.75rem;color:var(--muted);width:80px;flex-shrink:0}
.dna-bar{flex:1;height:6px;background:var(--bg3);position:relative;border-radius:1px;overflow:hidden}
.dna-fill{height:100%;border-radius:1px;background:var(--bar-color,var(--g));box-shadow:0 0 8px var(--bar-color,var(--g));transition:width 0.5s cubic-bezier(0.4,0,0.2,1)}
.dna-pct{font-family:'Space Mono',monospace;font-size:0.65rem;color:var(--muted);width:28px;text-align:right}
.lounge-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:1px;background:var(--border);border:1px solid var(--border);margin-bottom:2rem}
.lounge-card{background:var(--bg2);padding:2rem 1.5rem;cursor:pointer;transition:all 0.2s;position:relative;overflow:hidden}
.lounge-card::before{content:'';position:absolute;inset:0;background:radial-gradient(ellipse at 50% 0%,var(--lc,rgba(57,255,20,0.15)),transparent 70%);opacity:0;transition:opacity 0.3s}
.lounge-card:hover::before{opacity:1} .lounge-card:hover{background:var(--bg3)}
.lounge-vibe{font-size:2.5rem;margin-bottom:0.75rem;display:block;filter:drop-shadow(0 0 8px rgba(255,255,255,0.3))}
.lounge-name{font-family:'Orbitron',monospace;font-size:0.85rem;font-weight:700;margin-bottom:0.35rem;letter-spacing:1px}
.lounge-desc{font-size:0.85rem;color:var(--muted);margin-bottom:1rem}
.lounge-meta{display:flex;gap:1rem;font-size:0.7rem;color:var(--muted)}
.lounge-meta span{color:var(--g);font-weight:700}
.feed-post{background:var(--bg2);border:1px solid var(--border);padding:1rem 1.25rem;margin-bottom:1px;display:flex;gap:1rem;cursor:pointer;transition:background 0.15s}
.feed-post:hover{background:var(--bg3)}
.avatar{width:40px;height:40px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:1.2rem;flex-shrink:0;border:2px solid var(--border)}
.post-body{flex:1}
.post-user{font-family:'Orbitron',monospace;font-size:0.7rem;font-weight:700;color:var(--c);margin-bottom:0.2rem}
.post-user .gas{color:var(--y)}
.post-text{font-size:0.9rem;color:var(--text);margin-bottom:0.5rem}
.post-actions{display:flex;gap:1rem}
.post-action{font-size:0.7rem;color:var(--muted);cursor:pointer;display:flex;align-items:center;gap:4px;transition:color 0.15s}
.post-action:hover{color:var(--g)}
.economy-layout{display:grid;grid-template-columns:1fr 1fr;gap:1px;background:var(--border);padding:0}
.eco-section{background:var(--bg2);padding:2rem}
.section-header{font-family:'Orbitron',monospace;font-size:0.65rem;font-weight:700;color:var(--v);letter-spacing:3px;text-transform:uppercase;margin-bottom:1.5rem;padding-bottom:0.75rem;border-bottom:1px solid var(--border);display:flex;align-items:center;justify-content:space-between}
.lb-row{display:flex;align-items:center;gap:1rem;padding:0.75rem 0;border-bottom:1px solid rgba(153,48,255,0.1);cursor:pointer;transition:background 0.15s}
.lb-row:hover{padding-left:0.5rem}
.lb-rank{font-family:'Orbitron',monospace;font-size:1.1rem;font-weight:900;width:32px;text-align:center}
.lb-avatar{width:36px;height:36px;border-radius:50%;display:flex;align-items:center;justify-content:center;font-size:1.1rem;flex-shrink:0}
.lb-info{flex:1}
.lb-name{font-weight:700;font-size:0.9rem;color:var(--text)}
.lb-tag{font-size:0.7rem;color:var(--muted)}
.lb-pts{font-family:'Orbitron',monospace;font-size:0.85rem;font-weight:700;color:var(--y)}
.lb-bar{height:3px;background:var(--bg3);margin-top:4px;border-radius:1px;overflow:hidden}
.lb-bar-fill{height:100%;background:var(--fill-color,var(--g));box-shadow:0 0 6px var(--fill-color,var(--g));border-radius:1px}
.badge-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:0.75rem}
.badge{background:var(--bg3);border:1px solid var(--border);padding:1rem 0.5rem;text-align:center;cursor:pointer;transition:all 0.2s;position:relative}
.badge.earned{border-color:var(--g);background:rgba(57,255,20,0.05)}
.badge.legendary{border-color:var(--y);background:rgba(255,230,0,0.07);animation:legendaryPulse 2s ease-in-out infinite}
@keyframes legendaryPulse{0%,100%{box-shadow:0 0 8px rgba(255,230,0,0.2)}50%{box-shadow:0 0 20px rgba(255,230,0,0.4)}}
.badge-icon{font-size:1.8rem;display:block;margin-bottom:0.3rem}
.badge-name{font-size:0.6rem;letter-spacing:0.5px;font-weight:700;color:var(--muted);text-transform:uppercase}
.badge.earned .badge-name{color:var(--g)} .badge.legendary .badge-name{color:var(--y)}
.badge-locked{position:absolute;inset:0;background:rgba(6,0,16,0.7);display:flex;align-items:center;justify-content:center;font-size:1rem}
.level-tree{display:flex;flex-direction:column;gap:0}
.level-row{display:flex;align-items:center;gap:1rem;padding:0.6rem 0;border-bottom:1px solid rgba(153,48,255,0.1)}
.level-num{font-family:'Orbitron',monospace;font-size:0.7rem;font-weight:700;width:24px;text-align:right;color:var(--muted)}
.level-bar{flex:1;height:20px;background:var(--bg3);position:relative;border-radius:2px;overflow:hidden}
.level-bar-fill{height:100%;display:flex;align-items:center;padding-left:8px;font-size:0.6rem;font-weight:700;letter-spacing:1px;background:var(--lv-color,var(--v));transition:width 0.5s cubic-bezier(0.4,0,0.2,1);white-space:nowrap;overflow:hidden}
.level-unlock{font-size:0.7rem;color:var(--muted);width:160px;text-align:right}
.marketplace{display:grid;grid-template-columns:repeat(3,1fr);gap:1px;background:var(--border);border:1px solid var(--border)}
.market-card{background:var(--bg2);padding:1.25rem;cursor:pointer;transition:background 0.2s;position:relative}
.market-card:hover{background:var(--bg3)}
.market-thumb{height:120px;border-radius:2px;display:flex;align-items:center;justify-content:center;font-size:3rem;margin-bottom:1rem;position:relative;overflow:hidden}
.market-rarity{position:absolute;top:6px;right:6px;font-size:0.55rem;font-weight:700;letter-spacing:1px;padding:2px 6px;border-radius:2px;font-family:'Orbitron',monospace}
.market-name{font-family:'Orbitron',monospace;font-size:0.75rem;font-weight:700;margin-bottom:0.25rem;color:var(--text);letter-spacing:0.5px}
.market-seller{font-size:0.7rem;color:var(--muted);margin-bottom:0.75rem}
.market-price{display:flex;justify-content:space-between;align-items:center}
.market-cost{font-family:'Orbitron',monospace;font-size:0.9rem;font-weight:900;color:var(--y)}
.market-cost span{font-size:0.6rem;color:var(--muted)}
.mono-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:1px;background:var(--border);border:1px solid var(--border);margin-bottom:2rem}
.mono-card{background:var(--bg2);padding:2rem;border-top:3px solid var(--mc-color,var(--v))}
.mono-icon{font-size:2rem;margin-bottom:0.75rem;display:block}
.mono-title{font-family:'Orbitron',monospace;font-size:0.75rem;font-weight:700;color:var(--mc-color,var(--v));letter-spacing:1px;margin-bottom:0.5rem}
.mono-desc{font-size:0.85rem;color:var(--muted);margin-bottom:1rem}
.mono-items{list-style:none}
.mono-items li{font-size:0.8rem;padding:0.3rem 0;color:var(--text);display:flex;gap:0.5rem;border-bottom:1px solid rgba(153,48,255,0.1)}
.mono-items li::before{content:'→';color:var(--mc-color,var(--v));flex-shrink:0}
.revenue-bars{display:flex;gap:8px;align-items:flex-end;height:160px;padding:0 0 0.5rem;border-bottom:1px solid var(--border);margin-bottom:0.75rem}
.rev-bar-wrap{flex:1;display:flex;flex-direction:column;align-items:center;justify-content:flex-end;gap:4px;height:100%}
.rev-bar{width:100%;border-radius:2px 2px 0 0;transition:height 1s cubic-bezier(0.4,0,0.2,1);position:relative}
.rev-val{font-family:'Orbitron',monospace;font-size:0.55rem;text-align:center;color:var(--muted);white-space:nowrap;position:absolute;top:-16px;left:50%;transform:translateX(-50%)}
.rev-label{font-size:0.65rem;color:var(--muted);text-align:center}
.virality-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:1px;background:var(--border);border:1px solid var(--border)}
.viral-cell{background:var(--bg2);padding:1.5rem 1rem;text-align:center}
.viral-num{font-family:'Orbitron',monospace;font-size:1.5rem;font-weight:900;display:block;margin-bottom:0.25rem}
.viral-label{font-size:0.65rem;color:var(--muted);text-transform:uppercase;letter-spacing:1px}
.page{padding:2rem;max-width:1300px;margin:0 auto}
.page-title{font-family:'Orbitron',monospace;font-size:0.6rem;font-weight:700;color:var(--v);letter-spacing:4px;text-transform:uppercase;margin-bottom:0.5rem}
.page-headline{font-family:'Orbitron',monospace;font-size:2rem;font-weight:900;line-height:1.1;margin-bottom:0.5rem}
.page-sub{font-size:1rem;color:var(--muted);margin-bottom:2.5rem;max-width:600px}
.color-picker{display:flex;gap:0.4rem;flex-wrap:wrap;margin-top:0.5rem}
.color-swatch{width:28px;height:28px;border-radius:50%;cursor:pointer;border:2px solid transparent;transition:transform 0.15s}
.color-swatch:hover{transform:scale(1.2)} .color-swatch.sel{border-color:#fff;transform:scale(1.15)}
::-webkit-scrollbar{width:4px} ::-webkit-scrollbar-track{background:var(--bg)} ::-webkit-scrollbar-thumb{background:var(--v);border-radius:2px}
.marquee-wrap{overflow:hidden;background:var(--g);padding:6px 0;white-space:nowrap}
.marquee-inner{display:inline-block;animation:marquee 30s linear infinite}
.marquee-inner span{font-family:'Orbitron',monospace;font-size:0.6rem;font-weight:700;color:#000;letter-spacing:3px;margin-right:4rem;text-transform:uppercase}
@keyframes marquee{0%{transform:translateX(0)}100%{transform:translateX(-50%)}}
.badge-live{font-size:0.55rem;background:var(--p);color:#fff;padding:2px 6px;border-radius:2px;font-family:'Orbitron',monospace;letter-spacing:1px;animation:blink 1.5s step-end infinite}
@keyframes blink{0%,100%{opacity:1}50%{opacity:0.3}}
.divider{height:1px;background:var(--border);margin:2rem 0}
.minigame-card{background:var(--bg2);border:1px solid var(--border);padding:1.5rem;display:flex;align-items:center;gap:1.5rem;margin-bottom:1px;cursor:pointer;transition:background 0.15s;position:relative;overflow:hidden}
.minigame-card:hover{background:var(--bg3)}
.minigame-card::before{content:'';position:absolute;top:0;left:0;width:4px;height:100%;background:var(--mg-color,var(--g))}
.mg-thumb{width:60px;height:60px;display:flex;align-items:center;justify-content:center;font-size:2.2rem;flex-shrink:0;background:var(--bg3);border-radius:2px}
.mg-info{flex:1}
.mg-name{font-family:'Orbitron',monospace;font-size:0.8rem;font-weight:700;color:var(--mg-color,var(--g));margin-bottom:0.25rem}
.mg-desc{font-size:0.85rem;color:var(--muted)}
.mg-reward{text-align:right;flex-shrink:0}
.mg-pts{font-family:'Orbitron',monospace;font-size:0.8rem;font-weight:900;color:var(--y);display:block}
.mg-type{font-size:0.65rem;color:var(--muted)}
.notif{position:fixed;top:80px;right:20px;z-index:200;background:var(--bg2);border:1px solid var(--g);border-left:4px solid var(--g);padding:0.75rem 1rem;min-width:240px;animation:slideIn 0.3s ease-out,slideOut 0.3s ease-in 2.7s forwards;pointer-events:none}
@keyframes slideIn{from{transform:translateX(110%);opacity:0}to{transform:translateX(0);opacity:1}}
@keyframes slideOut{from{transform:translateX(0);opacity:1}to{transform:translateX(110%);opacity:0}}
@media (max-width:768px){.nav-tabs li{padding:0.5rem 0.5rem;font-size:0.5rem}.feature-grid,.lounge-grid{grid-template-columns:1fr}.lab-layout{grid-template-columns:1fr}.economy-layout,.mono-grid{grid-template-columns:1fr}.stats-row{grid-template-columns:repeat(2,1fr)}}
</style>
</head>
<body>
<div class="cosmos" id="cosmos">
<div class="floater" style="width:400px;height:400px;top:-10%;left:-10%;background:rgba(153,48,255,0.12);--fd:18s;--fy:-30px;--fx:40px;--fs:1.1"></div>
<div class="floater" style="width:300px;height:300px;top:60%;right:-5%;background:rgba(0,245,255,0.1);--fd:22s;--fy:20px;--fx:-30px;--fs:1.2"></div>
<div class="floater" style="width:250px;height:250px;top:40%;left:40%;background:rgba(57,255,20,0.06);--fd:15s;--fy:-50px;--fx:20px;--fs:0.9"></div>
</div>
<nav>
<div class="logo" onclick="switchTab(0)">YOU<span>BE</span>ENGASSED</div>
<ul class="nav-tabs" id="navTabs">
<li class="active" onclick="switchTab(0)">ENTER THE GAS</li><li onclick="switchTab(1)">STRAIN LAB</li><li onclick="switchTab(2)">VIBE LOUNGES</li><li onclick="switchTab(3)">GAS ECONOMY</li><li onclick="switchTab(4)">MONETIZATION</li>
</ul>
<div class="gas-meter"><div>⚡ GAS PTS</div><div class="pts" id="gasDisplay">4,200</div></div>
</nav>
<div class="marquee-wrap"><div class="marquee-inner">
<span>🔥 GalacticKush just dropped a legendary strain</span><span>⚡ New Vibe Lounge: "Cosmic Paranoia" now open</span><span>🏆 PurpleRainGod reached Level 50</span><span>💎 Rare "Alien OG Nebula" trading for 12,000 gas pts</span><span>🎮 Psychedelic Puzzle Event ends in 6H 42M</span>
</div></div>
<div class="section active" id="sec0">
<div class="hero">
<div class="hero-eyebrow">// ENTER THE UNIVERSE //</div>
<h1 class="hero-title"><span class="ht1">YOUBEEN</span><span class="ht2">GASSED</span></h1>
<p class="hero-sub">The world's most chaotic, psychedelic, community-powered cannabis universe. Design strains. Build vibes. Stack gas points. Ascend.</p>
<div class="hero-ctas">
<button class="btn btn-primary" onclick="switchTab(1)">BUILD A STRAIN →</button><button class="btn btn-secondary" onclick="switchTab(2)">FIND YOUR LOUNGE</button>
</div>
<div class="stats-row">
<div class="stat-cell"><span class="stat-num" style="color:var(--g)">847K</span><div class="stat-label">Gas Heads</div></div>
<div class="stat-cell"><span class="stat-num" style="color:var(--p)">2.4M</span><div class="stat-label">Strains Created</div></div>
<div class="stat-cell"><span class="stat-num" style="color:var(--c)">312</span><div class="stat-label">Active Lounges</div></div>
<div class="stat-cell"><span class="stat-num" style="color:var(--y)">∞</span><div class="stat-label">Vibes Per Day</div></div>
</div></div>
<div class="page" style="padding-top:0"><div class="feature-grid">
<div class="feature-card" style="--accent:var(--g)" onclick="switchTab(1)"><span class="fc-icon">🧬</span><div class="fc-title">AI STRAIN LAB</div><div class="fc-desc">Engineer impossible strains with 200+ flavor, effect, and visual parameters. Mint your creation as a tradeable collectible.</div></div>
<div class="feature-card" style="--accent:var(--p)" onclick="switchTab(2)"><span class="fc-icon">🌐</span><div class="fc-title">VIBE LOUNGES</div><div class="fc-desc">Micro-communities sorted by mood, strain preference, or cosmic energy. Host events, drop exclusives, run your own zone.</div></div>
<div class="feature-card" style="--accent:var(--c)" onclick="switchTab(3)"><span class="fc-icon">⚡</span><div class="fc-title">GAS ECONOMY</div><div class="fc-desc">Earn Gas Points for creativity, interaction, and influence. Spend them on rare drops, secret zones, and legendary status.</div></div>
<div class="feature-card" style="--accent:var(--y)" onclick="switchTab(3)"><span class="fc-icon">🎮</span><div class="fc-title">MINI-GAMES</div><div class="fc-desc">AR scavenger hunts, psychedelic puzzle runs, collaborative grow challenges. Win exclusive collectibles and social clout.</div></div>
<div class="feature-card" style="--accent:var(--o)"><span class="fc-icon">💎</span><div class="fc-title">COLLECTIBLE MARKET</div><div class="fc-desc">Trade strains, accessories, grow spaces, and limited drops. Full peer-to-peer economy powered by Gas Points.</div></div>
<div class="feature-card" style="--accent:var(--v)" onclick="switchTab(4)"><span class="fc-icon">👑</span><div class="fc-title">GAS LORD PASS</div><div class="fc-desc">Premium membership unlocking secret lounges, early drops, AI generation credits, and your own branded strain line.</div></div>
</div></div></div>
<div class="section" id="sec1"><div class="lab-layout">
<div class="lab-panel">
<div class="panel-title">🧬 AI STRAIN DESIGNER</div>
<div class="form-group"><div class="form-label">STRAIN NAME</div><input type="text" id="strainName" value="Galactic Mango Krush" oninput="updateStrain()" style="width:100%;background:var(--bg3);border:1px solid var(--border);color:var(--text);padding:0.5rem 0.75rem;font-family:'Rajdhani',sans-serif;font-size:0.9rem;outline:none;"></div>
<div class="form-group"><div class="form-label">PRIMARY COLOR <span id="c1Label">#39FF14</span></div><div class="color-picker" id="colorPicker1">
<div class="color-swatch sel" style="background:#39FF14" onclick="selectColor(1,'#39FF14','rgba(57,255,20,0.4)')"></div><div class="color-swatch" style="background:#FF2D78" onclick="selectColor(1,'#FF2D78','rgba(255,45,120,0.4)')"></div><div class="color-swatch" style="background:#9B30FF" onclick="selectColor(1,'#9B30FF','rgba(155,48,255,0.4)')"></div><div class="color-swatch" style="background:#00F5FF" onclick="selectColor(1,'#00F5FF','rgba(0,245,255,0.4)')"></div><div class="color-swatch" style="background:#FFE600" onclick="selectColor(1,'#FFE600','rgba(255,230,0,0.4)')"></div><div class="color-swatch" style="background:#FF7700" onclick="selectColor(1,'#FF7700','rgba(255,119,0,0.4)')"></div><div class="color-swatch" style="background:#FF003C" onclick="selectColor(1,'#FF003C','rgba(255,0,60,0.4)')"></div><div class="color-swatch" style="background:#7DFFB0" onclick="selectColor(1,'#7DFFB0','rgba(125,255,176,0.4)')"></div>
</div></div>
<div class="form-group"><div class="form-label">ACCENT COLOR <span id="c2Label">#FF2D78</span></div><div class="color-picker" id="colorPicker2">
<div class="color-swatch" style="background:#39FF14" onclick="selectColor(2,'#39FF14','rgba(57,255,20,0.4)')"></div><div class="color-swatch sel" style="background:#FF2D78" onclick="selectColor(2,'#FF2D78','rgba(255,45,120,0.4)')"></div><div class="color-swatch" style="background:#9B30FF" onclick="selectColor(2,'#9B30FF','rgba(155,48,255,0.4)')"></div><div class="color-swatch" style="background:#00F5FF" onclick="selectColor(2,'#00F5FF','rgba(0,245,255,0.4)')"></div><div class="color-swatch" style="background:#FFE600" onclick="selectColor(2,'#FFE600','rgba(255,230,0,0.4)')"></div><div class="color-swatch" style="background:#FF7700" onclick="selectColor(2,'#FF7700','rgba(255,119,0,0.4)')"></div><div class="color-swatch" style="background:#7DFFB0" onclick="selectColor(2,'#7DFFB0','rgba(125,255,176,0.4)')"></div><div class="color-swatch" style="background:#C0A0FF" onclick="selectColor(2,'#C0A0FF','rgba(192,160,255,0.4)')"></div>
</div></div>
<div class="form-group"><div class="form-label">THC POTENCY <span id="thcLabel">82%</span></div><input type="range" min="0" max="100" value="82" id="thcRange" oninput="updateSlider('thc',this.value); updateStrain()"></div>
<div class="form-group"><div class="form-label">CBD BLEND <span id="cbdLabel">18%</span></div><input type="range" min="0" max="100" value="18" id="cbdRange" oninput="updateSlider('cbd',this.value); updateStrain()"></div>
<div class="form-group"><div class="form-label">EUPHORIA <span id="euphoriaLabel">91%</span></div><input type="range" min="0" max="100" value="91" id="euphoriaRange" oninput="updateSlider('euphoria',this.value); updateStrain()"></div>
<div class="form-group"><div class="form-label">COSMIC ENERGY <span id="cosmicLabel">76%</span></div><input type="range" min="0" max="100" value="76" id="cosmicRange" oninput="updateSlider('cosmic',this.value); updateStrain()"></div>
<div class="form-group"><div class="form-label">RARITY SCORE <span id="rarityLabel">67%</span></div><input type="range" min="0" max="100" value="67" id="rarityRange" oninput="updateSlider('rarity',this.value); updateStrain()"></div>
<div class="form-group"><div class="form-label">FLAVOR PROFILE</div><div class="tag-group">
<div class="tag sel" onclick="toggleTag(this,'sel')">Mango</div><div class="tag sel" onclick="toggleTag(this,'sel')">Citrus</div><div class="tag" onclick="toggleTag(this,'sel')">Diesel</div><div class="tag" onclick="toggleTag(this,'sel')">Pine</div><div class="tag sel" onclick="toggleTag(this,'sel')">Vanilla</div><div class="tag" onclick="toggleTag(this,'sel')">Skunk</div><div class="tag" onclick="toggleTag(this,'sel')">Berry</div><div class="tag" onclick="toggleTag(this,'sel')">Earthy</div><div class="tag" onclick="toggleTag(this,'sel')">Grape</div><div class="tag" onclick="toggleTag(this,'sel')">Mint</div>
</div></div>
<div class="form-group"><div class="form-label">EFFECTS</div><div class="tag-group">
<div class="tag sel-p" onclick="toggleTag(this,'sel-p')">Euphoric</div><div class="tag sel-p" onclick="toggleTag(this,'sel-p')">Creative</div><div class="tag" onclick="toggleTag(this,'sel-p')">Relaxed</div><div class="tag sel-p" onclick="toggleTag(this,'sel-p')">Uplifted</div><div class="tag" onclick="toggleTag(this,'sel-p')">Focused</div><div class="tag" onclick="toggleTag(this,'sel-p')">Giggly</div><div class="tag" onclick="toggleTag(this,'sel-p')">Talkative</div><div class="tag sel-p" onclick="toggleTag(this,'sel-p')">Cosmic</div>
</div></div>
<div class="form-group"><div class="form-label">STRAIN TYPE</div><div class="tag-group">
<div class="tag sel-c" onclick="toggleType(this)">Sativa</div><div class="tag" onclick="toggleType(this)">Indica</div><div class="tag" onclick="toggleType(this)">Hybrid</div><div class="tag" onclick="toggleType(this)">Exotic</div>
</div></div>
<button class="btn btn-primary" style="width:100%;margin-top:1rem" onclick="mintStrain()">MINT STRAIN — 500 GAS PTS ⚡</button>
</div>
<div class="lab-preview">
<div class="strain-card" id="strainCard">
<div class="strain-visual" id="strainVisual">🌿</div>
<div class="strain-body">
<div class="strain-name" id="strainNameDisplay">Galactic Mango Krush</div>
<div class="strain-lineage">Mango Tango × Cosmic Purple × Alien Haze</div>
<div class="strain-stats">
<div class="ss-cell"><span class="ss-val" style="color:var(--g)" id="thcDisplay">82%</span><div class="ss-label">THC</div></div>
<div class="ss-cell"><span class="ss-val" style="color:var(--c)" id="cbdDisplay">18%</span><div class="ss-label">CBD</div></div>
<div class="ss-cell"><span class="ss-val" style="color:var(--y)" id="rarityDisplay">RARE</span><div class="ss-label">RARITY</div></div>
</div>
<div class="effects-bar">
<div class="effect-pill" style="background:rgba(255,45,120,0.2);color:var(--p);border:1px solid rgba(255,45,120,0.4)">Euphoric</div>
<div class="effect-pill" style="background:rgba(0,245,255,0.2);color:var(--c);border:1px solid rgba(0,245,255,0.4)">Creative</div>
<div class="effect-pill" style="background:rgba(255,230,0,0.2);color:var(--y);border:1px solid rgba(255,230,0,0.4)">Uplifted</div>
<div class="effect-pill" style="background:rgba(155,48,255,0.2);color:var(--v);border:1px solid rgba(155,48,255,0.4)">Cosmic</div>
</div></div></div>
<div class="dna-meter">
<div class="dna-title">// DNA PROFILE //</div>
<div class="dna-row"><div class="dna-label">THC</div><div class="dna-bar"><div class="dna-fill" id="dnaThc" style="width:82%;--bar-color:var(--g)"></div></div><div class="dna-pct" id="dnaTp">82%</div></div>
<div class="dna-row"><div class="dna-label">CBD</div><div class="dna-bar"><div class="dna-fill" id="dnaCbd" style="width:18%;--bar-color:var(--c)"></div></div><div class="dna-pct" id="dnaCp">18%</div></div>
<div class="dna-row"><div class="dna-label">Euphoria</div><div class="dna-bar"><div class="dna-fill" id="dnaEuph" style="width:91%;--bar-color:var(--p)"></div></div><div class="dna-pct" id="dnaEp">91%</div></div>
<div class="dna-row"><div class="dna-label">Cosmic</div><div class="dna-bar"><div class="dna-fill" id="dnaCos" style="width:76%;--bar-color:var(--v)"></div></div><div class="dna-pct" id="dnaCop">76%</div></div>
<div class="dna-row"><div class="dna-label">Rarity</div><div class="dna-bar"><div class="dna-fill" id="dnaRar" style="width:67%;--bar-color:var(--y)"></div></div><div class="dna-pct" id="dnaRp">67%</div></div>
</div>
<div style="text-align:center;font-size:0.75rem;color:var(--muted);font-family:'Space Mono',monospace">ESTIMATED MARKET VALUE: <span style="color:var(--y);font-size:1rem;font-weight:700" id="strainValue">2,847 ⚡</span></div>
</div></div></div>
<div class="section" id="sec2"><div class="page">
<div class="page-title">// SOCIAL UNIVERSE //</div><div class="page-headline" style="color:var(--p)">VIBE LOUNGES</div><div class="page-sub">Find your frequency. Every lounge has its own culture, rules, and exclusive drops. Rep your zone.</div>
<div class="lounge-grid">
<div class="lounge-card" style="--lc:rgba(57,255,20,0.15)"><span class="lounge-vibe">🌿</span><div class="lounge-name" style="color:var(--g)">FOREST DIMENSION</div><div class="lounge-desc">Earthy vibes. Nature lovers. Zen growers. Slow burns and deep thoughts. No drama permitted.</div><div class="lounge-meta"><div><span>3,241</span> heads inside</div><div><span>OPEN</span></div></div></div>
<div class="lounge-card" style="--lc:rgba(255,45,120,0.15)"><span class="lounge-vibe">🚀</span><div class="lounge-name" style="color:var(--p)">COSMIC EUPHORIA</div><div class="lounge-desc">Sativa nation. Creativity overload. Art drops, music collabs, and maximum brain activation.</div><div class="lounge-meta"><div><span>7,892</span> heads inside</div><div><span>🔴 PACKED</span></div></div></div>
<div class="lounge-card" style="--lc:rgba(155,48,255,0.15)"><span class="lounge-vibe">🔮</span><div class="lounge-name" style="color:var(--v)">PURPLE DIMENSION</div><div class="lounge-desc">Indica gods. Deep relaxation. Premium strains only. Exclusive drops every 48 hours.</div><div class="lounge-meta"><div><span>2,100</span> heads inside</div><div><span style="color:var(--y)">INVITE ONLY</span></div></div></div>
<div class="lounge-card" style="--lc:rgba(0,245,255,0.15)"><span class="lounge-vibe">🌊</span><div class="lounge-name" style="color:var(--c)">WAVE CRASH ZONE</div><div class="lounge-desc">Hybrid heads. Balance seekers. The in-between dimension. Community events 24/7.</div><div class="lounge-meta"><div><span>5,443</span> heads inside</div><div><span>OPEN</span></div></div></div>
<div class="lounge-card" style="--lc:rgba(255,230,0,0.15)"><span class="lounge-vibe">👑</span><div class="lounge-name" style="color:var(--y)">GAS LORD CHAMBER</div><div class="lounge-desc">Top 1% Gas Point holders only. Legendary drops. Secret auctions. The inner circle.</div><div class="lounge-meta"><div><span>88</span> lords inside</div><div><span style="color:var(--p)">🔒 10K+ GAS</span></div></div></div>
<div class="lounge-card" style="--lc:rgba(255,119,0,0.15)"><span class="lounge-vibe">🔥</span><div class="lounge-name" style="color:var(--o)">BLAZED & CONFUSED</div><div class="lounge-desc">Total chaos. Maximum humor. Meme battles, absurd strains, and unhinged vibes only.</div><div class="lounge-meta"><div><span>9,999+</span> heads inside</div><div><span>OPEN ALWAYS</span></div></div></div>
</div>
<div class="divider"></div>
<div style="display:grid;grid-template-columns:1fr 360px;gap:1px;background:var(--border)">
<div>
<div class="section-header" style="padding:1rem 1.25rem;border-bottom:1px solid var(--border);margin:0">LIVE UNIVERSE FEED <span class="badge-live">LIVE</span></div>
<div class="feed-post"><div class="avatar" style="background:rgba(57,255,20,0.15);border-color:rgba(57,255,20,0.4)">🌿</div><div class="post-body"><div class="post-user">GalacticKush420 <span class="gas">⚡ 12,840 GAS</span> · Forest Dimension</div><div class="post-text">Just dropped "Moonbeam Skunk Deluxe" — took 6 hours to engineer. The glow profile alone should get me into Gas Lord Chamber 👀</div><div class="post-actions"><div class="post-action" onclick="addGas(50)">🔥 <span>847 gas it</span></div><div class="post-action">💬 <span>34 replies</span></div><div class="post-action">🔄 <span>share strain</span></div></div></div></div>
<div class="feed-post"><div class="avatar" style="background:rgba(255,45,120,0.15);border-color:rgba(255,45,120,0.4)">🚀</div><div class="post-body"><div class="post-user">CosmicPurpleGod <span class="gas">⚡ 8,210 GAS</span> · Cosmic Euphoria</div><div class="post-text">Anyone else feel like the Psychedelic Puzzle event is TOO easy? Already on wave 9. Where's the chaos they promised??? 🧩</div><div class="post-actions"><div class="post-action" onclick="addGas(25)">🔥 <span>312 gas it</span></div><div class="post-action">💬 <span>89 replies</span></div><div class="post-action">🔄 <span>share</span></div></div></div></div>
<div class="feed-post"><div class="avatar" style="background:rgba(255,230,0,0.15);border-color:rgba(255,230,0,0.4)">👑</div><div class="post-body"><div class="post-user">GasLordOmega <span class="gas">⚡ 44,000 GAS</span> · Gas Lord Chamber</div><div class="post-text">Auctioning "Nebula OG Prime Edition" starting at 5,000 gas points. Legendaries only. Chamber members get first look in 1H.</div><div class="post-actions"><div class="post-action" onclick="addGas(100)">🔥 <span>2,100 gas it</span></div><div class="post-action">💬 <span>144 replies</span></div><div class="post-action">💎 <span>bid now</span></div></div></div></div>
<div class="feed-post"><div class="avatar" style="background:rgba(0,245,255,0.15);border-color:rgba(0,245,255,0.4)">🌊</div><div class="post-body"><div class="post-user">WaveRider_Tex <span class="gas">⚡ 1,920 GAS</span> · Wave Crash Zone</div><div class="post-text">Just unlocked my first Rare badge 🏆 "Flavor Chemist" — the strain I made with blueberry + turpentine + moon dust actually worked lmao</div><div class="post-actions"><div class="post-action" onclick="addGas(25)">🔥 <span>654 gas it</span></div><div class="post-action">💬 <span>21 replies</span></div><div class="post-action">🎁 <span>send gas</span></div></div></div></div>
</div>
<div style="background:var(--bg2);padding:1.25rem;border-left:1px solid var(--border)">
<div class="section-header" style="margin-bottom:1rem">ACTIVE EVENTS</div>
<div style="margin-bottom:1rem;padding:1rem;background:var(--bg3);border:1px solid rgba(255,45,120,0.3)"><div style="font-family:'Orbitron',monospace;font-size:0.65rem;color:var(--p);margin-bottom:0.3rem">🎮 LIVE NOW</div><div style="font-size:0.85rem;font-weight:700;margin-bottom:0.25rem">Psychedelic Puzzle Marathon</div><div style="font-size:0.75rem;color:var(--muted);margin-bottom:0.5rem">Solve 12 increasingly unhinged visual puzzles. Top 50 win Legendary drops.</div><div style="font-size:0.7rem;color:var(--y)">⏱ Ends in 6H 42M · 3,847 players</div></div>
<div style="margin-bottom:1rem;padding:1rem;background:var(--bg3);border:1px solid rgba(57,255,20,0.3)"><div style="font-family:'Orbitron',monospace;font-size:0.65rem;color:var(--g);margin-bottom:0.3rem">🌱 UPCOMING</div><div style="font-size:0.85rem;font-weight:700;margin-bottom:0.25rem">Grow-Off Championship S3</div><div style="font-size:0.75rem;color:var(--muted);margin-bottom:0.5rem">Design the highest-rated virtual grow space. Community votes determine winners.</div><div style="font-size:0.7rem;color:var(--y)">Starts in 2D 14H · 1,200 registered</div></div>
<div style="padding:1rem;background:var(--bg3);border:1px solid rgba(155,48,255,0.3)"><div style="font-family:'Orbitron',monospace;font-size:0.65rem;color:var(--v);margin-bottom:0.3rem">👑 CHAMBER ONLY</div><div style="font-size:0.85rem;font-weight:700;margin-bottom:0.25rem">Legendary Strain Auction</div><div style="font-size:0.75rem;color:var(--muted);margin-bottom:0.5rem">Auction of 6 hand-picked community legendary strains. Gas Lord Pass required.</div><div style="font-size:0.7rem;color:var(--y)">Starts in 58M · Invite only</div></div>
</div></div></div></div>
<div class="section" id="sec3"><div class="page">
<div class="page-title">// GAMIFICATION & ECONOMY //</div><div class="page-headline" style="color:var(--y)">GAS ECONOMY</div><div class="page-sub">Gas Points are the lifeblood of the universe. Earn through creation, community, and chaos. Spend to ascend.</div>
<div class="economy-layout">
<div class="eco-section"><div class="section-header">⚡ GAS LORDS LEADERBOARD <span style="color:var(--muted)">this week</span></div>
<div class="lb-row"><div class="lb-rank" style="color:var(--y)">01</div><div class="lb-avatar" style="background:rgba(255,230,0,0.2);border:2px solid rgba(255,230,0,0.5)">👑</div><div class="lb-info"><div class="lb-name">GasLordOmega</div><div class="lb-tag">Gas Lord · Cosmic Euphoria</div><div class="lb-bar"><div class="lb-bar-fill" style="width:100%;--fill-color:var(--y)"></div></div></div><div class="lb-pts">44,000 ⚡</div></div>
<div class="lb-row"><div class="lb-rank" style="color:rgba(192,192,192,1)">02</div><div class="lb-avatar" style="background:rgba(0,245,255,0.2);border:2px solid rgba(0,245,255,0.4)">🚀</div><div class="lb-info"><div class="lb-name">CosmicPurpleGod</div><div class="lb-tag">Legend · Cosmic Euphoria</div><div class="lb-bar"><div class="lb-bar-fill" style="width:75%;--fill-color:var(--c)"></div></div></div><div class="lb-pts">32,800 ⚡</div></div>
<div class="lb-row"><div class="lb-rank" style="color:var(--o)">03</div><div class="lb-avatar" style="background:rgba(57,255,20,0.2);border:2px solid rgba(57,255,20,0.4)">🌿</div><div class="lb-info"><div class="lb-name">GalacticKush420</div><div class="lb-tag">Legend · Forest Dimension</div><div class="lb-bar"><div class="lb-bar-fill" style="width:62%;--fill-color:var(--g)"></div></div></div><div class="lb-pts">27,400 ⚡</div></div>
<div class="lb-row"><div class="lb-rank" style="color:var(--muted)">04</div><div class="lb-avatar" style="background:rgba(155,48,255,0.2)">🔮</div><div class="lb-info"><div class="lb-name">PurpleRainGod</div><div class="lb-tag">Elite · Purple Dimension</div><div class="lb-bar"><div class="lb-bar-fill" style="width:48%;--fill-color:var(--v)"></div></div></div><div class="lb-pts">21,100 ⚡</div></div>
<div class="lb-row"><div class="lb-rank" style="color:var(--muted)">05</div><div class="lb-avatar" style="background:rgba(255,45,120,0.2)">🔥</div><div class="lb-info"><div class="lb-name">BlazedConfused99</div><div class="lb-tag">Elite · Blazed & Confused</div><div class="lb-bar"><div class="lb-bar-fill" style="width:35%;--fill-color:var(--p)"></div></div></div><div class="lb-pts">15,500 ⚡</div></div>
<div class="lb-row"><div class="lb-rank" style="color:var(--muted)">YOU</div><div class="lb-avatar" style="background:rgba(255,119,0,0.2)">😤</div><div class="lb-info"><div class="lb-name">You (GasHead)</div><div class="lb-tag">Rank #4,821 · Keep grinding</div><div class="lb-bar"><div class="lb-bar-fill" style="width:10%;--fill-color:var(--o)"></div></div></div><div class="lb-pts">4,200 ⚡</div></div>
</div>
<div class="eco-section"><div class="section-header">🏆 LEVEL ASCENSION TREE</div><div class="level-tree">
<div class="level-row"><div class="level-num" style="color:var(--g)">1</div><div class="level-bar"><div class="level-bar-fill" style="width:100%;--lv-color:var(--g);color:#000">SEEDLING</div></div><div class="level-unlock" style="color:var(--g)">✓ Basic strain tools</div></div>
<div class="level-row"><div class="level-num" style="color:var(--c)">10</div><div class="level-bar"><div class="level-bar-fill" style="width:100%;--lv-color:var(--c);color:#000">GAS HEAD</div></div><div class="level-unlock" style="color:var(--c)">✓ 3 lounge access</div></div>
<div class="level-row"><div class="level-num" style="color:var(--v)">20</div><div class="level-bar"><div class="level-bar-fill" style="width:100%;--lv-color:var(--v)">CLOUD RIDER</div></div><div class="level-unlock" style="color:var(--v)">✓ Marketplace access</div></div>
<div class="level-row"><div class="level-num" style="color:var(--p)">30</div><div class="level-bar"><div class="level-bar-fill" style="width:100%;--lv-color:var(--p)">VIBE CHEMIST</div></div><div class="level-unlock" style="color:var(--p)">✓ Host events</div></div>
<div class="level-row"><div class="level-num" style="color:var(--o)">40</div><div class="level-bar"><div class="level-bar-fill" style="width:100%;--lv-color:var(--o)">SMOKE DEITY</div></div><div class="level-unlock" style="color:var(--o)">✓ Create lounges</div></div>
<div class="level-row"><div class="level-num" style="color:var(--y)">50</div><div class="level-bar"><div class="level-bar-fill" style="width:85%;--lv-color:var(--y);color:#000">GAS LORD</div></div><div class="level-unlock" style="color:var(--y)">👑 The Chamber</div></div>
</div></div>
<div class="eco-section" style="grid-column:1/-1"><div class="section-header">🏅 BADGE COLLECTION <span style="color:var(--muted);font-weight:400">12 / 64 earned</span></div><div class="badge-grid">
<div class="badge earned"><span class="badge-icon">🧬</span><div class="badge-name">Strain Pioneer</div></div>
<div class="badge earned"><span class="badge-icon">🌿</span><div class="badge-name">First Grow</div></div>
<div class="badge earned"><span class="badge-icon">🔥</span><div class="badge-name">Viral Drop</div></div>
<div class="badge legendary"><span class="badge-icon">👑</span><div class="badge-name">Gas Lord</div></div>
<div class="badge"><span class="badge-icon">🚀</span><div class="badge-name">Cosmic Traveler</div><div class="badge-locked">🔒</div></div>
<div class="badge"><span class="badge-icon">💎</span><div class="badge-name">Diamond Hands</div><div class="badge-locked">🔒</div></div>
<div class="badge"><span class="badge-icon">🏆</span><div class="badge-name">Event Champion</div><div class="badge-locked">🔒</div></div>
<div class="badge"><span class="badge-icon">🌌</span><div class="badge-name">Universe Founder</div><div class="badge-locked">🔒</div></div>
</div></div></div>
<div class="divider"></div>
<div style="font-family:'Orbitron',monospace;font-size:0.65rem;color:var(--v);letter-spacing:3px;margin-bottom:1.5rem">🎮 MINI-GAMES</div>
<div>
<div class="minigame-card" style="--mg-color:var(--p)"><div class="mg-thumb">🧩</div><div class="mg-info"><div class="mg-name">PSYCHEDELIC PUZZLE MARATHON</div><div class="mg-desc">12 increasingly unhinged visual puzzles. Each wave harder, more surreal, more rewarding. Community event format.</div></div><div class="mg-reward"><span class="mg-pts">+500-5000 ⚡</span><div class="mg-type">EVENT · LIVE NOW</div></div></div>
<div class="minigame-card" style="--mg-color:var(--c)"><div class="mg-thumb">🔍</div><div class="mg-info"><div class="mg-name">AR STRAIN SCAVENGER HUNT</div><div class="mg-desc">Hidden virtual strains scattered across the universe. Find them before anyone else. First to 10 wins the drop.</div></div><div class="mg-reward"><span class="mg-pts">+250-2500 ⚡</span><div class="mg-type">DAILY · SOLO</div></div></div>
<div class="minigame-card" style="--mg-color:var(--g)"><div class="mg-thumb">🌱</div><div class="mg-info"><div class="mg-name">COLLABORATIVE GROW CHALLENGE</div><div class="mg-desc">Teams of 4 design a grow space together. Community votes on the best setup. Weekly format, legendary prizes.</div></div><div class="mg-reward"><span class="mg-pts">+1000-8000 ⚡</span><div class="mg-type">WEEKLY · TEAM</div></div></div>
<div class="minigame-card" style="--mg-color:var(--y)"><div class="mg-thumb">⚗️</div><div class="mg-info"><div class="mg-name">STRAIN ROULETTE</div><div class="mg-desc">Daily spin. Random parameters assigned. You have 10 minutes to engineer the best strain possible with what you got.</div></div><div class="mg-reward"><span class="mg-pts">+100-1000 ⚡</span><div class="mg-type">DAILY · SOLO</div></div></div>
</div>
<div class="divider"></div>
<div style="font-family:'Orbitron',monospace;font-size:0.65rem;color:var(--v);letter-spacing:3px;margin-bottom:1.5rem">💎 COLLECTIBLE MARKETPLACE</div>
<div class="marketplace">
<div class="market-card"><div class="market-thumb" style="background:linear-gradient(135deg,rgba(57,255,20,0.2),rgba(0,245,255,0.2))">🌿<div class="market-rarity" style="background:rgba(0,245,255,0.3);color:var(--c)">RARE</div></div><div class="market-name">Nebula OG Prime</div><div class="market-seller">by GasLordOmega</div><div class="market-price"><div class="market-cost">8,400 <span>GAS</span></div><button class="btn btn-secondary" style="font-size:0.55rem;padding:0.3rem 0.7rem" onclick="addGas(-100)">BID</button></div></div>
<div class="market-card"><div class="market-thumb" style="background:linear-gradient(135deg,rgba(255,230,0,0.2),rgba(255,119,0,0.2))">🔮<div class="market-rarity" style="background:rgba(255,230,0,0.3);color:var(--y)">LEGENDARY</div></div><div class="market-name">Alien Haze Genesis</div><div class="market-seller">by CosmicPurpleGod</div><div class="market-price"><div class="market-cost">12,000 <span>GAS</span></div><button class="btn btn-secondary" style="font-size:0.55rem;padding:0.3rem 0.7rem" onclick="addGas(-100)">BID</button></div></div>
<div class="market-card"><div class="market-thumb" style="background:linear-gradient(135deg,rgba(255,45,120,0.2),rgba(155,48,255,0.2))">🌌<div class="market-rarity" style="background:rgba(155,48,255,0.3);color:var(--v)">EPIC</div></div><div class="market-name">Moonbeam Skunk DX</div><div class="market-seller">by GalacticKush420</div><div class="market-price"><div class="market-cost">4,200 <span>GAS</span></div><button class="btn btn-secondary" style="font-size:0.55rem;padding:0.3rem 0.7rem" onclick="addGas(-100)">BID</button></div></div>
</div></div></div>
<div class="section" id="sec4"><div class="page">
<div class="page-title">// REVENUE BLUEPRINT //</div><div class="page-headline" style="color:var(--c)">MONETIZATION MAP</div><div class="page-sub">Six interlocked revenue streams designed to scale virally. The universe pays for itself — and then some.</div>
<div class="mono-grid">
<div class="mono-card" style="--mc-color:var(--y)"><span class="mono-icon">👑</span><div class="mono-title">GAS LORD PASS — SUBSCRIPTION</div><div class="mono-desc">Premium membership tier with tiered pricing for serious gas heads.</div><ul class="mono-items"><li>Apprentice Pass — $7.99/mo: Extra strain slots + basic lounge</li><li>Rider Pass — $19.99/mo: All lounges + 500 monthly gas credits</li><li>Lord Pass — $49.99/mo: Chamber access + exclusive drops + AI credits</li><li>Lifetime Gas Lord — $499 one-time: Permanent everything</li></ul></div>
<div class="mono-card" style="--mc-color:var(--p)"><span class="mono-icon">💎</span><div class="mono-title">COLLECTIBLE ECONOMY — MARKETPLACE FEES</div><div class="mono-desc">Platform takes 5% on all Gas Point trades and collectible transactions.</div><ul class="mono-items"><li>Strain NFT-style minting — 500 gas pts per mint (~$4.99 equiv)</li><li>5% platform fee on all marketplace transactions</li><li>Listing boost fees — premium placement in discovery feed</li><li>Exclusive drops / limited edition auctions — 15% platform cut</li></ul></div>
<div class="mono-card" style="--mc-color:var(--g)"><span class="mono-icon">🎟️</span><div class="mono-title">EVENTS & EXPERIENCES</div><div class="mono-desc">Ticketed events, branded competitions, and community championships.</div><ul class="mono-items"><li>Event entry passes — $2.99-$24.99 depending on prize pool</li><li>Sponsored event slots — brand partnerships for lounge events</li><li>Annual Gas Games championship — $49.99 ticket, massive prize pool</li><li>IRL festival tie-ins — digital + physical hybrid experiences</li></ul></div>
<div class="mono-card" style="--mc-color:var(--v)"><span class="mono-icon">🤖</span><div class="mono-title">AI CREDITS — STRAIN GENERATION</div><div class="mono-desc">Pay-per-use AI strain generation beyond free tier limits.</div><ul class="mono-items"><li>Free tier: 5 AI strain generations/month</li><li>AI Credit Pack: 50 gens for $4.99</li><li>Unlimited AI: included in Lord Pass</li><li>AI Grow Space Designer: $1.99 per premium build</li></ul></div>
<div class="mono-card" style="--mc-color:var(--o)"><span class="mono-icon">📦</span><div class="mono-title">BRAND PARTNERSHIPS & DROPS</div><div class="mono-desc">Cannabis brands, merch companies, and lifestyle brands pay to drop inside the universe.</div><ul class="mono-items"><li>Branded lounge sponsorship: $2,000-$10,000/month</li><li>Limited edition co-branded strain drops</li><li>Merch integration: physical goods tied to digital collectibles</li><li>Affiliate product placements in accessory marketplace</li></ul></div>
<div class="mono-card" style="--mc-color:var(--c)"><span class="mono-icon">🚀</span><div class="mono-title">VIRALITY FLYWHEEL</div><div class="mono-desc">Self-reinforcing growth loops that reduce paid acquisition costs to near-zero.</div><ul class="mono-items"><li>Strain share cards: auto-generated social graphics for every strain</li><li>Gas Point gifting: viral social loop — gift gas, earn gas</li><li>Lounge invite mechanics: host earns bonus pts per invited user</li><li>TikTok / Reel challenge hooks: #YouBeEngassed weekly challenges</li></ul></div>
</div>
<div style="background:var(--bg2);border:1px solid var(--border);padding:2rem;margin-bottom:2rem">
<div class="section-header" style="margin-bottom:1.5rem">📈 REVENUE PROJECTION (12-MONTH RAMP)</div>
<div class="revenue-bars">
<div class="rev-bar-wrap"><div class="rev-bar" style="height:8%;background:var(--g);position:relative"><div class="rev-val" style="color:var(--g)">$8K</div></div><div class="rev-label">M1</div></div>
<div class="rev-bar-wrap"><div class="rev-bar" style="height:12%;background:var(--g);position:relative"><div class="rev-val" style="color:var(--g)">$15K</div></div><div class="rev-label">M2</div></div>
<div class="rev-bar-wrap"><div class="rev-bar" style="height:18%;background:var(--g);position:relative"><div class="rev-val" style="color:var(--g)">$28K</div></div><div class="rev-label">M3</div></div>
<div class="rev-bar-wrap"><div class="rev-bar" style="height:25%;background:var(--c);position:relative"><div class="rev-val" style="color:var(--c)">$42K</div></div><div class="rev-label">M4</div></div>
<div class="rev-bar-wrap"><div class="rev-bar" style="height:35%;background:var(--c);position:relative"><div class="rev-val" style="color:var(--c)">$65K</div></div><div class="rev-label">M5</div></div>
<div class="rev-bar-wrap"><div class="rev-bar" style="height:45%;background:var(--v);position:relative"><div class="rev-val" style="color:var(--v)">$90K</div></div><div class="rev-label">M6</div></div>
<div class="rev-bar-wrap"><div class="rev-bar" style="height:55%;background:var(--v);position:relative"><div class="rev-val" style="color:var(--v)">$120K</div></div><div class="rev-label">M7</div></div>
<div class="rev-bar-wrap"><div class="rev-bar" style="height:62%;background:var(--p);position:relative"><div class="rev-val" style="color:var(--p)">$155K</div></div><div class="rev-label">M8</div></div>
<div class="rev-bar-wrap"><div class="rev-bar" style="height:70%;background:var(--p);position:relative"><div class="rev-val" style="color:var(--p)">$200K</div></div><div class="rev-label">M9</div></div>
<div class="rev-bar-wrap"><div class="rev-bar" style="height:78%;background:var(--o);position:relative"><div class="rev-val" style="color:var(--o)">$260K</div></div><div class="rev-label">M10</div></div>
<div class="rev-bar-wrap"><div class="rev-bar" style="height:88%;background:var(--o);position:relative"><div class="rev-val" style="color:var(--o)">$340K</div></div><div class="rev-label">M11</div></div>
<div class="rev-bar-wrap"><div class="rev-bar" style="height:100%;background:var(--y);position:relative"><div class="rev-val" style="color:var(--y)">$480K</div></div><div class="rev-label">M12</div></div>
</div>
<div style="font-size:0.75rem;color:var(--muted);text-align:center;margin-top:0.5rem">Conservative projection assuming 50K users, 8% paid conversion, and 2 brand partnership deals by M6</div>
</div>
<div style="font-family:'Orbitron',monospace;font-size:0.65rem;color:var(--v);letter-spacing:3px;margin-bottom:1rem">📊 VIRALITY TARGET METRICS</div>
<div class="virality-grid">
<div class="viral-cell"><span class="viral-num" style="color:var(--g)">K=1.4</span><div class="viral-label">Viral Coefficient Target</div></div>
<div class="viral-cell"><span class="viral-num" style="color:var(--p)">8%</span><div class="viral-label">Free-to-Paid Conversion</div></div>
<div class="viral-cell"><span class="viral-num" style="color:var(--c)">$24</span><div class="viral-label">ARPU Monthly</div></div>
<div class="viral-cell"><span class="viral-num" style="color:var(--y)">$0.80</span><div class="viral-label">Avg CAC (viral loop)</div></div>
</div></div></div>
<div id="notifContainer"></div>
<script>
let gasPoints=4200;let activeTab=0;let notifQueue=[];
const cosmos=document.getElementById('cosmos');
for(let i=0;i<80;i++){const s=document.createElement('div');s.className='star';s.style.cssText=`left:${Math.random()*100}%;top:${Math.random()*100}%;--d:${2+Math.random()*4}s;--o2:${0.3+Math.random()*0.7};animation-delay:${Math.random()*4}s`;cosmos.appendChild(s);}
function switchTab(i){document.querySelectorAll('.section').forEach((s,j)=>s.classList.toggle('active',j===i));document.querySelectorAll('.nav-tabs li').forEach((t,j)=>t.classList.toggle('active',j===i));activeTab=i;window.scrollTo(0,0);}
function updateGasDisplay(){const el=document.getElementById('gasDisplay');el.textContent=gasPoints.toLocaleString();el.style.animation='none';void el.offsetWidth;el.style.animation='countUp 0.4s ease-out';}
function addGas(pts){gasPoints+=pts;updateGasDisplay();showNotif(pts>0?'⚡ GAS EARNED':'💸 GAS SPENT',pts>0?`+${pts} Gas Points added to your stack!`:`${Math.abs(pts)} Gas Points spent.`);}
function showNotif(title,body){const n=document.createElement('div');n.className='notif';n.innerHTML=`<div class="notif-title">${title}</div><div class="notif-body">${body}</div>`;document.getElementById('notifContainer').appendChild(n);setTimeout(()=>n.remove(),3200);}
function updateSlider(key,val){const lbl=document.getElementById(key+'Label');if(lbl)lbl.textContent=val+'%';const dnaMap={thc:'Thc',cbd:'Cbd',euphoria:'Euph',cosmic:'Cos',rarity:'Rar'};const pMap={thc:'Tp',cbd:'Cp',euphoria:'Ep',cosmic:'Cop',rarity:'Rp'};const dna=document.getElementById('dna'+dnaMap[key]);if(dna)dna.style.width=val+'%';const pEl=document.getElementById('dna'+pMap[key]);if(pEl)pEl.textContent=val+'%';const displayMap={thc:'thcDisplay',cbd:'cbdDisplay'};if(displayMap[key])document.getElementById(displayMap[key]).textContent=val+'%';updateMarketValue();}
function updateMarketValue(){const thc=parseInt(document.getElementById('thcRange').value);const rar=parseInt(document.getElementById('rarityRange').value);const euph=parseInt(document.getElementById('euphoriaRange').value);const val=Math.round((thc*12)+(rar*18)+(euph*8)+Math.random()*200);const el=document.getElementById('strainValue');if(el)el.textContent=val.toLocaleString()+' ⚡';const rarEl=document.getElementById('rarityDisplay');if(rarEl)rarEl.textContent=rar>80?'LEGENDARY':rar>60?'RARE':rar>40?'EPIC':'COMMON';}
let c1='#39FF14',c1glow='rgba(57,255,20,0.4)',c2='#FF2D78';
function selectColor(num,hex,glow){if(num===1){c1=hex;c1glow=glow;document.getElementById('c1Label').textContent=hex;}else{c2=hex;document.getElementById('c2Label').textContent=hex;}document.querySelectorAll(`#colorPicker${num} .color-swatch`).forEach(s=>s.classList.remove('sel'));event.target.classList.add('sel');updateStrain();}
function updateStrain(){const name=document.getElementById('strainName').value||'Unknown Strain';document.getElementById('strainNameDisplay').textContent=name;const visual=document.getElementById('strainVisual');visual.style.background=`radial-gradient(ellipse at 50% 60%, ${c1glow}, transparent 70%), linear-gradient(135deg, ${c1}22 0%, ${c2}22 100%)`;updateMarketValue();}
function mintStrain(){if(gasPoints<500){showNotif('❌ NOT ENOUGH GAS','You need at least 500 Gas Points to mint.');return;}gasPoints-=500;updateGasDisplay();const name=document.getElementById('strainName').value||'Unknown Strain';showNotif('🧬 STRAIN MINTED!',`"${name}" has been minted as a collectible!`);setTimeout(()=>showNotif('💎 LISTED IN MARKET',`Your strain is now visible in the Marketplace!`),1500);}
function toggleTag(el,cls){el.classList.toggle(cls);}
function toggleType(el){el.closest('.tag-group').querySelectorAll('.tag').forEach(t=>t.classList.remove('sel-c'));el.classList.add('sel-c');}
updateStrain();
setInterval(()=>{if(Math.random()<0.15){const pts=[10,25,50][Math.floor(Math.random()*3)];gasPoints+=pts;updateGasDisplay();}},8000);
const universeMsgs=[['🔥 HOT DROP','Alien Mango Diesel just hit the marketplace'],['🏆 ACHIEVEMENT','You\'re in the top 15% of creators this week'],['🎮 EVENT ALERT','Strain Roulette resets in 10 minutes'],['💬 LOUNGE BUZZ','Forest Dimension is hosting a live drop in 30min']];
setInterval(()=>{if(Math.random()<0.3){const m=universeMsgs[Math.floor(Math.random()*universeMsgs.length)];showNotif(m[0],m[1]);}},25000);
</script>
</body>
</html>
