{% for band in site.categories %}

<!--  -->

{% assign band_name = band[0] | remove: "Music" %}

<!-- remove filter leaves "" which is bad for slugify filter so I am checking for it -->

{% if band_name != empty %}

<ul>
  <li>
    <a
      href="{{ site.baseurl }}/{{ page.band_page_url }}/{{ band_name | slugify }}"
      ><h1>{{ band_name | replace: "-", " " }}</h1></a
    >
  </li>
</ul>
{% endif %}
<!--  -->
{% endfor %}

<h2>List of all bands</h2>

{% assign categories_sorted = site.categories | sort %}

<!--  -->

{% for band in categories_sorted %}

<!--  -->

{% assign band_name = band[0] | remove: "Music" %}

<!-- remove filter leaves "" which is bad for slugify filter so I am checking for it -->

{% if band_name != empty %}
<!--  -->

{% assign first_band = band[1] | sort: year_of_release %}
<!--  -->
{% for data in first_band  %}

<!--  -->
<div class="flex flex-col">
  <div class="bands-container">
    <div class="band-desc">
      <h2>{{ band_name | replace: "-", " " }}</h2>
      <p>
        {{ data.band_desc | truncatewords: 75 }}
        <a
          href="{{ site.baseurl }}/{{ page.band_page_url }}/{{ band_name | slugify }}"
          >Read more</a
        >
      </p>
    </div>
    <div class="band-photo"></div>
  </div>
</div>
<!--  -->
{% endfor %}
<!--  -->
{% endif %}
<!--  -->
{% endfor %}
