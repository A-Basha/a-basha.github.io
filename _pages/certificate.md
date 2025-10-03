---
layout: single
title: Certificate
permalink: /certificate/
author_profile: true
---


<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/glightbox/dist/css/glightbox.min.css"/>
{% include base_path %}

<style>
    .cert-grid { display: grid; grid-template-columns: repeat(auto-fit, minmax(280px, 1fr)); gap: 1.5rem; max-width: 1100px; margin: 2rem auto; padding: 0 1rem; } .cert-card { position: relative; background: var(--global-bg-color, #fff); padding: 1.2rem; border-radius: 10px; border: 1px solid rgba(255, 255, 255, 0.08); box-shadow: 0 4px 16px rgba(0, 0, 0, 0.12); transition: box-shadow 0.15s ease-out, transform 0.15s ease-out; cursor: pointer; overflow: visible; } .cert-card:hover { box-shadow: 0 8px 28px rgba(0, 0, 0, 0.18); transform: translateY(-2px); } .cert-card::before { content: ""; position: absolute; inset: 0; background-image: var(--hover-bg); background-size: cover; background-position: center; opacity: 0; filter: blur(1.5px); z-index: 0; border-radius: 10px; transition: opacity 0.15s ease-in-out; } .cert-card:hover::before { opacity: 0.2; } .cert-card > * { position: relative; z-index: 1; } .cert-logo { height: 24px !important; max-height: 24px !important; width: auto; max-width: 100px; /* Prevents logos from being too wide */ margin-bottom: 0.4rem; object-fit: contain; vertical-align: middle; display: inline-block; } .cert-title { font-weight: 600; font-size: 1.1rem; margin: 0.2rem 0; } .cert-issuer { font-size: 0.9rem; color: var(--meta-color); margin-bottom: 0.6rem; } .cert-desc { font-size: 0.9rem; color: var(--global-text-color, #333); flex-grow: 1; } /* Lightbox Styles */ #certLightbox { display: none; position: fixed; z-index: 10000; top: 0; left: 0; width: 100%; height: 100%; background-color: rgba(0, 0, 0, 0.8); align-items: center; justify-content: center; padding: 1rem; } #lightboxInner { background: rgba(244, 244, 244, 0.92); padding: 1.5rem; border-radius: 10px; max-width: 95%; max-height: 95vh; width: 850px; text-align: center; position: relative; } .lightbox-img { max-width: 100%; max-height: 75vh; border-radius: 6px; margin-bottom: 1rem; } .lightbox-caption { font-size: 0.95rem; color: #333; } .lightbox-close { position: absolute; top: 10px; right: 15px; font-size: 2rem; font-weight: bold; cursor: pointer; color: #666; } .lightbox-arrow { position: absolute; top: 50%; transform: translateY(-50%); background: rgba(255, 255, 255, 0.75); border-radius: 50%; padding: 0.6rem; cursor: pointer; z-index: 10001; display: flex; align-items: center; justify-content: center; width: 44px; height: 44px; } #lightbox-prev { left: 20px; } #lightbox-next { right: 20px; } .verify-link { display: inline-block; margin-top: 0.5rem; padding: 0.4rem 0.9rem; background: rgba(35, 34, 78, 1); color: white; font-weight: 500; font-size: 0.85rem; border-radius: 5px; text-decoration: none; transition: background 0.2s; } .verify-link:hover { background: rgba(77, 93, 170, 1); } .cert-icon { position: absolute; top: 10px; right: 10px; opacity: 0.8; pointer-events: none; border-radius: 50%; padding: 2px; transition: opacity 0.2s ease; } .cert-card:hover .cert-icon { opacity: 1; } .cert-icon svg { width: 16px; height: 16px; display: block; color: var(--meta-color); } .cert-date { color: #888; font-size: 0.95em; display: block; margin: 0.2em 0; }
</style>

<div class="cert-grid">
  {% for c in site.data.certifications %}
  <a class="cert-card glightbox"
     href="{{ c.cert_image | prepend: base_path }}"
     data-gallery="certs"
     data-title="{{ c.title }} — {{ c.issuer }}{% if c.verify_url %}<br><a href='{{ c.verify_url }}' target='_blank' rel='noopener'>Verify</a>{% endif %}"
     style="--hover-bg: url('{{ c.hover_bg | prepend: base_path }}')"
     title="Click to view certificate">

    <span class="cert-icon" aria-hidden="true">
      <!-- eye icon -->
      <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16" fill="currentColor"><path d="M16 8s-3-5.5-8-5.5S0 8 0 8s3 5.5 8 5.5S16 8 16 8M1.173 8a13 13 0 0 1 1.66-2.043C4.12 4.668 5.88 3.5 8 3.5s3.879 1.168 5.168 2.457A13 13 0 0 1 14.828 8q-.086.13-.195.288c-.335.48-.83 1.12-1.465 1.755C11.879 11.332 10.119 12.5 8 12.5s-3.879-1.168-5.168-2.457A13 13 0 0 1 1.172 8z"/><path d="M8 5.5a2.5 2.5 0 1 0 0 5 2.5 2.5 0 0 0 0-5M4.5 8a3.5 3.5 0 1 1 7 0 3.5 3.5 0 0 1-7 0"/></svg>
    </span>

    <img class="cert-logo logo-light" src="{{ c.logo_light | prepend: base_path }}" alt="{{ c.issuer }} logo">
    <img class="cert-logo logo-dark"  src="{{ c.logo_dark  | prepend: base_path }}" alt="{{ c.issuer }} logo dark">

    <div class="cert-title">{{ c.title }}</div>
    <div class="cert-issuer">{{ c.issuer }}</div>
    <div class="cert-date">{{ c.date }}</div>
    <div class="cert-desc">{{ c.desc }}</div>
  </a>
  {% endfor %}
</div>

<script src="https://cdn.jsdelivr.net/npm/glightbox/dist/js/glightbox.min.js"></script>
<script>
  /* initialize the lightbox */
  const lightbox = GLightbox({ selector: '.glightbox' });
</script>
