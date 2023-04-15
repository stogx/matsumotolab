# Publications

## Group highlights

**At the end of this page, you can find the [full list of publications](#full-list-of-publications).**

{% assign number_printed = 0 %}
{% for publi in site.data.publist %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if publi.highlight == 1 %}

{% if even_odd == 0 %}
<div class="row">
{% endif %}

<div class="col-sm-6 clearfix">
 <div class="well">
  <pubtit>{{ publi.title }}</pubtit>
  <em>{{ publi.authors }}</em>
  <img src="{{ site.url }}{{ site.baseurl }}/images/pubpic/{{ publi.image }}" class="img-responsive" width="100%" style="float: left" />
  <p>{{ publi.description }}</p>
  <p><em>{{ publi.journal }}</em>, <strong>{{ publi.year }}</strong>, <em>{{ publi.volume }}</em>, {{ publi.page }}. <a href="{{ publi.url }}">{{ publi.doi }}</a></p>
  <p class="text-danger"><strong> {{ publi.news1 }}</strong></p>
  <p> {{ publi.news2 }}</p>
 </div>
</div>

{% assign number_printed = number_printed | plus: 1 %}

{% if even_odd == 1 %}
</div>
{% endif %}

{% endif %}
{% endfor %}

{% assign even_odd = number_printed | modulo: 2 %}
{% if even_odd == 1 %}
</div>
{% endif %}

<p> &nbsp; </p>

## Full List of publications

{% for publi in site.data.publist %}
  {{ publi.number }}  {{ publi.authors }}<br />
                      {{ publi.title }}<br />
                      <em>{{ publi.journal }}</em>, <strong>{{ publi.year }}</strong>, <em>{{ publi.volume }}</em>, {{ publi.page }}. <a href="{{ publi.url }}">{{ publi.doi }}</a>

{% endfor %}
