---
title: Syllabus
permalink: /syllabus/
layout: base
---

{% assign d = site.data.syllabus %}

# {{ page.title }} -- {{d.course_number}}: {{d.course_title}}.

{{d.law_school}} ({{d.semester}})

## Description
{{ d.description}}

{% for fm in d.front_matter %}

**{{fm.meta}}**. {{fm.content}}

{% endfor %}

{% for s in d.sessions %}

## Session {{s.session}}: {{s.topic}} ({{s.date | date: "%b %d, %Y"}}).

{{s.description}}

### Guest Lecturer

{% if s.guest_lecturer.website %}
[{{s.guest_lecturer.name}}]({{s.guest_lecturer.website}})
{% else %}
{{s.guest_lecturer.name}}
{% endif %}

{% if s.materials.size > 0 %}

### Reading Materials

{% for m in s.materials %}* [{{m.name}}]({{m.url}})
{% endfor %}

{% endif %}

{% endfor %}
