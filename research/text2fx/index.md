---
layout: page
# title: Text2FX
which_category: research
permalink: /text2fx/
---
<style>
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
</head>



<!-- ## Text2FX -->
<div class="container">
  <p align="center"> <strong><font size="5">Text2FX: Harnessing CLAP Embeddings for Text-Guided Audio Effects</font></strong> </p>
  <p align="center"><font size="3"><u>Annie Chu</u>, Patrick O'Reilly, Julia Barnett, Bryan Pardo</font></p>
  <p align="center"><font size="3">Northwestern University</font></p>
</div>

<hr> 

<p align="center"><font size="3" color="blue">ICASSP 2025</font></p>

<hr> 



<div align="center">
  <a href="https://arxiv.org/abs/2409.18847" target="_blank" style="
    display: inline-block;
    padding: 8px 16px;
    font-size: 14px;
    color: rgb(222, 74, 33);
    background-color: white;
    text-decoration: none;
    border-radius: 5px;
    border: 2px solid rgb(222, 74, 33);
    transition: all 0.3s ease;
  "
  onmouseover="this.style.backgroundColor='rgb(222, 74, 33)'; this.style.color='white'; this.style.borderColor='rgb(200, 60, 20)'; this.style.boxShadow='0px 0px 10px rgba(222, 74, 33, 0.7)';"
  onmouseout="this.style.backgroundColor='white'; this.style.color='rgb(222, 74, 33)'; this.style.borderColor='rgb(222, 74, 33)'; this.style.boxShadow='none';">
    Paper (arXiv)
  </a>

  <a href="https://github.com/anniejchu/text2fx" style="
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 8px 16px;
      font-size: 14px;
      color: rgb(25, 118, 210); /* Blue text */
      background-color: white;
      text-decoration: none;
      border-radius: 5px;
      border: 2px solid rgb(25, 118, 210); /* Blue border */
      transition: all 0.3s ease;
    "
    onmouseover="this.style.backgroundColor='rgb(25, 118, 210)'; this.style.color='white'; this.style.borderColor='rgb(20, 100, 180)'; this.style.boxShadow='0px 0px 10px rgba(25, 118, 210, 0.7)';"
    onmouseout="this.style.backgroundColor='white'; this.style.color='rgb(25, 118, 210)'; this.style.borderColor='rgb(25, 118, 210)'; this.style.boxShadow='none';">
    <i class="fa-brands fa-github"></i>
    Github
  </a>
</div>



#### Abstract
**tl;dr: How can we apply audio effects (e.g., EQ, reverb, etc) with any natural language prompt (e.g., make this 'warm and cozy')?**

This work introduces Text2FX, a method that leverages CLAP embeddings and differentiable digital signal processing to control audio effects, such as equalization and reverberation, using open-vocabulary natural language prompts (e.g., "make this sound in-your-face and bold"). Text2FX operates without retraining any models, relying instead on single-instance optimization within the existing embedding space, thus enabling a flexible, scalable approach to open-vocabulary sound transformations through interpretable and disentangled FX manipulation. We show that CLAP encodes valuable information for controlling audio effects and propose two optimization approaches using CLAP to map text to audio effect parameters. While we demonstrate with CLAP, this approach is applicable to any shared text-audio embedding space. Similarly, while we demonstrate with equalization and reverberation, any differentiable audio effect may be controlled. We conduct a listener study with diverse text prompts and source audio to evaluate the quality and alignment of these methods with human perception.


#### Examples

| Target Word       |  FX    | Sample    | Clean Audio                           | FX'd Audio                          |
|------------|----------------|----------------------|---------------------------------------|---------------------------------------|
| **bright**     | EQ            | Music   | <audio controls><source src="/research/text2fx/audio/EQ_only/bright_guitar/guitar__ref.wav" type="audio/mpeg">Your browser does not support the audio element.</audio> | <audio controls><source src="/research/text2fx/audio/EQ_only/bright_guitar/guitar_600.wav" type="audio/mpeg">Your browser does not support the audio element.</audio> |
| **coming through an old telephone**    | EQ            | Speech   | <audio controls><source src="/research/text2fx/audio/EQ_only/coming through an old telephone_speech/original.wav" type="audio/mpeg">Your browser does not support the audio element.</audio> | <audio controls><source src="/research/text2fx/audio/EQ_only/coming through an old telephone_speech/cosine.wav" type="audio/mpeg">Your browser does not support the audio element.</audio> |
| **underwater** | Reverb           | Music   | <audio controls><source src="/research/text2fx/audio/Reverb_only/underwater_bass/original.wav" type="audio/mpeg">Your browser does not support the audio element.</audio> | <audio controls><source src="/research/text2fx/audio/Reverb_only/underwater_bass/cosine.wav" type="audio/mpeg">Your browser does not support the audio element.</audio> |
| **hollow and far away** | Reverb           | Speech   | <audio controls><source src="/research/text2fx/audio/Reverb_only/hollow-and-far-away_speech/speech__ref.wav" type="audio/mpeg">Your browser does not support the audio element.</audio> | <audio controls><source src="/research/text2fx/audio/Reverb_only/hollow-and-far-away_speech/speech_650.wav" type="audio/mpeg">Your browser does not support the audio element.</audio> |
| **dramatic** | EQ --> Reverb           | Music   | <audio controls><source src="/research/text2fx/audio/EQ_Reverb/dramatic_music/original.wav" type="audio/mpeg">Your browser does not support the audio element.</audio> | <audio controls><source src="/research/text2fx/audio/EQ_Reverb/dramatic_music/directional.wav" type="audio/mpeg">Your browser does not support the audio element.</audio> |
| **warm and full-bodied** | EQ --> Reverb           | Speech   | <audio controls><source src="/research/text2fx/audio/EQ_Reverb/warm and full-bodied_speech/original.wav" type="audio/mpeg">Your browser does not support the audio element.</audio> | <audio controls><source src="/research/text2fx/audio/EQ_Reverb/warm and full-bodied_speech/cosine.wav" type="audio/mpeg">Your browser does not support the audio element.</audio> |



