<!-- This file is for storing liquid code -->
<!-- Loop for showing albums -->

    {% for band_hash in site.data.pendulum %} {% assign band = band_hash[1] %}
    <div class="album-block">{{ band.album_name }}</div>
    {% endfor %}

<!-- ------------------------------------------ -->
<!-- ------------------------------------------ -->
<!-- ------------------------------------------ -->

 <div class="album-container">
    {% assign albumcount = page.albumcount %} {% assign value = page.albumcount
    | modulo:2 %} {% if value == 0 %} {% assign value = "even" %} {% else %} {%
    assign value = "odd" %} {% endif %} {% for i in (1..albumcount) %} {% if i
    == 1 %}
    <div
      class="{% if i != albumcount %}album-block{% elsif value == 'even' %}album-block{% else %}album-block-centered{% endif %}"
    >
      <p>{{page.album-1}} {{value}}</p>
    </div>
    {% endif %} {% if i == 2 %}
    <div
      class="{% if i != albumcount %}album-block{% elsif value == 'even' %}album-block{% else %}album-block-centered{% endif %}"
    >
      <p>{{page.album-2}}</p>
    </div>
    {% endif %} {% if i == 3 %}
    <div
      class="{% if i != albumcount %}album-block{% elsif value == 'even' %}album-block{% else %}album-block-centered{% endif %}"
    >
      <p>{{page.album-3}}</p>
    </div>
    {% endif %} {% if i == 4 %}
    <div
      class="{% if i != albumcount %}album-block{% elsif value == 'even' %}album-block{% else %}album-block-centered{% endif %}"
    >
      <p>{{page.album-4}}</p>
    </div>
    {% endif %} {% if i == 5 %}
    <div
      class="{% if i != albumcount %}album-block{% elsif value == 'even' %}album-block{% else %}album-block-centered{% endif %}"
    >
      <p>{{page.album-5}}</p>
    </div>
    {% endif %} {% endfor %}
  </div>
</div>

<!-- ------------------------------------------ -->
<!-- ------------------------------------------ -->
<!-- ------------------------------------------ -->
