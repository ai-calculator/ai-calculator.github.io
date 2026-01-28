---
layout: page
title: Download AI
permalink: /download/
---

<div class="downloads-container">
  <p>Download our latest AI tools and resources from the list below.</p>
  
  <ul class="download-list list-reset">
    {% for file in site.static_files %}
      {% if file.path contains '/ai-download/' %}
        <li class="download-item">
          <div class="download-item__info">
            <i class="ion ion-md-document"></i>
            <span class="download-item__name">{{ file.name }}</span>
          </div>
          <a href="{{ site.baseurl }}{{ file.path }}" class="btn btn--primary" download>Download</a>
        </li>
      {% endif %}
    {% endfor %}
  </ul>
</div>

<style>
.downloads-container {
  margin-top: 30px;
}
.download-list {
  display: flex;
  flex-direction: column;
  gap: 15px;
  margin-top: 20px;
}
.download-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 20px;
  background: var(--background-alt);
  border-radius: 8px;
  border: 1px solid var(--border-color);
  transition: transform 0.2s ease;
}
.download-item:hover {
  transform: translateY(-2px);
}
.download-item__info {
  display: flex;
  align-items: center;
  gap: 10px;
  font-weight: 500;
}
.download-item__info i {
  font-size: 1.5rem;
  color: var(--primary-color);
}
.btn--primary {
  padding: 8px 20px;
  border-radius: 5px;
  background: #007bff;
  color: white;
  text-decoration: none;
  font-size: 0.9rem;
  font-weight: 500;
}
.btn--primary:hover {
  background: #0056b3;
}
</style>
