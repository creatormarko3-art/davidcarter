<html lang="en">
<head>
  <meta charset="UTF-8">
  <!-- Critical: Viewport settings for Mobile -->
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <title>The Iron-Dad | Dad Glow-Up System</title>
  
  <!-- Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600&family=Oswald:wght@400;500;700&display=swap" rel="stylesheet">

  <style>
    /* --- RESET & VARIABLES --- */
    :root {
      --bg-body: #0b0f14;       /* Deep Black/Navy background */
      --card-bg: #151a21;       /* Slightly lighter card bg */
      --accent-blue: #2c6fdf;   /* Blue accent */
      --text-main: #ffffff;     /* Pure white text */
      --text-muted: #9ca3af;    /* Muted gray text */
      --gradient-btn: linear-gradient(135deg, #2c6fdf 0%, #1d4ed8 100%);
      --border-color: rgba(255,255,255,0.08);
    }

    * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
    
    html { scroll-behavior: smooth; }

    body {
      font-family: 'Inter', sans-serif;
      background-color: var(--bg-body);
      color: var(--text-main);
      line-height: 1.5;
      overflow-x: hidden;
      -webkit-font-smoothing: antialiased; /* Smooths fonts on iPhones */
    }

    h1, h2, h3, h4 {
      font-family: 'Oswald', sans-serif;
      text-transform: uppercase;
      letter-spacing: 1px;
      color: var(--text-main);
      margin-bottom: 1rem;
    }

    /* ANIMATIONS */
    .reveal {
      opacity: 0;
      transform: translateY(15px);
      transition: all 0.5s ease-out;
    }

    .reveal.active {
      opacity: 1;
      transform: translateY(0);
    }

    .container { 
      max-width: 580px; /* Narrow width optimized for phone reading */
      margin: 0 auto; 
      padding: 0 20px; 
    }

    /* BUTTONS - Thumb-friendly size */
    .btn {
      display: block;
      width: 100%;
      padding: 14px 20px;
      background: var(--gradient-btn);
      color: var(--text-main);
      text-align: center;
      font-family: 'Oswald', sans-serif;
      font-size: 1.05rem;
      font-weight: 700;
      text-transform: uppercase;
      border-radius: 8px;
      text-decoration: none;
      box-shadow: 0 4px 12px rgba(44, 111, 223, 0.3);
      transition: transform 0.2s;
      border: 1px solid rgba(255,255,255,0.1);
      cursor: pointer;
      margin-top: 10px;
    }

    .btn:active { transform: scale(0.98); }
    .btn-small { width: auto !important; padding: 8px 16px !important; font-size: 0.85rem !important; }

    /* NAVIGATION */
    nav {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      background: rgba(11, 15, 20, 0.95);
      backdrop-filter: blur(10px);
      border-bottom: 1px solid var(--border-color);
      z-index: 1000;
      padding: 12px 20px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .logo {
      font-size: 1.25rem;
      font-weight: 700;
      color: var(--text-main);
      text-decoration: none;
      font-family: 'Oswald', sans-serif;
    }

    .highlight { color: var(--accent-blue); }

    /* HERO SECTION */
    .hero {
      min-height: 90vh;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      padding-top: 80px;
      padding-bottom: 40px;
      background: radial-gradient(circle at 50% 0%, #1e293b 0%, var(--bg-body) 60%);
    }

    .badge-pill {
      display: inline-block;
      padding: 5px 12px;
      border-radius: 20px;
      background: rgba(44, 111, 223, 0.15);
      color: var(--accent-blue);
      font-weight: 600;
      font-size: 0.8rem;
      margin-bottom: 15px;
      border: 1px solid rgba(44, 111, 223, 0.3);
      text-transform: uppercase;
    }

    .hero h1 {
      font-size: 2.5rem; /* Smaller for mobile */
      line-height: 1.1;
      margin-bottom: 1.2rem;
    }

    .hero p {
      font-size: 1.05rem;
      color: var(--text-muted);
      max-width: 100%;
      margin: 0 auto 30px auto;
      line-height: 1.5;
    }

    /* SECTIONS GENERAL */
    section { padding: 50px 0; }

    .section-title {
      text-align: center;
      font-size: 1.8rem;
      margin-bottom: 25px;
    }

    .card-list {
      display: flex;
      flex-direction: column;
      gap: 15px;
      margin-top: 30px;
    }

    .feature-card {
      background: var(--card-bg);
      padding: 20px;
      border-radius: 12px;
      border: 1px solid var(--border-color);
      transition: 0.3s;
    }

    .feature-card:hover { transform: translateY(-3px); border-color: var(--accent-blue); }

    .icon-box {
      font-size: 1.5rem;
      color: var(--accent-blue);
      margin-bottom: 12px;
    }

    .feature-text h3 {
      font-size: 1.1rem;
      margin-bottom: 8px;
    }

    .feature-text p {
      font-size: 0.95rem;
      color: var(--text-muted);
    }

    /* PRICING CARD */
    .pricing-card {
      background: var(--card-bg);
      border: 2px solid var(--accent-blue);
      border-radius: 16px;
      padding: 30px 20px;
      text-align: center;
      max-width: 500px;
      margin: 0 auto;
      box-shadow: 0 10px 40px rgba(0,0,0,0.5);
      position: relative;
    }

    .price-badge {
      position: absolute;
      top: -12px;
      left: 50%;
      transform: translateX(-50%);
      background: var(--accent-blue);
      color: white;
      padding: 4px 12px;
      border-radius: 12px;
      font-size: 0.75rem;
      font-weight: 700;
      text-transform: uppercase;
    }

    .old-price {
      text-decoration: line-through;
      color: var(--text-muted);
      font-size: 1rem;
    }

    .current-price {
      font-size: 3.5rem;
      font-weight: 700;
      font-family: 'Oswald';
      color: var(--text-main);
      line-height: 1;
      margin: 5px 0 15px 0;
    }

    .checklist {
      list-style: none;
      text-align: left;
      margin: 20px 0;
      padding: 0 10px;
    }

    .checklist li {
      padding: 8px 0;
      border-bottom: 1px solid rgba(255,255,255,0.05);
      color: var(--text-muted);
      font-size: 0.95rem;
    }
    .checklist li:last-child { border-bottom: none; }

    /* REVIEWS */
    .review-grid {
      display: grid;
      gap: 15px;
      margin-top: 30px;
    }

    .review-item {
      background: var(--card-bg);
      padding: 20px;
      border-radius: 12px;
      border: 1px solid var(--border-color);
    }

    .stars { color: var(--accent-blue); margin-bottom: 8px; font-size: 1rem; }
    
    .review-quote {
      font-style: italic;
      color: var(--text-main);
      margin-bottom: 12px;
      font-size: 0.95rem;
      line-height: 1.5;
    }

    .reviewer-name {
      font-size: 0.9rem;
      font-weight: 600;
      color: var(--text-muted);
    }

    /* FAQ */
    details {
      background: var(--card-bg);
      margin-bottom: 12px;
      border-radius: 8px;
      border: 1px solid var(--border-color);
      overflow: hidden;
    }

    summary {
      padding: 15px 20px;
      font-weight: 600;
      cursor: pointer;
      color: var(--text-main);
      position: relative;
      font-size: 0.95rem;
      list-style: none; /* Hides default triangle */
    }

    summary::-webkit-details-marker { display: none; } /* Hide default triangle */

    summary::after {
      content: "+";
      position: absolute;
      right: 20px;
      font-size: 1.2rem;
      color: var(--accent-blue);
    }

    details[open] summary::after { content: "-"; }

    .answer-text {
      padding: 15px 20px;
      border-top: 1px solid rgba(255,255,255,0.05);
      color: var(--text-muted);
      font-size: 0.95rem;
      background: rgba(0,0,0,0.2);
    }

    /* FOOTER */
    footer {
      border-top: 1px solid var(--border-color);
      padding: 30px 20px;
      text-align: center;
      font-size: 0.8rem;
      color: var(--text-muted);
      background: #080b10;
    }
    
    footer a { color: var(--text-muted); text-decoration: none; margin: 0 10px; }

    /* DESKTOP STYLES */
    @media(min-width: 768px) {
      .hero h1 { font-size: 3.5rem; }
      
      .card-list { flex-direction: row; flex-wrap: wrap; }
      .feature-card { flex: 1; min-width: 250px; }
      
      .review-grid { grid-template-columns: repeat(2, 1fr); }
      
      .btn { width: auto; }
    }
  </style>
</head>
<body>

  <!-- NAV -->
  <nav>
    <a href="#" class="logo">IRON<span class="highlight">DAD</span>.</a>
    <a href="#pricing" class="btn btn-small">BUY NOW</a>
  </nav>

  <!-- HERO -->
  <header class="hero reveal active">
    <span class="badge-pill">For Fathers Over 35</span>
    <h1>Skip The Gym.<br>Build Your Body.</h1>
    
    <p>A simple 90-day protocol to lose belly fat, gain strength, and improve energy—without spending hours in the gym.</p>
    
    <a href="#pricing" class="btn">START MY TRANSFORMATION</a>

    <div style="margin-top: 30px; font-size: 0.8rem; color: var(--text-muted);">
      Based on David Carter's story • Age 52 Transformation
    </div>
  </header>

  <!-- BENEFITS -->
  <section id="benefits">
    <div class="container">
      <h2 class="section-title reveal">Why This Works For Dads</h2>
      
      <div class="card-list">
        <div class="feature-card reveal">
          <div class="icon-box">⏱️</div>
          <div class="feature-text">
            <h3>Under 45 Mins</h3>
            <p>No commute needed. Short, intense workouts you can do at home.</p>
          </div>
        </div>
        
        <div class="feature-card reveal stagger-1">
          <div class="icon-box">🍔</div>
          <div class="feature-text">
            <h3>No Diet Struggles</h3>
            <p>Eat enough food to build muscle without starving yourself.</p>
          </div>
        </div>

        <div class="feature-card reveal stagger-2">
          <div class="icon-box">📊</div>
          <div class="feature-text">
            <h3>Track Everything</h3>
            <p>Digital dashboard included to see results instantly.</p>
          </div>
        </div>

        <div class="feature-card reveal stagger-3">
          <div class="icon-box">🛡️</div>
          <div class="feature-text">
            <h3>Lifetime Access</h3>
            <p>Pay once, keep the guides forever. Updated for life.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- REVIEWS -->
  <section id="reviews" style="background: #080b10;">
    <div class="container">
      <h2 class="section-title reveal">Happy Customers</h2>
      <div class="review-grid">
        
        <div class="review-item reveal">
          <div class="stars">★★★★★</div>
          <p class="review-quote">"I lost 15lbs in month 1. It's not magic, it just fits my schedule."</p>
          <div class="reviewer-name">James W., Engineer</div>
        </div>

        <div class="review-item reveal stagger-1">
          <div class="stars">★★★★★</div>
          <p class="review-quote">"Stopped guessing at the gym. The tracker keeps me honest even on busy days."</p>
          <div class="reviewer-name">David C., Sales Director</div>
        </div>

        <div class="review-item reveal">
          <div class="stars">★★★★★</div>
          <p class="review-quote">"Finally feel energetic during the school run. The meals were simple."</p>
          <div class="reviewer-name">Mike T., Teacher</div>
        </div>

        <div class="review-item reveal stagger-1">
          <div class="stars">★★★★★</div>
          <p class="review-quote">"Lost the gut and built arms again. Best investment I've made for myself."</p>
          <div class="reviewer-name">Tom B., Father of 3</div>
        </div>

      </div>
    </div>
  </section>

  <!-- WHAT'S INCLUDED -->
  <section id="products">
    <div class="container">
      <h2 class="section-title reveal">Everything You Get</h2>
      
      <div class="card-list">
        <div class="feature-card reveal stagger-1" style="flex-direction: row-reverse; text-align: right;">
           <!-- Placeholder icon instead of image -->
          <div class="feature-text" style="text-align: right;">
            <h3>Phase 1 Guide</h3>
            <p>Comprehensive PDF Workbooks focused on Calisthenics.</p>
          </div>
          <div class="icon-box">📘</div>
        </div>

        <div class="feature-card reveal stagger-2">
          <div class="icon-box">🥗</div>
          <div class="feature-text">
            <h3>Nutrition Blueprint</h3>
            <p>Family-Friendly Meals & Grocery Shopping Lists.</p>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- PRICING -->
  <section id="pricing" class="reveal">
    <div class="container">
      <div class="pricing-card">
        <div class="price-badge">Best Value</div>
        <h3 style="color: var(--text-muted); font-size: 1rem; font-weight: 400; margin-bottom: 10px;">ONE-TIME PAYMENT</h3>
        <div class="old-price">$197 Value</div>
        <div class="current-price">$47</div>
        
        <ul class="checklist">
          <li>Complete 90-Day Workout Guide</li>
          <li>Meal Prep Cookbook</li>
          <li>Digital Tracker Access</li>
        </ul>

        <!-- REPLACE WITH SHOPIFY LINK -->
        <a href="https://your-shopify-checkout-link.com/products/the-iron-dad-system" class="btn">BUY NOW →</a>
      </div>
    </div>
  </section>

  <!-- FAQ -->
  <section id="faq">
    <div class="container">
      <h2 class="section-title reveal">Common Questions</h2>
      
      <details class="reveal">
        <summary>Do I need a gym?</summary>
        <div class="answer-text">No. This program uses calisthenics designed to be done in a living room or garage.</div>
      </details>
      
      <details class="reveal">
        <summary>Is this suitable for beginners?</summary>
        <div class="answer-text">Yes. Phase 1 rebuilds your foundation safely so you don't get injured.</div>
      </details>

      <details class="reveal">
        <summary>How long do workouts take?</summary>
        <div class="answer-text">Short and intense. About 45 minutes from start to finish.</div>
      </details>

      <details class="reveal">
        <summary>What if I'm over 50?</summary>
        <div class="answer-text">Absolutely. Our founder started at 52 with joint health and functional strength in mind.</div>
      </details>
    </div>
  </section>

  <footer>
    <p>&copy; 2024 Iron-Dad Systems. All rights reserved.</p>
    <p style="margin-top: 10px;">
      <a href="#">Privacy Policy</a> | <a href="#">Terms of Service</a>
    </p>
  </footer>

  <!-- ANIMATION SCRIPT -->
  <script>
    window.addEventListener('scroll', revealElements);
    
    function revealElements() {
      const reveals = document.querySelectorAll('.reveal');
      
      for (let i = 0; i < reveals.length; i++) {
        let windowHeight = window.innerHeight;
        let elementTop = reveals[i].getBoundingClientRect().top;
        let elementVisible = 150;
        
        if (elementTop < windowHeight - elementVisible) {
          reveals[i].classList.add('active');
        }
      }
    }
    
    // Trigger immediately on load
    setTimeout(revealElements, 100);
  </script>

</body>
</html>
