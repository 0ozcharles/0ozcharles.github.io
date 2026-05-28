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
- **{{ edu.institution }}** - {{ edu.area }}{% if edu.endDate %}, {{ edu.endDate }}{% endif %}
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
