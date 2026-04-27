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

## new_pi
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

## PI
{% assign number_printed = 0 %}
{% for member in site.data.team_members %}
  <!-- {% if member.role == "pi" %} -->

    {% assign even_odd = number_printed | modulo: 2 %}

    {% if even_odd == 0 %}
    <div class="row" style="margin-bottom: 30px;">
    {% endif %}

    <div class="col-sm-6 d-flex align-items-start">
      <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}"
           class="img-responsive"
           style="width: 25%; margin-right: 15px;" />

      <div>
        <h4 style="margin-top: 0;">{{ member.name }}</h4>

        <ul class="list-unstyled">
          {% if member.tittle %}
            <li><i class="fa fa-graduation-cap"></i> {{ member.tittle }}</li>
          {% endif %}

          {% if member.email %}
            <li><i class="fa fa-envelope"></i> {{ member.email }}</li>
          {% endif %}
          
          {% if member.orcid %}
            <li><i class="ai ai-orcid"></i> 
              <a href="https://orcid.org/{{ member.orcid }}">ORCID Profile</a>
            </li>
          {% endif %}
          
          {% if member.linkedin %}
            <li><i class="fa fa-linkedin"></i> 
              <a href="{{ member.linkedin }}">LinkedIn</a>
            </li>
          {% endif %}
        </ul>
      </div>
    </div>

    {% assign number_printed = number_printed | plus: 1 %}
    {% assign next_even_odd = number_printed | modulo: 2 %}

    {% if next_even_odd == 0 %}
    </div>
    {% endif %}

  {% endif %}
{% endfor %}

{% assign final_check = number_printed | modulo: 2 %}
{% if final_check != 0 %}
</div>
{% endif %}

## PostDoc

## Students
