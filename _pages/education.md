---
layout: page
title: Education
permalink: /education/
---

<div class="education-list">

  {% for ed in site.data.education %}
  <div class="edu-card" style="display:flex; gap:1rem; align-items:flex-start; padding:1rem; border:1px solid #eee; border-radius:8px; margin-bottom:1rem;">
    
    {% if ed.badge %}
    <div class="edu-badge" style="flex:0 0 auto;">
      <img src="{{ ed.badge }}" alt="{{ ed.institution }} badge" style="width:64px; height:64px; object-fit:contain; border:1px solid #e5e5e5; border-radius:8px; padding:6px; background:#fff;">
    </div>
    {% endif %}

    <div class="edu-main" style="flex:1 1 auto;">
      <h3 style="margin:0 0 .25rem 0;">
        {{ ed.degree }}
        {% if ed.diploma_url %}
        <span style="font-weight:normal;">
          [<a href="{{ ed.diploma_url }}">{{ ed.diploma_label | default: "Diploma" }}</a>]
        </span>
        {% endif %}
      </h3>

      <p style="margin:.2rem 0 .6rem 0;">
        {% if ed.program_url %}
          <a href="{{ ed.program_url }}">{{ ed.institution }}</a>
        {% else %}
          {{ ed.institution }}
        {% endif %}
      </p>

      {% if ed.thesis or ed.grade %}
      <p style="margin:0;">
        {% if ed.thesis %}<strong>Thesis:</strong> “{{ ed.thesis }}”{% endif %}
        {% if ed.thesis and ed.grade %} — {% endif %}
        {% if ed.grade %}<strong>Grade:</strong> {{ ed.grade }}{% endif %}
      </p>
      {% endif %}
    </div>

    <div class="edu-side" style="flex:0 0 auto; text-align:right; color:#777;">
      {% if ed.location %}<div>{{ ed.location }}</div>{% endif %}
      {% if ed.start or ed.end %}<div>{{ ed.start }}{% if ed.end %} – {{ ed.end }}{% endif %}</div>{% endif %}
    </div>

  </div>
  {% endfor %}

</div>
