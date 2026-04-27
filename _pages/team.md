---
title: "Clock Lab - Team"
layout: gridlay
excerpt: "Clock Lab: Team members"
sitemap: false
permalink: /team/
---

# Group Members

 **We are  looking for new PhD students, Postdocs, and Master students to join the team** [(see openings)]({{ site.url }}{{ site.baseurl }}/vacancies) **!**

Jump to [PI](#pi), [PostDoc/Technician](#postdoc), [Students](#students)

## PI
{% assign number_printed = 0 %}
{% for member in site.data.team_members %}

{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">
  <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" class="img-responsive" width="25%" style="float: left" />
  <h4>{{ member.name }}</h4>
  <i>{{ member.info }} <!--<br>email: <{{ member.email }}></i> -->
  <ul style="overflow: hidden">

  </ul>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}

## PostDoc
{% assign number_printed = 0 %}
{% for member in site.data.team_members %}

{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix" style="margin-bottom: 20px;">

  <!-- Top: image + info side-by-side -->
  <div style="display: flex; align-items: flex-start;">

    <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}"
         class="img-responsive"
         width="25%"
         style="margin-right: 15px;" />

    <div>
      <h4 style="margin-top: 0;">{{ member.name }}</h4>

      <ul style="padding-left: 0; list-style: none;">

        {% if member.title %}
          <li>🎓 {{ member.title }}</li>
        {% endif %}

        {% if member.email %}
          <li>📧 {{ member.email }}</li>
        {% endif %}

        {% if member.orcid %}
          <li>🆔 <a href="https://orcid.org/{{ member.orcid }}">ORCID</a></li>
        {% endif %}

        {% if member.websites %}
          {% for site in member.websites %}
            {% if site.url %}
              <li>🌐 <a href="{{ site.url }}">{{ site.label }}</a></li>
            {% else %}
              <li>🌐 {{ site.label }}</li>
            {% endif %}
          {% endfor %}
        {% endif %}

      </ul>
    </div>

  </div>

  <!-- Bottom: full-width description -->
  {% if member.description %}
    <div style="margin-top: 10px;">
      <p style="margin: 0; text-align: left;">
        {{ member.description }}
      </p>
    </div>
  {% endif %}

</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}


## Students
## PostDoc
{% assign number_printed = 0 %}

{% for member in site.data.team_members %}

{% assign even_odd = number_printed | modulo: 2 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix" style="margin-bottom: 20px;">

  <div style="display: flex; align-items: flex-start;">

    <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}"
         class="img-responsive"
         width="25%"
         style="margin-right: 15px;" />

    <div>
      <h4 style="margin-top: 0;">{{ member.name }}</h4>

      <ul style="padding-left: 0; list-style: none;">

        {% if member.title %}
          <li>🎓 {{ member.title }}</li>
        {% endif %}

        {% if member.email %}
          <li>📧 {{ member.email }}</li>
        {% endif %}

        {% if member.orcid %}
          <li>🆔 <a href="https://orcid.org/{{ member.orcid }}">ORCID</a></li>
        {% endif %}

        {% if member.websites %}
          {% for w in member.websites %}
            {% if w.url %}
              <li>🌐 <a href="{{ w.url }}">{{ w.label }}</a></li>
            {% else %}
              <li>🌐 {{ w.label }}</li>
            {% endif %}
          {% endfor %}
        {% endif %}

      </ul>
    </div>

  </div>

  {% if member.description %}
    <div style="margin-top: 10px;">
      <p style="margin: 0; text-align: left;">
        {{ member.description }}
      </p>
    </div>
  {% endif %}

</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}