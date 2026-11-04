---
layout: archive
title: "Gallery"
permalink: /gallery/
author_profile: true
# ------------------------------------------------------------------
# HOW TO ADD PHOTOS
# 1. Put the image in images/gallery/  (JPG/PNG/WebP, ~1600px wide)
# 2. Add it to one of the lists below (or create a new list + block).
#    image_path and url use the same file; url makes it open full-size.
# 3. Delete the placeholder-*.svg entries once you have real photos.
# ------------------------------------------------------------------
gallery_lab:
  - url: gallery/placeholder-lab-1.svg
    image_path: gallery/placeholder-lab-1.svg
    alt: "With lab mates at TANUH, IISc"
    title: "With lab mates at TANUH, IISc Bengaluru (2026)"
  - url: gallery/placeholder-lab-2.svg
    image_path: gallery/placeholder-lab-2.svg
    alt: "Research group, IIT Indore"
    title: "Research group, Dept. of CSE, IIT Indore (2025)"
  - url: gallery/placeholder-campus-1.svg
    image_path: gallery/placeholder-campus-1.svg
    alt: "IISc campus"
    title: "IISc campus, Bengaluru"
gallery_conf:
  - url: gallery/placeholder-conference-1.svg
    image_path: gallery/placeholder-conference-1.svg
    alt: "Presenting at EMNLP 2026"
    title: "Presenting CliQ-RRG at EMNLP 2026"
  - url: gallery/placeholder-talk-1.svg
    image_path: gallery/placeholder-talk-1.svg
    alt: "Oral presentation at RIC 2026"
    title: "Oral presentation, Research and Industrial Conclave, IIT Indore (Jan 2026)"
  - url: gallery/placeholder-award-1.svg
    image_path: gallery/placeholder-award-1.svg
    alt: "Best Research Presentation award"
    title: "Best Research Presentation, Symposium 4.0, IIT Indore (Feb 2026)"
---

{% include base_path %}

<p class="pub__intro">Lab mates, conferences, talks and campus life. Click a photo to view it full size.</p>

<div class="gallery__block">
<h2>Lab and colleagues</h2>
{% include gallery id="gallery_lab" %}
<p class="gallery__caption">Hover over a photo for its caption.</p>
</div>

<div class="gallery__block">
<h2>Conferences, talks and awards</h2>
{% include gallery id="gallery_conf" %}
</div>
