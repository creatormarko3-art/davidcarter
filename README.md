<!DOCTYPE html>
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
      transition: all 0.8s cubic-bezier(0.2, 0.8, 0.2, 1);
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
    section { padding: 80px 0; }

    .card-grid {
      display: grid;
      gap: 20px;
      margin-top: 40px;
    }

    .card {
      background: var(--bg-card);
      padding: 30px;
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
      padding: 30px;
      margin-bottom: 30px;
      border-left: 4px solid var(--accent-blue);
      display: flex;
      flex-direction: column;
      gap: 20px;
    }

    .feature-list li {
      list-style: none;
      margin-bottom: 12px;
      display: flex;
      align-items: center;
      gap: 10px;
      color: var(--text-white);
    }

    .check-mark { color: var(--accent-blue); font-weight: bold; font-size: 1.2rem; }

    .placeholder-img {
      flex: 1;
      height: 250px;
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
    }

    .showcase-text { flex: 1; }

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

    /* DESKTOP RESPONSIVENESS */
    @media (min-width: 768px) {
      h1 { font-size: 4rem; }
      .card-grid { grid-template-columns: repeat(2, 1fr); }
      
      .showcase-item { flex-direction: row; }
      .showcase-text { padding-left: 20px; }
      
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

    <div style="margin-top: 40px; font-size: 0.9rem; color: var(--text-light);">
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
        <div class="placeholder-img">[WORKOUT PDF COVER IMAGE HERE]</div>
        <div class="showcase-text">
          <h3>Phase 1: Wake Up Protocol</h3>
          <ul class="feature-list">
            <li><span class="check-mark">✓</span> Full Video Guides</li>
            <li><span class="check-mark">✓</span> Calisthenics Focused</li>
            <li><span class="check-mark">✓</span> Minimal Equipment Needed</li>
          </ul>
        </div>
      </div>

      <div class="showcase-item reveal stagger-2">
        <div class="placeholder-img">[MEAL PLAN BOOK COVER HERE]</div>
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

  <!-- REVIEWS -->
  <section id="reviews">
    <div class="container">
      <h2 class="reveal" style="text-align: center;">Real Results From Real Dads</h2>
      <div class="review-grid">
        
        <div class="review-card reveal stagger-1">
          <div class="stars">★★★★★</div>
          <p class="review-text">"I lost 15lbs in month 1. It's not magic, it just fits my schedule."</p>
          <div class="reviewer-info">
            <img src="https://randomuser.me/api/portraits/men/32.jpg" alt="James" class="avatar">
            <div class="reviewer-details">
              <h4>James W., 48</h4>
              <span>Engineer</span>
            </div>
          </div>
        </div>

        <div class="review-card reveal stagger-2">
          <div class="stars">★★★★★</div>
          <p class="review-text">"Stopped guessing at the gym. The tracker keeps me honest even on busy days."</p>
          <div class="reviewer-info">
            <img src="https://randomuser.me/api/portraits/men/45.jpg" alt="David" class="avatar">
            <div class="reviewer-details">
              <h4>David C., 52</h4>
              <span>Sales Director</span>
            </div>
          </div>
        </div>

        <div class="review-card reveal stagger-3">
          <div class="stars">★★★★★</div>
          <p class="review-text">"Finally feel energetic during the school run. The meals were simple."</p>
          <div class="reviewer-info">
            <img src="https://randomuser.me/api/portraits/men/11.jpg" alt="Mike" class="avatar">
            <div class="reviewer-details">
              <h4>Mike T., 41</h4>
              <span>Teacher</span>
            </div>
          </div>
        </div>

        <div class="review-card reveal stagger-1">
          <div class="stars">★★★★★</div>
          <p class="review-text">"Lost the gut and built arms again. Best investment I've made for myself."</p>
          <div class="reviewer-info">
            <img src="https://randomuser.me/api/portraits/men/65.jpg" alt="Tom" class="avatar">
            <div class="reviewer-details">
              <h4>Tom B., 55</h4>
              <span>Father of 3</span>
            </div>
          </div>
        </div>

        <div class="review-card reveal stagger-2">
          <div class="stars">★★★★★</div>
          <p class="review-text">"The 3x week plan was perfect. I actually finished it before the kids needed lunch."</p>
          <div class="reviewer-info">
            <img src="https://randomuser.me/api/portraits/men/22.jpg" alt="Steve" class="avatar">
            <div class="reviewer-details">
              <h4>Steve R., 44</h4>
              <span>Accountant</span>
            </div>
          </div>
        </div>

        <div class="review-card reveal stagger-3">
          <div class="stars">★★★★★</div>
          <p class="review-text">"My wife noticed first! She asked how I had the energy to play with the kids again."</p>
          <div class="reviewer-info">
            <img src="https://randomuser.me/api/portraits/men/88.jpg" alt="Paul" class="avatar">
            <div class="reviewer-details">
              <h4>Paul K., 49</h4>
              <span>IT Manager</span>
            </div>
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

        <!-- REPLACE WITH YOUR SHOPIFY CHECKOUT LINK BELOW -->
        <a href="https://your-shopify-checkout-link.com/products/the-iron-dad-system" class="btn">BUY NOW →</a>
      </div>
    </div>
  </section>

  <!-- FAQ -->
  <section>
    <div class="container">
      <h2 class="text-center" style="margin-bottom: 40px;">Common Questions</h2>
      
      <div class="reveal">
        <details>
          <summary>Do I need a gym?</summary>
          <div class="answer-box">
            No. This program uses calisthenics and bodyweight movements designed to be done in a living room or garage.
          </div>
        </details>
        
        <details>
          <summary>Is this suitable for beginners?</summary>
          <div class="answer-box">
            Yes. Phase 1 is specifically designed to rebuild your foundation safely so you don't get injured when returning to fitness.
          </div>
        </details>

        <details>
          <summary>How long do the workouts take?</summary>
          <div class="answer-box">
            Each workout is high intensity but short. The average session takes about 45 minutes from start to finish.
          </div>
        </details>

        <details>
          <summary>What if I'm over 50?</summary>
          <div class="answer-box">
            Absolutely. Our founder started at 52. The plan focuses on joint health and functional strength rather than heavy lifting.
          </div>
        </details>
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
