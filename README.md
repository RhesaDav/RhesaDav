
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8"/>
<meta name="viewport" content="width=device-width, initial-scale=1.0"/>
<link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&family=Rajdhani:wght@400;500;600;700&display=swap" rel="stylesheet"/>
<style>
  *{margin:0;padding:0;box-sizing:border-box;}
  :root{
    --cyan:#00D4FF;
    --cyan2:#7DF9FF;
    --bg:#090E1A;
    --bg2:#0D1629;
    --bg3:#0A1220;
    --border:#1A2E4A;
    --text:#C9E0F5;
    --dim:#4A6A8A;
  }
  body{background:var(--bg);color:var(--text);font-family:'Rajdhani',sans-serif;min-height:100vh;overflow-x:hidden;}
  .mono{font-family:'Share Tech Mono',monospace;}

  /* GRID BG */
  .grid-bg{
    position:fixed;inset:0;
    background-image:
      linear-gradient(rgba(0,212,255,0.03) 1px, transparent 1px),
      linear-gradient(90deg, rgba(0,212,255,0.03) 1px, transparent 1px);
    background-size:40px 40px;
    pointer-events:none;z-index:0;
  }

  .container{position:relative;z-index:1;max-width:860px;margin:0 auto;padding:32px 24px;}

  /* HEADER */
  .header{text-align:center;padding:48px 0 40px;position:relative;}
  .header::before{
    content:'';position:absolute;top:0;left:50%;transform:translateX(-50%);
    width:300px;height:1px;background:linear-gradient(90deg,transparent,var(--cyan),transparent);
  }
  .avatar-ring{
    width:110px;height:110px;border-radius:50%;margin:0 auto 20px;
    background:linear-gradient(135deg,var(--cyan),#0047A0);
    padding:3px;position:relative;
    animation:spin-ring 8s linear infinite;
  }
  @keyframes spin-ring{
    0%{box-shadow:0 0 0 0 rgba(0,212,255,0.4),0 0 30px rgba(0,212,255,0.1);}
    50%{box-shadow:0 0 0 8px rgba(0,212,255,0),0 0 40px rgba(0,212,255,0.2);}
    100%{box-shadow:0 0 0 0 rgba(0,212,255,0.4),0 0 30px rgba(0,212,255,0.1);}
  }
  .avatar-inner{
    width:100%;height:100%;border-radius:50%;
    background:var(--bg2);
    display:flex;align-items:center;justify-content:center;
    font-size:36px;font-weight:700;color:var(--cyan);
    font-family:'Share Tech Mono',monospace;
    letter-spacing:-1px;
  }
  .name{font-size:36px;font-weight:700;color:#fff;letter-spacing:3px;text-transform:uppercase;}
  .name span{color:var(--cyan);}
  .role-bar{
    display:inline-flex;align-items:center;gap:8px;
    margin:10px auto 0;padding:6px 20px;
    border:1px solid var(--border);
    background:rgba(0,212,255,0.05);
    border-radius:2px;font-size:13px;
    color:var(--cyan);letter-spacing:2px;
    font-family:'Share Tech Mono',monospace;
  }
  .dot{width:6px;height:6px;border-radius:50%;background:var(--cyan);animation:blink 1.4s infinite;}
  @keyframes blink{0%,100%{opacity:1;}50%{opacity:0.2;}}

  /* SOCIAL */
  .socials{display:flex;justify-content:center;gap:10px;margin:24px 0 0;flex-wrap:wrap;}
  .social-btn{
    display:flex;align-items:center;gap:6px;
    padding:7px 16px;border:1px solid var(--border);
    background:rgba(0,212,255,0.04);
    color:var(--cyan);font-size:12px;letter-spacing:1px;
    text-decoration:none;border-radius:2px;
    font-family:'Share Tech Mono',monospace;
    transition:all 0.2s;cursor:pointer;
  }
  .social-btn:hover{background:rgba(0,212,255,0.12);border-color:var(--cyan);}
  .social-icon{width:14px;height:14px;fill:var(--cyan);}

  /* DIVIDER */
  .divider{
    display:flex;align-items:center;gap:12px;margin:36px 0 20px;
  }
  .divider-line{flex:1;height:1px;background:linear-gradient(90deg,var(--border),transparent);}
  .divider-line.r{background:linear-gradient(270deg,var(--border),transparent);}
  .divider-label{
    font-family:'Share Tech Mono',monospace;
    font-size:11px;color:var(--cyan);letter-spacing:3px;
  }

  /* ABOUT */
  .about-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px;}
  .about-card{
    background:var(--bg2);border:1px solid var(--border);
    border-radius:2px;padding:14px 18px;
    display:flex;gap:12px;align-items:flex-start;
    transition:border-color 0.2s;
  }
  .about-card:hover{border-color:rgba(0,212,255,0.4);}
  .about-icon{font-size:18px;line-height:1;margin-top:2px;}
  .about-title{font-size:11px;color:var(--dim);letter-spacing:2px;font-family:'Share Tech Mono',monospace;margin-bottom:3px;}
  .about-val{font-size:14px;color:var(--text);font-weight:500;}

  /* STACK */
  .stack-section{}
  .stack-group{margin-bottom:20px;}
  .stack-group-label{
    font-size:10px;letter-spacing:3px;color:var(--dim);
    font-family:'Share Tech Mono',monospace;margin-bottom:10px;
  }
  .badges{display:flex;flex-wrap:wrap;gap:8px;}
  .badge{
    display:flex;align-items:center;gap:6px;
    padding:6px 14px;
    background:var(--bg2);
    border:1px solid var(--border);
    border-radius:2px;
    font-size:12px;color:var(--text);
    letter-spacing:0.5px;font-weight:500;
    transition:all 0.2s;cursor:default;
  }
  .badge:hover{border-color:var(--cyan);color:var(--cyan);background:rgba(0,212,255,0.06);}
  .badge-dot{width:5px;height:5px;border-radius:50%;background:var(--cyan);flex-shrink:0;}

  /* STATS */
  .stats-grid{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-bottom:12px;}
  .stat-card{
    background:var(--bg2);border:1px solid var(--border);
    border-radius:2px;overflow:hidden;
  }
  .stat-card img{width:100%;display:block;}

  .streak-card{
    background:var(--bg2);border:1px solid var(--border);
    border-radius:2px;overflow:hidden;text-align:center;
  }
  .streak-card img{max-width:100%;display:block;margin:0 auto;}

  /* TROPHY */
  .trophy-card{
    background:var(--bg2);border:1px solid var(--border);
    border-radius:2px;overflow:hidden;text-align:center;padding:12px;
  }
  .trophy-card img{max-width:100%;}

  /* QUOTE */
  .quote-block{
    border-left:2px solid var(--cyan);
    padding:16px 20px;
    background:rgba(0,212,255,0.04);
    margin:8px 0;
    border-radius:0 2px 2px 0;
  }
  .quote-text{
    font-family:'Share Tech Mono',monospace;
    font-size:13px;color:var(--text);
    line-height:1.7;
  }
  .quote-author{font-size:11px;color:var(--dim);margin-top:8px;letter-spacing:1px;}

  /* CTA */
  .cta{
    text-align:center;padding:32px;
    background:linear-gradient(135deg,rgba(0,212,255,0.05),rgba(0,71,160,0.05));
    border:1px solid var(--border);
    border-radius:2px;
    position:relative;overflow:hidden;
  }
  .cta::before{
    content:'';position:absolute;top:0;left:0;right:0;height:1px;
    background:linear-gradient(90deg,transparent,var(--cyan),transparent);
  }
  .cta-title{font-size:22px;font-weight:700;color:#fff;letter-spacing:2px;margin-bottom:6px;}
  .cta-sub{font-size:13px;color:var(--dim);font-family:'Share Tech Mono',monospace;margin-bottom:20px;}
  .cta-btn{
    display:inline-flex;align-items:center;gap:8px;
    padding:10px 28px;
    background:var(--cyan);color:#090E1A;
    font-weight:700;font-size:13px;letter-spacing:2px;
    border:none;border-radius:2px;cursor:pointer;
    font-family:'Rajdhani',sans-serif;
    text-transform:uppercase;transition:all 0.2s;
    text-decoration:none;
  }
  .cta-btn:hover{background:var(--cyan2);transform:translateY(-1px);}

  /* VIEWS COUNTER */
  .footer{text-align:center;margin-top:32px;padding-top:24px;border-top:1px solid var(--border);}
  .footer-label{font-family:'Share Tech Mono',monospace;font-size:11px;color:var(--dim);letter-spacing:2px;}
  .view-count{
    display:inline-block;
    margin-top:8px;
    font-family:'Share Tech Mono',monospace;
    font-size:20px;color:var(--cyan);letter-spacing:4px;
  }

  @media(max-width:560px){
    .about-grid{grid-template-columns:1fr;}
    .stats-grid{grid-template-columns:1fr;}
    .name{font-size:26px;}
  }
</style>
</head>
<body>
<div class="grid-bg"></div>
<div class="container">

  <!-- HEADER -->
  <div class="header">
    <div class="avatar-ring">
      <div class="avatar-inner">RD</div>
    </div>
    <div class="name">RHESA <span>DAVINANTO</span></div>
    <div class="role-bar mono">
      <span class="dot"></span>
      FULLSTACK DEVELOPER · REACT SPECIALIST
      <span class="dot"></span>
    </div>
    <div class="socials">
      <a class="social-btn" href="https://twitter.com/davinanto">
        <svg class="social-icon" viewBox="0 0 24 24"><path d="M23 3a10.9 10.9 0 01-3.14 1.53 4.48 4.48 0 00-7.86 3v1A10.66 10.66 0 013 4s-4 9 5 13a11.64 11.64 0 01-7 2c9 5 20 0 20-11.5a4.5 4.5 0 00-.08-.83A7.72 7.72 0 0023 3z"/></svg>
        Twitter
      </a>
      <a class="social-btn" href="https://linkedin.com/in/rhesa-davinanto">
        <svg class="social-icon" viewBox="0 0 24 24"><path d="M16 8a6 6 0 016 6v7h-4v-7a2 2 0 00-2-2 2 2 0 00-2 2v7h-4v-7a6 6 0 016-6zM2 9h4v12H2z"/><circle cx="4" cy="4" r="2"/></svg>
        LinkedIn
      </a>
      <a class="social-btn" href="https://instagram.com/rhesadavinanto">
        <svg class="social-icon" viewBox="0 0 24 24"><rect x="2" y="2" width="20" height="20" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1112.63 8 4 4 0 0116 11.37z" fill="var(--bg2)"/><line x1="17.5" y1="6.5" x2="17.51" y2="6.5" stroke="var(--bg2)" stroke-width="1.5"/></svg>
        Instagram
      </a>
      <a class="social-btn" href="mailto:rhesadav48@gmail.com">
        <svg class="social-icon" viewBox="0 0 24 24"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6" stroke="var(--bg2)" stroke-width="1.5" fill="none"/></svg>
        Email
      </a>
    </div>
  </div>

  <!-- ABOUT -->
  <div class="divider">
    <div class="divider-line"></div>
    <span class="divider-label mono">ABOUT.SYS</span>
    <div class="divider-line r"></div>
  </div>
  <div class="about-grid">
    <div class="about-card">
      <div class="about-icon">🌏</div>
      <div><div class="about-title mono">LOCATION</div><div class="about-val">Indonesia</div></div>
    </div>
    <div class="about-card">
      <div class="about-icon">⚡</div>
      <div><div class="about-title mono">STATUS</div><div class="about-val">Open to Collaborations</div></div>
    </div>
    <div class="about-card">
      <div class="about-icon">🎯</div>
      <div><div class="about-title mono">LEARNING</div><div class="about-val">React · Angular · MERN Stack</div></div>
    </div>
    <div class="about-card">
      <div class="about-icon">💬</div>
      <div><div class="about-title mono">ASK ME ABOUT</div><div class="about-val">React · Angular · Architecture</div></div>
    </div>
    <div class="about-card">
      <div class="about-icon">🌱</div>
      <div><div class="about-title mono">GROWING IN</div><div class="about-val">Performance Optimization · Micro-frontend</div></div>
    </div>
    <div class="about-card">
      <div class="about-icon">☕</div>
      <div><div class="about-title mono">FUN FACT</div><div class="about-val">Turns coffee into clean code daily</div></div>
    </div>
  </div>

  <!-- TECH STACK -->
  <div class="divider">
    <div class="divider-line"></div>
    <span class="divider-label mono">TECH.STACK</span>
    <div class="divider-line r"></div>
  </div>
  <div class="stack-section">
    <div class="stack-group">
      <div class="stack-group-label mono">— FRONTEND</div>
      <div class="badges">
        <div class="badge"><span class="badge-dot"></span>React</div>
        <div class="badge"><span class="badge-dot"></span>Angular</div>
        <div class="badge"><span class="badge-dot"></span>Next.js</div>
        <div class="badge"><span class="badge-dot"></span>TypeScript</div>
        <div class="badge"><span class="badge-dot"></span>JavaScript</div>
        <div class="badge"><span class="badge-dot"></span>TailwindCSS</div>
        <div class="badge"><span class="badge-dot"></span>Redux</div>
        <div class="badge"><span class="badge-dot"></span>HTML5 / CSS3</div>
      </div>
    </div>
    <div class="stack-group">
      <div class="stack-group-label mono">— BACKEND & DATABASE</div>
      <div class="badges">
        <div class="badge"><span class="badge-dot"></span>Node.js</div>
        <div class="badge"><span class="badge-dot"></span>Express.js</div>
        <div class="badge"><span class="badge-dot"></span>MongoDB</div>
        <div class="badge"><span class="badge-dot"></span>MySQL</div>
        <div class="badge"><span class="badge-dot"></span>Firebase</div>
      </div>
    </div>
    <div class="stack-group">
      <div class="stack-group-label mono">— MOBILE & DEVOPS</div>
      <div class="badges">
        <div class="badge"><span class="badge-dot"></span>React Native</div>
        <div class="badge"><span class="badge-dot"></span>Ionic</div>
        <div class="badge"><span class="badge-dot"></span>Android</div>
        <div class="badge"><span class="badge-dot"></span>Git</div>
        <div class="badge"><span class="badge-dot"></span>Google Cloud</div>
        <div class="badge"><span class="badge-dot"></span>Heroku</div>
      </div>
    </div>
  </div>

  <!-- GITHUB STATS -->
  <div class="divider">
    <div class="divider-line"></div>
    <span class="divider-label mono">GITHUB.STATS</span>
    <div class="divider-line r"></div>
  </div>
  <div class="stats-grid">
    <div class="stat-card">
      <img src="https://github-readme-stats.vercel.app/api?username=rhesadav&show_icons=true&theme=github_dark&include_all_commits=true&count_private=true&border_color=1A2E4A&title_color=00D4FF&icon_color=00D4FF&ring_color=00D4FF&bg_color=0D1629&text_color=C9E0F5&hide_border=false" alt="GitHub Stats"/>
    </div>
    <div class="stat-card">
      <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=rhesadav&layout=compact&langs_count=8&theme=github_dark&border_color=1A2E4A&title_color=00D4FF&bg_color=0D1629&text_color=C9E0F5" alt="Top Languages"/>
    </div>
  </div>
  <div class="streak-card">
    <img src="https://github-readme-streak-stats.herokuapp.com/?user=rhesadav&theme=github-dark-blue&border=1A2E4A&ring=00D4FF&fire=7DF9FF&currStreakLabel=00D4FF&sideLabels=00D4FF&background=0D1629" alt="Streak Stats"/>
  </div>

  <!-- TROPHIES -->
  <div class="divider">
    <div class="divider-line"></div>
    <span class="divider-label mono">ACHIEVEMENTS</span>
    <div class="divider-line r"></div>
  </div>
  <div class="trophy-card">
    <img src="https://github-profile-trophy.vercel.app/?username=rhesadav&theme=darkhub&no-frame=true&margin-w=6&row=1&column=7" alt="Trophies"/>
  </div>

  <!-- QUOTE -->
  <div class="divider">
    <div class="divider-line"></div>
    <span class="divider-label mono">PHILOSOPHY</span>
    <div class="divider-line r"></div>
  </div>
  <div class="quote-block">
    <div class="quote-text mono">"First, solve the problem. Then, write the code."</div>
    <div class="quote-author mono">— John Johnson</div>
  </div>

  <!-- CTA -->
  <div class="divider">
    <div class="divider-line"></div>
    <span class="divider-label mono">CONNECT</span>
    <div class="divider-line r"></div>
  </div>
  <div class="cta">
    <div class="cta-title">Let's Build Together</div>
    <div class="cta-sub mono">Open for freelance · collaborations · exciting projects</div>
    <a class="cta-btn" href="mailto:rhesadav48@gmail.com">
      <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/><polyline points="22,6 12,13 2,6"/></svg>
      SEND MESSAGE
    </a>
  </div>

  <!-- FOOTER -->
  <div class="footer">
    <div class="footer-label mono">SYSTEM UPTIME · PROFILE VIEWS</div>
    <img style="margin-top:10px;" src="https://komarev.com/ghpvc/?username=rhesadav&color=00D4FF&style=for-the-badge&label=VISITORS" alt="Views"/>
  </div>

</div>
</body>
</html>
