<?xml version="1.0" encoding="UTF-8"?>
<svg xmlns="http://www.w3.org/2000/svg" width="900" height="250" viewBox="0 0 900 250" role="img" aria-labelledby="title desc">
  <title id="title">Vishwa R — Front-End Developer (glitch)</title>
  <desc id="desc">Animated glitch banner with RGB split and scanline slices for GitHub README.</desc>
  <defs>
    <!-- font + baseline -->
    <style><![CDATA[
      .label { font-family: 'Segoe UI', Roboto, system-ui, -apple-system, 'Helvetica Neue', Arial; font-weight: 800; }
      .title { font-size: 64px; letter-spacing: 4px; }
      .subtitle { font-size: 28px; letter-spacing: 3px; }
    ]]></style>

    <!-- mask used to create horizontal slice glitches -->
    <clipPath id="sliceClip">
      <rect x="0" y="0" width="900" height="250" />
      <!-- animated rectangles will be added by <use> trick; we'll instead animate multiple rects in the main svg -->
    </clipPath>

    <!-- simple grain/noise texture (subtle) -->
    <filter id="grain">
      <feTurbulence baseFrequency="0.8" numOctaves="1" stitchTiles="stitch" seed="2" result="noise" />
      <feColorMatrix type="saturate" values="0" />
      <feBlend in2="SourceGraphic" mode="overlay" />
    </filter>
  </defs>

  <!-- background -->
  <rect width="100%" height="100%" fill="#0f0f10" />

  <!-- subtle scanlines -->
  <g opacity="0.06">
    <rect width="100%" height="100%" fill="url(#)" />
    <g>
      <!-- repeating thin lines -->
      <!-- create many 2px high lines with 4px gap -->
      <!-- using pattern would be smaller but simpler to draw quickly -->
      <!-- We'll draw with a loop-like pattern using multiple rects -->
      <g fill="#ffffff">
        <!-- generate ~40 lines -->
        <!-- hardcoded for portability -->
        <rect x="0" y="0" width="900" height="1" />
        <rect x="0" y="6" width="900" height="1" />
        <rect x="0" y="12" width="900" height="1" />
        <rect x="0" y="18" width="900" height="1" />
        <rect x="0" y="24" width="900" height="1" />
        <rect x="0" y="30" width="900" height="1" />
        <rect x="0" y="36" width="900" height="1" />
        <rect x="0" y="42" width="900" height="1" />
        <rect x="0" y="48" width="900" height="1" />
        <rect x="0" y="54" width="900" height="1" />
        <rect x="0" y="60" width="900" height="1" />
        <rect x="0" y="66" width="900" height="1" />
        <rect x="0" y="72" width="900" height="1" />
        <rect x="0" y="78" width="900" height="1" />
        <rect x="0" y="84" width="900" height="1" />
        <rect x="0" y="90" width="900" height="1" />
        <rect x="0" y="96" width="900" height="1" />
        <rect x="0" y="102" width="900" height="1" />
        <rect x="0" y="108" width="900" height="1" />
        <rect x="0" y="114" width="900" height="1" />
        <rect x="0" y="120" width="900" height="1" />
        <rect x="0" y="126" width="900" height="1" />
        <rect x="0" y="132" width="900" height="1" />
        <rect x="0" y="138" width="900" height="1" />
        <rect x="0" y="144" width="900" height="1" />
        <rect x="0" y="150" width="900" height="1" />
        <rect x="0" y="156" width="900" height="1" />
        <rect x="0" y="162" width="900" height="1" />
        <rect x="0" y="168" width="900" height="1" />
        <rect x="0" y="174" width="900" height="1" />
        <rect x="0" y="180" width="900" height="1" />
        <rect x="0" y="186" width="900" height="1" />
        <rect x="0" y="192" width="900" height="1" />
        <rect x="0" y="198" width="900" height="1" />
        <rect x="0" y="204" width="900" height="1" />
        <rect x="0" y="210" width="900" height="1" />
        <rect x="0" y="216" width="900" height="1" />
        <rect x="0" y="222" width="900" height="1" />
        <rect x="0" y="228" width="900" height="1" />
        <rect x="0" y="234" width="900" height="1" />
        <rect x="0" y="240" width="900" height="1" />
      </g>
    </g>
  </g>

  <!-- Glitch groups: cyan, magenta and base -->
  <!-- title group (centered) -->
  <g transform="translate(50,90)">
    <!-- CYAN layer (left shifted briefly) -->
    <text class="label title" x="0" y="0" fill="#00ffff" style="mix-blend-mode:screen;" >Vishwa R</text>
    <g>
      <!-- small animated shifts for cyan title -->
      <animateTransform xlink:href="#" attributeName="transform" type="translate" from="0,0" to="0,0" dur="4s" repeatCount="indefinite" />
    </g>

    <!-- MAGENTA layer (right shifted briefly) -->
    <text class="label title" x="0" y="70" fill="#ff00ff" style="mix-blend-mode:screen; opacity:0.85;">Front-End Developer</text>
  </g>

  <!-- White (main) title with glitches applied as clipped moving slices -->
  <g class="mainText" transform="translate(50,90)">
    <text class="label title" x="0" y="0" fill="#ffffff">Vishwa R</text>
    <text class="label subtitle" x="0" y="70" fill="#cfcfcf">Front-End Developer</text>

    <!-- Animated glitch slices: rectangles that briefly reveal shifted copies -->
    <!-- slice 1 -->
    <g clip-path="url(#sliceClip)">
      <text class="label title" x="0" y="0" fill="#00ffff" opacity="0.9">
        <animate attributeName="x" values="0;-6;0" dur="2.2s" repeatCount="indefinite" />
        Vishwa R
      </text>
      <text class="label title" x="0" y="0" fill="#ff00ff" opacity="0.9">
        <animate attributeName="x" values="0;6;0" dur="2.6s" repeatCount="indefinite" />
        Vishwa R
      </text>

      <!-- subtitle slices -->
      <text class="label subtitle" x="0" y="70" fill="#00ffff" opacity="0.85">
        <animate attributeName="x" values="0;-4;0" dur="2s" repeatCount="indefinite" />
        Front-End Developer
      </text>
      <text class="label subtitle" x="0" y="70" fill="#ff00ff" opacity="0.85">
        <animate attributeName="x" values="0;4;0" dur="2.4s" repeatCount="indefinite" />
        Front-End Developer
      </text>
    </g>

    <!-- moving slice rectangles that mask parts to create jump cuts -->
    <rect x="0" y="10" width="900" height="18" fill="#ffffff" opacity="0" >
      <animate attributeName="x" values="-30;900" dur="3.6s" repeatCount="indefinite" />
    </rect>
    <rect x="0" y="40" width="900" height="12" fill="#ffffff" opacity="0" >
      <animate attributeName="x" values="900;-30" dur="2.8s" repeatCount="indefinite" />
    </rect>
    <rect x="0" y="80" width="900" height="10" fill="#ffffff" opacity="0" >
      <animate attributeName="x" values="-30;900" dur="4.2s" repeatCount="indefinite" />
    </rect>
  </g>

  <!-- small flicker of opacity for whole group to emulate glitch pulse -->
  <g>
    <rect x="0" y="0" width="900" height="250" fill="#ffffff" opacity="0">
      <animate attributeName="opacity" values="0;0.02;0" dur="5s" repeatCount="indefinite" />
    </rect>
  </g>

