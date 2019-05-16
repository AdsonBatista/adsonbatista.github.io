---
layout: page
title: Arquivo
permalink: /tags/
---
# Lista de Posts!
<!-- I follow the file from cloudoftags file of my github(https://github.com/hyunyoung2/hyunyoung2.github.io/blob/master/cloudoftags.html)-->
<!-- this code from https://github.com/codinfox/codinfox-lanyon/blob/dev/blog/categories.html-->
  <div class="page"> 
    {% assign tags = site.tags | sort %}
    <div class="items">
    {% for tag in tags %}
    <a href="#{{ tag[0] | slugify }}"> <!-- style="color: #1C1C1C;" is font color of cloud index -->
    <div class="item">
      <span> <!-- I get rid of left option -->
        {{ tag[0] }} <i><sub>[{{ tag | last | size }}]</sub></i>
      </span>
      </div>
    </a>
    {% endfor %}
    </div>
 <!--  </div>-->
  <hr/> <!-- margin-top and margin-bottom in main.css -->
  <!-- <div class="post-preview">--> <!--post-preview -->
    {% for tag in tags %} <!-- style="padding-top: 70px;" is used to deal with nav-custom bar -->
      <h2 id="{{ tag[0] | slugify }}"> {{ tag[0] }}  <i><sub>[{{ tag | last | size }}]</sub></i></h2> <!-- I added new class -->
      <ul> <!-- post-subtitle -->
        {% for post in tag[1] %}
          <a href="{{ site.baseurl }}{{ post.url }}">
        <li>
          {{ post.title }}
        <small class="post-meta" style="color: #313131;"> - Posted on {{ post.date | date: "%B %-d, %Y" }}</small>
        </li>
        </a>
        {% endfor %}
      </ul>
        <a href="#top" class="btn btn-default" style="font-size: 15px; padding: 0px 5px; margin-left: 30px">
          <span class="fa fa-refresh" aria-hidden="true"></span> Go back to the top
        </a> 
        <hr/>
    {% endfor %}
  </div>