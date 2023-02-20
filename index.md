---
layout: default
---

Some text here. Not sure if this is working


[Link](/npi2023/phdtheses)

<details markdown=block>
<summary markdown=span>A *Summary*</summary>
These are the **details** for this item.
</details>



{% assign types = site.data.publications | map: 'type' | uniq %}

{% for type in types %}
  <h2 id="{{ type }}">{{ type }}</h2>
  {% assign type_pubs = site.data.publications | where: 'type', type %}
  {% assign years = type_pubs | map: 'year' | uniq | sort | reverse %}
  {% for year in years %}
   **{{ year }}**
    {% assign year_pubs = type_pubs | where: 'year', year %}
    {% for pub in year_pubs %}
 {{ pub.authors | join: ', '}} ({{ pub.year }}). {{ pub.title }}, {{ pub.journal }}.
       {% if pub.link %}[[Link]]({{ pub.link }}){% endif %}
       {% if pub.pdf %} [[PDF]]({{ pub.pdf }}) {% endif %}
       {% if publ.code %}[[Rcode]]({{ pub.code }}){% endif %}
     {% endfor %}
  {% endfor %}
{% endfor %}
