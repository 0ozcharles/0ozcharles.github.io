---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% assign cv_data = site.data.cv %}

## Education
{% for edu in cv_data.education %}
{% assign date_range = "" %}
{% if edu.startDate != "" and edu.endDate != "" %}
  {% assign date_range = edu.startDate | append: "-" | append: edu.endDate %}
{% elsif edu.endDate != "" %}
  {% assign date_range = edu.endDate %}
{% elsif edu.startDate != "" %}
  {% assign date_range = edu.startDate %}
{% endif %}
- **{{ edu.institution }}** - {{ edu.area }}{% if date_range != "" %}, {{ date_range }}{% endif %}
{% endfor %}

## Work Experience
{% for job in cv_data.work %}
- **{{ job.position }}**, {{ job.company }}{% if job.summary %}. {{ job.summary }}{% endif %}
{% endfor %}

## Publications
{% for pub in cv_data.publications %}
- {{ pub.name }}. *{{ pub.publisher }}*, {{ pub.releaseDate | slice: 0, 4 }}.
{% endfor %}

## Skills
{% for skill in cv_data.skills %}
- **{{ skill.name }}**: {{ skill.keywords | join: ", " }}
{% endfor %}
