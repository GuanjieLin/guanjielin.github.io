---
permalink: /
title: "Guanjie LIN"
excerpt: ""
author_profile: true
redirect_from:
  - /about/
  - /about.html
---

{% if site.google_scholar_stats_use_cdn %}
{% assign gsDataBaseUrl = "https://cdn.jsdelivr.net/gh/" | append: site.repository | append: "@" %}
{% else %}
{% assign gsDataBaseUrl = "https://raw.githubusercontent.com/" | append: site.repository | append: "/" %}
{% endif %}
{% assign url = gsDataBaseUrl | append: "google-scholar-stats/gs_data_shieldsio.json" %}

<span class='anchor' id='about-me'></span>

<section class="home-hero">
  <div class="home-eyebrow">PhD Student in Computer Science</div>
  <h1>Guanjie Lin</h1>
  <p class="home-lede">I study future Internet architectures, blockchain systems, and computer networks for large language model ecosystems.</p>
  <div class="home-actions">
    <a href="#publications" class="home-button home-button-primary">View Publications</a>
    <a href="mailto:Guanjie.Lin001@umb.edu" class="home-button">Contact</a>
  </div>
</section>

<section class="home-section home-about">
  <div class="section-kicker">About</div>
  <h2>Researching networked systems for the next generation of Internet services.</h2>
  <p>I am currently a PhD student in Computer Science at the University of Massachusetts Boston (UMass Boston), advised by Prof. <a href="https://www.cs.umb.edu/~ywan/">Yinxin Wan</a>. I received my Bachelor of Engineering degree in Computer Science from Foshan University in June 2024.</p>
  <p>Before joining UMass Boston, I was a Research Intern at the Shenzhen Key Lab for ICN and Blockchain Technologies (ICNLAB), Shenzhen Graduate School, Peking University, mentored by Prof. <a href="https://www.icnlab.cn/?page_id=6360">Kai Lei</a>.</p>
</section>

<section class="home-section">
  <div class="section-kicker">Research Focus</div>
  <div class="research-grid">
    <div class="research-card">
      <span>01</span>
      <h3>Future Internet</h3>
      <p>Architectures and protocols for resilient, evolvable networked services.</p>
    </div>
    <div class="research-card">
      <span>02</span>
      <h3>Blockchain Systems</h3>
      <p>Distributed trust, Web3 infrastructure, and network-level behavior.</p>
    </div>
    <div class="research-card">
      <span>03</span>
      <h3>LLM Networks</h3>
      <p>Transparency, consistency, and connectivity in LLM API gateways.</p>
    </div>
  </div>
</section>

<section class="home-section compact-section">
  <div class="section-kicker">Education</div>
  <div class="info-list">
    <div class="info-item">
      <div>
        <h3>Ph.D. in Computer Science</h3>
        <p>University of Massachusetts Boston, United States</p>
      </div>
      <span>Jan 2025 - Now</span>
    </div>
    <div class="info-item">
      <div>
        <h3>B.E. in Computer Science</h3>
        <p>Foshan University, China</p>
      </div>
      <span>Sept 2020 - June 2024</span>
    </div>
  </div>
</section>

<section class="home-section compact-section">
  <div class="section-kicker">News</div>
  <div class="news-list">
    <div class="news-item">
      <time>2026.03</time>
      <p>Our paper <em>"Behavioral Consistency and Transparency Analysis on Large Language Model API Gateways"</em> has been accepted by <strong>IMC 2026</strong> Cycle 1.</p>
    </div>
    <div class="news-item">
      <time>2025.01</time>
      <p>I joined UMass Boston and began my PhD journey with Prof. Yinxin Wan.</p>
    </div>
  </div>
</section>

<section class="home-section compact-section" id="experience">
<div class="section-kicker">Experience</div>

<div class="timeline-container">
<div class="timeline">
  <div class="timeline-item">
    <div class="timeline-content">
      <div class="timeline-header">
        <h3 class="timeline-title">Graduate Assistant</h3>
        <span class="timeline-date">Jan 2025 - Now</span>
      </div>
      <div class="timeline-company">Department of Computer Science, University of Massachusetts Boston</div>
      <div class="timeline-location">Boston, United States</div>
      <div class="timeline-description">
        <p></p>
      </div>
    </div>
  </div>

  <div class="timeline-item">
    <div class="timeline-content">
      <div class="timeline-header">
        <h3 class="timeline-title">Research Intern</h3>
        <span class="timeline-date">Dec 2021 - Sept 2024</span>
      </div>
      <div class="timeline-company">
        <a href="http://www.icnlab.cn/">Shenzhen Key Lab for ICN and Blockchain Technologies (ICNLAB)</a>, Shenzhen Graduate School, Peking University
      </div>
      <div class="timeline-location">Shenzhen, China</div>
      <div class="timeline-description">
        <p></p>
      </div>
    </div>
  </div>
</div>
</div>
</section>

<section class="home-section compact-section" id="publications">
<div class="section-kicker">Publications</div>

{% include publications.html %}

</section>

<section class="home-section compact-section">
  <div class="section-kicker">Honors and Awards</div>
  <div class="award-card">
    <time>2023.12</time>
    <p><strong>Silver Award</strong> (Bonus: $30,000 HKD) at the 2023 Web 3.0 Innovation Hackathon, Hong Kong, China.</p>
  </div>
</section>
