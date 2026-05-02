---
layout: default
title: Toby Young - Portfolio
permalink: /projects/
---

<style>
  .gallery-container {
    display: flex;
    justify-content: center;
    padding: 2rem;
  }

  .project-gallery {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(220px, 220px));
    gap: 1.5rem;
    justify-content: center;
  }

  .gallery-item {
    width: 220px;
  }

  .gallery-item a {
    display: block;
    text-decoration: none;
    color: inherit;
  }

  .gallery-item-img {
    width: 220px;
    height: 160px;
    display: flex;
    align-items: center;
    justify-content: center;
    background: #f0f0eb;
    border: 1px solid #ddd;
    border-radius: 6px;
    overflow: hidden;
  }

  .gallery-item-img img {
    width: 100%;
    height: 100%;
    object-fit: contain;
    padding: 8px;
    box-sizing: border-box;
  }

  .gallery-item a:hover .gallery-item-img {
    border-color: #aaa;
    background: #e8e8e2;
  }

  .gallery-item p {
    margin: 0.5rem 0 0;
    font-size: 14px;
    text-align: center;
    color: #333;
    line-height: 1.4;
  }
</style>

<div class="gallery-container">
  <div class="project-gallery">
    {% for project in site.projects %}
      <div class="gallery-item">
        <a href="{{ project.url | relative_url }}">
          <div class="gallery-item-img">
            <img src="{{ project.image | relative_url }}" alt="{{ project.title }}" />
          </div>
          <p>{{ project.title }}</p>
        </a>
      </div>
    {% endfor %}
  </div>
</div>