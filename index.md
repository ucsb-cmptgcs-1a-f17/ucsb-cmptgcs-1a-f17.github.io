---
title: CMPTGCS 1A, Fall 2017
---

# {{site.course}}, {{site.quarter}}


<div id="info" data-role="collapsible" data-collapsed="false">
<h2>Course Information</h2>
<ul>
{% for item in site.info %}
<li><a href="{{item.url}}"  data-ajax="false">{{item.title }}</a></li>
{% endfor %}
</ul>
</div>

<div data-role="collapsible" data-collapsed="false">
<h2 id="lectures">Lectures:</h2>
<table id="hwk_table" class="asn_table">
{% for asn in site.lectures %}

<tr>
  <td ><a href="{{asn.url}}" data-ajax="false">lecture {{ asn.topic }}</a></td>
  <td class="asn_desc" >{{ asn.desc }}</td>
</tr>

{% endfor %}
</table>

</div>

<div data-role="collapsible" data-collapsed="true">
<h2 id="f16lectures">F16 Lectures:</h2>
<table id="hwk_table" class="asn_table">
{% for asn in site.f16lectures %}

<tr>
  <td ><a href="{{asn.url}}" data-ajax="false">lecture {{ asn.topic }}</a></td>
  <td class="asn_desc" >{{ asn.desc }}</td>
</tr>

{% endfor %}
</table>

</div>

<div data-role="collapsible" data-collapsed="false">
<h2 id="labs">Labs:</h2>
{% include lab_table.html %}
</div>

<div data-role="collapsible" data-collapsed="false">
<h2 id="cs16">CS16 Labs:</h2>
<table id="cs16_table" class="asn_table">
  {% include asn_table_header_row.html %}
 {% for asn in site.cs16 %}
 {% if asn.num %}
   {% include asn_table_row.html %}
 {% endif %}
{% endfor %}
</table>
</div>

<div data-role="collapsible" data-collapsed="false">
<h2 id="cs24">CS24 Labs:</h2>
<table id="cs24_table" class="asn_table">
  {% include asn_table_header_row.html %}
 {% for asn in site.cs24 %}
 {% if asn.num %}
   {% include asn_table_row.html %}
 {% endif %}
{% endfor %}
</table>
</div>
<div data-role="collapsible" data-collapsed="false">
<h2 id="cs32">CS32 Labs:</h2>
<table id="cs32_table" class="asn_table">
  {% include asn_table_header_row.html %}
 {% for asn in site.cs32 %}
 {% if asn.num %}
   {% include asn_table_row.html %}
 {% endif %}
{% endfor %}
</table>
</div>
<div data-role="collapsible" data-collapsed="true">
<h2 id="cs56">CS56 Labs:</h2>
<table id="cs56_table" class="asn_table">
  {% include asn_table_header_row.html %}
 {% for asn in site.cs56 %}
 {% if asn.num %}
   {% include asn_table_row.html %}
 {% endif %}
{% endfor %}
</table>
</div>

<div data-role="collapsible" data-collapsed="false">
<h2 id="exams">Exams</h2>
{%include exam_table.html %}
</div>
