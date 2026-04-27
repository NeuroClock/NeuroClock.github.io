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


  {% if member.number_web == 1 %}
  {% assign label = member.web1 | split: "(" | first %}
  {% assign url = member.web1 | split: "url:" | last | remove: ")" %}
  <li>
      🌐 <a href="{{ url }}" target="_blank">
      {{ label | replace: "_", " " | capitalize }}
      </a>
  </li>
  {% endif %}

  {% if member.number_web == 2 %}
  <li> 🌐 {{ member.web1 | markdownify}} </li>
  <li> 🌐 {{ member.web2 | markdownify}} </li>
  {% endif %}

  {% if member.number_web == 3 %}
  <li> 🌐 {{ member.web1 | markdownify}} </li>
  <li> 🌐 {{ member.web2 | markdownify}} </li>
  <li> 🌐 {{ member.web3 | markdownify}} </li>
  {% endif %}

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

# PostDoc


# Students