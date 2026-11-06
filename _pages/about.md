---
layout: about
title: About
permalink: /
subtitle: Research Assistant | Microelectronics &amp; AI Hardware Researcher<br>Newcastle University, United Kingdom

profile:
  align: right
  image: profile-placeholder.svg # TODO: replace with a personal photograph in assets/img/.
  image_circular: true
  more_info: >
    <p>Newcastle University</p>
    <p>United Kingdom</p>

selected_papers: false
social: true
announcements:
  enabled: false # The collection is rendered below with years only.
latest_posts:
  enabled: false
---

I am a Research Assistant at Newcastle University, UK, working on energy-efficient computing architectures for artificial intelligence, with a particular focus on in-memory computing and integrated circuit design.

I hold an MSc in Microelectronics: Systems and Devices from Newcastle University, where I was a Chevening Scholar, and an Engineering degree in Electronics and Computer Science from the University of Kinshasa, Democratic Republic of the Congo.

My research focuses on the intersection of microelectronics, computer architecture, and machine learning, particularly memory-centric computing architectures that reduce data movement and enable energy-efficient computation.

My recent work investigates SRAM-based in-memory computing architectures for Tsetlin Automata, with an emphasis on hardware-efficient state updates, circuit-level design, and low-power implementation.

My broader interests include VLSI design, emerging memory technologies, digital and mixed-signal integrated circuits, FPGA-based acceleration, and Edge AI.

## Research interests

In-Memory Computing · VLSI and Integrated Circuit Design · Energy-Efficient AI Hardware · Emerging Memory Technologies · Edge AI · Computer Architecture

## Featured research

[SRAM-Based In-Memory Computing for Tsetlin Automata]({{ '/projects/sram-in-memory-computing/' | relative_url }}) — investigation of training-aware memory architectures for hardware-efficient state updates.

Explore my [research directions]({{ '/research/' | relative_url }}) and [technical projects]({{ '/projects/' | relative_url }}).

## Latest news

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

## Academic and professional links

[GitHub](https://github.com/maz-git-design) · [Publications]({{ '/publications/' | relative_url }}) · [Online CV]({{ '/cv/' | relative_url }})
