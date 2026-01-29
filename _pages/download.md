---
layout: page
title: Download AI Apps & Plugins 
image: /images/ai-download-image.webp
permalink: /download/
---

<div class="downloads-container">
  
  <ul class="download-list list-reset">
    {% for file in site.static_files %}
      {% if file.path contains '/ai-download/' %}
        <li class="download-item">
          <div class="download-item__header">
            <div class="download-item__info">
              <i class="ion ion-md-document"></i>
              <div class="download-item__details">
            <div class="download-item__actions">
              {% if file.name == 'rankready-ai.zip' %}
                <a href="{{ site.baseurl }}/rankready-ai-plugin/" class="btn btn--outline">View Details</a>
              {% endif %}
              <a href="{{ site.baseurl }}{{ file.path }}" class="btn btn--primary" download>Download</a>
            </div>
          </div>
          
          {% if file.name == 'rankready-ai.zip' %}
          <div class="download-item__content">
            <p><strong>RankReady AI</strong> is a premium WordPress plugin designed to generate high-quality, human-like content and automate your blog's publishing schedule. It features advanced AI logic for keyword-based and title-based article generation.</p>
            <a href="{{ site.baseurl }}/rankready-ai-plugin/" class="link-more">Learn more & Installation steps &rarr;</a>
          </div>
          {% endif %}
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
  gap: 20px;
  margin-top: 20px;
}
.download-item {
  display: flex;
  flex-direction: column;
  padding: 20px;
  background: var(--background-alt);
  border-radius: 12px;
  border: 1px solid var(--border-color);
  box-shadow: 0 4px 6px rgba(0,0,0,0.05);
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}
.download-item:hover {
  transform: translateY(-3px);
  box-shadow: 0 8px 15px rgba(0,0,0,0.1);
}
.download-item__header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}
.download-item__info {
  display: flex;
  align-items: center;
  gap: 15px;
}
.download-item__details {
  display: flex;
  flex-direction: column;
  gap: 4px;
}
.download-item__name {
  font-weight: 600;
  font-size: 1.1rem;
  color: var(--heading-color);
}
.badge {
  display: inline-block;
  padding: 2px 8px;
  border-radius: 4px;
  font-size: 0.75rem;
  font-weight: 600;
  text-transform: uppercase;
}
.badge--wp {
  background: #21759b;
  color: white;
}
.download-item__info i {
  font-size: 2rem;
  color: var(--primary-color);
}
.download-item__actions {
  display: flex;
  gap: 10px;
}
.download-item__content {
  margin-top: 15px;
  padding-top: 15px;
  border-top: 1px solid var(--border-color);
  font-size: 0.95rem;
  color: var(--text-color);
  line-height: 1.6;
}
.feature-list {
  list-style: none;
  padding: 0;
  margin: 10px 0 0 0;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 8px;
}
.feature-list li {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 0.9rem;
}
.feature-list i {
  color: #28a745;
}
.link-more {
  display: inline-block;
  margin-top: 10px;
  font-weight: 600;
  color: var(--primary-color);
  text-decoration: none;
}
.link-more:hover {
  text-decoration: underline;
}
.btn--primary, .btn--outline {
  padding: 10px 24px;
  border-radius: 6px;
  text-decoration: none;
  font-size: 0.95rem;
  font-weight: 600;
  transition: all 0.2s;
  display: inline-block;
}
.btn--primary {
  background: #007bff;
  color: white;
  border: 1px solid #007bff;
}
.btn--primary:hover {
  background: #0056b3;
}
.btn--outline {
  background: transparent;
  color: #007bff;
  border: 1px solid #007bff;
}
.btn--outline:hover {
  background: #007bff;
  color: white;
}
</style>
