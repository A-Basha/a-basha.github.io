---
layout: single
title: Education
permalink: /education/
author_profile: true
---

<style>
    

/* personal style  */

/* education page */

.edu-entry {
  display: flex;
  /* justify-content: space-between; */
  align-items: flex-start;
  margin-bottom: 1.5em;
  flex-wrap: wrap;
}


.edu-logo, .exp-logo {
  width: 120px;
  /* height: 50px; */
  object-fit: contain;
  /* transition: transform 0.2s; */
}

.logo-wrapper {
  background-color: var(--global-bg-color);
  /* box-shadow: rgba(0, 0, 0, 0.05) 0px 2px 6px; */
  display: inline-flex;
  align-items: center;
  justify-content: center;
  margin-top: 10px;
  margin-left: 10px;
  min-width: 80px;
  min-height: 50px;
  /* border: 1px solid var(--global-border-color); */
  padding: 8px;
  border-radius: 8px;
    margin-right: 50px;
}

.edu-details {
  max-width: 75%;
}

.edu-degree {
  font-weight: bold;
  font-size: 1.1em;
}

.edu-univ {
  margin-top: 0.2em;
  font-style: italic;
    display: flex;
}

.edu-univ div{
    font-style: normal;
}

.edu-thesis {
  margin-top: 0.3em;
  font-size: 0.97em;
}

.meta-text {
  /* text-align: right; */
  min-width: 170px;
  color: var(--meta-color);
  font-size: 0.95em;
}

</style>


<div class="education-list">


{% include base_path %}
{% for ed in site.data.education %}
    <div class="edu-entry">

    <div class="logo-wrapper">
        <img class="edu-logo" src="{{ ed.logo | prepend: "/images/" | prepend: base_path }}" alt="{{ ed.institution }} Logo">
    </div>

    <div class="edu-details">
        <div class="edu-degree">
        {{ ed.degree }}
        {% if ed.diploma_url %}
            <a href="{{ ed.diploma_url }}" target="_blank" rel="noopener noreferrer">
            <i class="fas fa-fw fa-link icon-pad-right" aria-hidden="true"></i></a>
        {% endif %}
        </div>

        <div class="edu-univ">
        {% if ed.institution_url %}
            <a href="{{ ed.institution_url }}" target="_blank" rel="noopener noreferrer">{{ ed.institution }}</a>
            <div class="edu-loca">&nbsp; – {{ ed.location }}</div>
        {% else %}
            {{ ed.institution }}
        {% endif %}
        </div>

        <div class="meta-text">
         {{ ed.start }} – {{ ed.end }}
        </div>

        {% if ed.thesis or ed.grade %}
        <div class="edu-thesis">
        {% if ed.thesis %}Thesis: "{{ ed.thesis }}"{% endif %}
        {% if ed.grade %} – Grade: {{ ed.grade }}{% endif %}
        </div>
        {% endif %}
    </div>


    </div>
{% endfor %}

</div>
