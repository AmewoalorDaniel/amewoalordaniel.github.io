---
title: "Gallery"
permalink: /gallery/
author_profile: true
---

*Fieldwork, laboratory work, conferences, and scientific events.*

<!--
HOW TO ADD PHOTOS
─────────────────
1. Upload images to /images/ in your repo (e.g. tekconfab25.jpg)
2. In each <figure> block below, change:
     src="/images/YOUR-FILENAME.jpg"
     alt="Short description"
     and update the <figcaption> text
3. Add more <figure> blocks by copy-pasting an existing one
-->

<style>
.photo-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(265px, 1fr));
  gap: 18px;
  margin-top: 24px;
}
.photo-grid figure {
  margin: 0;
  border-radius: 8px;
  overflow: hidden;
  background: #f4f4f4;
}
.photo-grid img {
  width: 100%;
  height: 210px;
  object-fit: cover;
  display: block;
  transition: opacity 0.2s;
}
.photo-grid img:hover { opacity: 0.85; cursor: zoom-in; }
.photo-grid figcaption {
  padding: 9px 13px 11px;
  font-size: 0.83em;
  color: #555;
  line-height: 1.45;
}
</style>

<div class="photo-grid">

  <figure>
    <img src="/images/tekconfab25.jpg" alt="TEKCONFAB 2025">
    <figcaption><strong>TEKCONFAB'25</strong> · KNUST Scientific Conference, November 2025 · Presenting the LMNA Mandibuloacral Dysplasia poster.</figcaption>
  </figure>

  <figure>
    <img src="/images/Clinical_oncology.JPG" alt="Oncology Training Workshop 2025">
    <figcaption><strong> Clinical Oncology Training Centre</strong> · Kumasi, October 2025 · Training on multidisciplinary approaches in oncology to enhance patient outcomes, including challenges faced in underrepresented regions.</figcaption>
  </figure>

  <figure>
    <img src="/images/posterfest24.jfif" alt="Faculty of Physical and Computational Sciences, October 2024">
    <figcaption><strong>KNUST PosterFest'24</strong> · Kumasi, October 2024 · Presenting research on lymphatic filariasis vaccine design.</figcaption>
  </figure>

  <figure>
    <img src="/images/hugene-lab.jpg" alt="HuGene Lab">
    <figcaption><strong>HuGene Lab, KNUST</strong> · DNA extraction and sample processing for the neurodevelopmental disorders WGS project.</figcaption>
  </figure>

  <figure>
    <img src="/images/kccr-2025.jpg" alt="KCCR Internship 2025">
    <figcaption><strong>KCCR Graduate Internship</strong> · Kumasi Centre for Collaborative Research in Tropical Medicine, 2025. View of ring-stage malaria examined with bright microscope.</figcaption>
  </figure>

  <figure>
    <img src="/images/kath-clinic.jpg" alt="Pediatric Neurology Clinic KATH">
    <figcaption><strong>Pediatric Neurology Clinic</strong> · Komfo Anokye Teaching Hospital · Sample collection for the neurodevelopmental disorders WGS project.</figcaption>
  </figure>

</div>
