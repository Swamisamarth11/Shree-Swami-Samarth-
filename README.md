<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
  <title>Swami Samarth — Sadhana, Habit & Electrical Exam Portal</title>

  <!-- Google Fonts & Font Awesome CDN -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Mukta:wght@300;400;600;700;800&family=Poppins:wght@300;400;500;600;700;800&display=swap" rel="stylesheet" />
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" />

  <style>
    /* ==========================================================================
       CSS VARIABLES & SACRED ENGINEERING THEME
       ========================================================================== */
    :root {
      --bg-porcelain: #FDFBF7;
      --bg-surface: #FFFFFF;
      --bg-glass: rgba(255, 255, 255, 0.85);
      --bg-glass-strong: rgba(255, 255, 255, 0.95);
      
      --saffron-primary: #FF7700;
      --saffron-deep: #E65100;
      --saffron-light: #FFF3E0;
      --gold-divine: #D4AF37;
      --gold-light: #FFF8E7;
      --amber-solar: #FFA000;
      --electric-orange: #FF5722;
      --electric-cyan: #0288D1;
      --electric-glow: rgba(255, 119, 0, 0.25);
      
      --text-main: #1F1F24;
      --text-muted: #666672;
      --text-light: #9494A0;
      --border-subtle: rgba(212, 175, 55, 0.2);
      --border-card: rgba(0, 0, 0, 0.06);
      
      --shadow-sm: 0 2px 8px rgba(0, 0, 0, 0.04);
      --shadow-md: 0 8px 24px rgba(212, 175, 55, 0.08), 0 2px 6px rgba(0, 0, 0, 0.03);
      --shadow-lg: 0 16px 36px rgba(230, 81, 0, 0.12), 0 4px 12px rgba(0, 0, 0, 0.04);
      --shadow-divine: 0 0 30px rgba(255, 153, 51, 0.35);

      --radius-sm: 10px;
      --radius-md: 16px;
      --radius-lg: 24px;
      --radius-full: 9999px;

      --transition-fast: 0.2s cubic-bezier(0.4, 0, 0.2, 1);
      --transition-smooth: 0.35s cubic-bezier(0.4, 0, 0.2, 1);
      --font-body: 'Poppins', 'Mukta', sans-serif;
      --font-devanagari: 'Mukta', 'Poppins', sans-serif;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      -webkit-tap-highlight-color: transparent;
    }

    body {
      background-color: var(--bg-porcelain);
      color: var(--text-main);
      font-family: var(--font-body);
      min-height: 100vh;
      overflow-x: hidden;
      line-height: 1.5;
      background-image: 
        radial-gradient(circle at 10% 20%, rgba(255, 243, 224, 0.6) 0%, transparent 40%),
        radial-gradient(circle at 90% 80%, rgba(255, 248, 231, 0.7) 0%, transparent 40%);
      background-attachment: fixed;
    }

    /* Scrollbar */
    ::-webkit-scrollbar { width: 6px; height: 6px; }
    ::-webkit-scrollbar-track { background: transparent; }
    ::-webkit-scrollbar-thumb { background: rgba(212, 175, 55, 0.3); border-radius: 10px; }
    ::-webkit-scrollbar-thumb:hover { background: var(--saffron-primary); }

    /* Touch Friendly Buttons */
    button, input, select, textarea {
      font-family: inherit;
      border: none;
      outline: none;
    }
    button {
      cursor: pointer;
      user-select: none;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      transition: var(--transition-fast);
      touch-action: manipulation;
    }
    button:active { transform: scale(0.97); }

    /* ==========================================================================
       AUTHENTICATION SCREEN (UNIFIED)
       ========================================================================== */
    #authOverlay {
      position: fixed;
      inset: 0;
      background: radial-gradient(circle at center, #FFF9F2 0%, #F5ECE0 100%);
      z-index: 10000;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 20px;
      transition: opacity 0.5s ease, visibility 0.5s ease;
    }
    #authOverlay.hidden {
      opacity: 0;
      visibility: hidden;
      pointer-events: none;
    }

    .auth-card {
      width: 100%;
      max-width: 420px;
      background: var(--bg-glass-strong);
      backdrop-filter: blur(16px);
      -webkit-backdrop-filter: blur(16px);
      border: 1px solid var(--border-subtle);
      border-radius: var(--radius-lg);
      padding: 40px 30px;
      box-shadow: var(--shadow-lg), 0 0 40px rgba(255, 153, 51, 0.15);
      text-align: center;
      position: relative;
      overflow: hidden;
      animation: authCardIn 0.6s cubic-bezier(0.16, 1, 0.3, 1);
    }
    .auth-card::before {
      content: '';
      position: absolute;
      top: 0; left: 0; right: 0; height: 5px;
      background: linear-gradient(90deg, var(--gold-divine), var(--saffron-primary), var(--electric-orange));
    }
    @keyframes authCardIn {
      0% { opacity: 0; transform: translateY(30px) scale(0.96); }
      100% { opacity: 1; transform: translateY(0) scale(1); }
    }

    .divine-orb {
      width: 86px;
      height: 86px;
      margin: 0 auto 16px;
      border-radius: 50%;
      background: linear-gradient(135deg, #FFF3E0, #FFE0B2);
      border: 2px solid var(--gold-divine);
      display: flex;
      align-items: center;
      justify-content: center;
      box-shadow: 0 0 25px rgba(255, 119, 0, 0.35);
      position: relative;
    }
    .divine-orb span {
      font-size: 42px;
      color: var(--saffron-deep);
      font-family: var(--font-devanagari);
      font-weight: 800;
      text-shadow: 0 2px 8px rgba(212, 175, 55, 0.4);
      animation: divineGlow 3s ease-in-out infinite alternate;
    }
    @keyframes divineGlow {
      from { filter: drop-shadow(0 0 2px var(--saffron-primary)); transform: scale(1); }
      to { filter: drop-shadow(0 0 10px var(--gold-divine)); transform: scale(1.06); }
    }

    .auth-title {
      font-size: 22px;
      font-weight: 700;
      color: var(--text-main);
      margin-bottom: 4px;
    }
    .auth-subtitle {
      font-size: 13px;
      color: var(--text-muted);
      margin-bottom: 28px;
      font-family: var(--font-devanagari);
      letter-spacing: 0.5px;
    }

    .form-group {
      margin-bottom: 20px;
      text-align: left;
    }
    .form-label {
      display: block;
      font-size: 12px;
      font-weight: 600;
      color: var(--text-muted);
      margin-bottom: 6px;
      text-transform: uppercase;
      letter-spacing: 0.5px;
    }
    .input-wrapper {
      position: relative;
      display: flex;
      align-items: center;
    }
    .input-icon {
      position: absolute;
      left: 14px;
      color: var(--saffron-primary);
      font-size: 15px;
      pointer-events: none;
    }
    .auth-input {
      width: 100%;
      height: 48px;
      padding: 0 42px 0 42px;
      border-radius: var(--radius-md);
      border: 1.5px solid rgba(0, 0, 0, 0.08);
      background: #FFFFFF;
      font-size: 15px;
      color: var(--text-main);
      transition: var(--transition-fast);
    }
    .auth-input:focus {
      border-color: var(--saffron-primary);
      box-shadow: 0 0 0 3px rgba(255, 119, 0, 0.15);
    }
    .password-toggle {
      position: absolute;
      right: 12px;
      background: none;
      color: var(--text-light);
      font-size: 14px;
      padding: 6px;
    }
    .password-toggle:hover { color: var(--text-main); }

    .btn-divine {
      width: 100%;
      height: 50px;
      background: linear-gradient(135deg, var(--saffron-primary), var(--saffron-deep));
      color: #FFFFFF;
      font-size: 15px;
      font-weight: 600;
      border-radius: var(--radius-md);
      box-shadow: 0 6px 18px rgba(230, 81, 0, 0.35);
      position: relative;
      overflow: hidden;
      margin-top: 10px;
    }
    .btn-divine:hover {
      box-shadow: 0 8px 24px rgba(230, 81, 0, 0.45);
      transform: translateY(-1px);
    }
    .btn-divine.loading {
      pointer-events: none;
      opacity: 0.85;
    }
    .btn-divine.loading .btn-text { opacity: 0; }
    .btn-spinner {
      display: none;
      position: absolute;
      width: 22px;
      height: 22px;
      border: 2px solid rgba(255, 255, 255, 0.4);
      border-top-color: #FFFFFF;
      border-radius: 50%;
      animation: spin 0.7s linear infinite;
    }
    .btn-divine.loading .btn-spinner { display: block; }
    @keyframes spin { to { transform: rotate(360deg); } }

    .auth-error {
      min-height: 22px;
      margin-top: 14px;
      font-size: 13px;
      font-weight: 500;
      color: #D32F2F;
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 6px;
      opacity: 0;
      transition: opacity 0.2s ease;
    }
    .auth-error.visible { opacity: 1; }
    .shake {
      animation: shakeErr 0.4s ease;
    }
    @keyframes shakeErr {
      0%, 100% { transform: translateX(0); }
      20%, 60% { transform: translateX(-8px); }
      40%, 80% { transform: translateX(8px); }
    }

    /* ==========================================================================
       MAIN APP SHELL & TOP BAR
       ========================================================================== */
    #appShell {
      min-height: 100vh;
      display: flex;
      flex-direction: column;
      padding-bottom: 90px;
    }

    .top-header {
      position: sticky;
      top: 0;
      z-index: 1000;
      background: var(--bg-glass-strong);
      backdrop-filter: blur(14px);
      -webkit-backdrop-filter: blur(14px);
      border-bottom: 1px solid var(--border-card);
      box-shadow: var(--shadow-sm);
      height: 70px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0 24px;
    }

    .brand-group {
      display: flex;
      align-items: center;
      gap: 12px;
      cursor: pointer;
    }
    .brand-icon {
      width: 44px;
      height: 44px;
      border-radius: 12px;
      background: linear-gradient(135deg, var(--saffron-light), #FFE0B2);
      border: 1.5px solid var(--gold-divine);
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--saffron-deep);
      font-size: 24px;
      font-family: var(--font-devanagari);
      font-weight: 800;
      box-shadow: 0 4px 12px rgba(255, 119, 0, 0.2);
    }
    .brand-text h1 {
      font-size: 17px;
      font-weight: 700;
      letter-spacing: -0.2px;
      color: var(--text-main);
      display: flex;
      align-items: center;
      gap: 6px;
    }
    .brand-text p {
      font-size: 11px;
      color: var(--saffron-deep);
      font-family: var(--font-devanagari);
      font-weight: 600;
      letter-spacing: 0.4px;
    }

    .header-actions {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .admin-pill-badge {
      display: none;
      align-items: center;
      gap: 6px;
      background: linear-gradient(135deg, #2A2D34, #1B1D22);
      color: #FFD54F;
      padding: 6px 14px;
      border-radius: var(--radius-full);
      font-size: 12px;
      font-weight: 600;
      letter-spacing: 0.4px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.15);
      cursor: pointer;
      border: 1px solid rgba(255, 213, 79, 0.3);
    }
    .admin-pill-badge.active { display: inline-flex; }

    .header-stats-pill {
      display: flex;
      align-items: center;
      gap: 14px;
      background: var(--gold-light);
      border: 1px solid var(--border-subtle);
      padding: 6px 14px;
      border-radius: var(--radius-full);
      font-size: 13px;
      font-weight: 600;
    }
    .pill-item {
      display: flex;
      align-items: center;
      gap: 6px;
    }
    .pill-item.coins { color: var(--amber-solar); }
    .pill-item.xp { color: var(--electric-cyan); }

    .btn-icon {
      width: 40px;
      height: 40px;
      border-radius: 50%;
      background: #FFFFFF;
      border: 1px solid var(--border-card);
      color: var(--text-muted);
      font-size: 15px;
      box-shadow: var(--shadow-sm);
    }
    .btn-icon:hover {
      color: var(--saffron-primary);
      border-color: var(--saffron-primary);
    }

    /* Desktop Navigation */
    .desktop-nav {
      display: none;
      align-items: center;
      gap: 6px;
    }
    @media (min-width: 992px) {
      .desktop-nav { display: flex; }
      #appShell { padding-bottom: 40px; }
      .bottom-nav { display: none !important; }
    }
    .nav-btn {
      padding: 8px 16px;
      border-radius: var(--radius-full);
      font-size: 13.5px;
      font-weight: 500;
      color: var(--text-muted);
      background: transparent;
      gap: 8px;
    }
    .nav-btn:hover {
      color: var(--saffron-deep);
      background: rgba(255, 119, 0, 0.06);
    }
    .nav-btn.active {
      background: linear-gradient(135deg, var(--saffron-primary), var(--saffron-deep));
      color: #FFFFFF;
      box-shadow: 0 4px 14px rgba(230, 81, 0, 0.3);
      font-weight: 600;
    }

    /* Mobile Bottom Navigation */
    .bottom-nav {
      position: fixed;
      bottom: 0;
      left: 0;
      right: 0;
      height: 68px;
      background: var(--bg-glass-strong);
      backdrop-filter: blur(16px);
      -webkit-backdrop-filter: blur(16px);
      border-top: 1px solid var(--border-card);
      display: flex;
      align-items: center;
      justify-content: space-around;
      padding: 0 8px;
      z-index: 999;
      box-shadow: 0 -4px 18px rgba(0,0,0,0.05);
    }
    .bottom-nav-item {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      gap: 4px;
      background: transparent;
      color: var(--text-muted);
      font-size: 10.5px;
      font-weight: 500;
      flex: 1;
      height: 100%;
      border-radius: var(--radius-sm);
      position: relative;
    }
    .bottom-nav-item i { font-size: 18px; transition: var(--transition-fast); }
    .bottom-nav-item.active {
      color: var(--saffron-deep);
      font-weight: 700;
    }
    .bottom-nav-item.active i {
      transform: translateY(-2px);
      color: var(--saffron-primary);
    }
    .bottom-nav-item.active::after {
      content: '';
      position: absolute;
      top: 6px;
      width: 20px;
      height: 3px;
      background: var(--saffron-primary);
      border-radius: var(--radius-full);
    }

    /* ==========================================================================
       CONTAINER & VIEW SECTIONS
       ========================================================================== */
    .main-container {
      max-width: 1240px;
      width: 100%;
      margin: 0 auto;
      padding: 24px 20px;
    }

    .view-section {
      display: none;
      animation: fadeInSection 0.35s ease-out;
    }
    .view-section.active { display: block; }
    @keyframes fadeInSection {
      from { opacity: 0; transform: translateY(12px); }
      to { opacity: 1; transform: translateY(0); }
    }

    /* ==========================================================================
       EMERGENCY BROADCAST ALERT & NOTICE BANNER
       ========================================================================== */
    #emergencyBanner {
      display: none;
      background: linear-gradient(90deg, #D32F2F, #B71C1C);
      color: #FFFFFF;
      padding: 12px 20px;
      font-size: 13.5px;
      font-weight: 600;
      align-items: center;
      justify-content: space-between;
      box-shadow: 0 4px 16px rgba(183, 28, 28, 0.35);
      animation: pulseAlert 2s infinite alternate;
      z-index: 998;
    }
    #emergencyBanner.active { display: flex; }
    @keyframes pulseAlert {
      0% { opacity: 0.95; }
      100% { opacity: 1; filter: drop-shadow(0 0 6px rgba(255, 23, 68, 0.8)); }
    }

    /* ==========================================================================
       SECTION 1: HOME DASHBOARD
       ========================================================================== */
    .hero-banner {
      background: linear-gradient(135deg, #FFFFFF 0%, #FFF8EE 100%);
      border: 1px solid var(--border-subtle);
      border-radius: var(--radius-lg);
      padding: 34px 28px;
      box-shadow: var(--shadow-md);
      position: relative;
      overflow: hidden;
      margin-bottom: 28px;
    }
    .hero-banner::after {
      content: '॥ श्री स्वामी समर्थ ॥';
      position: absolute;
      right: 20px;
      bottom: -15px;
      font-family: var(--font-devanagari);
      font-size: 64px;
      font-weight: 800;
      color: rgba(212, 175, 55, 0.06);
      pointer-events: none;
      user-select: none;
      white-space: nowrap;
    }

    .hero-flex {
      display: flex;
      flex-direction: column;
      gap: 20px;
      align-items: flex-start;
    }
    @media (min-width: 768px) {
      .hero-flex {
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
      }
    }

    .hero-left {
      display: flex;
      align-items: center;
      gap: 20px;
    }
    .hero-om-orb {
      width: 76px;
      height: 76px;
      border-radius: 50%;
      background: radial-gradient(circle, #FFF3E0 30%, #FFE0B2 100%);
      border: 2px solid var(--gold-divine);
      display: flex;
      align-items: center;
      justify-content: center;
      box-shadow: 0 0 25px rgba(255, 119, 0, 0.25);
      flex-shrink: 0;
    }
    .hero-om-orb span {
      font-family: var(--font-devanagari);
      font-size: 38px;
      font-weight: 800;
      color: var(--saffron-deep);
      text-shadow: 0 2px 10px rgba(212, 175, 55, 0.4);
    }
    .hero-texts h2 {
      font-size: 24px;
      font-weight: 700;
      color: var(--text-main);
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .hero-sadhak-badge {
      display: inline-block;
      font-size: 11.5px;
      font-weight: 600;
      color: var(--saffron-deep);
      background: var(--saffron-light);
      padding: 3px 10px;
      border-radius: var(--radius-full);
      margin-top: 4px;
      letter-spacing: 0.4px;
    }
    .sacred-blessing-box {
      margin-top: 10px;
      font-family: var(--font-devanagari);
      font-size: 17px;
      font-weight: 700;
      color: var(--saffron-primary);
      text-shadow: 0 1px 4px rgba(212, 175, 55, 0.25);
    }

    /* Live Stat Cards Grid */
    .stats-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 16px;
      margin-bottom: 28px;
    }
    @media (min-width: 768px) {
      .stats-grid { grid-template-columns: repeat(5, 1fr); }
    }

    .stat-card {
      background: #FFFFFF;
      border: 1px solid var(--border-card);
      border-radius: var(--radius-md);
      padding: 18px 16px;
      box-shadow: var(--shadow-sm);
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      position: relative;
      overflow: hidden;
      transition: var(--transition-smooth);
    }
    .stat-card:hover {
      transform: translateY(-3px);
      box-shadow: var(--shadow-md);
      border-color: var(--border-subtle);
    }
    .stat-card-top {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 10px;
    }
    .stat-icon-wrap {
      width: 36px;
      height: 36px;
      border-radius: 10px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 16px;
    }
    .stat-val {
      font-size: 24px;
      font-weight: 700;
      color: var(--text-main);
      line-height: 1.1;
      margin-bottom: 4px;
    }
    .stat-label {
      font-size: 11.5px;
      color: var(--text-muted);
      font-weight: 500;
    }
    .stat-progress {
      height: 4px;
      background: #F0F0F4;
      border-radius: var(--radius-full);
      margin-top: 10px;
      overflow: hidden;
    }
    .stat-progress-bar {
      height: 100%;
      border-radius: var(--radius-full);
      transition: width 1s ease-in-out;
    }

    /* Notice Board Section on Home */
    .section-header-w
