<svg width="800" height="180" viewBox="0 0 800 180" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <style>
      .name { font-family: 'Segoe UI', sans-serif; font-size: 28px; font-weight: 700; fill: #1a1a2e; }
      .greeting { font-family: 'Segoe UI', sans-serif; font-size: 28px; font-weight: 400; fill: #555; }
      .tw { font-family: 'Courier New', monospace; font-size: 16px; fill: #4f46e5; }
      .tagline { font-family: 'Segoe UI', sans-serif; font-size: 13px; fill: #888; }
      .badge-text { font-family: 'Segoe UI', sans-serif; font-size: 11px; fill: #fff; font-weight: 600; }
      .divider { stroke: #e8e8f0; stroke-width: 1; }
      .cursor { fill: #4f46e5; animation: blink 0.8s step-end infinite; }
      @keyframes blink { 0%,100%{opacity:1;} 50%{opacity:0;} }

      .tw1 { font-family: 'Courier New', monospace; font-size: 16px; fill: #4f46e5; animation: tw1 30s linear infinite; }
      .tw2 { font-family: 'Courier New', monospace; font-size: 16px; fill: #4f46e5; animation: tw2 30s linear infinite; }
      .tw3 { font-family: 'Courier New', monospace; font-size: 16px; fill: #4f46e5; animation: tw3 30s linear infinite; }
      .tw4 { font-family: 'Courier New', monospace; font-size: 16px; fill: #4f46e5; animation: tw4 30s linear infinite; }
      .tw5 { font-family: 'Courier New', monospace; font-size: 16px; fill: #4f46e5; animation: tw5 30s linear infinite; }

      @keyframes tw1 {
        0%    { clip-path: inset(0 100% 0 0); opacity: 1; }
        8%    { clip-path: inset(0 0% 0 0);   opacity: 1; }
        18%   { clip-path: inset(0 0% 0 0);   opacity: 1; }
        20%   { clip-path: inset(0 100% 0 0); opacity: 0; }
        100%  { clip-path: inset(0 100% 0 0); opacity: 0; }
      }
      @keyframes tw2 {
        0%    { clip-path: inset(0 100% 0 0); opacity: 0; }
        20%   { clip-path: inset(0 100% 0 0); opacity: 0; }
        20.1% { clip-path: inset(0 100% 0 0); opacity: 1; }
        28%   { clip-path: inset(0 0% 0 0);   opacity: 1; }
        38%   { clip-path: inset(0 0% 0 0);   opacity: 1; }
        40%   { clip-path: inset(0 100% 0 0); opacity: 0; }
        100%  { clip-path: inset(0 100% 0 0); opacity: 0; }
      }
      @keyframes tw3 {
        0%    { clip-path: inset(0 100% 0 0); opacity: 0; }
        40%   { clip-path: inset(0 100% 0 0); opacity: 0; }
        40.1% { clip-path: inset(0 100% 0 0); opacity: 1; }
        48%   { clip-path: inset(0 0% 0 0);   opacity: 1; }
        58%   { clip-path: inset(0 0% 0 0);   opacity: 1; }
        60%   { clip-path: inset(0 100% 0 0); opacity: 0; }
        100%  { clip-path: inset(0 100% 0 0); opacity: 0; }
      }
      @keyframes tw4 {
        0%    { clip-path: inset(0 100% 0 0); opacity: 0; }
        60%   { clip-path: inset(0 100% 0 0); opacity: 0; }
        60.1% { clip-path: inset(0 100% 0 0); opacity: 1; }
        68%   { clip-path: inset(0 0% 0 0);   opacity: 1; }
        78%   { clip-path: inset(0 0% 0 0);   opacity: 1; }
        80%   { clip-path: inset(0 100% 0 0); opacity: 0; }
        100%  { clip-path: inset(0 100% 0 0); opacity: 0; }
      }
      @keyframes tw5 {
        0%    { clip-path: inset(0 100% 0 0); opacity: 0; }
        80%   { clip-path: inset(0 100% 0 0); opacity: 0; }
        80.1% { clip-path: inset(0 100% 0 0); opacity: 1; }
        88%   { clip-path: inset(0 0% 0 0);   opacity: 1; }
        98%   { clip-path: inset(0 0% 0 0);   opacity: 1; }
        100%  { clip-path: inset(0 100% 0 0); opacity: 0; }
      }
    </style>
  </defs>

  <!-- white background -->
  <rect width="800" height="180" fill="#ffffff"/>

  <!-- subtle top accent bar -->
  <rect x="0" y="0" width="800" height="3" fill="#4f46e5" opacity="0.75"/>

  <!-- greeting + name -->
  <text y="58">
    <tspan x="40" class="greeting">Hi there, I'm </tspan><tspan class="name">Andrew Baldonado 👋</tspan>
  </text>

  <!-- typewriter phrases -->
  <text x="40" y="90" class="tw1">💻 Software Developer</text>
  <text x="40" y="90" class="tw2">🤖 AI Automation Specialist</text>
  <text x="40" y="90" class="tw3">⚡ Full-Stack Engineer</text>
  <text x="40" y="90" class="tw4">🔧 Embedded Systems Builder</text>
  <text x="40" y="90" class="tw5">🌐 VB.NET · Web · Hardware</text>

  <!-- blinking cursor -->
  <rect x="274" y="76" width="2" height="16" class="cursor"/>

  <!-- tagline -->
  <text x="40" y="115" class="tagline">Full-Stack to Hardware — building solutions that bridge software and the physical world.</text>

  <!-- divider -->
  <line x1="40" y1="130" x2="760" y2="130" class="divider"/>

  <!-- LinkedIn badge -->
  <rect x="40" y="143" width="90" height="24" fill="#0077b5" rx="4"/>
  <text x="54" y="159" class="badge-text">🔗 LinkedIn</text>

  <!-- Gmail badge -->
  <rect x="138" y="143" width="70" height="24" fill="#ea4335" rx="4"/>
  <text x="152" y="159" class="badge-text">✉ Gmail</text>

  <!-- Portfolio badge -->
  <rect x="216" y="143" width="90" height="24" fill="#1a1a2e" rx="4"/>
  <text x="229" y="159" class="badge-text">🌐 Portfolio</text>

</svg>
---

## 🌐 Portfolio

> 🚀 **Andrew C. Baldonado** — Software Developer & AI Automation Specialist  
> [![Portfolio](https://img.shields.io/badge/Visit%20My%20Portfolio-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://andrewbdev.vercel.app/)

---

## 🛠️ Tech Stack

### 💻 Software & Web
![VB.NET](https://img.shields.io/badge/VB.NET-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)
![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-005C84?style=for-the-badge&logo=mysql&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)

### 🔧 Embedded & Hardware
![Arduino](https://img.shields.io/badge/Arduino-00979D?style=for-the-badge&logo=arduino&logoColor=white)
![Raspberry Pi](https://img.shields.io/badge/Raspberry%20Pi-C51A4A?style=for-the-badge&logo=raspberrypi&logoColor=white)
![C++](https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)

### ⚙️ DevOps & Tools
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub%20Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)

---

## 📈 Contribution Graph

![Activity Graph](https://github-readme-activity-graph.vercel.app/graph?username=acbaldonado&theme=tokyo-night)

---

## 🏆 GitHub Trophies

![Trophies](https://github-trophies.vercel.app/?username=acbaldonado&theme=tokyonight&no-frame=true)

---

## 🔥 Streak

![GitHub Streak](https://streak-stats.demolab.com?user=acbaldonado&theme=tokyonight)

---

## 📫 Connect with Me

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](http://linkedin.com/in/andrew-b-38134927b)
[![Gmail](https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:baldonado0514@gmail.com)
