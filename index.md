---
layout: default
title: Home
---

<section class="hero-full" style="background-image:url('{{ "/assets/images/hero.webp" | relative_url }}');">
  <div class="hero-overlay"></div>
  <div class="hero-content">
    <h1>Selfless service. Honest advice.</h1>
    <p>Our approach to real estate is different.</p>
    <p>We're not focused on selling the most homes. Our goal is to give each client an unforgettable experience.</p>
    <div class="actions" style="justify-content:center">
      <a class="btn-cta" href="{{ site.calendly_url }}">Book discovery call</a>
    </div>
  </div>
</section>

<section class="section-light">
  <div class="container">
    <h2>Why Nalin Sharma &amp; SAYVA Real Estate?</h2>

    <div class="grid-3 why-grid">
      <div class="why-item">
        <div class="why-icon">✦</div>
        <h3>We truly care &lt;3</h3>
        <p>Whether you’re a 1st time buyer or a real estate veteran – we’ve got heart for this business and everyone we help.</p>
      </div>

      <div class="why-item">
        <div class="why-icon">$</div>
        <h3>Negotiation skills</h3>
        <p>From the notable Certified Negotiation Expert to The Black Swan Negotiation Method, we invest in ourselves to better serve you.</p>
      </div>

      <div class="why-item">
        <div class="why-icon">▦</div>
        <h3>West End bred</h3>
        <p>We’ve called West End Toronto our home for 30+ years, so believe it when we say we know the area.</p>
      </div>
    </div>
  </div>
</section>

<section class="section-dark">
  <div class="container">
    <h2>How can we help you?</h2>

    <div class="grid-3 help-grid">
      <div class="help-item">
        <div class="help-icon">⌕</div>
        <h3>Buy with us</h3>
        <p>Your trusted guide through a hyper competitive market</p>
      </div>

      <div class="help-item">
        <div class="help-icon">⌂</div>
        <h3>Sell with us</h3>
        <p>From start to finish, we’ll build your customized selling plan</p>
      </div>

      <div class="help-item">
        <div class="help-icon">⋯</div>
        <h3>Talk to us</h3>
        <p>Let’s chat! We’ll help you achieve your real estate goals</p>
      </div>
    </div>
  </div>
</section>

<section class="section-featured">
  <div class="container">
    <h2>Featured Listings</h2>

    <div class="listings-grid">
      {% assign feats = site.listings | where: "featured", true %}
      {% for l in feats %}
        <a class="listing-card" href="{{ l.url | relative_url }}">
          {% if l.hero %}
            <img src="{{ l.hero | relative_url }}" alt="{{ l.title }}">
          {% else %}
            <img src="{{ '/assets/images/hero.webp' | relative_url }}" alt="{{ l.title }}">
          {% endif %}
          <div class="listing-meta">
            <div class="listing-title">{{ l.title }}</div>
            {% if l.description %}<div class="listing-sub">{{ l.description }}</div>{% endif %}
            {% if l.status %}<div class="listing-status">{{ l.status }}</div>{% endif %}
          </div>
        </a>
      {% endfor %}
    </div>
  </div>
</section>
