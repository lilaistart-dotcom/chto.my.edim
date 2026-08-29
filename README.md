[index-2.html](https://github.com/user-attachments/files/31599791/index-2.html)
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>ЧтоМыЕдим — Состав. Польза. Правда.</title>
  <meta name="description" content="Канал о еде, которую мы на самом деле едим. Факты, наука, правда." />
  <style>
    :root {
      --navy-0:  oklch(14% 0.04 250);
      --navy-1:  oklch(18% 0.05 250);
      --navy-2:  oklch(24% 0.05 250);
      --navy-3:  oklch(32% 0.05 250);
      --navy-4:  oklch(44% 0.04 250);
      --muted:   oklch(58% 0.03 250);
      --off-wht: oklch(97% 0.01 250);
      --body:    oklch(92% 0.01 250);
      --amber-0: oklch(72% 0.16 72);
      --amber-1: oklch(80% 0.14 72);
      --amber-2: oklch(88% 0.10 72);
      --red-acc: oklch(58% 0.22 25);
      --green-acc: oklch(60% 0.18 145);
      --radius-sm: 8px;
      --radius-md: 14px;
      --radius-pill: 9999px;
      --space-1: 4px; --space-2: 8px; --space-3: 12px;
      --space-4: 16px; --space-5: 24px; --space-6: 32px;
      --space-7: 48px;
      --shadow-sm: 0 1px 3px oklch(0% 0 0 / 0.25);
      --shadow-md: 0 4px 16px oklch(0% 0 0 / 0.35);
      --transition: 160ms cubic-bezier(0.4,0,0.2,1);
    }

    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    html { scroll-behavior: smooth; }
    body {
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", system-ui, sans-serif;
      background: var(--navy-0);
      color: var(--body);
      min-height: 100dvh;
      line-height: 1.5;
      -webkit-font-smoothing: antialiased;
    }

    .page {
      display: grid;
      place-items: center;
      min-height: 100dvh;
      padding: var(--space-6) var(--space-4);
    }

    .container {
      width: 100%;
      max-width: 420px;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: var(--space-5);
    }

    /* ── Avatar ── */
    .avatar-wrap {
      position: relative;
      width: 96px;
      height: 96px;
    }

    .avatar-ring {
      position: absolute;
      inset: -4px;
      border-radius: var(--radius-pill);
      background: conic-gradient(
        from 0deg,
        var(--amber-0) 0%,
        var(--amber-1) 25%,
        oklch(62% 0.12 200) 60%,
        var(--amber-0) 100%
      );
      z-index: 0;
      animation: spin 8s linear infinite;
    }

    @keyframes spin { to { transform: rotate(360deg); } }
    @media (prefers-reduced-motion: reduce) { .avatar-ring { animation: none; } }

    .avatar {
      position: relative;
      z-index: 1;
      width: 96px;
      height: 96px;
      border-radius: var(--radius-pill);
      background: oklch(16% 0.06 250);
      border: 3px solid oklch(22% 0.06 250);
      overflow: hidden;
      display: grid;
      place-items: center;
    }

    /* ── Scientist SVG illustration ── */
    .scientist-svg {
      width: 86px;
      height: 86px;
    }

    /* ── Header ── */
    .header {
      text-align: center;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: var(--space-2);
    }

    .channel-name {
      font-size: clamp(1.5rem, 6vw, 1.875rem);
      font-weight: 700;
      letter-spacing: -0.03em;
      color: var(--off-wht);
      line-height: 1.1;
    }

    .tagline {
      font-size: 0.8125rem;
      color: var(--muted);
      letter-spacing: 0.08em;
      text-transform: uppercase;
      font-weight: 500;
    }
    .tagline span { color: var(--amber-0); }

    /* ── Quote ── */
    .quote-card {
      width: 100%;
      background: var(--navy-1);
      border: 1px solid var(--navy-3);
      border-radius: var(--radius-md);
      padding: var(--space-4) var(--space-5);
      position: relative;
      overflow: hidden;
    }
    .quote-card::before {
      content: '"';
      position: absolute;
      top: -8px; left: 12px;
      font-size: 5rem;
      line-height: 1;
      color: var(--navy-3);
      font-family: Georgia, serif;
      pointer-events: none;
    }
    .quote-text {
      font-size: 0.9375rem;
      color: var(--body);
      font-style: italic;
      line-height: 1.55;
      position: relative;
      z-index: 1;
    }
    .quote-author {
      font-size: 0.75rem;
      color: var(--muted);
      margin-top: var(--space-2);
      font-weight: 500;
    }

    /* ── Stats ── */
    .stats {
      width: 100%;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: var(--space-3);
    }
    .stat {
      background: var(--navy-1);
      border: 1px solid var(--navy-3);
      border-radius: var(--radius-md);
      padding: var(--space-4) var(--space-3);
      text-align: center;
      display: flex;
      flex-direction: column;
      gap: var(--space-1);
    }
    .stat-value {
      font-size: 1.25rem;
      font-weight: 700;
      color: var(--amber-0);
      letter-spacing: -0.02em;
    }
    .stat-label {
      font-size: 0.6875rem;
      color: var(--muted);
      text-transform: uppercase;
      letter-spacing: 0.05em;
      line-height: 1.3;
    }

    /* ── Fact ticker ── */
    .ticker-wrap {
      width: 100%;
      overflow: hidden;
      background: var(--navy-1);
      border: 1px solid var(--navy-3);
      border-radius: var(--radius-md);
      padding: var(--space-3) 0;
    }
    .ticker {
      display: flex;
      gap: var(--space-7);
      animation: ticker 28s linear infinite;
      white-space: nowrap;
    }
    @keyframes ticker {
      from { transform: translateX(0); }
      to   { transform: translateX(-50%); }
    }
    @media (prefers-reduced-motion: reduce) {
      .ticker { animation: none; padding: 0 var(--space-4); }
    }
    .ticker-item {
      font-size: 0.8125rem;
      color: var(--muted);
      display: inline-flex;
      align-items: center;
      gap: var(--space-3);
    }
    .ticker-item span { color: var(--amber-0); font-weight: 600; }
    .ticker-dot {
      width: 3px; height: 3px;
      border-radius: 50%;
      background: var(--navy-4);
      display: inline-block;
    }

    /* ── Links ── */
    .links {
      width: 100%;
      display: flex;
      flex-direction: column;
      gap: var(--space-3);
    }
    .link-btn {
      display: flex;
      align-items: center;
      gap: var(--space-4);
      width: 100%;
      padding: var(--space-4) var(--space-5);
      border-radius: var(--radius-md);
      text-decoration: none;
      border: 1px solid transparent;
      cursor: pointer;
      transition:
        background var(--transition),
        border-color var(--transition),
        transform var(--transition),
        box-shadow var(--transition);
      -webkit-tap-highlight-color: transparent;
    }
    .link-btn:focus-visible {
      outline: 2px solid var(--amber-0);
      outline-offset: 3px;
    }

    /* Primary — Telegram */
    .link-btn--primary {
      background: var(--amber-0);
      color: var(--navy-0);
    }
    .link-btn--primary:hover {
      background: var(--amber-1);
      transform: translateY(-1px);
      box-shadow: var(--shadow-md);
    }
    .link-btn--primary:active { transform: translateY(0); box-shadow: none; }
    .link-btn--primary .link-icon { color: var(--navy-0); }
    .link-btn--primary .link-label { color: var(--navy-0); opacity: 0.65; }
    .link-btn--primary .link-title { color: var(--navy-0); }

    /* Secondary */
    .link-btn--secondary {
      background: var(--navy-1);
      border-color: var(--navy-3);
      color: var(--body);
    }
    .link-btn--secondary:hover {
      background: var(--navy-2);
      border-color: var(--navy-4);
      transform: translateY(-1px);
      box-shadow: var(--shadow-sm);
    }
    .link-btn--secondary:active { transform: translateY(0); box-shadow: none; }
    .link-btn--secondary .link-icon { color: var(--amber-0); }
    .link-btn--secondary .link-label { color: var(--muted); }
    .link-btn--secondary .link-title { color: var(--off-wht); }

    /* YouTube red tint */
    .link-btn--youtube {
      background: var(--navy-1);
      border-color: var(--navy-3);
      color: var(--body);
    }
    .link-btn--youtube:hover {
      background: oklch(18% 0.04 25);
      border-color: oklch(38% 0.12 25);
      transform: translateY(-1px);
      box-shadow: var(--shadow-sm);
    }
    .link-btn--youtube:active { transform: translateY(0); box-shadow: none; }
    .link-btn--youtube .link-icon { color: var(--red-acc); }
    .link-btn--youtube .link-label { color: var(--muted); }
    .link-btn--youtube .link-title { color: var(--off-wht); }

    /* Ghost */
    .link-btn--ghost {
      background: transparent;
      border-color: var(--navy-3);
      cursor: default;
    }
    .link-btn--ghost .link-icon { color: var(--amber-0); }
    .link-btn--ghost .link-label { color: var(--muted); }
    .link-btn--ghost .link-title { color: var(--off-wht); }

    .link-icon {
      flex-shrink: 0;
      width: 20px; height: 20px;
      display: grid;
      place-items: center;
    }
    .link-text {
      display: flex;
      flex-direction: column;
      gap: 1px;
      flex: 1;
    }
    .link-label {
      font-size: 0.6875rem;
      text-transform: uppercase;
      letter-spacing: 0.06em;
      font-weight: 500;
    }
    .link-title { font-size: 0.9375rem; font-weight: 600; }
    .link-arrow {
      flex-shrink: 0;
      opacity: 0.45;
      transition: opacity var(--transition), transform var(--transition);
    }
    .link-btn:hover .link-arrow { opacity: 0.9; transform: translateX(3px); }

    /* ── Topics ── */
    .topics {
      display: flex;
      flex-wrap: wrap;
      gap: var(--space-2);
      justify-content: center;
    }
    .tag {
      font-size: 0.75rem;
      padding: var(--space-1) var(--space-3);
      border-radius: var(--radius-pill);
      background: var(--navy-2);
      color: var(--muted);
      border: 1px solid var(--navy-3);
      letter-spacing: 0.03em;
    }
    .tag--accent {
      background: oklch(from var(--amber-0) l c h / 0.12);
      color: var(--amber-1);
      border-color: oklch(from var(--amber-0) l c h / 0.25);
    }

    /* ── Divider / Footer ── */
    .divider { width: 100%; height: 1px; background: var(--navy-3); }
    .footer {
      text-align: center;
      font-size: 0.75rem;
      color: var(--navy-4);
      line-height: 1.6;
    }
  </style>
</head>
<body>
<main class="page">
  <div class="container">

    <!-- Avatar with scientist illustration -->
    <div class="avatar-wrap">
      <div class="avatar-ring"></div>
      <div class="avatar">
        <!-- Scientist holding magnifying glass with tomato+DNA — inline SVG recreation -->
        <svg class="scientist-svg" viewBox="0 0 86 86" fill="none" xmlns="http://www.w3.org/2000/svg" aria-hidden="true">
          <!-- Background circle -->
          <circle cx="43" cy="43" r="43" fill="oklch(16% 0.06 250)"/>
          <circle cx="43" cy="43" r="40" fill="none" stroke="oklch(90% 0.01 250)" stroke-width="1.5"/>

          <!-- Lab coat body -->
          <path d="M24 72 C24 58 30 54 35 52 L38 56 L43 54 L48 56 L51 52 C56 54 62 58 62 72 Z"
                fill="oklch(92% 0.01 100)"/>
          <!-- Coat lapels -->
          <path d="M38 56 L36 64 L43 60 L50 64 L48 56" fill="oklch(80% 0.02 250)"/>
          <!-- Dark shirt underneath -->
          <path d="M38 56 L43 60 L48 56 L48 70 L38 70 Z" fill="oklch(22% 0.05 250)"/>

          <!-- Neck -->
          <rect x="40" y="46" width="6" height="7" rx="3"
                fill="oklch(74% 0.08 55)"/>

          <!-- Head -->
          <ellipse cx="43" cy="38" rx="11" ry="12" fill="oklch(74% 0.08 55)"/>

          <!-- Hair — dark messy bun style -->
          <path d="M32 34 C32 22 54 22 54 34 C54 28 49 24 43 24 C37 24 32 28 32 34 Z"
                fill="oklch(22% 0.05 250)"/>
          <ellipse cx="49" cy="24" rx="5" ry="4" fill="oklch(22% 0.05 250)"/>
          <ellipse cx="52" cy="26" rx="3" ry="3" fill="oklch(22% 0.05 250)"/>

          <!-- Glasses frames -->
          <circle cx="38.5" cy="39" r="4" stroke="oklch(15% 0.03 250)" stroke-width="1.2" fill="none"/>
          <circle cx="47.5" cy="39" r="4" stroke="oklch(15% 0.03 250)" stroke-width="1.2" fill="none"/>
          <line x1="42.5" y1="39" x2="43.5" y2="39" stroke="oklch(15% 0.03 250)" stroke-width="1.2"/>
          <line x1="34.5" y1="38.5" x2="32" y2="37.5" stroke="oklch(15% 0.03 250)" stroke-width="1.2"/>
          <line x1="51.5" y1="38.5" x2="54" y2="37.5" stroke="oklch(15% 0.03 250)" stroke-width="1.2"/>

          <!-- Eyes (smirk expression) -->
          <ellipse cx="38.5" cy="39" rx="2" ry="2.2" fill="oklch(15% 0.03 250)"/>
          <ellipse cx="47.5" cy="39" rx="2" ry="2.2" fill="oklch(15% 0.03 250)"/>
          <!-- Left eye slightly narrowed -->
          <path d="M36.5 38 Q38.5 37 40.5 38" stroke="oklch(74% 0.08 55)" stroke-width="0.8" fill="none"/>

          <!-- Smirk mouth -->
          <path d="M40 43 Q43 45 46 43" stroke="oklch(55% 0.06 55)" stroke-width="1.2" fill="none" stroke-linecap="round"/>

          <!-- Right arm raising magnifying glass -->
          <path d="M51 52 L56 44 L60 40" stroke="oklch(74% 0.08 55)" stroke-width="5" stroke-linecap="round"/>
          <!-- Sleeve over arm -->
          <path d="M51 53 L55 46 L58 42" stroke="oklch(92% 0.01 100)" stroke-width="4" stroke-linecap="round"/>

          <!-- Magnifying glass handle -->
          <line x1="61" y1="39" x2="67" y2="33" stroke="oklch(55% 0.04 250)" stroke-width="2.5" stroke-linecap="round"/>

          <!-- Magnifying glass circle -->
          <circle cx="57" cy="43" r="8" fill="oklch(75% 0.04 200)" fill-opacity="0.15"
                  stroke="oklch(85% 0.03 200)" stroke-width="1.8"/>

          <!-- Tomato inside magnifier -->
          <circle cx="57" cy="44" r="5" fill="var(--red-acc)"/>
          <!-- Tomato highlight -->
          <ellipse cx="55" cy="42" rx="1.5" ry="1" fill="oklch(80% 0.08 25)" opacity="0.6"/>
          <!-- Tomato stem + leaf -->
          <rect x="56.5" y="38.5" width="1" height="2.5" fill="var(--green-acc)"/>
          <path d="M55.5 40 Q57 38.5 58.5 40" stroke="var(--green-acc)" stroke-width="1" fill="none"/>

          <!-- DNA strand inside tomato (simplified) -->
          <path d="M55 41 Q57 42.5 59 41" stroke="white" stroke-width="0.7" fill="none" opacity="0.8"/>
          <path d="M55 43 Q57 44.5 59 43" stroke="white" stroke-width="0.7" fill="none" opacity="0.8"/>
          <line x1="55.8" y1="41.2" x2="55.8" y2="42.8" stroke="white" stroke-width="0.5" opacity="0.7"/>
          <line x1="57" y1="42" x2="57" y2="43.5" stroke="white" stroke-width="0.5" opacity="0.7"/>
          <line x1="58.2" y1="41.2" x2="58.2" y2="42.8" stroke="white" stroke-width="0.5" opacity="0.7"/>

          <!-- Left arm crossed -->
          <path d="M35 52 L30 58 L38 60" stroke="oklch(74% 0.08 55)" stroke-width="5" stroke-linecap="round" stroke-linejoin="round"/>
          <path d="M35 53 L31 58 L38 60" stroke="oklch(92% 0.01 100)" stroke-width="3.5" stroke-linecap="round" stroke-linejoin="round"/>
        </svg>
      </div>
    </div>

    <!-- Header -->
    <header class="header">
      <h1 class="channel-name">ЧтоМыЕдим</h1>
      <p class="tagline">Состав&nbsp;·&nbsp;<span>Польза</span>&nbsp;·&nbsp;Правда</p>
    </header>

    <!-- Quote -->
    <div class="quote-card" role="blockquote">
      <p class="quote-text">Скажи мне, что ты ешь, и я скажу тебе, кто ты.</p>
      <p class="quote-author">— Брийа-Саварен</p>
    </div>

    <!-- Stats — general food facts -->
    <div class="stats" aria-label="Интересные факты">
      <div class="stat">
        <span class="stat-value">3 000</span>
        <span class="stat-label">лет история пищи без изменений</span>
      </div>
      <div class="stat">
        <span class="stat-value">80%</span>
        <span class="stat-label">людей едят не то, что думают</span>
      </div>
      <div class="stat">
        <span class="stat-value">100%</span>
        <span class="stat-label">без паники — только факты</span>
      </div>
    </div>

    <!-- Fact ticker — general facts, no specific products -->
    <div class="ticker-wrap" aria-hidden="true">
      <div class="ticker">
        <!-- set 1 -->
        <span class="ticker-item"><span>Состав</span> важнее названия продукта<span class="ticker-dot"></span></span>
        <span class="ticker-item"><span>Нагрев</span> убивает большинство ферментов<span class="ticker-dot"></span></span>
        <span class="ticker-item"><span>Цвет</span> упаковки влияет на вкус<span class="ticker-dot"></span></span>
        <span class="ticker-item"><span>Срок годности</span> — не всегда правда<span class="ticker-dot"></span></span>
        <span class="ticker-item"><span>Первый ингредиент</span> — самый главный<span class="ticker-dot"></span></span>
        <span class="ticker-item"><span>Органическое</span> не значит полезное<span class="ticker-dot"></span></span>
        <!-- set 2 duplicate for seamless loop -->
        <span class="ticker-item"><span>Состав</span> важнее названия продукта<span class="ticker-dot"></span></span>
        <span class="ticker-item"><span>Нагрев</span> убивает большинство ферментов<span class="ticker-dot"></span></span>
        <span class="ticker-item"><span>Цвет</span> упаковки влияет на вкус<span class="ticker-dot"></span></span>
        <span class="ticker-item"><span>Срок годности</span> — не всегда правда<span class="ticker-dot"></span></span>
        <span class="ticker-item"><span>Первый ингредиент</span> — самый главный<span class="ticker-dot"></span></span>
        <span class="ticker-item"><span>Органическое</span> не значит полезное<span class="ticker-dot"></span></span>
      </div>
    </div>

    <!-- Links -->
    <nav class="links" aria-label="Ссылки">

      <!-- Telegram — primary CTA -->
      <a href="https://t.me/amuryuz" target="_blank" rel="noopener noreferrer"
         class="link-btn link-btn--primary" aria-label="Написать в Telegram">
        <span class="link-icon">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
            <path d="M12 0C5.373 0 0 5.373 0 12s5.373 12 12 12 12-5.373 12-12S18.627 0 12 0zm5.894 8.221-1.97 9.28c-.145.658-.537.818-1.084.508l-3-2.21-1.447 1.394c-.16.16-.295.295-.605.295l.213-3.053 5.56-5.023c.242-.213-.054-.333-.373-.12L7.16 13.947l-2.952-.924c-.642-.204-.657-.642.135-.953l11.525-4.444c.534-.194 1.001.13.826.595z"/>
          </svg>
        </span>
        <span class="link-text">
          <span class="link-label">Написать напрямую</span>
          <span class="link-title">Telegram @amuryuz</span>
        </span>
        <svg class="link-arrow" width="16" height="16" viewBox="0 0 24 24" fill="none"
             stroke="currentColor" stroke-width="2.5">
          <path d="M5 12h14M12 5l7 7-7 7"/>
        </svg>
      </a>

      <!-- Instagram -->
      <a href="https://instagram.com/chto.my.edim" target="_blank" rel="noopener noreferrer"
         class="link-btn link-btn--secondary" aria-label="Instagram канал">
        <span class="link-icon">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
            <path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zM12 0C8.741 0 8.333.014 7.053.072 2.695.272.273 2.69.073 7.052.014 8.333 0 8.741 0 12c0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98C8.333 23.986 8.741 24 12 24c3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98C15.668.014 15.259 0 12 0zm0 5.838a6.162 6.162 0 100 12.324 6.162 6.162 0 000-12.324zM12 16a4 4 0 110-8 4 4 0 010 8zm6.406-11.845a1.44 1.44 0 100 2.881 1.44 1.44 0 000-2.881z"/>
          </svg>
        </span>
        <span class="link-text">
          <span class="link-label">Смотреть рилсы</span>
          <span class="link-title">Instagram @chto.my.edim</span>
        </span>
        <svg class="link-arrow" width="16" height="16" viewBox="0 0 24 24" fill="none"
             stroke="currentColor" stroke-width="2.5">
          <path d="M5 12h14M12 5l7 7-7 7"/>
        </svg>
      </a>

      <!-- YouTube -->
      <a href="https://www.youtube.com/@chtomyedim" target="_blank" rel="noopener noreferrer"
         class="link-btn link-btn--youtube" aria-label="YouTube канал">
        <span class="link-icon">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
            <path d="M23.498 6.186a3.016 3.016 0 00-2.122-2.136C19.505 3.545 12 3.545 12 3.545s-7.505 0-9.377.505A3.017 3.017 0 00.502 6.186C0 8.07 0 12 0 12s0 3.93.502 5.814a3.016 3.016 0 002.122 2.136c1.871.505 9.376.505 9.376.505s7.505 0 9.377-.505a3.015 3.015 0 002.122-2.136C24 15.93 24 12 24 12s0-3.93-.502-5.814zM9.545 15.568V8.432L15.818 12l-6.273 3.568z"/>
          </svg>
        </span>
        <span class="link-text">
          <span class="link-label">Смотреть видео</span>
          <span class="link-title">YouTube @chtomyedim</span>
        </span>
        <svg class="link-arrow" width="16" height="16" viewBox="0 0 24 24" fill="none"
             stroke="currentColor" stroke-width="2.5">
          <path d="M5 12h14M12 5l7 7-7 7"/>
        </svg>
      </a>

      <!-- Schedule badge -->
      <div class="link-btn link-btn--ghost" aria-label="Расписание">
        <span class="link-icon">
          <svg width="20" height="20" viewBox="0 0 24 24" fill="none"
               stroke="currentColor" stroke-width="2">
            <circle cx="12" cy="12" r="10"/>
            <polyline points="12 6 12 12 16 14"/>
          </svg>
        </span>
        <span class="link-text">
          <span class="link-label">Расписание</span>
          <span class="link-title">Новый рилс каждый день</span>
        </span>
      </div>

    </nav>

    <!-- Topics -->
    <div class="topics" role="list" aria-label="Темы канала">
      <span class="tag tag--accent" role="listitem">#чтомыедим</span>
      <span class="tag tag--accent" role="listitem">#живи100лет</span>
      <span class="tag tag--accent" role="listitem">#правдаоеде</span>
      <span class="tag" role="listitem">#составпродуктов</span>
      <span class="tag" role="listitem">#наукаотарелке</span>
      <span class="tag" role="listitem">#здоровоепитание</span>
    </div>

    <div class="divider" role="separator"></div>

    <footer class="footer">
      <p>© 2026 ЧтоМыЕдим</p>
      <p>Факты о еде, которые меняют жизнь</p>
    </footer>

  </div>
</main>
</body>
</html>
