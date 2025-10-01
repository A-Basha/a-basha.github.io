---
layout: single
title: Experience
permalink: /experience/
author_profile: true
---


<style>
    

/* personal style  */
/* Experience page */

.exp-entry {
  display: flex;
  justify-content: normal;
  align-items: flex-start;
  margin-bottom: 1.5em;
  flex-wrap: wrap;
}


.exp-logo, .exp-logo {
  width: 120px;
  /* height: 50px; */
  object-fit: contain;
  /* transition: transform 0.2s; */
}

.logo-wrapper {
  background-color: var(--global-bg-color);
  display: inline-flex;
  align-items: center;
  justify-content: center;
  margin-top: 10px;
  margin-left: 10px;
  min-width: 80px;
  min-height: 50px;
  padding: 8px;
  border-radius: 8px;
    margin-right: 5%;
    max-width: 20%;
}

.exp-details {
  max-width: 75%;
}

.exp-degree {
  font-weight: bold;
  font-size: 1.1em;
}

.exp-univ {
  margin-top: 0.2em;
  font-style: italic;
    display: flex;
}

.exp-univ div{
    font-style: normal;
}

.exp-thesis {
  margin-top: 0.3em;
  font-size: 0.97em;
}

.meta-text {
  min-width: 170px;
  color: var(--meta-color);
  font-size: 0.95em;
}

</style>

{% include base_path %}
<div class="experience-list">

    <div class="exp-entry">

    <div class="logo-wrapper">
        <img class="exp-logo" src="{{ bakerHughes.png | prepend: "/images/" | prepend: base_path }}" alt="BH Logo">
    </div>

    <div class="exp-details">
        <div class="exp-degree">
        Digitalization and Pipeline Management
            <!-- <a href="https://www.bakerhughes.com/" target="_blank" rel="noopener noreferrer">
            <i class="fas fa-fw fa-link icon-pad-right" aria-hidden="true"></i></a> -->
        </div>

        <div class="exp-univ">
            <a href="https://www.bakerhughes.com/" target="_blank" rel="noopener noreferrer">Baker Hughes</a>
            <div class="exp-loca">&nbsp; – Hamburg, Germany</div>
        </div>

        <div class="meta-text">
         Feb 2024 – Present
        </div>

        <div class="exp-thesis">
         <ul>
         <li>Developing and implementing automation and software solutions to enhance efficiency and functionality in production processes.</li>
         <li>Collaborated with the team to digitalize business objectives and maintain active piplines, while also conducting training sessions to support the adoption of new digital tools and workflows.</li>
         </ul>
        </div>

    </div>


    </div>


</div>
