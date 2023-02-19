---
layout: default
title: Phdtheses
---

<h3>PhD theses on NPI</h3>


<ul class="fa-ul">
{% for member in site.data.members %}
  <li style="margin-top: 20px;"><i class="fa-li fa fa-graduation-cap fa-lg" aria-hidden="true"> </i>
      {{ member.name }}  ({{ member.year }}).  {{ member.title }}.  Durham University, UK.
  </li>
    
    
{% if member.pdflink %}     
   <div class="btn-group">
<a role="button" class="btn btn-primary btn-xs" href="/pdfs/theses/{{ member.key }}.pdf" target="_blank">PDF</a>
    </div>  
{% endif %}
    
    
    
{% if member.abstract %} 
<a class="btn btn-success btn-xs" role="button" data-toggle="collapse" href="#{{ member.key }}" aria-expanded="false" aria-controls="{{ member.key }}">Abstract
        <span class="caret"></span></a>
<div class="collapse" id="{{ member.key }}">    
  <div class="well">
    {{ member.abstract }}   
  </div>  
</div>
  {% endif %}
    
    
{% endfor %}
</ul>

