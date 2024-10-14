---
layout: about
title: about
permalink: /


profile:
  align: left
  image: profile1.jpeg
  image_circular: false # crops the image to make it circular
  more_info: >
    Sungjun Sun Lee
    zinpolygon35@gmail.com

news: false # includes a list of news items
selected_papers: false # includes a list of papers marked as "selected={true}"
social: false # includes social icons at the bottom of the page
---

I am interested in <b>HCI, with a focus on AR/VR and AI programming.</b> I enjoy creating software that combines these technologies, such as <b>educational programs or control systems that support collaboration.</b>

I am also interested in using <b>AI models like GPT and reinforcement learning to build human-AI interactions in virtual environments or user interfaces.</b> Rather than focusing on technical engineering or optimization, I aim to <b>explore new ideas for using AI and computer interaction to enhance education, productivity, and gaming in a human-centered way.</b>

My background includes research and development in AR/VR using Unity during both my undergraduate and graduate studies. During my undergraduate years, I made on <b>creating emotional interactions with AI-driven NPCs in an AR environment.</b> In my master's, I researched <b>reducing motion sickness in VR using sound, specifically studying whether reverse sound stimuli can help reduce motion sickness.</b>

I also have experience building various applications using <b>Python</b>, such as web applications with Flask and FastAPI, desktop software, automation scripts, chatbots, and trading systems. And I have an <b>experience of publishing mobile games ( 5 more ) and VR Game.</b> I am using Unity Engine for making games. Additionally, I have used <b>JavaScript</b> to develop APIs and automation servers, studied <b>smart contracts with Solidity for blockchain applications</b>, and <b>created over 50 trading indicators using Pinescript</b>.
<div class="clearfix"></div>

---

## Publications



<div class="publications">

{% bibliography %}

</div>

<div class="clearfix"></div>



---
## Education & Experience
<div class="education"></div>

<div class="education-section">
  {% assign education = site.data.resume.education %}
  <ul class="card-text font-weight-light list-group list-group-flush">
    {% for content in education %}
      <li class="list-group-item">
        <div class="row">
          <div class="col-xs-2 col-sm-2 col-md-2 text-center date-column">
            <table class="table-cv">
              <tbody>
                <tr>
                  <td>
                    {% if content.startDate and content.endDate %}
                      <span class="badge font-weight-bold danger-color-dark text-uppercase align-middle" style="min-width: 75px">
                        {{ content.startDate }} - {{ content.endDate }}
                      </span>
                    {% endif %}
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
          <div class="col-xs-10 col-sm-10 col-md-10 mt-2 mt-md-0">
            <h6 class="title font-weight-bold ml-1 ml-md-4">{{ content.studyType }} in {{ content.area }}</h6>
            <h6 class="ml-1 ml-md-4" style="font-size: 0.95rem">
              <a href="{{ content.url }}" target="_blank">{{ content.institution }}</a>
            </h6>
            <p class="ml-1 ml-md-4" style="font-size: 0.85rem">{{ content.location }}</p>
            {% if content.score %}
              <p class="ml-1 ml-md-4" style="font-size: 0.85rem">Score: {{ content.score }}</p>
            {% endif %}
          </div>
        </div>
      </li>
    {% endfor %}
  </ul>
</div>

<div class="clearfix"></div>

---

## Projects

<div class="post">


  <ul class="post-list">

    {% if page.pagination.enabled %}
      {% assign postlist = paginator.posts %}
    {% else %}
      {% assign postlist = site.posts %}
    {% endif %}

    {% for post in postlist %}

    {% if post.external_source == blank %}
      {% assign read_time = post.content | number_of_words | divided_by: 180 | plus: 1 %}
    {% else %}
      {% assign read_time = post.feed_content | strip_html | number_of_words | divided_by: 180 | plus: 1 %}
    {% endif %}
    {% assign year = post.date | date: "%Y" %}
    {% assign tags = post.tags | join: "" %}
    {% assign categories = post.categories | join: "" %}

    <li>