</svg>



###
- 🔭 I’m currently working on **Building projects with Angular and strengthening my base to land my first job as a Frontend Developer**  
- 🌱 I’m currently learning **Full-stack, and deepening my knowledge of Angular, JavaScript, and TypeScript**  
- 💬 Ask me about **Angular, JavaScript, and frontend development**  
- 📫 How to reach me **vishwa.r.ramesh@gmail.com**

###
<img align="right" height="350" width="550" src="https://gifdb.com/images/high/cartoon-character-louise-belcher-coding-is-fun-ctmkcciuc1gyxos2.webp"/>

###
<h3 align="left">🛠 Tech Stack</h3>
<div align="left">
   <a href="https://developer.mozilla.org/en-US/docs/Web/HTML" target="_blank">
     <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" height="30" alt="html5 logo" />
     <img width="12" />
   </a>
   <a href="https://developer.mozilla.org/en-US/docs/Web/CSS" target="_blank">
     <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" height="30" alt="css3 logo" />
     <img width="12" />
   </a>
   <a href="https://tailwindcss.com/" target="_blank">
      <img src="https://www.vectorlogo.zone/logos/tailwindcss/tailwindcss-icon.svg" height="30" alt="tailwindcss logo" />
      <img width="12" />
   </a>
   <a href="https://getbootstrap.com" target="_blank">
      <img src="https://www.vectorlogo.zone/logos/getbootstrap/getbootstrap-icon.svg" height="30" alt="bootstrap logo" />
      <img width="12" />
   </a>
   <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript" target="_blank">
     <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" height="30" alt="javascript logo" />
     <img width="12" />
   </a>
   <a href="https://www.typescriptlang.org" target="_blank">
     <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg" height="30" alt="typescript logo" />
     <img width="12" />
   </a>
   <a href="https://angular.dev" target="_blank">
     <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/angularjs/angularjs-original.svg" height="30" alt="angular logo" />
   </a>
  <a href="https://git-scm.com/" target="_blank">
     <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" height="30" alt="git logo" />
     <img width="12" />
   </a>
</div>

###
<h3 align="left">🌐 Connect with me</h3>
<div align="left">
  <a href="mailto:vishwa.r.ramesh@gmail.com">
    <img src="https://img.shields.io/static/v1?message=Gmail&logo=gmail&label=&color=D14836&logoColor=white&labelColor=&style=for-the-badge" height="35" alt="gmail logo" />
  </a>
  <a href="https://www.linkedin.com/in/vishwa-frontend" target="_blank">
    <img src="https://img.shields.io/static/v1?message=LinkedIn&logo=linkedin&label=&color=0077B5&logoColor=white&labelColor=&style=for-the-badge" height="35" alt="linkedin logo" />
  </a>
</div>

###
<h3 align="left">📊 GitHub Stats</h3>
<div align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=Vishwa-Sam&hide_title=false&hide_rank=false&show_icons=true&include_all_commits=true&count_private=true&disable_animations=false&theme=dracula&locale=en&hide_border=false" height="150" alt="stats graph" />
  <img src="https://github-readme-stats.vercel.app/api/top-langs?username=Vishwa-Sam&locale=en&hide_title=false&layout=compact&card_width=320&langs_count=5&theme=dracula&hide_border=false" height="150" alt="languages graph" />
</div>

###
<br clear="both">
<img align="center" height="200" width="900" src="https://media.licdn.com/dms/image/v2/C4E22AQFbPVAJDdZGyQ/feedshare-shrink_800/feedshare-shrink_800/0/1637057593647?e=1759363200&v=beta&t=rYPfAHI6iGt-DIZdgIL-65NNs83TAj_UiZ6uFSKQBow" />
