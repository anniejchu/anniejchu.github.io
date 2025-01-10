---
layout: page
# title: Text2FX
which_category: research
permalink: /text2fx/
---

<!-- ## Text2FX -->
<p align="center"> <strong><font size="5">Text2FX: Harnessing CLAP Embeddings for Text-Guided Audio Effects</font></strong> </p>
<p align="center"><font size="3"><u>Annie Chu</u>, Patrick O'Reilly, Julia Barnett, Bryan Pardo</font></p>
<p align="center"><font size="3">Northwestern University</font></p>

<!-- #### Key Goal
How can we apply audio FX (e.g., EQ, reverb, etc) with any natural language prompt (e.g., make this 'warm and cozy')? -->

<div align="center">
  <a href="https://arxiv.org/abs/2409.18847" target="_blank" style="
    display: inline-block;
    padding: 10px 20px;
    font-size: 16px;
    color: white;
    background-color: #007bff;
    text-decoration: none;
    border-radius: 5px;
    border: none;
    margin-right: 10px;
  ">
    View on ArXiv
  </a>
  <a href="#" style="
    display: inline-block;
    padding: 10px 20px;
    font-size: 16px;
    color: white;
    background-color: #6c757d;
    text-decoration: none;
    border-radius: 5px;
    border: none;
    cursor: not-allowed;
  ">
    Github (soon)
  </a>
  <!-- <button style="
    display: inline-block;
    padding: 10px 20px;
    font-size: 16px;
    color: white;
    background-color: #6c757d;
    text-decoration: none;
    border-radius: 5px;
    border: none;
    cursor: not-allowed;
  ">
    Github (soon)
  </button> -->
</div>

<hr> 



#### Abstract
**tl;dr: How can we apply audio effects (e.g., EQ, reverb, etc) with any natural language prompt (e.g., make this 'warm and cozy')?**

This work introduces Text2FX, a method that leverages CLAP embeddings and differentiable digital signal processing to control audio effects, such as equalization and reverberation, using open-vocabulary natural language prompts (e.g., "make this sound in-your-face and bold"). Text2FX operates without retraining any models, relying instead on single-instance optimization within the existing embedding space. We show that CLAP encodes valuable information for controlling audio effects and propose two optimization approaches using CLAP to map text to audio effect parameters. While we demonstrate with CLAP, this approach is applicable to any shared text-audio embedding space. Similarly, while we demonstrate with equalization and reverberation, any differentiable audio effect may be controlled. We conduct a listener study with diverse text prompts and source audio to evaluate the quality and alignment of these methods with human perception.


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

  <!-- <div style="flex: 3 1 0%; max-width: 100%;"> -->
 <img src="/research/text2fx/img/Text2FX_Hero_small_fonts.png" alt="Large Image" style="width: 100%; height: auto; border-radius: 8px;">
  <!-- </div> -->

##### Example Optimization (Ex.1)
  <!-- Left Column: Large Image -->
<div style="display: flex; gap: 0px;">

  <!-- Left Column: Large Image -->
  <div style="flex: 3 1 0%; max-width: 75%;">
    <img src="/research/text2fx/img/optimization_example.png" alt="Large Image" style="width: 100%; height: auto; border-radius: 8px;">
  </div>

  <!-- Right Column: Table of Audio Examples -->
  <div style="flex: 1 1 0%; max-width: 25%;">
    <table style="width: 100%; border-collapse: collapse;">
      <tr>
        <!-- <th style="text-align: left; padding-right: 0px; font-size: 10px;">Iter #</th>
        <th style="text-align: left; font-size: 10px;">Audio</th> -->
      </tr>

      <!-- Row 1 -->
      <tr>
        <td style="font-size: 12px; padding-bottom: 10px; color: darkred;"><strong>Iteration 0 (randomly applied FX)</strong></td>
        <td style="padding-bottom: 20px;">
          <audio controls>
            <source src="/research/text2fx/audio/EQ_only/bright_guitar/guitar_start.wav" type="audio/mpeg">
            Your browser does not support the audio element.
          </audio>
        </td>
      </tr>

      <!-- Row 2 -->
      <tr>
        <td style="font-size: 12px; padding-bottom: 10px; color: darkgreen;"><strong>Iteration 200 (mid-optimization)</strong></td>
        <td style="padding-bottom: 20px;">
          <audio controls>
            <source src="/research/text2fx/audio/EQ_only/bright_guitar/guitar_200.wav" type="audio/mpeg">
            Your browser does not support the audio element.
          </audio>
        </td>
      </tr>

      <!-- Row 3 -->
      <tr>
        <td style="font-size: 12px; padding-bottom: 10px; color: darkpurple;"><strong>Iteration 600 (end)</strong></td>
        <td style="padding-bottom: 20px;">
          <audio controls>
            <source src="/research/text2fx/audio/EQ_only/bright_guitar/guitar_600.wav" type="audio/mpeg">
            Your browser does not support the audio element.
          </audio>
        </td>
      </tr>

    </table>
  </div>

</div>


<style>
    img {
    width: 100%; /* Set to 100% of the container width */
    max-width: 500px; /* Set the maximum width of the image */
    height: auto; /* Maintain the aspect ratio */
    margin-bottom: 1px; /* Add space between the image and audio widget */
    }
    video {
    width: 100%; /* Set to 100% of the container width */
    max-width: 800px8; /* Set the maximum width of the video */
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
