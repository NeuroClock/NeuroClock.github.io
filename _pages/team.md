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

  {% if member.number_web == 1 %}
    {% assign label = member.web1 | split: "(" | first %}
    {% assign url = member.web1 | split: "url:" | last | remove: ")" %}
    <div>
      🌐 <a href="{{ url }}" target="_blank">
        {{ label | replace: "_", " " | capitalize }}
      </a>
    </div>
  {% endif %}

  {% if member.number_web == 2 %}
    {% assign label1 = member.web1 | split: "(" | first %}
    {% assign url1 = member.web1 | split: "url:" | last | remove: ")" %}
    {% assign label2 = member.web2 | split: "(" | first %}
    {% assign url2 = member.web2 | split: "url:" | last | remove: ")" %}

    <div>
      🌐 <a href="{{ url1 }}" target="_blank">
        {{ label1 | replace: "_", " " | capitalize }}
      </a>
    </div>

    <div>
      🌐 <a href="{{ url2 }}" target="_blank">
        {{ label2 | replace: "_", " " | capitalize }}
      </a>
    </div>
  {% endif %}
  <!-- <ul style="overflow: hidden">

  </ul> -->
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