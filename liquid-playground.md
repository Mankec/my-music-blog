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

{% assign songs = site.data.pendulum.albums[i].songs.size %}
{% if songs <= 10 %}album-block{% else %}album-block-overflow{% endif %}

<!-- ------------------------------------------ -->
<!-- ------------------------------------------ -->
<!-- ------------------------------------------ -->

{% assign albums = site.data.pendulum.albums %} {% assign i = 0 %} {% for album
in albums %} {% assign genres = albums[i].genres %}

<div class="album-preview">
  {% if genres contains "Drum and bass" %}
  <img src="{{ album.album_cover }}" />
  {% endif %}
</div>
{% assign i = i | plus: 1 %} {% endfor %} {% if i == 0 %} {% endif %}

<!-- ------------------------------------------ -->
<!-- ------------------------------------------ -->
<!-- ------------------------------------------ -->
<!-- Best solution for now -->

{% assign dnb = site.data.tags.drum_and_bass.albums | sort: "year_of_release" |
reverse %} {% for album in dnb %}

<div class="album-preview">
  <h1>{{ album.name }}</h1>
  <h1>{{ album.year_of_release }}</h1>
  <img src="{{ album.album_cover }}" />
</div>
{% endfor %}

<!-- ------------------------------------------ -->
<!-- ------------------------------------------ -->
<!-- ------------------------------------------ -->
<!-- Possible better solution -->

{{ site.data.bands[0] | where_exp: "pendulum", "pendulum.genre == 'test'" }
