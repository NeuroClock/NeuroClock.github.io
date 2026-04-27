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
{% assign count = 0 %}

{% for member in site.data.team_members %}
  {% if member.role == "PI" %}

    {% if count modulo 2 == 0 %}
    <div class="row">
    {% endif %}

    <div class="col-sm-6 clearfix">
      <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}"
           class="img-responsive"
           width="25%"
           style="float: left; margin-right: 15px;" />

      <h4>{{ member.name }}</h4>
      <i>{{ member.info }}</i>

      <ul style="overflow: hidden"></ul>
    </div>

    {% assign count = count | plus: 1 %}

    {% if count modulo 2 == 0 %}
    </div>
    {% endif %}

  {% endif %}
{% endfor %}

{% if count modulo 2 != 0 %}
</div>
{% endif %}

## PostDoc

{% assign count = 0 %}

{% for member in site.data.team_members %}
  {% if member.role == "PostDoc" %}

    {% if count modulo 2 == 0 %}
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
        <p style="margin-top: 10px;">{{ member.description }}</p>
      {% endif %}

    </div>

    {% assign count = count | plus: 1 %}

    {% if count modulo 2 == 0 %}
    </div>
    {% endif %}

  {% endif %}
{% endfor %}

{% if count modulo 2 != 0 %}
</div>
{% endif %}
