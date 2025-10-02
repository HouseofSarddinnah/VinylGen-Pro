# VinylGen-Pro<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>VinylGen Pro - Smart Fashion Aware Prompt Generator</title>
  <style>
    body {
      box-sizing: border-box;
      font-family: 'Arial', sans-serif;
      background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
      margin: 0;
      padding: 20px;
      min-height: 100vh;
      color: #333;
    }
    .container {
      max-width: 820px;
      margin: 0 auto;
      background: white;
      border-radius: 20px;
      box-shadow: 0 20px 40px rgba(0,0,0,0.1);
      overflow: hidden;
    }
    .header {
      background: linear-gradient(45deg, #ff6b6b, #4ecdc4);
      padding: 30px;
      text-align: center;
      color: white;
    }
    .header h1 {
      margin: 0;
      font-size: 2.7rem;
      font-weight: 900;
      text-shadow: 2px 2px 5px rgba(0,0,0,0.35);
      letter-spacing: 2px;
    }
    .header p {
      margin: 12px 0 0 0;
      font-size: 1.15rem;
      font-weight: 600;
      opacity: 0.95;
      letter-spacing: 0.7px;
    }
    .brand-tagline {
      margin-top: 10px;
      font-size: 0.9rem;
      opacity: 0.9;
      font-weight: 400;
      letter-spacing: 1.4px;
      font-style: italic;
      user-select: none;
    }
    .content {
      padding: 40px 50px 50px;
      user-select: text;
    }
    .toggle-group {
      text-align: center;
      margin-bottom: 30px;
    }
    .toggle-btn {
      display: inline-block;
      padding: 14px 32px;
      margin: 0 12px;
      font-size: 1.1rem;
      cursor: pointer;
      border-radius: 30px;
      border: none;
      background: #222;
      color: #fff;
      font-weight: 700;
      letter-spacing: 1px;
      transition: background-color 0.25s ease, transform 0.3s ease;
      user-select: none;
      box-shadow: 0 5px 15px rgba(0,0,0,0.25);
    }
    .toggle-btn.active {
      background: #ff1493;
      box-shadow: 0 8px 22px rgba(255, 20, 147, 0.7);
      transform: scale(1.08);
    }
    .controls-section {
      background: #f8f9fa;
      border-radius: 15px;
      padding: 25px;
      margin-bottom: 30px;
      border: 2px solid #e9ecef;
    }
    .controls-title {
      font-size: 1.3rem;
      font-weight: 700;
      color: #333;
      margin-bottom: 20px;
      text-align: center;
    }
    .control-row {
      display: flex;
      gap: 20px;
      margin-bottom: 15px;
      flex-wrap: wrap;
      justify-content: center;
    }
    .control-group {
      display: flex;
      flex-direction: column;
      min-width: 150px;
    }
    .control-label {
      font-weight: 600;
      color: #555;
      margin-bottom: 5px;
      font-size: 0.9rem;
    }
    .control-select {
      padding: 10px;
      border: 2px solid #ddd;
      border-radius: 8px;
      font-size: 1rem;
      background: white;
      cursor: pointer;
      transition: border-color 0.3s ease;
    }
    .control-select:focus {
      outline: none;
      border-color: #ff1493;
    }
    .preset-section {
      text-align: center;
      margin-bottom: 30px;
    }
    .preset-title {
      font-size: 1.2rem;
      font-weight: 700;
      color: #333;
      margin-bottom: 15px;
    }
    .preset-buttons {
      display: flex;
      gap: 12px;
      justify-content: center;
      flex-wrap: wrap;
    }
    .preset-btn {
      padding: 12px 20px;
      background: linear-gradient(45deg, #4ecdc4, #44a08d);
      color: white;
      border: none;
      border-radius: 25px;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.3s ease;
      box-shadow: 0 4px 12px rgba(78,205,196,0.3);
    }
    .preset-btn:hover {
      transform: translateY(-2px);
      box-shadow: 0 6px 18px rgba(78,205,196,0.4);
    }
    .generate-btn {
      display: block;
      width: 280px;
      margin: 0 auto 30px auto;
      padding: 16px 30px;
      background: linear-gradient(45deg, #ff6b6b, #ff8e53);
      color: white;
      border: none;
      border-radius: 50px;
      font-size: 1.3rem;
      font-weight: 900;
      cursor: pointer;
      transition: all 0.35s ease;
      box-shadow: 0 6px 18px rgba(255, 107, 107, 0.45);
      user-select: none;
    }
    .generate-btn:hover {
      transform: translateY(-3px);
      box-shadow: 0 9px 28px rgba(255, 107, 107, 0.65);
    }
    .generate-btn:active {
      transform: translateY(1px);
    }
    .result-container {
      background: #f8f9fa;
      border-radius: 18px;
      padding: 28px 30px;
      margin-top: 24px;
      border-left: 7px solid #4ecdc4;
      box-shadow: 0 8px 30px rgba(0,0,0,0.08);
      display: none;
      white-space: pre-wrap;
      word-wrap: break-word;
      font-family: 'Courier New', monospace;
      font-size: 1rem;
      line-height: 1.55;
      color: #444;
      max-height: 360px;
      overflow-y: auto;
    }
    .result-container.show {
      display: block;
      animation: fadeInUp 0.5s ease forwards;
    }
    .character-title {
      font-size: 1.8rem;
      font-weight: 900;
      color: #2c3e50;
      margin-bottom: 22px;
      text-align: center;
      letter-spacing: 1.2px;
    }
    .copy-btn {
      display: block;
      margin: 25px auto 0 auto;
      background: #28a745;
      color: white;
      font-size: 1rem;
      font-weight: 700;
      padding: 10px 40px;
      border: none;
      border-radius: 30px;
      cursor: pointer;
      box-shadow: 0 6px 18px rgba(40, 167, 69, 0.5);
      transition: background 0.3s ease;
      user-select: none;
    }
    .copy-btn:hover {
      background: #218838;
    }
    .copy-btn:active {
      background: #19692c;
    }
    .stats {
      display: flex;
      justify-content: center;
      gap: 28px;
      margin-top: 35px;
      user-select: none;
    }
    .stat-card {
      background: white;
      padding: 18px 30px;
      border-radius: 14px;
      text-align: center;
      box-shadow: 0 3px 15px rgba(0,0,0,0.11);
      width: 180px;
    }
    .stat-number {
      font-size: 2.3rem;
      font-weight: 900;
      color: #ff6b6b;
      letter-spacing: 1.4px;
    }
    .stat-label {
      font-size: 1rem;
      color: #666;
      margin-top: 4px;
      font-weight: 500;
    }
    @keyframes fadeInUp {
      from {
        opacity: 0;
        transform: translateY(20px);
      }
      to {
        opacity: 1;
        transform: translateY(0);
      }
    }
    @media (max-width: 768px) {
      .content {
        padding: 30px 25px;
      }
      .toggle-btn {
        margin: 5px;
        padding: 12px 20px;
        font-size: 1rem;
      }
      .control-row {
        flex-direction: column;
        align-items: center;
      }
      .preset-buttons {
        flex-direction: column;
        align-items: center;
      }
      .stats-section {
        flex-direction: column;
        align-items: center;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="header">
      <h1>🎨 VinylGen Pro</h1>
      <p>Professional Vinyl Art Figure Prompt Generator</p>
      <div class="brand-tagline">Powered by Creative AI • Generate • Copy • Create</div>
    </div>
    
    <div class="content">
      <div class="toggle-group" role="group" aria-label="Style Selection">
        <button class="toggle-btn plush active" aria-pressed="true" id="plushBtn" onclick="setStyle('plush')">Plush Mascot Mode 🧸</button>
        <button class="toggle-btn vinyl" aria-pressed="false" id="vinylBtn" onclick="setStyle('vinyl')">Vinyl Toy Mode 💎</button>
        <button class="toggle-btn premium" aria-pressed="false" id="premiumBtn" onclick="setStyle('premium')">Premium Urban Hip-Hop 🔥</button>
      </div>

      <div class="controls-section">
        <div class="controls-title">🎨 Smart Style Controls</div>
        <div class="control-row">
          <div class="control-group">
            <label class="control-label">Theme</label>
            <select class="control-select" id="themeSelect" onchange="updateSettings()">
              <option value="classic">Classic</option>
              <option value="cyberpunk">Cyberpunk</option>
              <option value="fantasy">Fantasy</option>
              <option value="space">Space Age</option>
            </select>
          </div>
          <div class="control-group">
            <label class="control-label">Season</label>
            <select class="control-select" id="seasonSelect" onchange="updateSettings()">
              <option value="all">All Seasons</option>
              <option value="summer">Summer Vibes</option>
              <option value="winter">Winter Collection</option>
            </select>
          </div>
          <div class="control-group">
            <label class="control-label">Color Palette</label>
            <select class="control-select" id="paletteSelect" onchange="updateSettings()">
              <option value="vibrant">Vibrant</option>
              <option value="pastel">Pastel</option>
              <option value="monochrome">Monochrome</option>
              <option value="earth">Earth Tones</option>
              <option value="neon">Neon</option>
              <option value="galaxy">Galaxy</option>
            </select>
          </div>
        </div>
        <div class="control-row">
          <div class="control-group">
            <label class="control-label">Mood</label>
            <select class="control-select" id="moodSelect" onchange="updateSettings()">
              <option value="confident">Confident</option>
              <option value="chill">Chill & Relaxed</option>
              <option value="energetic">High Energy</option>
              <option value="mysterious">Mysterious</option>
              <option value="playful">Playful</option>
            </select>
          </div>
          <div class="control-group">
            <label class="control-label">Style Focus</label>
            <select class="control-select" id="focusSelect" onchange="updateSettings()">
              <option value="streetwear">Streetwear</option>
              <option value="luxury">Luxury</option>
              <option value="retro">Retro</option>
              <option value="avant-garde">Avant-Garde</option>
            </select>
          </div>
        </div>
      </div>

      <div class="preset-section">
        <div class="preset-title">⚡ Quick Style Presets</div>
        <div class="preset-buttons">
          <button class="preset-btn" onclick="loadPreset('Street Boss')">🔥 Street Boss</button>
          <button class="preset-btn" onclick="loadPreset('Luxury Icon')">💎 Luxury Icon</button>
          <button class="preset-btn" onclick="loadPreset('Retro Legend')">🎵 Retro Legend</button>
          <button class="preset-btn" onclick="loadPreset('Neon King')">🎨 Neon King</button>
          <button class="preset-btn" onclick="loadPreset('Cyber Punk')">🤖 Cyber Punk</button>
        </div>
      </div>

      <button class="generate-btn" aria-label="Generate Vinyl Art Prompt" id="generateBtn" onclick="generateCharacter()">✨ Generate Bear ✨</button>

      <div class="result-container" id="resultContainer" aria-live="polite" aria-atomic="true">
        <div class="character-title" id="characterTitle"></div>
        <pre class="prompt-text" id="promptText"></pre>
        <button class="copy-btn" aria-label="Copy Prompt to Clipboard" id="copyBtn" onclick="copyToClipboard()">📋 Copy Description</button>
      </div>
      
      <div class="stats" aria-label="Statistics">
        <div class="stat-card">
          <div class="stat-number" id="generatedCount">0</div>
          <div class="stat-label">Characters Generated</div>
        </div>
        <div class="stat-card">
          <div class="stat-number">10,000,000+</div>
          <div class="stat-label">Possible Combinations</div>
        </div>
      </div>
    </div>
  </div>

  <script>
    // Core arrays for character type and poses
    const CHARACTERS = [
      "plush bear mascot",
      "anthropomorphic vinyl figure",
      "collectible plush toy bear",
      "urban streetwear vinyl character",
      "pop surrealist vinyl bear"
    ];

    // Curated outfit groups per style for fashion coordination
    const OUTFIT_GROUPS = {
      streetwear: [
        {
          top: "oversized graffiti hoodie with neon paint accents",
          bottom: "baggy black cargo pants with neon green stripes",
          shoes: "neon pink graffiti mid-tops",
          accessories: ["spray can backpack", "colorful beaded bracelet"],
          eyewear: "mirrored aviator sunglasses"
        },
        {
          top: "color-blocked neon windbreaker",
          bottom: "ripped denim shorts with paint splatters",
          shoes: "black-and-white checkerboard slip-ons",
          accessories: ["snapback cap", "silver hoop earrings"],
          eyewear: "shutter shades with neon stripes"
        },
        {
          top: "hoodie with bold graffiti art print",
          bottom: "distressed tapered joggers",
          shoes: "high-top street skater sneakers",
          accessories: ["tattoo arm sleeves", "spray paint can keychain"],
          eyewear: "oversized square black spectacles"
        },
        {
          top: "bandana-print bomber jacket",
          bottom: "baggy cargo shorts with graffiti tags",
          shoes: "bright neon slip-on sneakers",
          accessories: ["chrome chain necklace", "headband with logo"],
          eyewear: "wraparound neon sports shades"
        }
      ],
      luxury: [
        {
          top: "silk varsity jacket with gold trims",
          bottom: "slim fitted tailored trousers",
          shoes: "polished leather loafers with gold buckles",
          accessories: ["gold medallion", "leather briefcase with money stacks"],
          eyewear: "sleek black luxury shades"
        },
        {
          top: "velvet bomber jacket with embroidered crest",
          bottom: "designer monogram sweatpants",
          shoes: "luxury branded sneakers",
          accessories: ["diamond watch", "gold bracelet"],
          eyewear: "designer square sunglasses"
        },
        {
          top: "cropped tailored blazer in gold satin",
          bottom: "high-rise silk cargo pants",
          shoes: "shiny patent loafers with crystal stones",
          accessories: ["platinum chain necklace", "black leather gloves"],
          eyewear: "diamond studded fashion eyeglasses"
        },
        {
          top: "luxury quilted bomber jacket with satin finish",
          bottom: "extreme slim-fit leather pants",
          shoes: "buckled velvet loafers with embroidery",
          accessories: ["gold cufflinks", "black leather designer belt"],
          eyewear: "gold-rimmed round glasses"
        }
      ],
      retro: [
        {
          top: "acid wash denim vest with retro patches",
          bottom: "faded corduroy bell bottoms",
          shoes: "classic Adidas shell toes",
          accessories: ["cassette player bag", "vintage chunky wristband"],
          eyewear: "retro round John Lennon glasses"
        },
        {
          top: "striped vintage rugby shirt",
          bottom: "wide-leg high-waist jeans",
          shoes: "colorful 80s-style runners",
          accessories: ["boombox accessory", "athletic wristband"],
          eyewear: "tinted aviators"
        },
        {
          top: "oversized cartoon print sweatshirt",
          bottom: "frayed hem denim shorts",
          shoes: "canvas high-top sneakers",
          accessories: ["retro fanny pack", "headband with colorful beads"],
          eyewear: "chunky 90s wraparound shades"
        },
        {
          top: "vintage leather motorcycle jacket",
          bottom: "wide cut corduroy pants",
          shoes: "classic black combat boots",
          accessories: ["silver hoop earrings", "studded leather wrist cuffs"],
          eyewear: "small oval colorful glasses"
        }
      ],
      "premium-urban-hiphop": [
        {
          top: "graffiti splash varsity jacket with neon paint accents",
          bottom: "camouflage cargo pants with neon graffiti tags",
          shoes: "custom neon graffiti mid-top sneakers",
          accessories: ["chain wallet with graffiti keychains", "colorful paint bomb backpack"],
          eyewear: "sleek black designer shades with neon lining"
        },
        {
          top: "bold color-blocked streetwear hoodie with oversized fit",
          bottom: "black tapered joggers with glowing side stripes",
          shoes: "limited edition streetstyle basketball shoes",
          accessories: ["oversized snapback hat with neon logo", "spray paint can holster belt"],
          eyewear: "oversized neon tinted sunglasses"
        },
        {
          top: "dripping paint-effect bomber jacket",
          bottom: "neon striped tapered sweatpants",
          shoes: "vibrant graffiti skate shoes",
          accessories: ["LED-lit gold chains", "glowing wristbands"],
          eyewear: "reflective chrome shield glasses"
        },
        {
          top: "oversized neon bodywarmer with abstract splatter prints",
          bottom: "splattered black-and-pink cargo pants",
          shoes: "neon paint splattered classic Jordans",
          accessories: ["graffiti tag embroidered backpack", "chunky neon bracelets"],
          eyewear: "artist signature frame glasses with graffiti patterns"
        }
      ]
    };

    // Style to outfit group selector helper
    const STYLE_TO_GROUP = {
      "Streetwear King": "streetwear",
      "Luxury Hustler": "luxury",
      "Retro Hip-Hop": "retro",
      "Premium Urban Hip-Hop": "premium-urban-hiphop"
    };

    const POSES = [
      "standing with arms crossed confidently",
      "posing with hands in pockets, relaxed",
      "pointing forward with attitude",
      "showing peace sign",
      "leaning against an invisible wall",
      "sitting sprawled with legs crossed",
      "dance move stance, dynamic and energetic"
    ];

    const BACKGROUNDS = [
      "urban graffiti mural wall, colorful and vibrant",
      "simple white studio background",
      "transparent background for sticker style",
      "soft depth-of-field urban street setting"
    ];

    const TEXTS = [
      "TRUST THE PROCESS",
      "BORN TO FLEX",
      "HUSTLE MODE",
      "STAY FRESH",
      "GRIND NEVER STOPS",
      "LEGENDARY VIBES"
    ];

    const PREMIUM_TEXTS = [
      "TRUST THE PROCESS",
      "HUSTLE MODE",
      "BORN TO FLEX",
      "STAY FRESH",
      "NEON NIGHT VIBES",
      "URBAN KING"
    ];

    const COLOR_PALETTES = {
      vibrant: ["electric blue", "hot pink", "neon green", "bright orange", "purple"],
      pastel: ["soft pink", "baby blue", "mint green", "lavender", "peach"],
      monochrome: ["black", "white", "charcoal gray", "silver", "pearl"],
      earth: ["forest green", "burnt orange", "deep brown", "golden yellow", "rust red"],
      neon: ["electric lime", "hot magenta", "cyber blue", "toxic yellow", "plasma pink"]
    };

    const FACIAL_EXPRESSIONS = [
      "confident smirk with raised eyebrow",
      "cool sunglasses-wearing expression",
      "determined focused look", 
      "playful winking expression",
      "serious boss-mode stare",
      "friendly approachable smile",
      "mysterious half-smile",
      "excited wide-eyed expression"
    ];

    let generatedCount = 0;
    let currentPrompt = '';
    let currentStyle = "plush";

    function randomChoice(arr) {
      return arr[Math.floor(Math.random() * arr.length)];
    }

    function setStyle(style) {
      currentStyle = style;
      
      // Update button states
      document.getElementById('plushBtn').classList.toggle('active', style === 'plush');
      document.getElementById('vinylBtn').classList.toggle('active', style === 'vinyl');  
      document.getElementById('premiumBtn').classList.toggle('active', style === 'premium');
      
      // Update aria-pressed attributes
      document.getElementById('plushBtn').setAttribute('aria-pressed', style === 'plush');
      document.getElementById('vinylBtn').setAttribute('aria-pressed', style === 'vinyl');
      document.getElementById('premiumBtn').setAttribute('aria-pressed', style === 'premium');
      
      // Show notification
      const notification = document.createElement('div');
      notification.textContent = `Switched to ${style === 'vinyl' ? 'Vinyl Toy Mode 💎' : style === 'premium' ? 'Premium Urban Hip-Hop 🔥' : 'Plush Mascot Mode 🧸'}`;
      notification.style.cssText = `
        position: fixed;
        top: 20px;
        right: 20px;
        background: ${style === 'vinyl' ? '#222' : style === 'premium' ? '#f39c12' : '#ff1493'};
        color: white;
        padding: 12px 26px;
        border-radius: 30px;
        font-size: 0.9rem;
        z-index: 10000;
        box-shadow: 0 6px 22px rgba(0,0,0,0.25);
        animation: fadeInUp 0.3s ease;
      `;
      document.body.appendChild(notification);
      setTimeout(() => notification.remove(), 1800);
    }

    function generateCharacter() {
      const character = randomChoice(CHARACTERS);

      let styleName;
      if (currentStyle === 'premium') {
        styleName = "Premium Urban Hip-Hop";
      } else if (currentStyle === 'vinyl') {
        styleName = randomChoice(["Streetwear King", "Luxury Hustler", "Retro Hip-Hop"]);
      } else {
        // plush mode picks random regular styles
        styleName = randomChoice(["Streetwear King", "Luxury Hustler", "Retro Hip-Hop"]);
      }

      // Get curated outfit group key
      const outfitGroupKey = STYLE_TO_GROUP[styleName];
      const outfitGroup = randomChoice(OUTFIT_GROUPS[outfitGroupKey]);

      const pose = randomChoice(POSES);
      const background = randomChoice(BACKGROUNDS);
      const text = currentStyle === 'premium' ? randomChoice(PREMIUM_TEXTS) : randomChoice(TEXTS);

      // Define style description based on current style
      let stylePrompt = "";
      if (currentStyle === "vinyl") {
        stylePrompt =
          "vinyl toy design, glossy hard plastic texture, pop surrealism, 4k hyper-detailed studio render, collectible figure, glossy finish";
      } else if (currentStyle === 'premium') {
        stylePrompt =
          "soft plush mascot with hyper-saturated neon colors, ultra-crisp vector-art style outlines, bold graffiti textures, glowing neon highlights, oversaturated pop art, high contrast, detailed fabric and paint splatter textures, 4k hyper-detailed studio render";
      } else {
        stylePrompt =
          "soft plush mascot, fuzzy fabric fur texture, squishy stuffed animal look, cohesive urban hip-hop fashion, matching outfit coordination, hyper-detailed, 4k render";
      }

      currentPrompt = `
3D collectible ${character} styled as "${styleName}".
Outfit: ${outfitGroup.top}, ${outfitGroup.bottom}, ${outfitGroup.shoes}.
Jewelry: ${outfitGroup.accessories.join(", ")}.
Eyewear: ${outfitGroup.eyewear}.
Pose: ${pose}.
Graffiti-style bold text: "${text}" below character.
Style: ${stylePrompt}.
Texture: detailed fabric weave, stitched seams, glowing neon paint splatter highlights.
Rendering: pop surrealism, toy drop studio render, hyper-detailed, 4k resolution.
Background: ${background}.
      `.trim();

      document.getElementById("characterTitle").textContent = `✨ ${styleName}: ${text} ✨`;
      document.getElementById("promptText").textContent = currentPrompt;
      document.getElementById("resultContainer").classList.add("show");

      // Update counter
      generatedCount++;
      document.getElementById("generatedCount").textContent = generatedCount;
    }

    function copyToClipboard() {
      const btn = document.getElementById("copyBtn");
      const originalText = btn.textContent;

      if (navigator.clipboard && window.isSecureContext) {
        navigator.clipboard
          .writeText(currentPrompt)
          .then(() => {
            btn.textContent = "✅ Copied!";
            btn.style.background = "#28a745";
            setTimeout(() => {
              btn.textContent = originalText;
              btn.style.background = "#28a745";
            }, 2000);
          })
          .catch(() => fallbackCopy());
      } else {
        fallbackCopy();
      }

      function fallbackCopy() {
        const textArea = document.createElement("textarea");
        textArea.value = currentPrompt;
        textArea.style.position = "fixed";
        textArea.style.left = "-999999px";
        textArea.style.top = "-999999px";
        document.body.appendChild(textArea);
        textArea.focus();
        textArea.select();

        try {
          document.execCommand("copy");
          btn.textContent = "✅ Copied!";
          btn.style.background = "#28a745";
          setTimeout(() => {
            btn.textContent = originalText;
            btn.style.background = "#28a745";
          }, 2000);
        } catch {
          btn.textContent = "❌ Copy failed";
          btn.style.background = "#dc3545";
          setTimeout(() => {
            btn.textContent = originalText;
            btn.style.background = "#28a745";
          }, 2000);
        }

        document.body.removeChild(textArea);
      }
    }

    // Init on load
    window.onload = () => {
      setStyle("plush");
      generateCharacter();
    };
  </script>
    // Smart Fashion Intelligence Data
    const SMART_CHARACTERS = {
      classic: [
        "fashion-forward plush bear mascot",
        "style-conscious vinyl figure",
        "trendsetting collectible bear",
        "urban fashion vinyl character",
        "designer toy bear with attitude"
      ],
      cyberpunk: [
        "neon-enhanced cyber bear with LED fashion accents",
        "holographic style-bot bear figure",
        "chrome-finished android bear with smart clothing",
        "digital fashion bear with glitch aesthetics",
        "tech-enhanced plush bear with wearable tech"
      ],
      fantasy: [
        "mystical fashion wizard bear",
        "enchanted style guardian bear",
        "magical couture bear with sparkles",
        "crystal-powered fashion bear",
        "fairy-tale designer bear"
      ],
      space: [
        "cosmic fashion astronaut bear",
        "intergalactic style explorer bear",
        "nebula-inspired space bear",
        "stellar fashion commander bear",
        "alien couture bear figure"
      ]
    };

    const SMART_OUTFITS = {
      streetwear: {
        tops: [
          "coordinated graffiti hoodie with matching color accents",
          "perfectly balanced color-blocked windbreaker",
          "street art bomber with complementary tones",
          "varsity jacket with harmonious patch colors",
          "graphic sweatshirt with smart color coordination"
        ],
        bottoms: [
          "cargo pants with color-matched utility details",
          "designer jeans with coordinated paint accents",
          "track pants with perfectly matched side stripes",
          "shorts with complementary graffiti elements",
          "joggers with harmonious color blocking"
        ]
      },
      luxury: {
        tops: [
          "silk jacket with perfectly matched monogram tones",
          "velvet blazer with coordinated gold accents",
          "designer bomber with harmonious embroidery",
          "premium windbreaker with balanced color palette",
          "luxury blazer with complementary satin details"
        ],
        bottoms: [
          "tailored trousers with matching crease details",
          "designer sweatpants with coordinated zippers",
          "velvet track pants with harmonious gold trim",
          "silk trousers with perfectly balanced tones",
          "leather pants with complementary metallic accents"
        ]
      },
      retro: {
        tops: [
          "vintage band tee with coordinated fade colors",
          "retro windbreaker with matching stripe patterns",
          "classic varsity jacket with period-accurate colors",
          "throwback hoodie with harmonious vintage tones",
          "old-school track jacket with balanced color blocking"
        ],
        bottoms: [
          "high-waisted jeans with coordinated wash tones",
          "retro track pants with matching side stripes",
          "vintage shorts with complementary color accents",
          "classic joggers with period-appropriate colors",
          "throwback cargo pants with harmonious details"
        ]
      },
      "avant-garde": {
        tops: [
          "experimental asymmetric jacket with color theory application",
          "avant-garde structured top with mathematical color ratios",
          "futuristic mesh overlay with scientifically balanced hues",
          "deconstructed blazer with artistic color placement",
          "conceptual layered piece with color psychology elements"
        ],
        bottoms: [
          "architectural pants with geometric color blocking",
          "experimental wide-leg trousers with color gradient theory",
          "avant-garde shorts with abstract color composition",
          "futuristic leggings with color spectrum mapping",
          "conceptual wrap pants with artistic color flow"
        ]
      }
    };

    const COLOR_PALETTES = {
      vibrant: ["electric blue", "hot pink", "neon green", "bright orange", "purple"],
      pastel: ["soft pink", "baby blue", "mint green", "lavender", "peach"],
      monochrome: ["black", "white", "charcoal gray", "silver", "pearl"],
      earth: ["forest green", "burnt orange", "deep brown", "golden yellow", "rust red"],
      neon: ["electric lime", "hot magenta", "cyber blue", "toxic yellow", "plasma pink"],
      galaxy: ["deep purple", "cosmic blue", "starlight silver", "nebula pink", "void black"]
    };

    const MOOD_EXPRESSIONS = {
      confident: [
        "determined boss-mode stare with raised chin",
        "confident smirk with piercing gaze",
        "powerful stance with intense focus",
        "commanding presence with slight smile"
      ],
      chill: [
        "relaxed half-smile with droopy eyes",
        "laid-back expression with casual gaze",
        "peaceful content look with soft features",
        "easygoing vibe with gentle smile"
      ],
      energetic: [
        "excited wide-eyed expression with big grin",
        "dynamic enthusiastic look with bright eyes",
        "high-energy smile with animated features",
        "pumped-up expression with vibrant energy"
      ],
      mysterious: [
        "enigmatic half-smile with shadowed eyes",
        "secretive gaze with subtle smirk",
        "intriguing expression with hidden depths",
        "cryptic look with knowing eyes"
      ],
      playful: [
        "mischievous grin with twinkling eyes",
        "playful wink with cheeky smile",
        "fun-loving expression with bright features",
        "jovial look with animated eyebrows"
      ]
    };

    const SMART_TEXTS = {
      streetwear: ["STREET KING", "URBAN LEGEND", "CITY BOSS", "BLOCK HERO"],
      luxury: ["LUXURY LIFE", "PREMIUM VIBES", "ELITE STATUS", "GOLD STANDARD"],
      retro: ["VINTAGE SOUL", "CLASSIC COOL", "RETRO KING", "OLD SCHOOL"],
      "avant-garde": ["FUTURE NOW", "ART FORM", "NEXT LEVEL", "VISION"]
    };

    // Global state
    let currentStyle = 'plush';
    let currentSettings = {
      theme: 'classic',
      season: 'all',
      palette: 'vibrant',
      mood: 'confident',
      focus: 'streetwear'
    };
    let generatedCount = 0;
    let currentPrompt = '';

    function randomChoice(arr) {
      return arr[Math.floor(Math.random() * arr.length)];
    }

    function setStyle(style) {
      currentStyle = style;
      document.getElementById('plushBtn').classList.toggle('active', style === 'plush');
      document.getElementById('vinylBtn').classList.toggle('active', style === 'vinyl');
      document.getElementById('premiumBtn').classList.toggle('active', style === 'premium');
      
      showNotification(`Switched to ${style === 'plush' ? 'Plush Mascot' : style === 'vinyl' ? 'Vinyl Toy' : 'Premium Neon'} Mode!`);
    }

    function updateSettings() {
      currentSettings.theme = document.getElementById('themeSelect').value;
      currentSettings.season = document.getElementById('seasonSelect').value;
      currentSettings.palette = document.getElementById('paletteSelect').value;
      currentSettings.mood = document.getElementById('moodSelect').value;
      currentSettings.focus = document.getElementById('focusSelect').value;
    }

    function loadPreset(presetName) {
      const presets = {
        'Street Boss': { theme: 'classic', palette: 'vibrant', mood: 'confident', focus: 'streetwear' },
        'Luxury Icon': { theme: 'classic', palette: 'monochrome', mood: 'confident', focus: 'luxury' },
        'Retro Legend': { theme: 'classic', palette: 'earth', mood: 'chill', focus: 'retro' },
        'Neon King': { theme: 'cyberpunk', palette: 'neon', mood: 'energetic', focus: 'streetwear' },
        'Cyber Punk': { theme: 'cyberpunk', palette: 'neon', mood: 'mysterious', focus: 'avant-garde' }
      };

      const preset = presets[presetName];
      if (preset) {
        currentSettings = { ...preset };
        
        document.getElementById('themeSelect').value = preset.theme;
        document.getElementById('paletteSelect').value = preset.palette;
        document.getElementById('moodSelect').value = preset.mood;
        document.getElementById('focusSelect').value = preset.focus;
        
        generateCharacter();
        showNotification(`Loaded ${presetName} preset!`);
      }
    }

    function generateCharacter() {
      const character = randomChoice(SMART_CHARACTERS[currentSettings.theme]);
      const outfitCategory = SMART_OUTFITS[currentSettings.focus];
      const outfit = {
        top: randomChoice(outfitCategory.tops),
        bottom: randomChoice(outfitCategory.bottoms)
      };
      
      const expression = randomChoice(MOOD_EXPRESSIONS[currentSettings.mood]);
      const colorPalette = COLOR_PALETTES[currentSettings.palette];
      const text = randomChoice(SMART_TEXTS[currentSettings.focus]);

      let stylePrompt = '';
      if (currentStyle === 'vinyl') {
        stylePrompt = 'vinyl toy design with smart color coordination, glossy finish, pop art aesthetics, designer toy proportions, hyper-detailed 4k render';
      } else if (currentStyle === 'premium') {
        stylePrompt = 'premium neon design with intelligent color matching, hyper-saturated tones, ultra-crisp vector art, bold graffiti textures, glowing highlights, 4k studio render';
      } else {
        stylePrompt = 'soft plush mascot with smart fashion coordination, fuzzy texture, perfectly matched outfit colors, cohesive style, 4k detailed render';
      }

      currentPrompt = `Smart Fashion AI Generated Character:

3D collectible ${character} with intelligent style coordination.

🎨 SMART STYLE ANALYSIS:
Theme: ${currentSettings.theme} aesthetics
Focus: ${currentSettings.focus} fashion intelligence
Mood: ${currentSettings.mood} energy expression
Season: ${currentSettings.season} collection

👕 AI-COORDINATED OUTFIT:
Top: ${outfit.top}
Bottom: ${outfit.bottom}
Color Harmony: ${colorPalette.join(', ')} (scientifically balanced palette)

😎 EXPRESSION & POSE:
Facial Expression: ${expression}
Graffiti Text: "${text}" with coordinated colors

🎯 RENDERING SPECIFICATIONS:
Style: ${stylePrompt}
Fashion Intelligence: Automatically coordinated colors, balanced proportions, trend-aware styling
Background: Smart color-matched environment with complementary tones
Quality: Pop surrealism, professional toy photography, hyper-detailed 4k resolution

🧠 AI FASHION NOTES:
- Colors scientifically balanced for maximum visual appeal
- Outfit pieces selected for perfect style harmony  
- Mood expression optimized for character personality
- Seasonal appropriateness considered in fabric choices
- Theme consistency maintained across all elements`;

      document.getElementById('characterTitle').textContent = `✨ ${currentSettings.focus.toUpperCase()}: ${text} ✨`;
      document.getElementById('promptText').textContent = currentPrompt;
      document.getElementById('resultContainer').classList.add('show');

      generatedCount++;
      document.getElementById('generatedCount').textContent = generatedCount;
    }

    function copyToClipboard() {
      if (navigator.clipboard && window.isSecureContext) {
        navigator.clipboard.writeText(currentPrompt).then(() => {
          showNotification('Smart prompt copied to clipboard!');
        });
      } else {
        const textArea = document.createElement('textarea');
        textArea.value = currentPrompt;
        document.body.appendChild(textArea);
        textArea.select();
        document.execCommand('copy');
        document.body.removeChild(textArea);
        showNotification('Smart prompt copied!');
      }
    }

    function showNotification(message) {
      const notification = document.createElement('div');
      notification.textContent = message;
      notification.style.cssText = `
        position: fixed;
        top: 20px;
        right: 20px;
        background: #4ecdc4;
        color: white;
        padding: 12px 24px;
        border-radius: 25px;
        font-weight: 600;
        z-index: 10000;
        box-shadow: 0 4px 15px rgba(0,0,0,0.2);
        animation: slideIn 0.3s ease;
      `;
      document.body.appendChild(notification);
      setTimeout(() => notification.remove(), 3000);
    }

    // Initialize the app
    window.onload = () => {
      generateCharacter();
      showNotification('Smart Fashion AI Ready! 🧠✨');
    };
  </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'988502496521ac42',t:'MTc1OTQxNjU5Mi4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
