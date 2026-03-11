<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Divyang Upreti · AI Dev · 3D GitHub Profile</title>
  <!-- Font Awesome for extra icons (optional but smooth) -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <!-- Google Fonts for modern look -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,600;14..32,800&display=swap" rel="stylesheet">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      background: #0a0c0f;
      font-family: 'Inter', sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 2rem 1rem;
      color: #f0e9ff;
      line-height: 1.6;
      overflow-x: hidden;
      perspective: 1200px;
    }

    /* 3D layered container with animated glow */
    .profile-card {
      max-width: 1100px;
      width: 100%;
      background: rgba(12, 10, 22, 0.75);
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
      border: 1px solid rgba(168, 85, 247, 0.3);
      box-shadow: 0 30px 50px -20px rgba(0,0,0,0.8), 0 0 0 1px rgba(168,85,247,0.2) inset, 0 0 40px rgba(168,85,247,0.2);
      border-radius: 48px;
      padding: 2.5rem 2rem;
      transform-style: preserve-3d;
      transform: rotateX(1deg) rotateY(0.5deg) translateZ(20px);
      transition: transform 0.3s ease, box-shadow 0.4s;
      animation: float3d 8s infinite alternate ease-in-out;
    }

    .profile-card:hover {
      transform: rotateX(0.5deg) rotateY(1.2deg) translateZ(30px);
      box-shadow: 0 40px 70px -10px #a855f7, 0 0 0 2px rgba(168,85,247,0.6) inset, 0 0 60px #c77dff;
    }

    @keyframes float3d {
      0% { transform: rotateX(0.8deg) rotateY(-0.3deg) translateZ(15px); }
      100% { transform: rotateX(1.3deg) rotateY(1.2deg) translateZ(30px); }
    }

    /* 3D text effect for main heading */
    h1 {
      font-size: 3.2rem;
      font-weight: 800;
      letter-spacing: -0.02em;
      text-shadow: 0 2px 0 #4a1d6d, 0 4px 0 #3b1557, 0 6px 10px rgba(0,0,0,0.5);
      color: white;
      transform: translateZ(25px) scale(1.02);
      animation: neonPulse 2.5s infinite alternate;
    }

    h1 span {
      color: #d8b4ff;
      text-shadow: 0 0 10px #c084fc, 0 0 20px #a855f7;
      display: inline-block;
      transform: translateZ(30px) scale(1.05);
    }

    @keyframes neonPulse {
      0% { text-shadow: 0 2px 0 #4a1d6d, 0 4px 0 #3b1557, 0 0 10px #a855f7, 0 0 20px #7e22ce; }
      100% { text-shadow: 0 2px 0 #6b21a5, 0 6px 0 #3b0764, 0 0 20px #d8b4ff, 0 0 40px #a855f7; }
    }

    h3 {
      font-size: 1.8rem;
      background: linear-gradient(90deg, #e9d5ff, #f0e9ff, #d8b4ff);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      background-clip: text;
      filter: drop-shadow(0 0 15px #c084fc);
      transform: translateZ(20px);
    }

    /* Typing SVG container */
    .typing-svg {
      transform: translateZ(30px);
      margin: 1rem 0 0.5rem;
      filter: drop-shadow(0 0 15px #a855f7);
    }

    /* Snake animation 3D lift */
    .snake-zone {
      transform: translateZ(20px) scale(0.98);
      border-radius: 30px;
      overflow: hidden;
      box-shadow: 0 25px 40px -10px black, 0 0 0 2px #a855f7 inset, 0 0 30px #a855f7;
      margin: 2.5rem 0;
      transition: transform 0.5s;
    }

    .snake-zone:hover {
      transform: translateZ(40px) scale(1.01);
    }

    /* Activity graph 3d + neon */
    .graph-3d {
      transform: translateZ(15px) rotateY(0.2deg);
      border-radius: 28px;
      overflow: hidden;
      box-shadow: 0 30px 40px -15px #000, 0 0 0 2px rgba(168,85,247,0.7), 0 0 50px #a855f7;
      margin: 2rem 0;
    }

    /* stats cards with 3D rotation */
    .stats-panel {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 2rem;
      margin: 2.5rem 0 1.5rem;
      transform-style: preserve-3d;
    }

    .stat-3d {
      background: rgba(20, 15, 35, 0.7);
      backdrop-filter: blur(8px);
      border: 1px solid #a855f7;
      border-radius: 32px;
      padding: 0.5rem 1.5rem;
      transform: translateZ(30px) rotateY(2deg);
      box-shadow: 0 15px 30px -10px #000, 0 0 15px #a855f7 inset;
      transition: 0.3s;
    }

    .stat-3d:hover {
      transform: translateZ(50px) rotateY(0deg) scale(1.03);
      box-shadow: 0 0 30px #d8b4ff;
    }

    /* 3D icon wall */
    .tech-wall {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 1rem 1.5rem;
      margin: 2rem 0;
      transform-style: preserve-3d;
      transform: translateZ(10px);
    }

    .tech-icon {
      display: inline-block;
      background: rgba(255,255,255,0.02);
      border-radius: 24px;
      padding: 8px 12px;
      backdrop-filter: blur(4px);
      border: 1px solid rgba(168,85,247,0.3);
      box-shadow: 0 10px 15px -8px black;
      transition: 0.2s;
      transform: translateZ(5px) rotateY(0.5deg);
    }

    .tech-icon:hover {
      transform: translateZ(25px) rotateY(0deg) scale(1.15);
      border-color: #c084fc;
      box-shadow: 0 0 30px #a855f7;
    }

    .tech-icon img {
      width: 40px;
      height: 40px;
      filter: drop-shadow(0 5px 5px #000);
      transition: 0.2s;
    }

    .tech-icon:hover img {
      filter: drop-shadow(0 0 12px #f0e9ff);
    }

    /* yaml block as 3d floating terminal */
    .yaml-block {
      background: #0f0b1ad9;
      backdrop-filter: blur(10px);
      border: 1px solid #a855f7;
      border-radius: 28px;
      padding: 1.8rem;
      font-family: 'Fira Code', monospace;
      white-space: pre-wrap;
      color: #d4c0ff;
      box-shadow: 0 30px 30px -15px #000, 0 0 30px #7e22ce inset;
      transform: translateZ(20px) rotateX(0.8deg);
      margin: 2rem 0;
      line-height: 1.5;
      font-size: 0.95rem;
    }

    .yaml-block:hover {
      transform: translateZ(35px) rotateX(0deg);
      box-shadow: 0 0 40px #a855f7;
    }

    /* glowing divider */
    .glow-divider {
      height: 4px;
      width: 80%;
      background: linear-gradient(90deg, transparent, #a855f7, #c084fc, #a855f7, transparent);
      box-shadow: 0 0 30px #a855f7, 0 0 10px #d8b4ff;
      border-radius: 4px;
      margin: 2.5rem auto;
      transform: translateZ(15px);
    }

    /* connect icons 3d */
    .connect-3d a {
      display: inline-block;
      margin: 0 0.8rem;
      transform: translateZ(15px) rotateY(1deg);
      filter: drop-shadow(0 10px 8px #000);
      transition: 0.2s;
    }

    .connect-3d a:hover {
      transform: translateZ(40px) rotateY(0deg) scale(1.2);
      filter: drop-shadow(0 0 25px #b978ff);
    }

    /* background moving particles effect */
    .particle-bg {
      position: fixed;
      top: 0; left: 0; width: 100%; height: 100%;
      pointer-events: none;
      z-index: -1;
      background: radial-gradient(circle at 30% 40%, #1e1029, #040208 70%);
      opacity: 0.9;
    }

    .particle-bg::before {
      content: '';
      position: absolute;
      width: 100%; height: 100%;
      background-image: radial-gradient(#a855f7 1px, transparent 1px);
      background-size: 50px 50px;
      animation: drift 40s infinite linear;
      opacity: 0.2;
    }

    @keyframes drift {
      0% { transform: translateY(0) translateX(0) rotate(0deg); }
      100% { transform: translateY(-80px) translateX(40px) rotate(5deg); }
    }

    /* badge / banner gif */
    .banner-gif {
      border-radius: 36px;
      box-shadow: 0 30px 30px -10px black, 0 0 0 2px #a855f7, 0 0 70px #a855f7;
      transform: translateZ(30px) scale(0.99);
      transition: 0.4s;
    }

    .banner-gif:hover {
      transform: translateZ(50px) scale(1.01);
      box-shadow: 0 0 60px #d8b4ff;
    }

    /* any small 3D touches */
    .quote {
      font-style: italic;
      transform: translateZ(10px);
      color: #c7b3ff;
    }
  </style>
</head>
<body>
  <div class="particle-bg"></div>

  <div class="profile-card">

    <!-- banner gif with 3d lift -->
    <div align="center" class="banner-gif">
      <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExZ3NjMmwxZnlkYjB2Y2NoanNpNjN4N2c0OW5qaHk2dTBxYm01dDFibiZlcD12MV9naWZzX3NlYXJjaCZjdD1n/66M6ZwJkTLYikvhrqZ/giphy.gif" width="100%" alt="Banner GIF" style="border-radius: 32px; display: block;">
    </div>

    <!-- Heading with 3D depth -->
    <h1 align="center">👋 𝐇𝐞𝐲 𝐭𝐡𝐞𝐫𝐞, 𝐈'𝐦 <span>𝐃𝐢𝐯𝐲𝐚𝐧𝐠 𝐔𝐩𝐫𝐞𝐭𝐢</span></h1>
    <h3 align="center">💻 𝐀𝐈 & 𝐅𝐮𝐥𝐥-𝐒𝐭𝐚𝐜𝐤 𝐒𝐨𝐟𝐭𝐰𝐚𝐫𝐞 𝐃𝐞𝐯𝐞𝐥𝐨𝐩𝐞𝐫 | 𝐈𝐧𝐧𝐨𝐯𝐚𝐭𝐨𝐫 | 𝐏𝐫𝐨𝐛𝐥𝐞𝐦 𝐒𝐨𝐥𝐯𝐞𝐫</h3>

    <!-- Typing SVG (same style + 3D) -->
    <div align="center" class="typing-svg">
      <img src="https://readme-typing-svg.herokuapp.com?size=27&duration=3000&color=A855F7&center=true&vCenter=true&width=900&lines=⚡+Divyang+Upreti's+Tech+Universe+⚡;AI+Developer+|+Full+Stack+Software+Engineer+|+Innovator;Hey+Welcome+to+my+GitHub+Dashboard!" />
    </div>

    <!-- About section as YAML block with 3D effect -->
    <div class="yaml-block">
      <b>name</b>: Divyang Upreti<br>
      <b>located_in</b>: India<br>
      <b>current_role</b>: AI & Full-Stack Software Developer<br><br>
      <b>education</b>:<br>
      &nbsp;&nbsp;- Bachelor's in Computer Science — SRM University (2023–2027)<br><br>
      <b>fields_of_interests</b>:<br>
      &nbsp;&nbsp;- Artificial Intelligence<br>
      &nbsp;&nbsp;- Full-Stack Development<br>
      &nbsp;&nbsp;- Cloud & DevOps<br>
      &nbsp;&nbsp;- Machine Learning<br>
      &nbsp;&nbsp;- Blockchain & Web3<br>
      &nbsp;&nbsp;- Real-Time Systems<br>
      &nbsp;&nbsp;- Open Source Contribution<br><br>
      <b>technical_background</b>:<br>
      &nbsp;&nbsp;- Built SHEild — AI-powered Women Safety System<br>
      &nbsp;&nbsp;- Created Spark AI — Voice Assistant with STT/TTS + OpenAI<br>
      &nbsp;&nbsp;- Developed TOMATO — MERN Food Ordering System<br>
      &nbsp;&nbsp;- Experience with React, Next.js, Spring Boot, FastAPI, TensorFlow<br><br>
      <b>currently_learning</b>: Advanced AI/ML, LLMs, MLOps, Docker, Next.js, Spring Boot, Blockchain<br>
      <b>goals_2025</b>: Build more AI/Web3 products, expert backend, open source<br>
      <b>hobbies</b>: Coding, AI/ML & Blockchain Tools, Music, UI/UX Research
    </div>

    <!-- 3D snake contributions -->
    <div align="center" class="snake-zone">
      <img src="https://raw.githubusercontent.com/Platane/snk/output/github-contribution-grid-snake-dark.svg" width="100%" style="display: block; filter: brightness(1.1);"/>
    </div>

    <!-- activity graph with 3d box -->
    <div align="center" class="graph-3d">
      <img src="https://github-readme-activity-graph.vercel.app/graph?username=DivyangUGitHub&theme=react-dark&bg_color=0d1117&color=a855f7&line=c084fc&point=fafafa&area=true&area_color=8b5cf6&hide_border=true" width="100%" style="border-radius: 20px; display: block;">
    </div>

    <!-- Stats with 3D effect + top langs & general stats -->
    <div class="stats-panel">
      <div class="stat-3d">
        <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=DivyangUGitHub&layout=compact&theme=radical&bg_color=10,3f0071,000000&hide_border=true&title_color=ff00ff&text_color=f5d0ff&card_width=400" height="200px">
      </div>
      <div class="stat-3d">
        <img src="https://github-readme-stats.vercel.app/api?username=DivyangUGitHub&show_icons=true&hide_border=true&bg_color=0d1117&title_color=bc8cff&text_color=e8d9ff&icon_color=c084fc" height="200px">
      </div>
    </div>

    <!-- Glowing divider -->
    <div class="glow-divider"></div>

    <!-- Tech stack 3D wall (original icons enhanced) -->
    <h2 align="center" style="transform:translateZ(18px); text-shadow:0 0 15px violet;">🚀 <b>𝐋𝐚𝐧𝐠𝐮𝐚𝐠𝐞𝐬, 𝐓𝐨𝐨𝐥𝐬 & 𝐓𝐞𝐜𝐡𝐧𝐨𝐥𝐨𝐠𝐢𝐞𝐬</b></h2>
    <div class="tech-wall">
      <!-- core languages -->
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/cplusplus/cplusplus-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/php/php-original.svg"/></span>
      <!-- web -->
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nextjs/nextjs-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vite/vite-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original-wordmark.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/express/express-original.svg"/></span>
      <!-- databases -->
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-original-wordmark.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original-wordmark.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/sqlite/sqlite-original.svg"/></span>
      <!-- devops/cloud -->
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/kubernetes/kubernetes-plain.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/azure/azure-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/googlecloud/googlecloud-original.svg"/></span>
      <!-- AI/ML -->
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/tensorflow/tensorflow-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/pytorch/pytorch-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/numpy/numpy-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/pandas/pandas-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/opencv/opencv-original.svg"/></span>
      <!-- testing / tools -->
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/junit/junit-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/jest/jest-plain.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/figma/figma-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linux/linux-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/fastapi/fastapi-original.svg"/></span>
      <span class="tech-icon"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/redux/redux-original.svg"/></span>
    </div>

    <!-- glow divider again -->
    <div class="glow-divider"></div>

    <!-- connect with me 3d -->
    <h2 align="center" style="transform:translateZ(20px);">📫 𝐂𝐨𝐧𝐧𝐞𝐜𝐭 𝐖𝐢𝐭𝐡 𝐌𝐞</h2>
    <p align="center" class="connect-3d">
      <a href="https://www.linkedin.com/in/divyangupreti2/" target="_blank">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linkedin/linkedin-original.svg" width="50px"/>
      </a>
      <a href="mailto:upretidivyang@gmail.com" target="_blank">
        <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/google/google-original.svg" width="52px"/>
      </a>
      <a href="https://github.com/DivyangUGitHub" target="_blank">
        <img src="https://raw.githubusercontent.com/danielcranney/readme-generator/main/public/icons/socials/github.svg" width="55px"/>
      </a>
    </p>

    <!-- subtle footer 3D quote -->
    <div align="center" class="quote" style="margin-top: 2rem; transform:translateZ(10px);">
      <span>✨ building the future, one commit at a time ✨</span>
    </div>

  </div> <!-- end profile-card -->

  <!-- extra micro interaction: tiny 3D stats extra (optional) -->
  <div style="position: fixed; bottom: 20px; right: 20px; background: rgba(0,0,0,0.5); border-radius: 60px; padding: 0.3rem 1rem; backdrop-filter: blur(10px); border: 1px solid purple; transform: rotateZ(2deg) translateZ(50px); box-shadow: 0 0 20px magenta;">
    ⚡ 3D profile live ⚡
  </div>
</body>
</html>


