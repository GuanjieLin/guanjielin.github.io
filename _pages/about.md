---
permalink: /
title: "Guanjie LIN"
excerpt: ""
author_profile: false
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

<section class="home-hero" id="about-me">
  <div class="hero-portrait">
    <img src="{{ site.author.avatar | relative_url }}" alt="Guanjie Lin">
  </div>
  <div class="hero-copy">
    <div class="home-eyebrow">PhD Student in Computer Science</div>
    <h1>Guanjie Lin</h1>
    <p class="home-lede">Researching future Internet architectures, blockchain systems, and networked infrastructure for large language model ecosystems.</p>
    <div class="hero-tags">
      <span>University of Massachusetts Boston</span>
      <span>Computer Networks</span>
      <span>Blockchain</span>
      <span>LLM Gateways</span>
    </div>
  </div>
  <div class="hero-links" aria-label="External links">
    <button class="hero-icon-link email-link" type="button" data-email-user="Guanjie.Lin001" data-email-domain="umb.edu" aria-label="Email">
      <i class="fas fa-envelope" aria-hidden="true"></i>
    </button>
    <a class="hero-icon-link" href="https://github.com/{{ site.author.github }}" aria-label="GitHub">
      <i class="fab fa-github" aria-hidden="true"></i>
    </a>
    <a class="hero-icon-link" href="https://www.linkedin.com/in/{{ site.author.linkedin }}" aria-label="LinkedIn">
      <i class="fab fa-linkedin-in" aria-hidden="true"></i>
    </a>
    <a class="hero-icon-link" href="{{ site.author.googlescholar }}" aria-label="Google Scholar">
      <i class="fas fa-graduation-cap" aria-hidden="true"></i>
    </a>
    <a class="hero-icon-link" href="{{ site.author.researchgate }}" aria-label="ResearchGate">
      <i class="fab fa-researchgate" aria-hidden="true"></i>
    </a>
  </div>
</section>

<section class="home-section home-about">
  <div class="section-kicker">About</div>
  <h2>Researching networked systems for the next generation of Internet services.</h2>
  <p>I am currently a PhD student in Computer Science at the University of Massachusetts Boston (UMass Boston), advised by Prof. <a href="https://www.cs.umb.edu/~ywan/">Yinxin Wan</a>. I received my Bachelor of Engineering degree in Computer Science from Foshan University in June 2024.</p>
  <p>Before joining UMass Boston, I was a Research Intern at the Shenzhen Key Lab for ICN and Blockchain Technologies (ICNLAB), Shenzhen Graduate School, Peking University, mentored by Prof. <a href="https://www.icnlab.cn/?page_id=6360">Kai Lei</a>.</p>
</section>

<section class="home-section compact-section" id="education">
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

<section class="home-section compact-section" id="news">
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

<section class="home-section compact-section" id="projects">
  <div class="section-kicker">Projects</div>
  <div class="project-item">
    <div class="project-heading">
      <h3>China Merchants Group Blockchain Platform (Phase 2)</h3>
      <span>Sept 2022 - May 2023</span>
    </div>
    <p>In this project, ICNLAB acted as the technical consulting team and I participated in completing the information consultancy report on the construction and promotion of China Merchants Group Blockchain Platform (Phase 2). The project was led by China Merchants Group and jointly completed with Tencent Cloud and ICNLAB.</p>
  </div>
</section>

<section class="home-section compact-section" id="services">
  <div class="section-kicker">Services</div>
  <div class="service-list">
    <div class="service-item">STPC of ACM IMC 2026</div>
  </div>
</section>

<section class="home-section compact-section" id="honors">
  <div class="section-kicker">Honors and Awards</div>
  <div class="award-card">
    <time>2023.12</time>
    <p><strong>Silver Award</strong> (Bonus: $30,000 HKD) at the 2023 Web 3.0 Innovation Hackathon, Hong Kong, China.</p>
  </div>
</section>