<hr> 


#### How do we optimize?
##### Overview
We employ single-instance optimization (also referenced as inference-time optimization) -- directly optimizing in the FX parameter space, bypassing audio space to avoid introducing unwanted artifacts.  We try two different approaches for text-audio optimization of CLAP embeddings:
- Text2FX-cosine (left): directly minimizes the cosine distance between the optimized audio embedding and the target text embedding
- Text2FX-directional (right): leverages the directional relationship between two text-audio embedding pairs, guiding the optimized audio embedding to move in the direction defined by the difference between the target text and a contrasting text prompt.

<div style="flex: 3 1 0%; max-width:75%;margin: 0 auto;">
  <img src="/research/text2fx/img/Text2FX_Hero_small_fonts.png"
      alt="Large Image"
      style="display:block; margin: 0 auto; width: min(900px, 100%); height:auto; border-radius: 8px;">
</div>

<br> 

##### Example Optimization (Ex.1)
<div style="display:flex; justify-content:center; gap:8px; align-items:flex-start;">


  <!-- Left Column: Large Image -->
  <div style="flex: 3 1 0%; max-width:55%;">
    <img src="/research/text2fx/img/optimization_example.png"
         alt="Large Image"
         style="width: 100%; height: auto; border-radius: 8px; display: block;">
  </div>

  <!-- Right Column: Table of Audio Examples -->
  <!-- <div style="flex: 1 1 0%; max-width: 25%;"> -->
  <div style="flex: 1 1 0; max-width: 260px;">
    <table style="width: 100%; border-collapse: collapse;">
      <tr>
        <td style="padding: 0 0 12px 0;">
          <div style="font-size: 12px; margin-bottom: 6px; color: darkred;">
            <strong>Iteration 0 (randomly applied FX)</strong>
          </div>
          <audio controls style="width: 100%; display: block;">
            <source src="/research/text2fx/audio/EQ_only/bright_guitar/guitar_start.wav" type="audio/mpeg">
          </audio>
        </td>
      </tr>

      <tr>
        <td style="padding: 0 0 12px 0;">
          <div style="font-size: 12px; margin-bottom: 6px; color: darkgreen;">
            <strong>Iteration 200 (mid-optimization)</strong>
          </div>
          <audio controls style="width: 100%; display: block;">
            <source src="/research/text2fx/audio/EQ_only/bright_guitar/guitar_200.wav" type="audio/mpeg">
          </audio>
        </td>
      </tr>

      <tr>
        <td style="padding: 0;">
          <div style="font-size: 12px; margin-bottom: 6px; color: purple;">
            <strong>Iteration 600 (end)</strong>
          </div>
          <audio controls style="width: 100%; display: block;">
            <source src="/research/text2fx/audio/EQ_only/bright_guitar/guitar_600.wav" type="audio/mpeg">
          </audio>
        </td>
      </tr>
    </table>
  </div>

</div>



<style>
    video {
    width: 100%; /* Set to 100% of the container width */
    max-width: 800px; /* Set the maximum width of the video */
    height: auto; /* Maintain the aspect ratio */
    margin-bottom: 1px; /* Add space between the video and audio widget */
    display: block; /* Center the video */
    margin: auto;
    }
</style>

<style>
  table {
    width: 100%;
    border-collapse: collapse; /* Optional: For cleaner table appearance */
  }
  table th, table td {
    text-align: left;
    vertical-align: middle;
    padding: 8px; /* Optional: Adds spacing*/
  }
  table th:first-child, table td:first-child {
    width: 18%; /* Word column */
  }
  table th:nth-child(2), table td:nth-child(2) {
    width: 10%; /* Word Type column */
  }
  table th:nth-child(3), table td:nth-child(3) {
    width: 10%; /* Audio Sample Name column */
  }
  table th:nth-child(4), table td:nth-child(4),
  table th:nth-child(5), table td:nth-child(5) {
    width: 31%; /* Remaining space shared between Input and Output Audio */
  }
  audio {
    width: 200px; /* Compact audio controls */
    height: 50px; /* Optional: Adjust height for better compactness */
  }
  h4 {
    text-align: left;
    color: darkblue;
    margin-top: 30px;
  }
</style>

