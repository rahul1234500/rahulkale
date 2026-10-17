<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Rahul Kale – Full Stack Developer</title>
<link href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:wght@400;600;800&display=swap" rel="stylesheet">
<style>
:root{--bg:#0d1230;--ink:#eaf0ff;--mute:#9aa6d6;--cy:#5ce1e6;--co:#ff7a59;--card:rgba(20,28,70,.55);--line:rgba(92,225,230,.28);
box-sizing:border-box;padding-top:env(safe-area-inset-top,0px);padding-bottom:env(safe-area-inset-bottom,0px)}
@media (prefers-color-scheme:dark){:root:not([data-theme="light"]){--bg:#0d1230;--ink:#eaf0ff}}
*{box-sizing:border-box}
html{scroll-padding-top:env(safe-area-inset-top,0px);scroll-behavior:smooth}
body{margin:0;background:var(--bg);color:var(--ink);font-family:'Bricolage Grotesque',system-ui,sans-serif;line-height:1.5;overflow-x:hidden}
/* ---- 3D background ---- */
#stage{position:fixed;inset:0;perspective:700px;overflow:hidden;z-index:0;
background:radial-gradient(ellipse at 50% 40%,#25307a 0%,#0d1230 60%,#070a1c 100%)}
#world{position:absolute;inset:0;transform-style:preserve-3d;transform:rotateX(calc(var(--my,0)*-6deg)) rotateY(calc(var(--mx,0)*8deg))}
.ring{position:absolute;left:50%;top:50%;width:70vmin;height:70vmin;margin:-35vmin 0 0 -35vmin;border:2px solid var(--line);border-radius:18%;
box-shadow:0 0 30px rgba(92,225,230,.12),inset 0 0 30px rgba(92,225,230,.08);will-change:transform,opacity}
.ring:nth-child(3n){border-color:rgba(255,122,89,.3);border-radius:50%}
.floor{position:absolute;left:-50%;width:200%;height:200%;top:55%;transform-origin:top;transform:rotateX(78deg);
background-image:linear-gradient(var(--line) 1px,transparent 1px),linear-gradient(90deg,var(--line) 1px,transparent 1px);
background-size:60px 60px;background-position:0 calc(var(--p,0)*1px);
-webkit-mask-image:linear-gradient(transparent,#000 30%);mask-image:linear-gradient(transparent,#000 30%)}
.orb{position:absolute;border-radius:50%;filter:blur(60px);opacity:.5}
.o1{width:40vmin;height:40vmin;background:#4b5cff;left:8%;top:12%}
.o2{width:32vmin;height:32vmin;background:var(--co);right:6%;bottom:14%;opacity:.28}
/* ---- content ---- */
main{position:relative;z-index:1}
section{min-height:100vh;display:flex;flex-direction:column;justify-content:center;padding:12vh 6vw;max-width:1100px;margin:0 auto}
h1{font-size:clamp(3rem,10vw,7.5rem);line-height:.95;margin:0 0 1rem;font-weight:800;letter-spacing:-.03em}
h2{font-size:clamp(2rem,5vw,3.2rem);margin:0 0 .5rem;font-weight:800;letter-spacing:-.02em}
p.lead{font-size:clamp(1.05rem,2.2vw,1.4rem);color:var(--mute);max-width:34em;margin:0 0 2rem}
.btns{display:flex;gap:.8rem;flex-wrap:wrap}
a.btn{color:var(--ink);text-decoration:none;padding:.8rem 1.3rem;border-radius:999px;border:1px solid var(--cy);font-weight:600;transition:background .2s,color .2s}
a.btn.fill{background:var(--cy);color:#06102a}
a.btn:hover,a.btn:focus-visible{background:var(--co);border-color:var(--co);color:#06102a;outline:none}
.grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(150px,1fr));gap:14px;perspective:900px;margin-top:1.5rem}
.tile{background:var(--card);border:1px solid var(--line);border-radius:14px;padding:1.1rem .9rem;text-align:center;font-weight:600;
backdrop-filter:blur(8px);transform-style:preserve-3d;transition:transform .15s ease-out,border-color .2s;cursor:default}
.tile small{display:block;color:var(--mute);font-weight:400;font-size:.78rem;margin-top:.2rem}
.tile:hover{border-color:var(--co)}
.tile span{display:block;transform:translateZ(30px)}
.links{display:grid;grid-template-columns:repeat(auto-fit,minmax(230px,1fr));gap:16px;margin-top:1.5rem;perspective:900px}
.links a{display:block;color:var(--ink);text-decoration:none;background:var(--card);border:1px solid var(--line);border-radius:16px;padding:1.4rem;
backdrop-filter:blur(8px);transform-style:preserve-3d;transition:transform .15s ease-out,border-color .2s}
.links a:hover,.links a:focus-visible{border-color:var(--co);outline:none}
.links b{display:block;font-size:1.3rem;transform:translateZ(30px)}
.links em{font-style:normal;color:var(--mute);font-size:.9rem;word-break:break-all}
footer{position:relative;z-index:1;text-align:center;color:var(--mute);padding:3rem 1rem}
@media (prefers-reduced-motion:reduce){html{scroll-behavior:auto}.ring{transition:none}}
</style>
</head>
<body>
<div id="stage" aria-hidden="true">
  <div class="orb o1"></div><div class="orb o2"></div>
  <div id="world"><div class="floor"></div></div>
</div>

<main>
  <section id="home">
    <h1>Rahul Kale</h1>
    <p class="lead">Java full stack developer from Pune. Spring Boot on the back end, React on the front, and real projects in between. Open to internships and full-time roles.</p>
    <div class="btns">
      <a class="btn fill" href="#stack">See my tech stack</a>
      <a class="btn" href="#links">Find me online</a>
    </div>
  </section>

  <section id="stack">
    <h2>Tech stack</h2>
    <p class="lead">Move your pointer over a tile to tilt it.</p>
    <div class="grid" id="grid"></div>
  </section>

  <section id="links">
    <h2>My links</h2>
    <p class="lead">Code, résumé and profiles in one place.</p>
    <div class="links">
      <a href="https://github.com/rahul1234500" target="_blank" rel="noopener"><b>GitHub</b><em>github.com/rahul1234500</em></a>
      <a href="https://www.linkedin.com/in/rahul-kale-06b6b7258" target="_blank" rel="noopener"><b>LinkedIn</b><em>in/rahul-kale-06b6b7258</em></a>
      <a href="https://rahul-kale-full-stack-resume.netlify.app/" target="_blank" rel="noopener"><b>Résumé site</b><em>rahul-kale-full-stack-resume.netlify.app</em></a>
      <a href="https://www.naukri.com/mnjuser/profile" target="_blank" rel="noopener"><b>Naukri</b><em>naukri.com/mnjuser/profile</em></a>
    </div>
  </section>
</main>
<footer>Built with HTML, CSS and a little JavaScript.</footer>

<script>
(function(){
  var stack=[["Java","Language"],["Python","Language"],["JavaScript","Language"],["TypeScript","Language"],["HTML","Markup"],["CSS","Styling"],["Bootstrap","UI"],["Tailwind CSS","UI"],["ReactJS","Front end"],["Angular 22","Front end"],["Spring","Back end"],["Spring Boot","Back end"],["Microsoft Azure","Cloud"],["Postman","API tools"],["REST API","API"],["Swagger","API docs"],["Redis","Cache"],["Kafka","Messaging"],["Docker","Containers"],["GitHub","Version control"]];
  var g=document.getElementById('grid');
  stack.forEach(function(s){var d=document.createElement('div');d.className='tile';d.innerHTML='<span>'+s[0]+'<small>'+s[1]+'</small></span>';g.appendChild(d)});

  var world=document.getElementById('world'),N=14,rings=[],GAP=420;
  for(var i=0;i<N;i++){var r=document.createElement('div');r.className='ring';world.appendChild(r);rings.push(r)}
  var reduce=matchMedia('(prefers-reduced-motion: reduce)').matches;
  var depth=N*GAP,p=0,target=0;
  function draw(){
    p+=(target-p)*(reduce?1:.08);
    document.documentElement.style.setProperty('--p',p*0.4);
    for(var i=0;i<N;i++){
      var z=((i*GAP + p*1.6) % depth) - depth + 300; /* loops: rings stream toward you */
      var o=Math.max(0,Math.min(1,1+z/(depth*0.7)));
      rings[i].style.transform='translateZ('+z+'px) rotateZ('+(i*9+p*0.03)+'deg)';
      rings[i].style.opacity=o;
    }
    requestAnimationFrame(draw);
  }
  addEventListener('scroll',function(){target=scrollY},{passive:true});
  target=scrollY;draw();

  addEventListener('pointermove',function(e){
    var rt=document.documentElement;
    rt.style.setProperty('--mx',(e.clientX/innerWidth-.5)*2);
    rt.style.setProperty('--my',(e.clientY/innerHeight-.5)*2);
  });

  function tilt(sel){
    document.querySelectorAll(sel).forEach(function(el){
      el.addEventListener('pointermove',function(e){
        var b=el.getBoundingClientRect(),x=(e.clientX-b.left)/b.width-.5,y=(e.clientY-b.top)/b.height-.5;
        el.style.transform='rotateY('+(x*22)+'deg) rotateX('+(-y*22)+'deg) scale(1.05)';
      });
      el.addEventListener('pointerleave',function(){el.style.transform=''});
    });
  }
  tilt('.tile');tilt('.links a');
})();
</script>
</body>
</html>
