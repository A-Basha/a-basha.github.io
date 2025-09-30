---
layout: page
title: Education
permalink: /education/
author_profile: true
---

<div class="education-list">

<style> .edu-entry { display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 1.5em; flex-wrap: wrap; } .edu-details { max-width: 70%; } .edu-degree { font-weight : bold; font-size : 1.1em; } .edu-univ { margin-top: 0.2em; font-style: italic; } .edu-thesis { margin-top: 0.3em; font-size: 0.97em; }</style>

{% for ed in site.data.education %}
    <div class="edu-entry">

    <div class="logo-wrapper">
        <img class="edu-logo" src="{{ ed.logo | prepend: "/images/" | prepend: base_path }}" alt="{{ ed.institution }} Logo">
    </div>

    <div class="edu-details">
        <div class="edu-degree">
        {{ ed.degree }}
        {% if ed.diploma_url %}
            <a href="{{ ed.diploma_url }}" target="_blank" rel="noopener noreferrer">[{{ ed.diploma_label }}]</a>
        {% endif %}
        </div>

        <div class="edu-univ">
        {% if ed.institution_url %}
            <a href="{{ ed.institution_url }}" target="_blank" rel="noopener noreferrer">{{ ed.institution }}</a>
        {% else %}
            {{ ed.institution }}
        {% endif %}
        </div>

        {% if ed.thesis or ed.grade %}
        <div class="edu-thesis">
        {% if ed.thesis %}Thesis: "{{ ed.thesis }}"{% endif %}
        {% if ed.grade %} – Grade: {{ ed.grade }}{% endif %}
        </div>
        {% endif %}
    </div>

    <div class="meta-text">
        {{ ed.location }}<br>
        {{ ed.start }} – {{ ed.end }}
    </div>

    </div>
{% endfor %}

</div>