{% if post.thumbnail %}

<div class="row">
          <div class="col-sm-9">
{% endif %}
        <h3>
        {% if post.redirect == blank %}
          <a class="post-title" href="{{ post.url | relative_url }}">{{ post.title }}</a>
        {% elsif post.redirect contains '://' %}
          <a class="post-title" href="{{ post.redirect }}" target="_blank">{{ post.title }}</a>
          <svg width="2rem" height="2rem" viewBox="0 0 40 40" xmlns="http://www.w3.org/2000/svg">
            <path d="M17 13.5v6H5v-12h6m3-3h6v6m0-6-9 9" class="icon_svg-stroke" stroke="#999" stroke-width="1.5" fill="none" fill-rule="evenodd" stroke-linecap="round" stroke-linejoin="round"></path>
          </svg>
        {% else %}
          <a class="post-title" href="{{ post.redirect | relative_url }}">{{ post.title }}</a>
        {% endif %}
      </h3>
      <p>{{ post.description }}</p>
      <p class="post-tags">
      

          {% if tags != "" %}
          &nbsp; &middot; &nbsp;
            {% for tag in post.tags %}
            <a href="{{ tag | slugify | prepend: '/blog/tag/' | prepend: site.baseurl}}">
              <i class="fa-solid fa-hashtag fa-sm"></i> {{ tag }}</a>
              {% unless forloop.last %}
                &nbsp;
              {% endunless %}
              {% endfor %}
          {% endif %}

          {% if categories != "" %}
          &nbsp; &middot; &nbsp;
            {% for category in post.categories %}
            <a href="{{ category | slugify | prepend: '/blog/category/' | prepend: site.baseurl}}">
              <i class="fa-solid fa-tag fa-sm"></i> {{ category }}</a>
              {% unless forloop.last %}
                &nbsp;
              {% endunless %}
              {% endfor %}
          {% endif %}
    </p>

{% if post.thumbnail %}

</div>

  <div class="col-sm-3">
    <img class="card-img" src="{{post.thumbnail | relative_url}}" style="object-fit: cover; height: 90%" alt="image">
  </div>
</div>
{% endif %}
    </li>

    {% endfor %}

  </ul>

{% if page.pagination.enabled %}
{% include pagination.liquid %}
{% endif %}

</div>
<div class="clearfix"></div>


---

## Languages
<div class="languages-section">
  {% assign languages = site.data.resume.languages %}
  <ul class="card-text font-weight-light list-group list-group-flush">
    {% for language in languages %}
      <li class="list-group-item">
        <div class="row">
          <div class="col-md-2">
            {% if language.icon %}
              <i class="{{ language.icon }}"></i>
            {% endif %}
          </div>
          <div class="col-md-10">
            <h6 class="title font-weight-bold">{{ language.language }}</h6>
            <p>Fluency: {{ language.fluency }}</p>
          </div>
        </div>
      </li>
    {% endfor %}
  </ul>
</div>

<div class="clearfix"></div>

---

## Skills
<div class="skills-section">
  {% assign skills = site.data.resume.skills %}
  <ul class="card-text font-weight-light list-group list-group-flush">
    {% for skill in skills %}
      <li class="list-group-item">
        <div class="row">
          <div class="col-md-2 text-center">
            <i class="{{ skill.icon }}"></i>
          </div>
          <div class="col-md-10">
            <h6 class="title font-weight-bold">{{ skill.name }} - {{ skill.level }}</h6>
            {% if skill.keywords %}
              <p>Keywords:</p>
              <ul>
                {% for keyword in skill.keywords %}
                  <li>{{ keyword }}</li>
                {% endfor %}
              </ul>
            {% endif %}
          </div>
        </div>
      </li>
    {% endfor %}
  </ul>
</div>

<div class="clearfix"></div>
