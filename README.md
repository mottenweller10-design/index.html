# index.html
Wedding website
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Hudson & Matthew | Wedding</title>

  <!-- Elegant fonts -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@400;500;600&family=Montserrat:wght@400;500;600&display=swap" rel="stylesheet">

  <style>
    :root {
      --cream: #f7f3eb;
      --white: #fffdf8;
      --green: #748066;
      --green-dark: #59624f;
      --gold: #c8a46b;
      --text: #2f2e2a;
      --muted: #6f6b63;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: "Montserrat", sans-serif;
      background: var(--cream);
      color: var(--text);
      line-height: 1.6;
    }

    img {
      width: 100%;
      display: block;
      object-fit: cover;
    }

    h1, h2, h3 {
      font-family: "Cormorant Garamond", serif;
      font-weight: 500;
    }

    a {
      color: inherit;
      text-decoration: none;
    }

    .container {
      width: min(1100px, 90%);
      margin: auto;
    }

    /* NAV */
    nav {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      z-index: 1000;
      background: rgba(247, 243, 235, 0.94);
      backdrop-filter: blur(10px);
      border-bottom: 1px solid rgba(0,0,0,0.05);
    }

    .nav-inner {
      min-height: 68px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 20px;
    }

    .brand {
      font-family: "Cormorant Garamond", serif;
      font-size: 1.4rem;
      letter-spacing: 1px;
    }

    .nav-links {
      display: flex;
      gap: 24px;
      font-size: 0.75rem;
      text-transform: uppercase;
      letter-spacing: 1.5px;
    }

    .menu-btn {
      display: none;
      background: none;
      border: none;
      font-size: 1.6rem;
      cursor: pointer;
    }

    /* HERO */
    .hero {
      min-height: 100vh;
      display: grid;
      grid-template-columns: 1fr 1fr;
      padding-top: 68px;
      background: var(--white);
    }

    .hero-photo {
      background:
        linear-gradient(rgba(0,0,0,0.05), rgba(0,0,0,0.05)),
        url("images/hero.jpg") center/cover no-repeat;
      min-height: 600px;
    }

    .hero-content {
      display: flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      padding: 60px 30px;
    }

    .eyebrow {
      text-transform: uppercase;
      letter-spacing: 3px;
      font-size: 0.75rem;
      color: var(--gold);
      margin-bottom: 18px;
    }

    .hero h1 {
      font-size: clamp(3.5rem, 7vw, 6.5rem);
      line-height: 0.9;
      letter-spacing: 3px;
      margin-bottom: 20px;
    }

    .hero h1 span {
      display: block;
      font-size: 0.42em;
      font-style: italic;
      margin: 12px 0;
      color: var(--gold);
    }

    .date {
      text-transform: uppercase;
      letter-spacing: 3px;
      font-size: 0.85rem;
      margin-bottom: 8px;
    }

    .location {
      color: var(--muted);
      letter-spacing: 2px;
      font-size: 0.8rem;
      text-transform: uppercase;
      margin-bottom: 30px;
    }

    .btn {
      display: inline-block;
      padding: 14px 28px;
      border: none;
      background: var(--green);
      color: white;
      text-transform: uppercase;
      letter-spacing: 1.5px;
      font-size: 0.75rem;
      cursor: pointer;
      transition: 0.25s;
    }

    .btn:hover {
      background: var(--green-dark);
      transform: translateY(-2px);
    }

    .countdown {
      margin-top: 30px;
      display: flex;
      justify-content: center;
      gap: 22px;
      flex-wrap: wrap;
    }

    .count-box strong {
      display: block;
      font-family: "Cormorant Garamond", serif;
      font-size: 2rem;
    }

    .count-box span {
      font-size: 0.65rem;
      letter-spacing: 1px;
      text-transform: uppercase;
      color: var(--muted);
    }

    /* GENERAL SECTIONS */
    section {
      padding: 100px 0;
    }

    .section-title {
      text-align: center;
      margin-bottom: 50px;
    }

    .section-title h2 {
      font-size: clamp(2.5rem, 5vw, 4rem);
      margin-bottom: 8px;
    }

    .section-title p {
      color: var(--muted);
    }

    /* STORY */
    .story-grid {
      display: grid;
      grid-template-columns: 0.9fr 1.1fr;
      gap: 50px;
      align-items: center;
    }

    .story-text h2 {
      font-size: 3.5rem;
      line-height: 1;
      margin-bottom: 20px;
    }

    .story-text p {
      color: var(--muted);
      margin-bottom: 16px;
    }

    .story-photo img {
      height: 560px;
    }

    /* DETAILS */
    .details {
      background: var(--white);
    }

    .details-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 25px;
    }

    .detail-card {
      background: var(--cream);
      padding: 40px 28px;
      text-align: center;
    }

    .detail-card h3 {
      font-size: 2rem;
      margin-bottom: 14px;
    }

    .detail-card p {
      color: var(--muted);
    }

    /* SCHEDULE */
    .schedule-list {
      max-width: 720px;
      margin: auto;
    }

    .schedule-item {
      display: grid;
      grid-template-columns: 120px 1fr;
      gap: 30px;
      padding: 28px 0;
      border-bottom: 1px solid rgba(0,0,0,0.12);
    }

    .schedule-time {
      font-weight: 600;
      color: var(--green-dark);
    }

    .schedule-item h3 {
      font-size: 1.8rem;
    }

    /* GALLERY */
    .gallery {
      background: var(--white);
    }

    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 12px;
    }

    .gallery-grid img {
      height: 320px;
      transition: transform 0.3s ease;
    }

    .gallery-grid img:hover {
      transform: scale(1.02);
    }

    /* TRAVEL + RSVP */
    .split {
      display: grid;
      grid-template-columns: 1fr 1fr;
    }

    .split-box {
      padding: 80px 10%;
    }

    .split-box.green {
      background: var(--green);
      color: white;
    }

    .split-box.light {
      background: var(--cream);
    }

    .split-box h2 {
      font-size: 3rem;
      margin-bottom: 16px;
    }

    .split-box p {
      margin-bottom: 24px;
    }

    .green .btn {
      background: white;
      color: var(--green-dark);
    }

    /* RSVP FORM */
    form {
      display: grid;
      gap: 15px;
    }

    input,
    select,
    textarea {
      width: 100%;
      padding: 14px;
      border: 1px solid rgba(0,0,0,0.15);
      font-family: inherit;
      font-size: 1rem;
      background: white;
    }

    textarea {
      min-height: 120px;
      resize: vertical;
    }

    /* REGISTRY */
    .registry-links {
      display: flex;
      justify-content: center;
      gap: 16px;
      flex-wrap: wrap;
    }

    /* FAQ */
    .faq {
      background: var(--white);
    }

    details {
      max-width: 760px;
      margin: 0 auto 14px;
      border-bottom: 1px solid rgba(0,0,0,0.14);
      padding: 18px 0;
    }

    summary {
      cursor: pointer;
      font-weight: 600;
    }

    details p {
      padding-top: 12px;
      color: var(--muted);
    }

    /* FOOTER */
    footer {
      text-align: center;
      padding: 60px 20px;
      background: var(--green-dark);
      color: white;
    }

    footer h2 {
      font-size: 2.8rem;
      margin-bottom: 10px;
    }

    footer p {
      opacity: 0.8;
      font-size: 0.85rem;
    }

    /* MOBILE */
    @media (max-width: 850px) {
      .nav-links {
        display: none;
        position: absolute;
        top: 68px;
        left: 0;
        width: 100%;
        flex-direction: column;
        background: var(--cream);
        padding: 25px;
        text-align: center;
      }

      .nav-links.open {
        display: flex;
      }

      .menu-btn {
        display: block;
      }

      .hero,
      .story-grid,
      .split {
        grid-template-columns: 1fr;
      }

      .hero-photo {
        min-height: 60vh;
        order: 1;
      }

      .hero-content {
        order: 2;
        padding: 70px 25px;
      }

      .details-grid {
        grid-template-columns: 1fr;
      }

      .gallery-grid {
        grid-template-columns: 1fr 1fr;
      }

      .story-photo img {
        height: 420px;
      }
    }

    @media (max-width: 520px) {
      section {
        padding: 75px 0;
      }

      .gallery-grid {
        grid-template-columns: 1fr;
      }

      .gallery-grid img {
        height: 380px;
      }

      .schedule-item {
        grid-template-columns: 1fr;
        gap: 5px;
      }
    }
  </style>
