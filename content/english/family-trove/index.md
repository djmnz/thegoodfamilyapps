---
title: "Family Trove"
meta_title: "Family Trove"
description: "Requesting your own personal data"
image: "/images/about.png"
draft: false
---

<style>
    
ul.timeline {
  --col-gap: 2rem;
  --row-gap: 2rem;
  --line-w: 0.25rem;
  display: grid;
  grid-template-columns: var(--line-w) 1fr;
  grid-auto-columns: max-content;
  column-gap: var(--col-gap);
  list-style: none;
  width: min(60rem, 90%);
  margin-inline: auto;
}

/* line */
ul.timeline::before {
  content: "";
  grid-column: 1;
  grid-row: 1 / span 20;
  background: rgb(225, 225, 225);
  border-radius: calc(var(--line-w) / 2);
}

/* columns*/

/* row gaps */
ul.timeline li:not(:last-child) {
  margin-bottom: var(--row-gap);
}

/* card */
ul.timeline li {
  grid-column: 2;
  --inlineP: 1.5rem;
  margin-inline: var(--inlineP);
  grid-row: span 2;
  display: grid;
  grid-template-rows: min-content min-content min-content;
}

/* date */
ul.timeline li .date {
  --dateH: 3rem;
  height: var(--dateH);
  margin-inline: calc(var(--inlineP) * -1);

  text-align: center;
  background-color: var(--accent-color);

  color: white;
  font-size: 1.25rem;
  font-weight: 700;

  display: grid;
  place-content: center;
  position: relative;

  border-radius: calc(var(--dateH) / 2) 0 0 calc(var(--dateH) / 2);
}

/* date flap */
ul.timeline li .date::before {
  content: "";
  width: var(--inlineP);
  aspect-ratio: 1;
  background: var(--accent-color);
  background-image: linear-gradient(rgba(0, 0, 0, 0.2) 100%, transparent);
  position: absolute;
  top: 100%;

  clip-path: polygon(0 0, 100% 0, 0 100%);
  right: 0;
}

/* circle */
ul.timeline li .date::after {
  content: "";
  position: absolute;
  width: 2rem;
  aspect-ratio: 1;
  background: var(--bgColor);
  border: 0.3rem solid var(--accent-color);
  border-radius: 50%;
  top: 50%;

  transform: translate(50%, -50%);
  right: calc(100% + var(--col-gap) + var(--line-w) / 2);
}

/* title descr */
ul.timeline li .title,
ul.timeline li .descr {
  background: var(--bgColor);
  position: relative;
  padding-inline: 1.5rem;
}
ul.timeline li .title {
  overflow: hidden;
  padding-block-start: 1.5rem;
  padding-block-end: 1rem;
  font-weight: 500;
}
ul.timeline li .descr {
  padding-block-end: 1.5rem;
  font-weight: 300;
}

/* shadows */
ul.timeline li .title::before,
ul.timeline li .descr::before {
  content: "";
  position: absolute;
  width: 90%;
  height: 0.5rem;
  background: rgba(0, 0, 0, 0.5);
  left: 50%;
  border-radius: 50%;
  filter: blur(4px);
  transform: translate(-50%, 50%);
}
ul.timeline li .title::before {
  bottom: calc(100% + 0.125rem);
}

ul.timeline li .descr::before {
  z-index: -1;
  bottom: 0.25rem;
}

@media (min-width: 40rem) {
  ul.timeline {
    grid-template-columns: 1fr var(--line-w) 1fr;
  }
  ul.timeline::before {
    grid-column: 2;
  }
  ul.timeline li:nth-child(odd) {
    grid-column: 1;
  }
  ul.timeline li:nth-child(even) {
    grid-column: 3;
  }

  /* start second card */
  ul.timeline li:nth-child(2) {
    grid-row: 2/4;
  }

  ul.timeline li:nth-child(odd) .date::before {
    clip-path: polygon(0 0, 100% 0, 100% 100%);
    left: 0;
  }

  ul.timeline li:nth-child(odd) .date::after {
    transform: translate(-50%, -50%);
    left: calc(100% + var(--col-gap) + var(--line-w) / 2);
  }
  ul.timeline li:nth-child(odd) .date {
    border-radius: 0 calc(var(--dateH) / 2) calc(var(--dateH) / 2) 0;
  }
}
.timeline {
  --color: rgba(30, 30, 30);
  --bgColor: rgba(245, 245, 245);
  min-height: 100vh;
  display: grid;
  align-content: center;
  gap: 2rem;
  padding: 2rem;
  color: var(--color);
  background: var(--bgColor);
}

</style>

# What is Family Trove?

The Mission of Family Trove is to go beyond the idea of tracking points for children, but allowing parents to acknowledge the children efforts, enabling parents to have a more clear communication channel with their children - by tracking points and agreements (what we call "contracts")

{{< notice "warning" >}}
The app is currently in testing phase, if you are interested in helping testing, please contact us.
{{< /notice >}}


# Gallery

{{< gallery dir="images/gallery" class="" height="500" width="250" webp="true" command="Fit" option="" zoomable="true" >}}

# Roadmap

{{< notice "info" >}}
This roadmap is indicative only and subject to change according to the feedback and usage of the app.
{{< /notice >}}


<ul class="timeline">
    <li style="--accent-color:#41516C">
        <div class="date">November 2024</div>
        <div class="title">Android Internal testing</div>
        <div class="descr">Simple point system with two types of points: <strong>Good points</strong> and <strong>Improvements Points</strong>.</div>
    </li>
    <li style="--accent-color:#FBCA3E">
        <div class="date">January 2025</div>
        <div class="title">Feedback and improvements</div>
        <div class="descr">Adding more background and profiles for selection.</div>
    </li>
    <li style="--accent-color:#E24A68">
        <div class="date">February 2025</div>
        <div class="title">iPhone Version</div>
        <div class="descr">Further feedback and improvements according to testing results. Start release for iPhone</div>
    </li>
    <li style="--accent-color:#1B5F8C">
        <div class="date">April 2025</div>
        <div class="title">Premium Version</div>
        <div class="descr">Allow data to be synchronised between multiple devices</div>
    </li>
</ul>