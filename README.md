# bijouterie3ors
[index.html](https://github.com/user-attachments/files/26892906/index.html)
```html
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Bijouterie 3 Ors – Chartres</title>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Montserrat:wght@300;400;500;600&display=swap" rel="stylesheet"/>
  <style>
    *, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

    :root {
      --gold:    #b8973a;
      --gold-lt: #d4b96a;
      --purple:  #4a3060;
      --dark:    #1a1a2e;
      --cream:   #faf7f2;
      --white:   #ffffff;
      --text:    #3a3a3a;
    }

    html { scroll-behavior: smooth; }

    body {
      font-family: 'Montserrat', sans-serif;
      background: var(--cream);
      color: var(--text);
      overflow-x: hidden;
    }

    /* ── NAV ── */
    nav {
      position: fixed; top: 0; width: 100%; z-index: 999;
      background: rgba(26,26,46,0.96);
      backdrop-filter: blur(8px);
      display: flex; align-items: center; justify-content: space-between;
      padding: 0 5%;
      height: 70px;
      border-bottom: 1px solid var(--gold);
    }
    .nav-logo {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.8rem; font-weight: 600;
      color: var(--gold-lt); letter-spacing: 4px;
    }
    .nav-logo span { color: var(--white); font-weight: 300; }
    .nav-links { display: flex; gap: 2rem; list-style: none; }
    .nav-links a {
      color: #ccc; text-decoration: none;
      font-size: .75rem; font-weight: 500; letter-spacing: 2px; text-transform: uppercase;
      transition: color .3s;
    }
    .nav-links a:hover { color: var(--gold-lt); }

    /* ── HERO ── */
    .hero {
      position: relative; height: 100vh; min-height: 600px;
      display: flex; align-items: center; justify-content: center; text-align: center;
      overflow: hidden;
    }
    .hero-bg {
      position: absolute; inset: 0;
      background: url('https://images.unsplash.com/photo-1515562141207-7a88fb7ce338?w=1600&q=80') center/cover no-repeat;
      filter: brightness(.35);
    }
    /* purple-gold gradient overlay */
    .hero-bg::after {
      content: '';
      position: absolute; inset: 0;
      background: linear-gradient(135deg, rgba(74,48,96,.55) 0%, rgba(26,26,46,.6) 60%, rgba(184,151,58,.15) 100%);
    }
    .hero-content { position: relative; z-index: 1; padding: 0 1rem; }
    .hero-eyebrow {
      font-size: .7rem; letter-spacing: 5px; text-transform: uppercase;
      color: var(--gold-lt); margin-bottom: 1.2rem;
    }
    .hero h1 {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(3rem, 8vw, 6.5rem);
      font-weight: 300; color: var(--white);
      line-height: 1.05; letter-spacing: 6px;
    }
    .hero h1 strong { color: var(--gold-lt); font-weight: 600; }
    .hero-sub {
      margin-top: 1.4rem;
      font-size: .85rem; letter-spacing: 3px; text-transform: uppercase;
      color: rgba(255,255,255,.7);
    }
    .hero-divider {
      width: 80px; height: 1px;
      background: linear-gradient(90deg, transparent, var(--gold), transparent);
      margin: 2rem auto;
    }
    .btn-primary {
      display: inline-block;
      padding: .9rem 2.8rem;
      border: 1px solid var(--gold);
      color: var(--gold-lt); text-decoration: none;
      font-size: .75rem; letter-spacing: 3px; text-transform: uppercase;
      transition: all .35s;
    }
    .btn-primary:hover { background: var(--gold); color: var(--dark); }

    /* ── SECTION GENERIC ── */
    section { padding: 90px 5%; }
    .section-tag {
      font-size: .65rem; letter-spacing: 5px; text-transform: uppercase;
      color: var(--gold); margin-bottom: .8rem;
    }
    .section-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(2rem, 4vw, 3rem);
      font-weight: 300; color: var(--dark);
      line-height: 1.15;
    }
    .section-title em { color: var(--purple); font-style: italic; }
    .gold-rule {
      width: 60px; height: 2px;
      background: linear-gradient(90deg, var(--gold), var(--gold-lt));
      margin: 1.2rem 0 2rem;
    }

    /* ── ABOUT ── */
    #about { background: var(--white); }
    .about-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 60px; align-items: center;
      max-width: 1200px; margin: 0 auto;
    }
    .about-img { position: relative; }
    .about-img img {
      width: 100%; display: block;
      border: 1px solid rgba(184,151,58,.3);
    }
    .about-img .badge {
      position: absolute; bottom: -20px; right: -20px;
      background: var(--purple);
      color: var(--gold-lt);
      padding: 1.2rem 1.5rem;
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.1rem; text-align: center; line-height: 1.3;
    }
    .about-text p {
      font-size: .88rem; line-height: 1.9; color: #555;
      margin-bottom: 1.2rem;
    }
    .stat-row { display: flex; gap: 2.5rem; margin-top: 2rem; }
    .stat { text-align: center; }
    .stat .num {
      font-family: 'Cormorant Garamond', serif;
      font-size: 2.4rem; color: var(--gold); font-weight: 600;
    }
    .stat .label {
      font-size: .65rem; letter-spacing: 2px; text-transform: uppercase; color: #888;
    }

    /* ── SERVICES ── */
    #services { background: var(--dark); }
    #services .section-title { color: var(--white); }
    #services .section-tag { color: var(--gold-lt); }
    .services-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
      gap: 2px; margin-top: 3rem;
      max-width: 1200px;
    }
    .service-card {
      background: rgba(255,255,255,.04);
      border: 1px solid rgba(184,151,58,.18);
      padding: 2.5rem 2rem;
      transition: background .3s, border-color .3s;
    }
    .service-card:hover {
      background: rgba(184,151,58,.08);
      border-color: var(--gold);
    }
    .service-icon { font-size: 2rem; margin-bottom: 1rem; }
    .service-card h3 {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.3rem; color: var(--gold-lt);
      margin-bottom: .7rem;
    }
    .service-card p { font-size: .8rem; line-height: 1.8; color: #aaa; }

    /* ── COLLECTIONS ── */
    #collections { background: var(--cream); }
    .collections-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 1.5rem; margin-top: 3rem;
      max-width: 1200px;
    }
    .coll-card {
      position: relative; overflow: hidden;
      border: 1px solid rgba(184,151,58,.2);
      cursor: pointer;
    }
    .coll-card img { width: 100%; height: 320px; object-fit: cover; display: block; transition: transform .5s; }
    .coll-card:hover img { transform: scale(1.05); }
    .coll-card .overlay {
      position: absolute; bottom: 0; left: 0; right: 0;
      background: linear-gradient(transparent, rgba(26,26,46,.88));
      padding: 2rem 1.5rem 1.5rem;
      color: var(--white);
    }
    .coll-card .overlay h3 {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.5rem; font-weight: 300; letter-spacing: 2px;
    }
    .coll-card .overlay span {
      font-size: .65rem; letter-spacing: 3px; text-transform: uppercase; color: var(--gold-lt);
    }

    /* ── GALLERY ── */
    #gallery { background: var(--white); padding-bottom: 60px; }
    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      grid-template-rows: auto auto;
      gap: 6px; max-width: 1200px; margin-top: 2rem;
    }
    .gallery-grid img {
      width: 100%; height: 260px; object-fit: cover; display: block;
      filter: brightness(.95); transition: filter .3s, transform .4s;
    }
    .gallery-grid img:hover { filter: brightness(1.05); transform: scale(1.02); }
    .gallery-grid .tall { grid-row: span 2; }
    .gallery-grid .tall img { height: 526px; }

    /* ── REVIEWS ── */
    #reviews { background: var(--purple); }
    #reviews .section-tag { color: var(--gold-lt); }
    #reviews .section-title { color: var(--white); }
    #reviews .gold-rule { background: linear-gradient(90deg, var(--gold-lt), transparent); }
    .reviews-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
      gap: 1.5rem; margin-top: 2.5rem;
      max-width: 1200px;
    }
    .review-card {
      background: rgba(255,255,255,.08);
      border: 1px solid rgba(212,185,106,.25);
      padding: 2rem;
      transition: background .3s;
    }
    .review-card:hover { background: rgba(255,255,255,.13); }
    .stars { color: var(--gold-lt); font-size: 1rem; margin-bottom: .8rem; letter-spacing: 3px; }
    .review-text {
      font-size: .83rem; line-height: 1.8; color: rgba(255,255,255,.85);
      font-style: italic; margin-bottom: 1rem;
    }
    .review-author { font-size: .7rem; letter-spacing: 2px; text-transform: uppercase; color: var(--gold-lt); }

    /* ── CONTACT ── */
    #contact { background: var(--dark); }
    #contact .section-title { color: var(--white); }
    .contact-wrapper {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 60px; max-width: 1100px; margin-top: 3rem;
    }
    .contact-info h3 {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.4rem; color: var(--gold-lt); margin-bottom: 1.5rem;
    }
    .info-item { display: flex; gap: 1rem; margin-bottom: 1.4rem; align-items: flex-start; }
    .info-icon { font-size: 1.3rem; flex-shrink: 0; margin-top: 2px; }
    .info-item p { font-size: .82rem; line-height: 1.7; color: #bbb; }
    .info-item p strong { color: var(--gold-lt); display: block; font-weight: 500; margin-bottom: .2rem; }
    .hours-table { width: 100%; border-collapse: collapse; margin-top: .5rem; }
    .hours-table td { font-size: .78rem; color: #bbb; padding: .3rem 0; }
    .hours-table td:first-child { color: var(--gold-lt); font-weight: 500; width: 45%; }
    .map-container { position: relative; }
    .map-container iframe {
      width: 100%; height: 380px; border: 0;
      filter: grayscale(.2) contrast(1.05);
      border: 1px solid rgba(184,151,58,.3);
    }

    /* ── FOOTER ── */
    footer {
      background: #0d0d1a;
      padding: 2.5rem 5%;
      display: flex; align-items: center; justify-content: space-between;
      flex-wrap: wrap; gap: 1rem;
      border-top: 1px solid rgba(184,151,58,.2);
    }
    .footer-logo {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.4rem; color: var(--gold-lt); letter-spacing: 4px;
    }
    footer p { font-size: .7rem; color: #555; text-align: center; flex: 1; }

    /* ── RESPONSIVE ── */
    @media (max-width: 900px) {
      .about-grid, .contact-wrapper { grid-template-columns: 1fr; }
      .about-img .badge { right: 0; }
      .gallery-grid { grid-template-columns: 1fr 1fr; }
      .gallery-grid .tall, .gallery-grid .tall img { grid-row: auto; height: 260px; }
      nav { padding: 0 4%; }
      .nav-links { display: none; }
    }
    @media (max-width: 600px) {
      .gallery-grid { grid-template-columns: 1fr; }
      .stat-row { gap: 1.2rem; }
    }
  </style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">3<span>ORS</span></div>
  <ul class="nav-links">
    <li><a href="#about">La Boutique</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#collections">Collections</a></li>
    <li><a href="#reviews">Avis</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
</nav>

<!-- HERO -->
<section class="hero" id="home">
  <div class="hero-bg"></div>
  <div class="hero-content">
    <p class="hero-eyebrow">Bijouterie · Joaillerie · Chartres</p>
    <h1>BIJOUTERIE<br><strong>3 ORS</strong></h1>
    <p class="hero-sub">Vincent Kindmann — Rue de la Tonnellerie, Chartres</p>
    <div class="hero-divider"></div>
    <a href="#collections" class="btn-primary">Découvrir les Collections</a>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="about-grid">
    <div class="about-img">
      <img src="shop-front.jpg" alt="Façade Bijouterie 3 Ors Chartres"
           onerror="this.src='https://images.unsplash.com/photo-1617038220319-276d3cfab638?w=800&q=80'"/>
      <div class="badge">
        Votre bijouterie<br>de <em>confiance</em><br>à Chartres
      </div>
    </div>
    <div class="about-text">
      <p class="section-tag">Notre Histoire</p>
      <h2 class="section-title">Une maison <em>d'excellence</em><br>depuis des générations</h2>
      <div class="gold-rule"></div>
      <p>
        La Bijouterie 3 Ors est une adresse incontournable du cœur de Chartres, portée par une longue tradition familiale de la joaillerie. Installée au <strong>3 Rue de la Tonnellerie</strong>, elle accueille ses clients dans un cadre élégant et lumineux, entièrement dédié au beau.
      </p>
      <p>
        Sous la direction de <strong>Vincent Kindmann</strong>, l'équipe met un point d'honneur à offrir des conseils personnalisés, une sélection rigoureuse de bijoux de qualité et des prestations artisanales soignées. Chaque visite est une expérience unique.
      </p>
      <div class="stat-row">
        <div class="stat"><div class="num">4,3★</div><div class="label">Note Google</div></div>
        <div class="stat"><div class="num">97</div><div class="label">Avis clients</div></div>
        <div class="stat"><div class="num">30+</div><div class="label">Années d'expérience</div></div>
      </div>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section id="services">
  <p class="section-tag">Ce que nous faisons</p>
  <h2 class="section-title" style="color:var(--white)">Nos <em style="color:var(--gold-lt)">Services</em></h2>
  <div class="gold-rule"></div>
  <div class="services-grid">
    <div class="service-card">
      <div class="service-icon">💍</div>
      <h3>Vente de Bijoux</h3>
      <p>Un large choix de bagues, colliers, bracelets, boucles d'oreilles et alliances en or, argent et pierres précieuses, pour tous les goûts et tous les budgets.</p>
    </div>
    <div class="service-card">
      <div class="service-icon">⌚</div>
      <h3>Montres</h3>
      <p>Une sélection de montres de qualité, pour homme et femme, aliant style, précision et savoir-faire horloger.</p>
    </div>
    <div class="service-card">
      <div class="service-icon">🔧</div>
      <h3>Réparation de Bijoux</h3>
      <p>Soudure, remaillage, changement de fermoir, redimensionnement de bagues… Un service de réparation rapide et compétent réalisé avec le plus grand soin.</p>
    </div>
    <div class="service-card">
      <div class="service-icon">✍️</div>
      <h3>Gravure</h3>
      <p>Personnalisez vos bijoux avec une gravure sur mesure : prénom, date, message… Un souvenir impérissable gravé dans l'or.</p>
    </div>
    <div class="service-card">
      <div class="service-icon">🛠️</div>
      <h3>Fabrication Sur Mesure</h3>
      <p>Concrétisez vos envies les plus précieuses. Notre équipe conçoit et fabrique des bijoux uniques selon vos désirs, du croquis à la pièce finale.</p>
    </div>
    <div class="service-card">
      <div class="service-icon">🎁</div>
      <h3>Conseil & Cadeau</h3>
      <p>Vous cherchez le cadeau parfait ? Nos experts vous guident avec bienveillance pour trouver le bijou qui fera vibrer vos proches.</p>
    </div>
  </div>
</section>

<!-- COLLECTIONS -->
<section id="collections">
  <p class="section-tag">Nos Marques & Collections</p>
  <h2 class="section-title">Des pièces <em>d'exception</em></h2>
  <div class="gold-rule"></div>
  <div class="collections-grid">
    <!-- Gringoire -->
    <div class="coll-card">
      <img src="gringoire-collection.jpg" alt="Collection Gringoire"
           onerror="this.src='https://images.unsplash.com/photo-1535632066927-ab7c9ab60908?w=700&q=80'"/>
      <div class="overlay">
        <span>Nouveau · Exclusivité</span>
        <h3>Collection Gringoire</h3>
      </div>
    </div>
    <!-- Rainbow -->
    <div class="coll-card">
      <img src="rainbow-collection.jpg" alt="Rainbow Collection Gringoire"
           onerror="this.src='https://images.unsplash.com/photo-1589128777073-263566ae5e4d?w=700&q=80'"/>
      <div class="overlay">
        <span>Gringoire · Paris 1880</span>
        <h3>Rainbow Collection</h3>
      </div>
    </div>
    <!-- Una Storia -->
    <div class="coll-card">
      <img src="una-storia.jpg" alt="Una Storia"
           onerror="this.src='https://images.unsplash.com/photo-1611591437281-460bfbe1220a?w=700&q=80'"/>
      <div class="overlay">
        <span>Création italienne</span>
        <h3>Una Storia</h3>
      </div>
    </div>
  </div>
</section>

<!-- GALLERY -->
<section id="gallery">
  <p class="section-tag">L'univers de la boutique</p>
  <h2 class="section-title">La <em>Boutique</em></h2>
  <div class="gold-rule"></div>
  <div class="gallery-grid">
    <div class="tall">
      <img src="interior-display.jpg" alt="Vitrines Bijouterie 3 Ors"
           onerror="this.src='https://images.unsplash.com/photo-1573408301185-9146fe634ad0?w=700&q=80'"
           style="height:100%; object-fit:cover;"/>
    </div>
    <div>
      <img src="gringoire-collection.jpg" alt="Collection Gringoire"
           onerror="this.src='https://images.unsplash.com/photo-1535632066927-ab7c9ab60908?w=700&q=80'"/>
    </div>
    <div>
      <img src="una-storia-detail.jpg" alt="Una Storia détail"
           onerror="this.src='https://images.unsplash.com/photo-1611591437281-460bfbe1220a?w=700&q=80'"/>
    </div>
    <div>
      <img src="rainbow-collection.jpg" alt="Rainbow ring"
           onerror="this.src='https://images.unsplash.com/photo-1589128777073-263566ae5e4d?w=700&q=80'"/>
    </div>
    <div>
      <img src="shop-front.jpg" alt="Devanture 3 Ors"
           onerror="this.src='https://images.unsplash.com/photo-1617038220319-276d3cfab638?w=700&q=80'"/>
    </div>
  </div>
</section>

<!-- REVIEWS -->
<section id="reviews">
  <p class="section-tag">Ce que disent nos clients</p>
  <h2 class="section-title">Ils nous font <em style="color:var(--gold-lt)">confiance</em></h2>
  <div class="gold-rule"></div>
  <div class="reviews-grid">

    <div class="review-card">
      <div class="stars">★★★★★</div>
      <p class="review-text">« Très professionnel, très aimable et de très bon conseil. Je vous recommande cette bijouterie. »</p>
      <p class="review-author">— Michel Berardi · Google</p>
    </div>

    <div class="review-card">
      <div class="stars">★★★★★</div>
      <p class="review-text">« Accueillie avec le sourire et conseillé parfaitement ! Bijoux de qualité avec rapport qualité/prix très correct ! Boutique magnifique et bien agencée ! »</p>
      <p class="review-author">— Hervé Levert · Google</p>
    </div>

    <div class="review-card">
      <div class="stars">★★★★★</div>
      <p class="review-text">« Une bijouterie avec beaucoup de beaux choix et des bijoux de qualité. Les conseils sont adaptés et un accueil chaleureux avec de vrais professionnels. »</p>
      <p class="review-author">— Mendez Marie · Google</p>
    </div>

    <div class="review-card">
      <div class="stars">★★★★★</div>
      <p class="review-text">« Notre bijouterie de référence dans la famille. L'accueil, les conseils, les produits ont toujours été au rendez-vous. »</p>
      <p class="review-author">— Julie Bernard · Google</p>
    </div>

    <div class="review-card">
      <div class="stars">★★★★★</div>
      <p class="review-text">« Fidèle client depuis que nous habitons près de Chartres, je recommande vivement les 3 Ors. L'accueil est toujours sympathique, et le professionnalisme toujours au rendez-vous. »</p>
      <p class="review-author">— Christophe Prat · Google</p>
    </div>

    <div class="review-card">
      <div class="stars">★★★★★</div>
      <p class="review-text">« M. Sorel et son équipe sont au top. Amabilité, gentillesse, conseil. Je reviendrais avec plaisir. »</p>
      <p class="review-author">— Valentine · Google</p>
    </div>

    <div class="review-card">
      <div class="stars">★★★★★</div>
      <p class="review-text">« M. Sorel et son équipe assurent un accueil chaleureux et professionnel. Large gamme de produits de qualité et prestations très correctes. C'est une adresse incontournable. »</p>
      <p class="review-author">— Pierre-Alain Besnard · Google</p>
    </div>

    <div class="review-card">
      <div class="stars">★★★★★</div>
      <p class="review-text">« J'ai vécu une expérience exquise dans ce magasin. Le choix entre les divers joyaux est tout simplement cornélien ! Une équipe au top. »</p>
      <p class="review-author">— Family Kombo · Google</p>
    </div>

    <div class="review-card">
      <div class="stars">★★★★★</div>
      <p class="review-text">« Très belle boutique avec de nombreux choix et différents styles ! L'équipe est géniale et à l'écoute de nos envies. J'y trouve toujours mon bonheur ! »</p>
      <p class="review-author">— U Y · Google</p>
    </div>

    <div class="review-card">
      <div class="stars">★★★★★</div>
      <p class="review-text">« Mes grands-parents allaient déjà dans cette bijouterie. Je perpétue cette tradition avec bonheur — une adresse familiale irremplaçable. »</p>
      <p class="review-author">— Pauline M. · Google</p>
    </div>

    <div class="review-card">
      <div class="stars">★★★★★</div>
      <p class="review-text">« J'ai toujours acheté mes bijoux chez M. Sorel. Très professionnel et à l'écoute. »</p>
      <p class="review-author">— Sandrine Rotrou · Google</p>
    </div>

    <div class="review-card">
      <div class="stars">★★★★★</div>
      <p class="review-text">« Belle bijouterie où l'on y trouve un large choix de bijoux et montres. Service réparation rapide et compétent ! Bon accueil et bons conseils. »</p>
      <p class="review-author">— Avis Justacoté · Vérifié</p>
    </div>

  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <p class="section-tag" style="color:var(--gold-lt)">Nous trouver</p>
  <h2 class="section-title" style="color:var(--white)">Venez nous <em style="color:var(--gold-lt)">rendre visite</em></h2>
  <div class="gold-rule"></div>
  <div class="contact-wrapper">
    <div class="contact-info">
      <h3>Informations pratiques</h3>

      <div class="info-item">
        <span class="info-icon">📍</span>
        <p><strong>Adresse</strong>3 Rue de la Tonnellerie<br>28000 Chartres, France</p>
      </div>

      <div class="info-item">
        <span class="info-icon">📞</span>
        <p><strong>Téléphone</strong><a href="tel:0237367259" style="color:#bbb; text-decoration:none;">02 37 36 72 59</a></p>
      </div>

      <div class="info-item">
        <span class="info-icon">🕐</span>
        <p>
          <strong>Horaires d'ouverture</strong>
          <table class="hours-table">
            <tr><td>Lundi</td><td>10:00 – 19:00</td></tr>
            <tr><td>Mardi</td><td>10:00 – 19:00</td></tr>
            <tr><td>Mercredi</td><td>10:00 – 19:00</td></tr>
            <tr><td>Jeudi</td><td>10:00 – 19:00</td></tr>
            <tr><td>Vendredi</td><td>10:00 – 19:00</td></tr>
            <tr><td>Samedi</td><td>10:00 – 19:00</td></tr>
            <tr><td>Dimanche</td><td>Fermé</td></tr>
          </table>
        </p>
      </div>
    </div>

    <div class="map-container">
      <iframe
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2642.5!2d1.4889!3d48.4469!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47e2849e73e3c1cb%3A0x8e3a6f9e73e8b7f0!2s3%20Rue%20de%20la%20Tonnellerie%2C%2028000%20Chartres!5e0!3m2!1sfr!2sfr!4v1700000000000"
        allowfullscreen="" loading="lazy"
        referrerpolicy="no-referrer-when-downgrade"
        title="Bijouterie 3 Ors – Carte">
      </iframe>
    </div>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">3 ORS</div>
  <p>© 2025 Bijouterie 3 Ors – Vincent Kindmann · 3 Rue de la Tonnellerie, 28000 Chartres</p>
  <p style="font-size:.65rem; color:#444;">Tous droits réservés</p>
</footer>

</body>
</html>
```