</head>

<body>

  <!-- NAVIGATION -->
  <nav>
    <div class="container nav-inner">
      <a href="#home" class="brand">Jessica & Michael</a>

      <div class="nav-links" id="navLinks">
        <a href="#story">Our Story</a>
        <a href="#details">Details</a>
        <a href="#schedule">Schedule</a>
        <a href="#travel">Travel</a>
        <a href="#rsvp">RSVP</a>
        <a href="#registry">Registry</a>
        <a href="#faq">FAQ</a>
      </div>

      <button class="menu-btn" onclick="toggleMenu()">☰</button>
    </div>
  </nav>

  <!-- HERO -->
  <section class="hero" id="home">

    <div class="hero-photo"></div>

    <div class="hero-content">
      <div>
        <p class="eyebrow">We're getting married</p>

        <h1>
          Jessica
          <span>and</span>
          Michael
        </h1>

        <p class="date">October 10, 2027</p>
        <p class="location">Sonoma, California</p>

        <a href="#rsvp" class="btn">RSVP Now</a>

        <div class="countdown">
          <div class="count-box">
            <strong id="days">0</strong>
            <span>Days</span>
          </div>

          <div class="count-box">
            <strong id="hours">0</strong>
            <span>Hours</span>
          </div>

          <div class="count-box">
            <strong id="minutes">0</strong>
            <span>Minutes</span>
          </div>

          <div class="count-box">
            <strong id="seconds">0</strong>
            <span>Seconds</span>
          </div>
        </div>
      </div>
    </div>

  </section>

  <!-- OUR STORY -->
  <section id="story">
    <div class="container story-grid">

      <div class="story-text">
        <p class="eyebrow">Our Story</p>
        <h2>The best adventure so far.</h2>

        <p>
          We met in college, became best friends, and somewhere along the way
          realized we never wanted the adventure to end.
        </p>

        <p>
          We can't wait to celebrate this next chapter surrounded by the people
          we love most.
        </p>
      </div>

      <div class="story-photo">
        <img src="images/story.jpg" alt="Jessica and Michael">
      </div>

    </div>
  </section>

  <!-- WEDDING DETAILS -->
  <section class="details" id="details">

    <div class="container">

      <div class="section-title">
        <p class="eyebrow">The Wedding</p>
        <h2>Wedding Details</h2>
        <p>Everything you need to know for our special day.</p>
      </div>

      <div class="details-grid">

        <div class="detail-card">
          <h3>Ceremony</h3>
          <p>4:00 PM</p>
          <p>Beltane Ranch</p>
          <p>Glen Ellen, California</p>
        </div>

        <div class="detail-card">
          <h3>Reception</h3>
          <p>6:00 PM</p>
          <p>Dinner, drinks & dancing</p>
          <p>Beltane Ranch</p>
        </div>

        <div class="detail-card">
          <h3>Attire</h3>
          <p>Semi-Formal</p>
          <p>Cocktail attire encouraged</p>
        </div>

      </div>

    </div>
  </section>

  <!-- SCHEDULE -->
  <section id="schedule">

    <div class="container">

      <div class="section-title">
        <p class="eyebrow">October 10, 2027</p>
        <h2>Schedule</h2>
      </div>

      <div class="schedule-list">

        <div class="schedule-item">
          <div class="schedule-time">3:30 PM</div>
          <div>
            <h3>Guest Arrival</h3>
            <p>Please arrive and find your seat before the ceremony.</p>
          </div>
        </div>

        <div class="schedule-item">
          <div class="schedule-time">4:00 PM</div>
          <div>
            <h3>Ceremony</h3>
            <p>We'll officially say "I do."</p>
          </div>
        </div>

        <div class="schedule-item">
          <div class="schedule-time">5:00 PM</div>
          <div>
            <h3>Cocktail Hour</h3>
            <p>Drinks, appetizers, and photos.</p>
          </div>
        </div>

        <div class="schedule-item">
          <div class="schedule-time">6:00 PM</div>
          <div>
            <h3>Reception</h3>
            <p>Dinner, toasts, cake, and dancing.</p>
          </div>
        </div>

      </div>

    </div>

  </section>

  <!-- GALLERY -->
  <section class="gallery">

    <div class="container">

      <div class="section-title">
        <p class="eyebrow">Together</p>
        <h2>A Few Favorite Moments</h2>
      </div>

      <div class="gallery-grid">

        <img src="images/photo1.jpg" alt="Couple photo">
        <img src="images/photo2.jpg" alt="Couple photo">
        <img src="images/photo3.jpg" alt="Couple photo">
        <img src="images/photo4.jpg" alt="Couple photo">
        <img src="images/photo5.jpg" alt="Couple photo">
        <img src="images/photo6.jpg" alt="Couple photo">

      </div>

    </div>

  </section>

  <!-- TRAVEL -->
  <section class="split" id="travel">

    <div class="split-box light">
      <p class="eyebrow">Travel & Stay</p>
      <h2>Travel Information</h2>

      <p>
        We're so grateful you're traveling to celebrate with us.
        Add your recommended hotels, airports, transportation, and local
        information here.
      </p>

      <p>
        <strong>Nearest airport:</strong><br>
        Sonoma County Airport
      </p>

      <p>
        <strong>Recommended hotel:</strong><br>
        Add your hotel information here.
      </p>
    </div>

    <!-- RSVP -->
    <div class="split-box green" id="rsvp">

      <p class="eyebrow" style="color:#ead1a1;">Kindly Reply</p>
      <h2>RSVP</h2>

      <p>Please RSVP by August 15, 2027.</p>

      <form id="rsvpForm">

        <input
          type="text"
          id="guestName"
          placeholder="Your full name"
          required
        >

        <input
          type="email"
          id="guestEmail"
          placeholder="Email address"
          required
        >

        <select id="attendance" required>
          <option value="">Will you be attending?</option>
          <option value="Yes">Joyfully accepts</option>
          <option value="No">Regretfully declines</option>
        </select>

        <select id="meal">
          <option value="">Meal preference</option>
          <option>Chicken</option>
          <option>Beef</option>
          <option>Vegetarian</option>
        </select>

        <textarea
          id="message"
          placeholder="Message for the couple"
        ></textarea>

        <button class="btn" type="submit">
          Submit RSVP
        </button>

      </form>

      <p id="rsvpMessage" style="margin-top:18px;"></p>

    </div>

  </section>

  <!-- REGISTRY -->
  <section id="registry">

    <div class="container">

      <div class="section-title">
        <p class="eyebrow">Registry</p>
        <h2>Your Presence Is Our Present</h2>
        <p>
          If you would like to celebrate with a gift, our registries are below.
        </p>
      </div>

      <div class="registry-links">
        <a href="#" class="btn">Amazon Registry</a>
        <a href="#" class="btn">Target Registry</a>
        <a href="#" class="btn">Honeymoon Fund</a>
      </div>

    </div>

  </section>

  <!-- FAQ -->
  <section class="faq" id="faq">

    <div class="container">

      <div class="section-title">
        <p class="eyebrow">Questions</p>
        <h2>FAQ</h2>
      </div>

      <details>
        <summary>Can I bring a plus one?</summary>
        <p>
          Please check your invitation or RSVP information to see whether
          a plus one has been included.
        </p>
      </details>

      <details>
        <summary>Are children invited?</summary>
        <p>
          Add your preferred wording here regarding children at the wedding.
        </p>
      </details>

      <details>
        <summary>Is there parking?</summary>
        <p>
          Add parking and transportation details here.
        </p>
      </details>

      <details>
        <summary>What should I wear?</summary>
        <p>
          Our dress code is semi-formal / cocktail attire.
        </p>
      </details>

    </div>

  </section>

  <!-- FOOTER -->
  <footer>
    <h2>J & M</h2>
    <p>We can't wait to celebrate with you!</p>
    <p style="margin-top:18px;">October 10, 2027 · Sonoma, California</p>
  </footer>


  <script>
    // MOBILE MENU
    function toggleMenu() {
      document.getElementById("navLinks").classList.toggle("open");
    }

    document.querySelectorAll(".nav-links a").forEach(link => {
      link.addEventListener("click", () => {
        document.getElementById("navLinks").classList.remove("open");
      });
    });


    // COUNTDOWN
    const weddingDate = new Date("October 10, 2027 16:00:00").getTime();

    function updateCountdown() {
      const now = new Date().getTime();
      const distance = weddingDate - now;

      if (distance <= 0) {
        document.querySelector(".countdown").innerHTML =
          "<strong>Today is the day! ♥</strong>";
        return;
      }

      const days =
        Math.floor(distance / (1000 * 60 * 60 * 24));

      const hours =
        Math.floor(
          (distance % (1000 * 60 * 60 * 24))
          / (1000 * 60 * 60)
        );

      const minutes =
        Math.floor(
          (distance % (1000 * 60 * 60))
          / (1000 * 60)
        );

      const seconds =
        Math.floor(
          (distance % (1000 * 60))
          / 1000
        );

      document.getElementById("days").textContent = days;
      document.getElementById("hours").textContent = hours;
      document.getElementById("minutes").textContent = minutes;
      document.getElementById("seconds").textContent = seconds;
    }

    updateCountdown();
    setInterval(updateCountdown, 1000);


    // DEMO RSVP
    // This only shows a confirmation on the website.
    // It does NOT save the response anywhere yet.
    document
      .getElementById("rsvpForm")
      .addEventListener("submit", function(event) {

        event.preventDefault();

        const name =
          document.getElementById("guestName").value;

        document.getElementById("rsvpMessage").textContent =
          `Thank you, ${name}! Your RSVP has been entered.`;

        this.reset();
      });

  </script>

</body>
</html>