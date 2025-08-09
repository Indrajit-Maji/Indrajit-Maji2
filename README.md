<!doctype html>

<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Indrajit Maji — Portfolio</title>
  <style>
    /* --- Page reset --- */
    *{box-sizing:border-box;margin:0;padding:0}
    html,body{height:100%}
    body{
      font-family:Inter,ui-sans-serif,system-ui,-apple-system,Segoe UI,Roboto,Helvetica,Arial;
      color:#eae6e1;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      background: radial-gradient(1200px 600px at 10% 10%, rgba(255,215,0,0.06), transparent 10%),
                  radial-gradient(1000px 400px at 90% 90%, rgba(255,215,0,0.05), transparent 10%),
                  linear-gradient(135deg, #0b0710 0%, #20161a 35%, #2c1f12 60%, #0b0710 100%);
      min-height:100%;
      display:flex;align-items:center;justify-content:center;padding:40px;
      background-attachment: fixed;
    }/* Golden neon gradient card */
.card{
  width:100%;max-width:980px;background:linear-gradient(180deg, rgba(255,250,240,0.03), rgba(255,235,200,0.02));
  border-radius:18px;padding:36px;border:1px solid rgba(255,215,0,0.12);
  box-shadow: 0 10px 40px rgba(0,0,0,0.6), 0 0 30px rgba(255,215,0,0.03) inset;
  position:relative;overflow:hidden;
}

/* subtle animated gold sheen */
.card:before{
  content:'';position:absolute;left:-40%;top:-50%;width:200%;height:200%;
  background:linear-gradient(90deg, rgba(255,255,255,0.02), rgba(255,215,0,0.09), rgba(255,255,255,0.02));
  transform:rotate(25deg);animation: sheen 8s linear infinite;
  pointer-events:none;
}
@keyframes sheen{0%{transform:translateX(-60%) rotate(25deg)}50%{transform:translateX(60%) rotate(25deg)}100%{transform:translateX(-60%) rotate(25deg)}}

.top{
  display:flex;gap:22px;align-items:center;justify-content:center;margin-bottom:22px;flex-wrap:wrap;
}

.avatar{
  width:160px;height:160px;border-radius:50%;overflow:hidden;border:4px solid rgba(255,215,0,0.18);
  display:flex;align-items:center;justify-content:center;box-shadow:0 6px 30px rgba(0,0,0,0.6), 0 0 18px rgba(255,215,0,0.14);
  background:linear-gradient(180deg,#111,#1a1410);
}
.avatar img{width:100%;height:100%;object-fit:cover;display:block}

.intro{
  text-align:center;flex:1;min-width:300px
}

.hello{
  display:block;font-weight:700;font-size:20px;color:#ffd66b;letter-spacing:0.6px;
  margin-bottom:6px;text-shadow:0 2px 12px rgba(255,200,70,0.08);
  opacity:0;animation:fadeUp .6s ease forwards .2s;
}

@keyframes fadeUp{from{opacity:0;transform:translateY(8px)}to{opacity:1;transform:none}}

.name{
  font-size:36px;font-weight:800;background:linear-gradient(90deg,#ffe29f,#ffd066 40%,#ffd66b 60%);
  -webkit-background-clip:text;background-clip:text;color:transparent;letter-spacing:1px;
  margin-bottom:8px;text-shadow:0 10px 30px rgba(255,190,30,0.06);
}

/* Typing effect */
.typed{
  font-size:16px;color:#e9e6e1;opacity:0.95;height:22px;overflow:hidden;white-space:nowrap;border-right:3px solid rgba(255,215,0,0.9);
  width:0;animation: typing 3.6s steps(36,end) forwards, blink 1s step-end infinite alternate 3.8s;
}
@keyframes typing{from{width:0}to{width:100%}}
@keyframes blink{50%{border-color:transparent}100%{border-color:rgba(255,215,0,0.9)}}

.cta{display:flex;gap:14px;align-items:center;justify-content:center;margin-top:14px}
.btn{
  display:inline-flex;align-items:center;gap:10px;padding:10px 16px;border-radius:10px;border:1px solid rgba(255,215,0,0.12);
  background:linear-gradient(180deg, rgba(255,215,0,0.04), rgba(255,215,0,0.02));color:#fff;text-decoration:none;font-weight:600;
  box-shadow:0 6px 18px rgba(255,165,0,0.04);transition:transform .15s ease,box-shadow .15s ease;backdrop-filter: blur(4px);
}
.btn:hover{transform:translateY(-4px);box-shadow:0 18px 50px rgba(255,200,60,0.08)}

/* about */
.about{margin-top:18px;padding:18px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,215,0,0.01));
  border:1px solid rgba(255,215,0,0.06);box-shadow:0 10px 40px rgba(0,0,0,0.45) inset;}
.about p{line-height:1.45;color:#efeae2;font-size:15px}

/* horizontal skills */
.skills{display:flex;gap:12px;align-items:center;justify-content:flex-start;margin-top:18px;overflow:auto;padding-bottom:8px}
.skill{display:flex;align-items:center;gap:8px;padding:10px 12px;border-radius:999px;border:1px solid rgba(255,215,0,0.06);background:rgba(255,255,255,0.01)}
.skill img{width:28px;height:28px;object-fit:contain;filter:drop-shadow(0 4px 12px rgba(0,0,0,0.6))}

/* generative tools grid */
.gen-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:14px;margin-top:18px}
.gen-card{padding:14px;border-radius:12px;background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,215,0,0.01));border:1px solid rgba(255,215,0,0.04);display:flex;gap:12px;align-items:center}
.gen-card img{width:46px;height:46px}
.gen-card h4{font-size:15px;margin-bottom:4px}
.gen-card p{font-size:13px;color:#efe6dd}

/* courses */
.courses{display:flex;gap:12px;flex-wrap:wrap;margin-top:18px}
.course{flex:1 1 200px;padding:12px;border-radius:10px;border:1px solid rgba(255,215,0,0.04);background:linear-gradient(180deg, rgba(255,255,255,0.01), rgba(255,215,0,0.01));display:flex;gap:12px;align-items:center}
.course img{width:56px;height:56px}

footer{margin-top:18px;text-align:center;color:#d9d3c8;font-size:13px}

/* responsive */
@media (max-width:720px){.name{font-size:28px}.avatar{width:120px;height:120px}}

/* small animation for icons row */
.skills{animation: floaty 6s ease-in-out infinite}
@keyframes floaty{0%{transform:translateY(0)}50%{transform:translateY(-6px)}100%{transform:translateY(0)}}

/* highlight glow on hover */
.gen-card:hover{transform:translateY(-6px);transition:all .25s ease;box-shadow:0 20px 60px rgba(255,200,70,0.06)}

  </style>
</head>
<body>
  <div class="card">
    <div class="top">
      <div class="avatar">
        <!-- generated initials avatar -->
        <img src="https://ui-avatars.com/api/?name=Indrajit+Maji&size=512&rounded=true&background=111111&color=FFD700" alt="Indrajit Maji">
      </div><div class="intro">
    <div class="hello">HIII, Myself</div>
    <div class="name">INDRAJIT MAJI</div>
    <div class="typed" id="typed">BCom (Hons.) • Kirori Mal College, University of Delhi — Learning Power BI · Generative AI · Python</div>

    <div class="cta">
      <a class="btn" href="https://www.linkedin.com/in/indrajit-maji-954309221?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app" target="_blank" rel="noopener noreferrer">
        <img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/linkedin.svg" alt="LinkedIn" style="width:18px;height:18px;filter:invert(1)"> LinkedIn
      </a>
      <a class="btn" href="mailto:indrajitmajilive@gmail.com">
        <img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/gmail.svg" alt="Email" style="width:18px;height:18px;filter:invert(1)"> Email
      </a>
    </div>
  </div>
</div>

<div class="about">
  <p id="aboutText">I am a curious and driven BCom (Hons.) student at Kirori Mal College (University of Delhi) with a growth mindset. I build data-driven stories with Power BI, explore creative possibilities with generative AI (video, audio, image, and web), and experiment with Python to automate and analyze. I love blending business thinking with technology to solve practical problems — and I learn fast.</p>
</div>

<div class="skills" aria-hidden="false" style="margin-top:18px;">
  <!-- Use simple-icons SVGs hosted on jsdelivr for crisp icons -->
  <div class="skill"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/microsoftpowerbi.svg" alt="Power BI"> <span>Power BI</span></div>
  <div class="skill"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/wordpress.svg" alt="WordPress"> <span>WordPress</span></div>
  <div class="skill"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/openai.svg" alt="ChatGPT / OpenAI"> <span>ChatGPT</span></div>
  <div class="skill"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/claude.svg" alt="Claude (Anthropic)"> <span>Claude</span></div>
  <div class="skill"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/python.svg" alt="Python"> <span>Python</span></div>
  <div class="skill"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/figma.svg" alt="Figma"> <span>Figma</span></div>
</div>

<h3 style="margin-top:18px;color:#ffd66b">Generative AI Tools</h3>
<div class="gen-grid">
  <!-- each card: icon, title, short description -->
  <div class="gen-card"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/hailuoai.svg" onerror="this.src='https://img.icons8.com/ios-filled/50/ffd66b/video.png'" alt="Hailuo AI"><div><h4>Hailuo AI — Video</h4><p>Create dynamic AI-powered video ads and promos.</p></div></div>

  <div class="gen-card"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/klingai.svg" onerror="this.src='https://img.icons8.com/ios-filled/50/ffd66b/microphone.png'" alt="KlingAI"><div><h4>KlingAI</h4><p>Audio & voice generation for ads and narration.</p></div></div>

  <div class="gen-card"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/suno.svg" onerror="this.src='https://img.icons8.com/ios-filled/50/ffd66b/musical-notes.png'" alt="Suno"><div><h4>Suno — Music</h4><p>Compose original songs and background scores.</p></div></div>

  <div class="gen-card"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/huggingface.svg" alt="Hugging Face"><div><h4>Hugging Face</h4><p>Models, fine-tuning, and research-friendly tooling.</p></div></div>

  <div class="gen-card"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/openai.svg" alt="ChatGPT / OpenAI"><div><h4>ChatGPT</h4><p>Idea generation, scripts, and content drafts.</p></div></div>

  <div class="gen-card"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/google.svg" alt="Gemini"><div><h4>Gemini</h4><p>Multi-modal creative and semantic tools.</p></div></div>

  <div class="gen-card"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/anthropic.svg" alt="Claude"><div><h4>Claude</h4><p>Long-form reasoning and ideation support.</p></div></div>

  <div class="gen-card"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/sora.svg" onerror="this.src='https://img.icons8.com/ios-filled/50/ffd66b/video.png'" alt="Sora"><div><h4>Sora — Video</h4><p>Fast video generation and editing using AI templates.</p></div></div>

  <div class="gen-card"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/leonardo.svg" onerror="this.src='https://img.icons8.com/ios-filled/50/ffd66b/image.png'" alt="Leonardo AI"><div><h4>Leonardo AI — Image</h4><p>High-quality AI image generation and concept art.</p></div></div>

  <div class="gen-card"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/notebook.svg" onerror="this.src='https://img.icons8.com/ios-filled/50/ffd66b/notebook.png'" alt="Notebook LM"><div><h4>Notebook LM</h4><p>Organize knowledge, prompts, and research notes.</p></div></div>

  <!-- Additional industry tools -->
  <div class="gen-card"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/framer.svg" alt="Framer"><div><h4>Framer AI</h4><p>Design-led website prototyping with AI features.</p></div></div>

  <div class="gen-card"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/durable.svg" onerror="this.src='https://img.icons8.com/ios-filled/50/ffd66b/domain.png'" alt="Durable"><div><h4>Durable</h4><p>AI-first website builder for fast landing pages.</p></div></div>

  <div class="gen-card"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/wix.svg" alt="Wix"><div><h4>Wix ADI</h4><p>Guided AI website creation for business pages.</p></div></div>

</div>

<h3 style="margin-top:18px;color:#ffd66b">Courses & Certifications</h3>
<div class="courses">
  <div class="course"><img src="https://img.icons8.com/ios-filled/100/ffd66b/artificial-intelligence.png" alt="AI Engineering"> <div><strong>AI Engineering</strong><div style="font-size:13px;color:#efe6dd">Practical AI systems & tools</div></div></div>
  <div class="course"><img src="https://img.icons8.com/ios-filled/100/ffd66b/certificate.png" alt="NISM"> <div><strong>NISM Investor Certification</strong><div style="font-size:13px;color:#efe6dd">Regulatory & investment basics</div></div></div>
  <div class="course"><img src="https://img.icons8.com/ios-filled/100/ffd66b/power-bi.png" alt="Power BI"> <div><strong>Power BI</strong><div style="font-size:13px;color:#efe6dd">Dashboards, reports & DAX</div></div></div>
  <div class="course"><img src="https://img.icons8.com/ios-filled/100/ffd66b/robot-2.png" alt="Generative AI"> <div><strong>Generative AI</strong><div style="font-size:13px;color:#efe6dd">Creative AI for multimedia</div></div></div>
</div>

<footer>
  Built with passion • Always learning • Available for internships & collaborations
</footer>

  </div>  <script>
    // Typing effect: reveal text gradually (already emulated with CSS width animation), add JS fallback for better effect
    (function(){
      const el = document.getElementById('typed');
      const text = el.textContent;
      el.textContent = '';
      let i = 0;
      const speed = 18;
      function step(){
        if(i < text.length){
          el.textContent += text.charAt(i);
          i++;
          setTimeout(step, speed);
        } else {
          // done
        }
      }
      setTimeout(step, 600);

      // subtle small animation for about text (fade in word-by-word-ish)
      const about = document.getElementById('aboutText');
      about.style.opacity = 0;about.style.transform = 'translateY(10px)';
      setTimeout(()=>{about.style.transition = 'all 650ms ease';about.style.opacity=1;about.style.transform='none'},1200);
    })();
  </script></body>
</html>
