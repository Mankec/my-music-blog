---
layout: default
title: Immersion - Pendulum
band: Zendulum
name: Immersion
year_of_release: 2010
cover_img: img/hold_your_colour.jpg
tags: [Drum and bass, Electronic rock, Industrial rock]
category: Pendulum
songs: [
    Genesis,
    Salt in the Wounds,
    Watercolour,
    Set Me on Fire,
    Crush,
    Under
    the Waves,
    Immunize (featuring Liam Howlett),
    The Island - Pt.I (Dawn),
    The
    Island - Pt.II (Dusk),
    Comprachicos,
    The Vulture,
    Witchcraft,
    Self vs. Self
    (featuring In Flames),
    The Fountain (featuring Steven Wilson),
    Encoder,
  ]
band_page_url: pages/pendulum
---

<div class="albums-content-container">
  <div class="about-band-header">
    <h1>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Doloremque
      placeat iure sunt quaerat praesentium libero recusandae nemo est aliquid,
      dolorem necessitatibus voluptatibus natus! Autem, voluptatibus deleniti
      dicta omnis modi excepturi!
    </h1>
  </div>

  <div class="album-blocks-container">
    <!-- Assigning values needed for loop -->
    {% assign albums = site.data.pendulum.albums | sort:"year_of_release" %} {%
    assign sum = site.data.pendulum.albums_sum | modulo:2 %} {% if sum == 0 %}
    {% assign sum = "even" %} {% else %} {% assign sum = "odd" %} {% endif %} {%
    assign i = 0 %}

    <!-- Looping over albums arrays -->
    {% for album in albums %}

    <!-- Getting number of songs in album  -->
    {% assign songs = albums[i].songs %}

    <!-- Getting genres array -->
    {% assign genres = albums[i].genres %}

    <!-- Checking if album sum is even or odd (important for styling) -->
    {% if albums.last == album and sum == "odd" %}

    <div class="album-block-centered"></div>

    {% else %}

    <div class="album-block">
      <div class="album-block-1">
        <div class="album-header">
          <div class="album-name"><h2>{{ album.name }}</h2></div>
          <div class="album-release-date">
            <span>{{ album.year_of_release }}</span>
          </div>
        </div>
        <div class="album-cover-container">
          <img src="{{ album.album_cover }}" />
        </div>
      </div>

      <div class="genre-tags">
        <ul>
          {% for genre in genres %}
          <li class="genre">
            <a href="tags/{{ genre | slugify}}.html">{{ genre }}</a>
          </li>
          {% endfor %}
        </ul>
      </div>

      <div class="album-block-2">
        <div class="sub-album-block-2">
          <div class="album-songs-container">
            <div class="album-list-header">
              <span>Songs</span>
            </div>
            <div class="album-list-container">
              <ol>
                <!-- Counter for span element  -->
                {% assign n = 1 %} {% for song in songs %}

                <li class="album-list">
                  <span>{{ n }}</span>
                  <h3>{{ song }}</h3>
                </li>

                <!-- Increment counter by 1  -->
                {% assign n = n | plus: 1 %} {% endfor %}
              </ol>
            </div>
          </div>
        </div>
      </div>
    </div>

    {% endif %}

    <!-- Increment counter by 1 -->
    {% assign i = i | plus: 1 %} {% endfor %}

  </div>
</div>
