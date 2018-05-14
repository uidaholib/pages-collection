---
layout: page
title: Home
featured-image: "objects/test001.jpg"
# add top subjects, for list see data/subjects.csv
featured-subjects: "Buildings; Campuses; Picture postcards; County courthouses; Farms; Schools"
# add top locations, for list see data/places.csv
featured-places: "Moscow, Idaho; Tacoma, Washington; Pullman, Washington; Spokane, Washington"
---
{%- assign items = site.data.metadata -%}

{% include index/jumbotron.html %}

<div class="row">
  <div class="col-md-4">  

    {% include index/documents.html %}
    {% include index/time.html %}
    {% include index/subjects.html %}

  </div>
  <div class="col-md-8">

  {% include index/description.html %}
  {% include index/locations.html %}

  </div>
</div>
