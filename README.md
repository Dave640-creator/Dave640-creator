<svg width="900" height="200" viewBox="0 0 900 200" xmlns="http://www.w3.org/2000/svg">
  <defs>
    <linearGradient id="bg" x1="0%" y1="0%" x2="100%" y2="100%">
      <stop offset="0%"   stop-color="#020010"/>
      <stop offset="50%"  stop-color="#0a0030"/>
      <stop offset="100%" stop-color="#020010"/>
    </linearGradient>
    <linearGradient id="textGrad" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%"   stop-color="#00f5ff"/>
      <stop offset="50%"  stop-color="#bf00ff"/>
      <stop offset="100%" stop-color="#00f5ff">
        <animate attributeName="stop-color" values="#00f5ff;#ff006e;#00f5ff" dur="4s" repeatCount="indefinite"/>
      </stop>
    </linearGradient>
    <linearGradient id="lineGrad" x1="0%" y1="0%" x2="100%" y2="0%">
      <stop offset="0%"  stop-color="transparent"/>
      <stop offset="50%" stop-color="#00f5ff"/>
      <stop offset="100%" stop-color="transparent"/>
    </linearGradient>
    <filter id="glow">
      <feGaussianBlur stdDeviation="3" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
    <filter id="glow2">
      <feGaussianBlur stdDeviation="6" result="blur"/>
      <feMerge><feMergeNode in="blur"/><feMergeNode in="SourceGraphic"/></feMerge>
    </filter>
  </defs>

  <!-- Background -->
  <rect width="900" height="200" fill="url(#bg)" rx="16"/>

  <!-- Animated border -->
  <rect width="898" height="198" x="1" y="1" fill="none" rx="15"
    stroke="url(#lineGrad)" stroke-width="1.5" opacity="0.6">
    <animate attributeName="opacity" values="0.3;0.8;0.3" dur="3s" repeatCount="indefinite"/>
  </rect>

  <!-- Grid lines horizontal -->
  <line x1="0" y1="50"  x2="900" y2="50"  stroke="#00f5ff" stroke-width="0.3" opacity="0.12"/>
  <line x1="0" y1="100" x2="900" y2="100" stroke="#00f5ff" stroke-width="0.3" opacity="0.12"/>
  <line x1="0" y1="150" x2="900" y2="150" stroke="#00f5ff" stroke-width="0.3" opacity="0.12"/>

  <!-- Grid lines vertical -->
  <line x1="150" y1="0" x2="150" y2="200" stroke="#00f5ff" stroke-width="0.3" opacity="0.12"/>
  <line x1="300" y1="0" x2="300" y2="200" stroke="#00f5ff" stroke-width="0.3" opacity="0.12"/>
  <line x1="450" y1="0" x2="450" y2="200" stroke="#00f5ff" stroke-width="0.3" opacity="0.12"/>
  <line x1="600" y1="0" x2="600" y2="200" stroke="#00f5ff" stroke-width="0.3" opacity="0.12"/>
  <line x1="750" y1="0" x2="750" y2="200" stroke="#00f5ff" stroke-width="0.3" opacity="0.12"/>

  <!-- Floating particles -->
  <circle cx="80"  cy="40"  r="2" fill="#00f5ff" opacity="0.7" filter="url(#glow)">
    <animate attributeName="cy" values="40;20;40"   dur="4s"   repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0.7;0.2;0.7" dur="4s" repeatCount="indefinite"/>
  </circle>
  <circle cx="820" cy="160" r="1.5" fill="#bf00ff" opacity="0.7" filter="url(#glow)">
    <animate attributeName="cy" values="160;140;160" dur="5s" repeatCount="indefinite"/>
    <animate attributeName="opacity" values="0.7;0.2;0.7" dur="5s" repeatCount="indefinite"/>
  </circle>
  <circle cx="200" cy="170" r="1.5" fill="#ff006e" opacity="0.6" filter="url(#glow)">
    <animate attributeName="cy" values="170;150;170" dur="3.5s" repeatCount="indefinite"/>
  </circle>
  <circle cx="700" cy="30"  r="2" fill="#39ff14" opacity="0.5" filter="url(#glow)">
    <animate attributeName="cy" values="30;50;30" dur="6s" repeatCount="indefinite"/>
  </circle>
  <circle cx="500" cy="180" r="1.5" fill="#00f5ff" opacity="0.5" filter="url(#glow)">
    <animate attributeName="cy" values="180;160;180" dur="4.5s" repeatCount="indefinite"/>
  </circle>

  <!-- Scan line effect -->
  <rect x="0" y="0" width="900" height="4" fill="#00f5ff" opacity="0.07" rx="2">
    <animate attributeName="y" values="-4;204;-4" dur="5s" repeatCount="indefinite"/>
  </rect>

  <!-- Corner accents -->
  <polyline points="16,40 16,16 40,16"  stroke="#00f5ff" stroke-width="2" fill="none" opacity="0.8"/>
  <polyline points="860,16 884,16 884,40" stroke="#00f5ff" stroke-width="2" fill="none" opacity="0.8"/>
  <polyline points="16,160 16,184 40,184" stroke="#00f5ff" stroke-width="2" fill="none" opacity="0.8"/>
  <polyline points="860,184 884,184 884,160" stroke="#00f5ff" stroke-width="2" fill="none" opacity="0.8"/>

  <!-- Avatar circle -->
  <circle cx="120" cy="100" r="52" fill="none" stroke="#00f5ff" stroke-width="1.5" opacity="0.4">
    <animateTransform attributeName="transform" type="rotate" from="0 120 100" to="360 120 100" dur="8s" repeatCount="indefinite"/>
  </circle>
  <circle cx="120" cy="100" r="44" fill="#0a0030" stroke="#bf00ff" stroke-width="1" opacity="0.6"/>
  <text x="120" y="108" text-anchor="middle" font-size="36">👨‍💻</text>

  <!-- Small orbit dot -->
  <circle cx="120" cy="48" r="4" fill="#00f5ff" filter="url(#glow)">
    <animateTransform attributeName="transform" type="rotate" from="0 120 100" to="360 120 100" dur="8s" repeatCount="indefinite"/>
  </circle>

  <!-- Main name -->
  <text x="490" y="82"
    font-family="'Courier New', monospace"
    font-size="38"
    font-weight="900"
    text-anchor="middle"
    fill="url(#textGrad)"
    filter="url(#glow2)"
    letter-spacing="4">
    YOUR NAME
  </text>

  <!-- Underline glow -->
  <line x1="280" y1="92" x2="700" y2="92" stroke="url(#lineGrad)" stroke-width="1.5" opacity="0.7"/>

  <!-- Role text -->
  <text x="490" y="125"
    font-family="'Courier New', monospace"
    font-size="14"
    text-anchor="middle"
    fill="#a0c8d8"
    letter-spacing="6">
    FULL STACK DEVELOPER · AI ENTHUSIAST
  </text>

  <!-- Status badge -->
  <rect x="355" y="145" width="270" height="26" rx="13" fill="none" stroke="#39ff14" stroke-width="1" opacity="0.6"/>
  <circle cx="372" cy="158" r="5" fill="#39ff14" opacity="0.9">
    <animate attributeName="opacity" values="0.9;0.3;0.9" dur="1.5s" repeatCount="indefinite"/>
  </circle>
  <text x="490" y="163"
    font-family="'Courier New', monospace"
    font-size="11"
    text-anchor="middle"
    fill="#39ff14"
    letter-spacing="3">
    OPEN TO WORK
  </text>

  <!-- Side decorations -->
  <text x="30" y="104" font-family="'Courier New', monospace" font-size="9" fill="#00f5ff" opacity="0.4" letter-spacing="1">
    &lt;dev&gt;
  </text>
  <text x="840" y="104" font-family="'Courier New', monospace" font-size="9" fill="#00f5ff" opacity="0.4" letter-spacing="1">
    &lt;/dev&gt;
  </text>
</svg>
