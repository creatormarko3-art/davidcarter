<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <title>The Iron-Dad | Dad Glow-Up System</title>
  
  <!-- Google Fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600&family=Oswald:wght@400;500;700&display=swap" rel="stylesheet">

  <style>
    /* --- RESET & VARIABLES --- */
    :root {
      --bg-body: #05080f;
      --bg-card: #0b1120;
      --accent-blue: #3b82f6;
      --accent-glow: rgba(59, 130, 246, 0.3);
      --text-white: #ffffff;
      --text-light: #e5e7eb;
      --border-color: rgba(255,255,255,0.1);
      --gradient-btn: linear-gradient(90deg, #2563eb 0%, #3b82f6 100%);
    }

    * { margin: 0; padding: 0; box-sizing: border-box; -webkit-tap-highlight-color: transparent; }
    
    body {
      font-family: 'Inter', sans-serif;
      background-color: var(--bg-body);
      color: var(--text-white);
      line-height: 1.5;
      overflow-x: hidden;
    }

    h1, h2, h3, h4 {
      font-family: 'Oswald', sans-serif;
      text-transform: uppercase;
      letter-spacing: 1px;
      color: var(--text-white);
      margin-bottom: 1rem;
    }

    /* ANIMATIONS */
    .reveal {
      opacity: 0;
      transform: translateY(25px);
      transition: all 0.6s cubic-bezier(0.2, 0.8, 0.2, 1);
    }

    .reveal.active {
      opacity: 1;
      transform: translateY(0);
    }

    .container { max-width: 1100px; margin: 0 auto; padding: 0 20px; }
    .highlight { color: var(--accent-blue); }
    .text-center { text-align: center; }

    /* BUTTONS */
    .btn {
      display: block;
      width: 100%;
      max-width: 320px;
      padding: 16px 24px;
      background: var(--gradient-btn);
      color: var(--text-white);
      text-align: center;
      font-family: 'Oswald', sans-serif;
      font-size: 1.1rem;
      font-weight: 700;
      text-transform: uppercase;
      border-radius: 6px;
      text-decoration: none;
      box-shadow: 0 0 20px var(--accent-glow);
      transition: transform 0.2s ease, box-shadow 0.2s ease;
      border: 1px solid var(--border-color);
      cursor: pointer;
      margin-top: 15px;
      position: relative;
      z-index: 10;
    }

    .btn:hover {
      transform: scale(1.02);
      box-shadow: 0 0 30px var(--accent-glow);
    }

    .btn-small {
      width: auto !important;
      padding: 8px 20px !important;
      font-size: 0.9rem !important;
    }

    /* NAVIGATION */
    nav {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      background: rgba(5, 8, 15, 0.95);
      backdrop-filter: blur(10px);
      border-bottom: 1px solid var(--border-color);
      z-index: 1000;
      padding: 15px 20px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .logo {
      font-size: 1.5rem;
      font-weight: 700;
      color: var(--text-white);
      text-decoration: none;
      font-family: 'Oswald', sans-serif;
    }

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
      background: radial-gradient(circle at 50% 10%, #172a45 0%, #05080f 60%);
    }

    .hero-tag {
      display: inline-block;
      padding: 6px 14px;
      border-radius: 50px;
      background: rgba(59, 130, 246, 0.1);
      color: var(--accent-blue);
      font-weight: 600;
      font-size: 0.8rem;
      margin-bottom: 20px;
      border: 1px solid rgba(59, 130, 246, 0.3);
      text-transform: uppercase;
    }

    /* SECTIONS */
    section { padding: 60px 0; }

    .card-grid {
      display: grid;
      gap: 20px;
      margin-top: 40px;
    }

    .card {
      background: var(--bg-card);
      padding: 25px;
      border-radius: 12px;
      border: 1px solid var(--border-color);
      transition: 0.3s;
    }

    .card:hover { transform: translateY(-5px); border-color: var(--accent-blue); }

    .icon-box {
      font-size: 2rem;
      color: var(--accent-blue);
      margin-bottom: 20px;
    }

    /* PRODUCT SHOWCASE */
    .showcase-item {
      background: var(--bg-card);
      border-radius: 12px;
      padding: 20px;
      margin-bottom: 20px;
      border-left: 4px solid var(--accent-blue);
      display: flex;
      flex-direction: column;
      gap: 15px;
    }

    .feature-list li {
      list-style: none;
      margin-bottom: 8px;
      display: flex;
      align-items: center;
      gap: 10px;
      color: var(--text-white);
      font-size: 0.95rem;
    }

    .check-mark { color: var(--accent-blue); font-weight: bold; font-size: 1.1rem; }

    .product-cover {
      width: 100%;
      height: 220px;
      background: #0f172a;
      border: 1px dashed #334155;
      border-radius: 8px;
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--text-light);
      font-size: 0.9rem;
      text-align: center;
      padding: 20px;
      overflow: hidden;
      object-fit: cover;
      box-shadow: 0 4px 12px rgba(0,0,0,0.3);
    }

    .showcase-text { flex: 1; padding-left: 10px; }

    /* TRANSFORMATIONS SECTION */
    .transformation-section {
      background: #0b1120;
      border-top: 1px solid var(--border-color);
    }

    .tf-grid {
      display: grid;
      gap: 20px;
      margin-top: 30px;
    }

    .tf-card {
      background: var(--bg-card);
      border-radius: 12px;
      overflow: hidden;
      border: 1px solid var(--border-color);
    }

    .tf-image-container {
      position: relative;
      height: 250px;
      background: #0f172a;
      overflow: hidden;
    }

    .tf-image-container img {
      width: 100%;
      height: 100%;
      object-fit: cover;
    }

    .tf-badge {
      position: absolute;
      top: 10px;
      right: 10px;
      background: var(--accent-blue);
      color: white;
      padding: 4px 10px;
      border-radius: 4px;
      font-size: 0.8rem;
      font-weight: 700;
    }

    .tf-info {
      padding: 20px;
      text-align: center;
    }

    .tf-name {
      font-family: 'Oswald';
      font-size: 1.2rem;
      color: var(--text-white);
      margin-bottom: 5px;
    }

    .tf-story {
      color: var(--text-light);
      font-size: 0.9rem;
      font-style: italic;
    }

    /* REVIEWS */
    .review-grid {
      display: grid;
      gap: 20px;
      margin-top: 30px;
    }

    .review-card {
      background: var(--bg-card);
      padding: 20px;
      border-radius: 12px;
      border: 1px solid var(--border-color);
    }
    
    .stars { color: var(--accent-blue); margin-bottom: 15px; font-size: 1.2rem; }
    .review-text { 
      color: var(--text-white); 
      margin-bottom: 20px; 
      font-style: italic; 
      font-size: 1.05rem;
    }
    
    .reviewer-info {
      display: flex;
      align-items: center;
      gap: 12px;
      border-top: 1px solid rgba(255,255,255,0.1);
      padding-top: 15px;
    }
    
    .avatar {
      width: 48px;
      height: 48px;
      border-radius: 50%;
      background: #1e293b;
      object-fit: cover;
      border: 2px solid var(--accent-blue);
    }
    
    .reviewer-details h4 {
      font-family: 'Inter';
      font-size: 0.95rem;
      font-weight: 700;
      margin-bottom: 2px;
      color: var(--text-white);
    }
    
    .reviewer-details span {
      font-size: 0.8rem;
      color: var(--text-light);
    }

    /* PRICING */
    .pricing-wrapper {
      background: linear-gradient(180deg, #1e293b 0%, #0b1120 100%);
      border: 1px solid var(--accent-blue);
      border-radius: 20px;
      padding: 40px 20px;
      text-align: center;
      max-width: 500px;
      margin: 0 auto;
      box-shadow: 0 20px 50px rgba(0,0,0,0.8);
      position: relative;
      overflow: hidden;
    }

    .price-val {
      font-size: 4rem;
      font-weight: 700;
      font-family: 'Oswald';
      color: var(--text-white);
      line-height: 1;
      margin: 10px 0;
    }

    .price-old {
      text-decoration: line-through;
      color: var(--text-light);
      font-size: 1.2rem;
    }

    /* FAQ */
    details {
      background: var(--bg-card);
      margin-bottom: 15px;
      border-radius: 8px;
      border: 1px solid var(--border-color);
      overflow: hidden;
    }
    
    summary {
      padding: 20px;
      font-weight: 700;
      cursor: pointer;
      list-style: none;
      color: var(--text-white);
      position: relative;
      padding-right: 40px;
      font-size: 1rem;
    }
    
    summary::after {
      content: "+";
      position: absolute;
      right: 20px;
      font-size: 1.5rem;
      color: var(--accent-blue);
    }
    
    details[open] summary::after { content: "-"; }
    
    .answer-box {
      padding: 20px;
      border-top: 1px solid rgba(255,255,255,0.1);
      color: var(--text-white);
      font-size: 1rem;
      background: #0f172a;
    }

    /* FOOTER */
    footer {
      border-top: 1px solid var(--border-color);
      padding: 40px 20px;
      text-align: center;
      font-size: 0.8rem;
      color: var(--text-white);
      background: #05080f;
    }

    footer a { color: var(--text-white); text-decoration: none; }

    /* BACK IMAGE BELOW BUTTON */
    .back-silhouette {
      max-width: 100%;
      height: auto;
      width: 250px;
      margin-top: 25px;
      opacity: 0.9;
      filter: brightness(0.85) contrast(1.1);
      display: block;
      border-radius: 8px;
    }

    /* DESKTOP RESPONSIVENESS */
    @media (min-width: 768px) {
      h1 { font-size: 4rem; }
      .card-grid { grid-template-columns: repeat(2, 1fr); }
      
      .showcase-item { flex-direction: row; }
      .showcase-text { padding-left: 20px; }
      .product-cover { width: 180px; height: 220px; flex-shrink: 0; }
      
      .tf-grid { grid-template-columns: repeat(2, 1fr); }
      .review-grid { grid-template-columns: repeat(3, 1fr); }
      
      .btn { width: auto; display: inline-block; }
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
    <span class="hero-tag">For Fathers Over 35</span>
    <h1>Skip The Gym.<br>Build Your Body.</h1>
    
    <p style="color: var(--text-light); max-width: 600px; margin: 0 auto 30px auto; font-size: 1.1rem;">
      A simple 90-day protocol to lose belly fat, gain strength, and improve energy—without spending hours in the gym.
    </p>
    
    <a href="#pricing" class="btn">START MY TRANSFORMATION</a>

    <div style="margin-top: 30px; font-size: 0.9rem; color: var(--text-light);">
      Based on David Carter's story • Age 52 Transformation
    </div>
  </header>

  <!-- BENEFITS -->
  <section id="benefits">
    <div class="container">
      <h2 class="reveal" style="text-align: center;">Why This Works For Dads</h2>
      <div class="card-grid">
        <div class="card reveal stagger-1">
          <div class="icon-box">⏱️</div>
          <h3>Under 45 Mins</h3>
          <p>Structured home workouts. Zero commute time required.</p>
        </div>
        <div class="card reveal stagger-2">
          <div class="icon-box">🍔</div>
          <h3>No Diet Struggles</h3>
          <p>Eat enough food to build muscle without starving yourself.</p>
        </div>
        <div class="card reveal stagger-3">
          <div class="icon-box">📊</div>
          <h3>Track Everything</h3>
          <p>Digital dashboard included to see results instantly.</p>
        </div>
        <div class="card reveal stagger-4">
          <div class="icon-box">🛡️</div>
          <h3>Lifetime Access</h3>
          <p>Pay once, keep the guides forever. Updated for life.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- WHAT'S INCLUDED -->
  <section id="content" style="background: #05080f;">
    <div class="container">
      <h2 class="reveal" style="text-align: center;">Everything You Get</h2>
      
      <div class="showcase-item reveal stagger-1">
        <!-- EBOOK COVER PLACEHOLDER - REPLACE WITH YOUR ACTUAL COVER IMAGE -->
        <img src="https://placehold.co/200x250/0f172a/3b82f6?text=WORKOUT+GUIDE" alt="Workout Cover" class="product-cover">
        <div class="showcase-text">
          <h3>Phase 1: Wake Up Protocol</h3>
          <ul class="feature-list">
            <li><span class="check-mark">✓</span> Comprehensive PDF Workbooks</li>
            <li><span class="check-mark">✓</span> Calisthenics Focused</li>
            <li><span class="check-mark">✓</span> Minimal Equipment Needed</li>
          </ul>
        </div>
      </div>

      <div class="showcase-item reveal stagger-2">
        <!-- MEAL PLAN COVER PLACEHOLDER - REPLACE WITH YOUR ACTUAL COVER IMAGE -->
        <img src="https://placehold.co/200x250/0f172a/3b82f6?text=MEAL+PLAN" alt="Meal Plan Cover" class="product-cover">
        <div class="showcase-text">
          <h3>The Nutrition Blueprint</h3>
          <ul class="feature-list">
            <li><span class="check-mark">✓</span> Family-Friendly Meals</li>
            <li><span class="check-mark">✓</span> Grocery Shopping Lists</li>
            <li><span class="check-mark">✓</span> Meal Prep Shortcuts</li>
          </ul>
        </div>
      </div>
    </div>
  </section>

  <!-- REAL RESULTS -->
  <section id="transformations" class="transformation-section">
    <div class="container">
      <h2 class="reveal" style="text-align: center;">Real Results From Real Dads</h2>
      
      <div class="tf-grid">
        
        <!-- Story 1 -->
        <div class="tf-card reveal">
          <div class="tf-image-container">
            <img src="https://images.unsplash.com/photo-1571019614242-c5c5dee9f50b?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Body Transformation">
            <div class="tf-badge">Lost 30lbs</div>
          </div>
          <div class="tf-info">
            <div class="tf-name">James W., 48</div>
            <p class="tf-story">"Engineer. Used to come home too tired to lift a finger. Now I have more energy than my kids."</p>
          </div>
        </div>

        <!-- Story 2 -->
        <div class="tf-card reveal stagger-1">
          <div class="tf-image-container">
             <img src="https://images.unsplash.com/photo-1526506118085-60ce8714f8c5?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Body Transformation">
            <div class="tf-badge">Fat Loss + Muscle</div>
          </div>
          <div class="tf-info">
            <div class="tf-name">Michael R., 55</div>
            <p class="tf-story">"Father of 3. I lost the gut that had been there for 15 years just by eating smarter."</p>
          </div>
        </div>

        <!-- Story 3 -->
        <div class="tf-card reveal stagger-2">
          <div class="tf-image-container">
             <img src="https://images.unsplash.com/photo-1583454110551-21f2fa2afe61?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Body Transformation">
            <div class="tf-badge">Strength Gain</div>
          </div>
          <div class="tf-info">
            <div class="tf-name">David C., 52</div>
            <p class="tf-story">"I was skeptical at first. Now I've hit numbers I haven't seen since my 20s."</p>
          </div>
        </div>

        <!-- Story 4 -->
        <div class="tf-card reveal stagger-3">
          <div class="tf-image-container">
             <img src="https://images.unsplash.com/photo-1517836357463-d25dfeac3438?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80" alt="Body Transformation">
            <div class="tf-badge">Total Refill</div>
          </div>
          <div class="tf-info">
            <div class="tf-name">Thomas K., 60</div>
            <p class="tf-story">"Thought I was past prime. My wife noticed my clothes fitting differently within week 3."</p>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- PRICING -->
  <section id="pricing" class="reveal">
    <div class="container">
      <div class="pricing-wrapper">
        <h3>Get Instant Access</h3>
        <div class="price-old">$197 Value</div>
        <div class="price-val">$47</div>
        <p style="color: var(--text-light); margin-bottom: 20px;">One-time payment. Lifetime access.</p>
        
        <ul class="feature-list" style="display: inline-block; text-align: left; padding-left: 20px; margin-bottom: 30px;">
          <li style="justify-content: flex-start;"><span class="check-mark">+</span> 90-Day Workout Guide</li>
          <li style="justify-content: flex-start;"><span class="check-mark">+</span> Meal Prep Cookbook</li>
          <li style="justify-content: flex-start;"><span class="check-mark">+</span> Digital Tracker</li>
        </ul>

        <br>

        <!-- SHOPIFY LINK HERE -->
        <a href="https://your-shopify-checkout-link.com/products/the-iron-dad-system" class="btn">BUY NOW →</a>
        
        <!-- MAN'S BACK IMAGE (Dark PNG) -->
        <img src="https://images.unsplash.com/photo-1534438327276-14e5300c3a48?q=80&w=1000&auto=format&fit=crop" alt="Strong Back" class="back-silhouette">
        
      </div>
    </div>
  </section>

  <footer>
    <p>&copy; 2024 Iron-Dad Systems. All rights reserved.</p>
    <p style="margin-top: 10px;">
      <a href="#">Privacy Policy</a> | <a href="#">Terms of Service</a>
    </p>
  </footer>

  <!-- JAVASCRIPT FOR ANIMATION -->
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
    
    // Trigger on page load
    setTimeout(revealElements, 100);
  </script>

</body>
</html>
