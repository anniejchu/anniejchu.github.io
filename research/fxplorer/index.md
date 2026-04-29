---
layout: page
title: FXplorer
which_category: research
permalink: /fxplorer/
---
<!-- <style>
  sup {
    font-size: 0.75em;
    vertical-align: super;
    line-height: 0;
  }
  .container {
    max-width: 900px;
    font-family: "Inter", system-ui, -apple-system, BlinkMacSystemFont, sans-serif;
    font-size: 14px;
    line-height: 1.5;
    margin: 0 auto; /* centers the container */
    margin-bottom: -2em;
  }
</style>

<head>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css">
</head> -->


<p align="center"> <strong><font size="5">FXplorer: A Map-Based Interface for Exploratory Audio Effect Design</font></strong> </p>
<p align="center"><font size="3"><u>Annie Chu</u>, Jason Brent Smith, Bryan Pardo</font></p>
<p align="center"><font size="3">Northwestern University</font></p>

<hr> 

<div style="text-align: center; margin: 10px 0;">
  <span style="
    font-size: 16px;
    /* font-weight: bold; */
    color: blue;
    margin-right: 12px;
  ">
    Accepted to NIME 2026
  </span>

  <a href="#" aria-disabled="true" style="
    display: inline-block;
    padding: 6px 14px;
    font-size: 14px;
    font-weight: bold;
    color: #5308f5;
    background-color: #f7f7f7;
    text-decoration: none;
    border-radius: 6px;
    border: 2px solid #5308f5;
    pointer-events: none;
    cursor: not-allowed;
    opacity: 1.0;
  ">
    Paper link (soon)
  </a>
</div>

<hr>

## **What's FXplorer?**
***FXplorer*** is a 2D map-based interface for exploratory audio effect design. It lets users navigate audio effects spatially, continuously, and by ear, rather than through isolated presets, modules, and parameters.

Reflecting the cyclical nature of creative work, this interface aims to support users in moving towards a sonic goal via fluid movement between divergent exploration (what's possible?) and convergent refinement (how do I get closer to the sound I want?”).

Derived from design requirements for exploratory audio FX, ***FXplorer*** combines perceptually organized 2D maps, recent embedding models for timbral and semantic search, Tone.js real-time playback, and interpretable DAW-style controls.

## **How does it work?**
Users upload a dry audio sample and choose FX modules or FX chains to explore; ***FXplorer*** generates an adjustable set of effect variants, which users can browse by ear, search with text or audio examples, interpolate or “slingshot” between points, and refine in real time.

