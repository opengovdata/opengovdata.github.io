---
title: Syllabus
permalink: /syllabus/
layout: base
---

{% assign d = site.data.syllabus %}

# {{ page.title }} -- {{d.law_school}} {{d.course_number}}: {{d.course_title}}.

{{ d.description}}

{% for fm in d.front_matter %}

*{{fm.meta}}*. {{fm.content}}

{% endfor %}

{% for s in d.sessions %}

## Session {{s.session}}: {{s.topic}}.

{{s.description}}

### Guest Lecturer

{% if s.guest_lecturer.website %}
[{{s.guest_lecturer.name}}]({{s.guest_lecturer.website}})
{% else %}
{{s.guest_lecturer.name}}
{% endif %}

### Reading Materials

{% for m in s.materials %}
* [{{m.name}}]({{m.url}})
{% endfor %}

{% endfor %}
