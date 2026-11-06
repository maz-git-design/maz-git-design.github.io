---
layout: page
title: News
permalink: /news/
description: Academic updates.
nav: false
---

<div class="news table-responsive">
  <table class="table table-sm table-borderless">
    <caption class="sr-only">Academic updates by year</caption>
    <tbody>
      {% assign updates = site.news | sort: "order" | reverse %}
      {% for item in updates limit: 4 %}
      <tr>
        <th scope="row">{{ item.year }}</th>
        <td>{{ item.content | markdownify | remove: '<p>' | remove: '</p>' }}</td>
      </tr>
      {% endfor %}
    </tbody>
  </table>
</div>
