---
layout: page
title: Projects
permalink: /projects/
description: Research and technical work in microelectronics, digital systems, and embedded computing.
nav: true
nav_order: 3
---

This portfolio spans In-Memory Computing, VLSI and IC Design, FPGA and Digital Systems, Embedded Systems, and AI Hardware. The projects below document work undertaken; broader research interests are described on the [Research page]({{ '/research/' | relative_url }}).

<div class="projects">
  {% assign sorted_projects = site.projects | sort: "importance" %}
  <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
</div>
