---
tittle: "Clock Lab - Team"
layout: gridlay
excerpt: "Clock Lab: Team members"
sitemap: false
permalink: /team/
---

# Group Members

 **We are  looking for new PhD students, Postdocs, and Master students to join the team** [(see openings)]({{ site.url }}{{ site.baseurl }}/vacancies) **!**

Jump to [PI](#pi), [PostDoc/Technician](#postdoc), [Students](#students)

## pi
{% assign number_printed = 0 %}
{% for member in site.data.team_members %}
  {% if member.role == "pi" %}

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

## postdoc
{% assign number_printed = 0 %}
{% for member in site.data.team_members %}
  
  {% comment %} Only proceed if role is PostDoc or Technician {% endcomment %}
  {% if member.role == "PostDoc" or member.role == "Technician" %}
    
    {% assign even_odd = number_printed | modulo: 2 %}

    {% if even_odd == 0 %}
    <div class="row" style="margin-bottom: 30px;">
    {% endif %}

    <div class="col-sm-6 d-flex align-items-start">
      <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}"
           class="img-responsive" 
           style="width: 25%; margin-right: 15px; border-radius: 4px;" />

      <div>
        <h4 style="margin-top: 0;">{{ member.name }}</h4>
        <p style="font-size: 0.9em; font-weight: bold; color: #777;">{{ member.role }}</p>
        
        <ul class="list-unstyled" style="margin-bottom: 10px;">
          {% if member.orcid %}
            <li><i class="ai ai-orcid"></i> <a href="https://orcid.org/{{ member.orcid }}">ORCID Profile</a></li>
          {% endif %}
          
          <!-- {% if member.website %}
            <li><i class="fa fa-globe"></i> <a href="{{ member.website }}">Personal Website</a></li>
          {% endif %} -->

          {% for site in member.websites %}
            <li><i class="fa fa-globe"></i> <a href="{{ site.url }}">{{ site.label }}</a></li>
          {% endfor %}

        </ul>

        {% if member.description %}
          <p style="font-size: 0.85em; line-height: 1.4;">{{ member.description }}</p>
        {% endif %}
      </div>
    </div>

    {% assign number_printed = number_printed | plus: 1 %}
    {% assign next_even_odd = number_printed | modulo: 2 %}

    {% comment %} Close row if we just printed the second item OR if this is the last eligible person {% endcomment %}
    {% if next_even_odd == 0 %}
    </div>
    {% endif %}

  {% endif %}
{% endfor %}

{% comment %} Final safety check to close a row if the total count was odd {% endcomment %}
{% assign final_check = number_printed | modulo: 2 %}
{% if final_check != 0 %}
  </div>
{% endif %}

## students
{% assign number_printed = 0 %}
{% for member in site.data.team_members %}
  
  {% comment %} Only proceed if role is PhD or Master {% endcomment %}
  {% if member.role == "PhD" or member.role == "Master" %}
    
    {% assign even_odd = number_printed | modulo: 2 %}

    {% if even_odd == 0 %}
    <div class="row" style="margin-bottom: 30px;">
    {% endif %}

    <div class="col-sm-6 d-flex align-items-start">
      <img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}"
           class="img-responsive" 
           style="width: 25%; margin-right: 15px; border-radius: 4px;" />

      <div>
        <h4 style="margin-top: 0;">{{ member.name }}</h4>
        <p style="font-size: 0.9em; font-weight: bold; color: #777;">{{ member.role }}</p>
        
        <ul class="list-unstyled" style="margin-bottom: 10px;">
          {% if member.orcid %}
            <li><i class="ai ai-orcid"></i> <a href="https://orcid.org/{{ member.orcid }}">ORCID Profile</a></li>
          {% endif %}
          
          <!-- {% if member.website %}
            <li><i class="fa fa-globe"></i> <a href="{{ member.website }}">Personal Website</a></li>
          {% endif %} -->

          {% for site in member.websites %}
            <li><i class="fa fa-globe"></i> <a href="{{ site.url }}">{{ site.label }}</a></li>
          {% endfor %}

        </ul>

        {% if member.description %}
          <p style="font-size: 0.85em; line-height: 1.4;">{{ member.description }}</p>
        {% endif %}
      </div>
    </div>

    {% assign number_printed = number_printed | plus: 1 %}
    {% assign next_even_odd = number_printed | modulo: 2 %}

    {% comment %} Close row if we just printed the second item OR if this is the last eligible person {% endcomment %}
    {% if next_even_odd == 0 %}
    </div>
    {% endif %}

  {% endif %}
{% endfor %}

{% comment %} Final safety check to close a row if the total count was odd {% endcomment %}
{% assign final_check = number_printed | modulo: 2 %}
{% if final_check != 0 %}
  </div>
{% endif %}