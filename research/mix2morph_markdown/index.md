---
layout: page
# title: Text2FX
which_category: research
permalink: /mix2morph/
---
<style>
    sup {
    font-size: 0.75em;       /* make smaller than main text */
    vertical-align: super;   /* force superscript alignment */
    line-height: 0;          /* prevents extra spacing */
    }
    .container {
    max-width: 1200px;   /* wider container just for this page */
    font-family: "Helvetica Neue", Arial, sans-serif; /* swap in your font */
    font-size: 14px;     /* optional: adjust size */
    line-height: 1.5;    /* optional: improve readability */
    }
    .primary {
    color: #f2620f;
    font-weight: bold;
    }
    .secondary {
    color: #0000ff; 
    font-weight: bold;
    }


  table.custom-table {
    border-collapse: collapse;
    width: 100%;
    font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
    line-height: 1.1;    /* optional: improve readability */

  }

  table.custom-table th,
  table.custom-table td {
    border-bottom: 1px solid #ccc; /* divider after each row */
    padding: 8px;
    vertical-align: top;
  }

  .audioplayer {
    width: 150px; /* control width of audio players */
  }
  
</style>


<head>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/css/all.min.css">
</head>


<!-- <p align="center"> <strong><font size="5">Mix2Morph: Learning Sound Morphing from Noisy Mixes</font></strong> </p>
<p align="center"><font size="3"><u>Annie Chu</u>, Hugo Flores-García, Oriol Nieto, Justin Salamon, Bryan Pardo, Prem Seetharaman</font></p>
<p align="center"><font size="3">*Adobe Research; Northwestern University</font></p> -->

<p align="center" style="font-size: 24px; font-weight: bold;">
  Mix2Morph: Learning Sound Morphing from Noisy Mixes
</p>

<p align="center" style="font-size: 16px;">
  <u>Annie Chu</u><sup>1,2</sup>, Hugo Flores-García<sup>2</sup>, Oriol Nieto<sup>1</sup>, 
  Justin Salamon<sup>1</sup>, Bryan Pardo<sup>2</sup>, Prem Seetharaman<sup>1</sup>
</p>

<p align="center" style="font-size: 16px;">
  <sup>1</sup>Adobe Research; <sup>2</sup>Northwestern University
</p>


<hr> 

<div style="text-align: center; font-weight: bold; font-style: italic;">
  This is the supplementary page containing listening examples for the ICASSP 2026 paper submission “Mix2Morph: Learning Sound Morphing from Noisy Mixes”.
</div>

<hr>

## **Abstract**

We introduce Mix2Morph, a text-to-audio diffusion model fine-tuned to perform sound morphing without a dedicated morph dataset. By finetuning on noisy surrogate mixes at higher diffusion timesteps, Mix2Morph yields stable, perceptually coherent morphs that convincingly integrate qualities of both sources. We specifically target sound infusion, a practically and perceptually motivated subclass of morphing in which one sound acts as the dominant primary source, providing overall temporal and structural behavior, while a secondary sound is infused throughout, enriching its timbral and textural qualities. Objective evaluations and listening tests show that Mix2Morph outperforms prior baselines and produces high-quality sound infusions across diverse categories, representing a step toward more controllable and creative tools for sound design.

## Mix2Morph Fig 1. Audio Examples (headphones recommended)

![Artboard 14 copy 3.png](/research/mix2morph_markdown/assets/v7_simplified.jpg)

|  <span class="primary">wav1</span> : balls bouncing | <span class="secondary">wav2</span>: 808s (bass) | **None (Simple Mix)** | **+RMS-only** | **+Spectral-only** | **+Both** | **Generated Infusion** |
|---------------------------|-----------------------|------------------------|---------------|---------------------|-----------|-------------------------|
| <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/wav1_ball_bouncing.wav" type="audio/wav"></audio> | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/wav2_808s.wav" type="audio/wav"></audio> | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/mixing_notricks.wav" type="audio/wav"></audio> | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/mix_thenRMS_MIXTRICK1.wav" type="audio/wav"></audio> | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/MIXtrickspec_mixed_eq.wav" type="audio/wav"></audio> | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/MIXtrickspec_mixed_eq_and_rms.wav" type="audio/wav"></audio> | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/morph_viz_morph_ballboucinglike808s.wav" type="audio/wav"></audio> |


---


## Listening Examples (headphones recommended)

<div align="center">
  <h4>Prompt Template >> "behavior of <span class="primary">[primary source]</span> with timbre like <span class="secondary">[secondary source]</span>"</h4>
</div>

<!-- 
### **Mix2Morph: Most Convincing**
_Listener Likert Ratings below audio (if applicable)_

| Infusion Prompt | Mix2Morph (ours) | Latent Granular ReSynthesis (LGrS) | MorphFader | Simple Mixing | SoundMorpher | Base Model (no fine-tuning) |
|-----------------|------------------|------------------------------------|------------|---------------|--------------|-----------------------------|
|  behavior of <span class="primary">monster growling</span> with timbre like <span class="secondary">motorcycle revving</span>* | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_monster_growling_like_motorcycle_revving.wav" type="audio/wav"></audio><br>4.6/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_c1_motorcycle_revving_c2_monster_growling.wav" type="audio/wav"></audio><br>2.1/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_monster_growling_like_motorcycle_revving 1.wav" type="audio/wav"></audio><br>2.0/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_c1_motorcycle_revving_c2_monster_growling 1.wav" type="audio/wav"></audio><br>1.9/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.7060546875.wav" type="audio/wav"></audio><br>– | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_monster_growling_like_motorcycle_revving 2.wav" type="audio/wav"></audio><br>– |
|  behavior of <span class="primary">water dripping</span> with timbre like <span class="secondary">cowbell clang</span>* | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_water_dripping_like_cowbell_clang.wav" type="audio/wav"></audio><br>4.3/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_water_dripping_c2_cowbell_clang.wav" type="audio/wav"></audio><br>2.5/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_water_dripping_like_cowbell_clang 1.wav" type="audio/wav"></audio><br>1.1/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_water_dripping_c2_cowbell_clang 1.wav" type="audio/wav"></audio><br>3.0/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.79248046875.wav" type="audio/wav"></audio><br>– | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_cowbell_clang_like_water_dripping.wav" type="audio/wav"></audio><br>– |
|  behavior of <span class="primary">frog croaking</span> with timbre like <span class="secondary">ratchet crank</span>* | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_frog_croak_like_ratchet_crank.wav" type="audio/wav"></audio><br>4.2/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_c1_ratchet_crank_c2_frog_croak.wav" type="audio/wav"></audio><br>2.2/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_frog_croak_like_ratchet_crank 1.wav" type="audio/wav"></audio><br>1.9/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_c1_ratchet_crank_c2_frog_croak 1.wav" type="audio/wav"></audio><br>3.5/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.722412109375.wav" type="audio/wav"></audio><br>– | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_ratchet_crank_like_frog_croak.wav" type="audio/wav"></audio><br>– |
|  behavior of <span class="primary">tennis ball being served</span> with timbre like <span class="secondary">xylophone hit</span>* | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_tennis_ball_being_served_like_xylophone_hit.wav" type="audio/wav"></audio><br>4.2/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_tennis_ball_being_served_c2_xylophone_hit.wav" type="audio/wav"></audio><br>1.7/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_tennis_ball_being_served_like_xylophone_hit 1.wav" type="audio/wav"></audio><br>1.4/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_tennis_ball_being_served_c2_xylophone_hit 1.wav" type="audio/wav"></audio><br>3.2/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.7001953125.wav" type="audio/wav"></audio><br>– | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_tennis_ball_being_served_like_xylophone_hit 2.wav" type="audio/wav"></audio><br>– |
|  behavior of <span class="primary">dog barking</span> with timbre like <span class="secondary">car horn</span>* | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_dog_barking_like_car_horn.wav" type="audio/wav"></audio><br>4.12/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_dog_barking_c2_car_horn.wav" type="audio/wav"></audio><br>1.3/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_dog_barking_like_car_horn 1.wav" type="audio/wav"></audio><br>1.5/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_dog_barking_c2_car_horn 1.wav" type="audio/wav"></audio><br>2.8/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.3191986083984375.wav" type="audio/wav"></audio><br>– | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_dog_barking_like_car_horn 2.wav" type="audio/wav"></audio><br>– |
|  behavior of <span class="primary">electric buzz</span> with timbre like <span class="secondary">bee swarm</span>* | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_electric_buzz_like_bee_swarm.wav" type="audio/wav"></audio><br>4.0/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_electric_buzz_c2_bee_swarm.wav" type="audio/wav"></audio><br>2.1/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_electric_buzz_like_bee_swarm 1.wav" type="audio/wav"></audio><br>3.0/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_electric_buzz_c2_bee_swarm 1.wav" type="audio/wav"></audio><br>3.7/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.619140625.wav" type="audio/wav"></audio><br>– | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_electric_buzz_like_bee_swarm 2.wav" type="audio/wav"></audio><br>– |
|  behavior of <span class="primary">door creaking</span> with timbre like <span class="secondary">zombie groan</span>* | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_door_creaking_open_like_zombie_groan.wav" type="audio/wav"></audio><br>4.0/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_door_creaking_open_c2_zombie_groan.wav" type="audio/wav"></audio><br>1.4/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_door_creaking_open_like_zombie_groan 1.wav" type="audio/wav"></audio><br>2.3/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_door_creaking_open_c2_zombie_groan 1.wav" type="audio/wav"></audio><br>3.5/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.451171875.wav" type="audio/wav"></audio><br>– | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_door_creaking_open_like_zombie_groan 2.wav" type="audio/wav"></audio><br>– |
|  behavior of <span class="primary">phone ringing</span> with timbre like <span class="secondary">pigeon cooing</span>* | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_phone_ringing_like_pigeon_cooing.wav" type="audio/wav"></audio><br>3.9/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_c1_pigeon_cooing_c2_phone_ringing.wav" type="audio/wav"></audio><br>1.8/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_phone_ringing_like_pigeon_cooing 1.wav" type="audio/wav"></audio><br>1.6/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_c1_pigeon_cooing_c2_phone_ringing 1.wav" type="audio/wav"></audio><br>2.7/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.41619873046875.wav" type="audio/wav"></audio><br>– | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_phone_ringing_like_pigeon_cooing 2.wav" type="audio/wav"></audio><br>– |

---
### **Mix2Morph: Least Convincing**

| Infusion Prompt | Mix2Morph (ours) | Latent Granular ReSynthesis (LGrS) | MorphFader | Simple Mixing | SoundMorpher | Base Model |
|-----------------|------------------|------------------------------------|------------|---------------|--------------|------------|
|  behavior of <span class="primary">car tire screech</span> with timbre like <span class="secondary">hawk screech</span>* | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_car_tire_screech_like_hawk_screech.wav" type="audio/wav"></audio><br>2.2/5<br><sub>⚠️ failure example: collapse to single-concept</sub> | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_c1_hawk_screech_c2_car_tire_screech.wav" type="audio/wav"></audio><br>3.0/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_car_tire_screech_like_hawk_screech 1.wav" type="audio/wav"></audio><br>1.4/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_c1_hawk_screech_c2_car_tire_screech 1.wav" type="audio/wav"></audio><br>3.5/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.513427734375.wav" type="audio/wav"></audio><br>– | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_car_tire_screech_like_hawk_screech 2.wav" type="audio/wav"></audio><br>– |
|  behavior of <span class="primary">cow mooing</span> with timbre like <span class="secondary">horse neighing</span>* | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_a_cow_mooing_like_horse_neighing.wav" type="audio/wav"></audio><br>2.5/5<br><sub>⚠️ failure example: dynamic morph vs static infusion</sub> | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_a_cow_mooing_c2_horse_neighing.wav" type="audio/wav"></audio><br>2.0/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_a_cow_mooing_like_horse_neighing 1.wav" type="audio/wav"></audio><br>2.2/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_a_cow_mooing_c2_horse_neighing 1.wav" type="audio/wav"></audio><br>2.9/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.50146484375.wav" type="audio/wav"></audio><br>– | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_a_cow_mooing_like_horse_neighing 2.wav" type="audio/wav"></audio><br>– |
|  behavior of <span class="primary">boot steps</span> with timbre like <span class="secondary">metallic clank on metal</span>* | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_boot_steps_like__magnetic_clank_on_metal.wav" type="audio/wav"></audio><br>2.6/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_boot_steps_c2__magnetic_clank_on_metal.wav" type="audio/wav"></audio><br>1.9/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_boot_steps_like__magnetic_clank_on_metal 1.wav" type="audio/wav"></audio><br>1.1/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_boot_steps_c2__magnetic_clank_on_metal 1.wav" type="audio/wav"></audio><br>2.8/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.872802734375.wav" type="audio/wav"></audio><br>– | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1__magnetic_clank_on_metal_like_boot_steps.wav" type="audio/wav"></audio><br>– |
|  behavior of <span class="primary">swords clashing</span> with timbre like <span class="secondary">snare drum hits</span>* | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_sword_clashing_like_snare_drum_hits.wav" type="audio/wav"></audio><br>2.9/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_sword_clashing_c2_snare_drum_hits.wav" type="audio/wav"></audio><br>1.7/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_sword_clashing_like_snare_drum_hits 1.wav" type="audio/wav"></audio><br>1.3/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_sword_clashing_c2_snare_drum_hits 1.wav" type="audio/wav"></audio><br>3.6/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.53955078125.wav" type="audio/wav"></audio><br>– | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_sword_clashing_like_snare_drum_hits 2.wav" type="audio/wav"></audio><br>– |
|  behavior of <span class="primary">hammering into a door</span> with timbre like <span class="secondary">a marimba</span>* | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_hammering_into_a_door_like__marimba.wav" type="audio/wav"></audio><br>2.9/5<br><sub>⚠️ failure example: sounds like drums, not marimba</sub> | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_hammering_into_a_door_c2__marimba.wav" type="audio/wav"></audio><br>2.4/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_hammering_into_a_door_like__marimba 1.wav" type="audio/wav"></audio><br>1.8/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_hammering_into_a_door_c2__marimba 1.wav" type="audio/wav"></audio><br>3.0/5 | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.7867431640625.wav" type="audio/wav"></audio><br>– | <audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_hammering_into_a_door_like__marimba 2.wav" type="audio/wav"></audio><br>-
 -->

<h3><strong><u>Mix2Morph: Most Convincing</u></strong></h3>

_Listener Likert Ratings below audio (if applicable)_

<table class="custom-table">
  <tr>
    <th>Infusion Prompt</th>
    <th>Mix2Morph (ours)</th>
    <th><a href="https://www.arxiv.org/abs/2507.19202">LGrS</a></th>
    <th><a href="https://arxiv.org/abs/2408.07260">MorphFader</a></th>
    <th>Simple Mixing</th>
    <th><a href="https://arxiv.org/abs/2410.02144">SoundMorpher</a></th>
    <th>Base Model</th>
  </tr>

  <tr>
    <td> behavior of <span class="primary">monster growling</span> with timbre like <span class="secondary">motorcycle revving</span ></td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_monster_growling_like_motorcycle_revving.wav" type="audio/wav"></audio><br>4.6/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_c1_motorcycle_revving_c2_monster_growling.wav" type="audio/wav"></audio><br>2.1/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_monster_growling_like_motorcycle_revving 1.wav" type="audio/wav"></audio><br>2.0/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_c1_motorcycle_revving_c2_monster_growling 1.wav" type="audio/wav"></audio><br>1.9/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.7060546875.wav" type="audio/wav"></audio><br>–</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_monster_growling_like_motorcycle_revving 2.wav" type="audio/wav"></audio><br>–</td>
  </tr>

  <tr>
    <td> behavior of <span class="primary">water dripping</span> with timbre like <span class="secondary">cowbell clang</span ></td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_water_dripping_like_cowbell_clang.wav" type="audio/wav"></audio><br>4.3/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_water_dripping_c2_cowbell_clang.wav" type="audio/wav"></audio><br>2.5/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_water_dripping_like_cowbell_clang 1.wav" type="audio/wav"></audio><br>1.1/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_water_dripping_c2_cowbell_clang 1.wav" type="audio/wav"></audio><br>3.0/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.79248046875.wav" type="audio/wav"></audio><br>–</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_cowbell_clang_like_water_dripping.wav" type="audio/wav"></audio><br>–</td>
  </tr>

  <tr>
    <td> behavior of <span class="primary">frog croaking</span> with timbre like <span class="secondary">ratchet crank</span ></td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_frog_croak_like_ratchet_crank.wav" type="audio/wav"></audio><br>4.2/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_c1_ratchet_crank_c2_frog_croak.wav" type="audio/wav"></audio><br>2.2/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_frog_croak_like_ratchet_crank 1.wav" type="audio/wav"></audio><br>1.9/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_c1_ratchet_crank_c2_frog_croak 1.wav" type="audio/wav"></audio><br>3.5/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.722412109375.wav" type="audio/wav"></audio><br>–</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_ratchet_crank_like_frog_croak.wav" type="audio/wav"></audio><br>–</td>
  </tr>

  <tr>
    <td> behavior of <span class="primary">tennis ball being served</span> with timbre like <span class="secondary">xylophone hit</span ></td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_tennis_ball_being_served_like_xylophone_hit.wav" type="audio/wav"></audio><br>4.2/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_tennis_ball_being_served_c2_xylophone_hit.wav" type="audio/wav"></audio><br>1.7/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_tennis_ball_being_served_like_xylophone_hit 1.wav" type="audio/wav"></audio><br>1.4/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_tennis_ball_being_served_c2_xylophone_hit 1.wav" type="audio/wav"></audio><br>3.2/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.7001953125.wav" type="audio/wav"></audio><br>–</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_tennis_ball_being_served_like_xylophone_hit 2.wav" type="audio/wav"></audio><br>–</td>
  </tr>

  <tr>
    <td> behavior of <span class="primary">dog barking</span> with timbre like <span class="secondary">car horn</span ></td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_dog_barking_like_car_horn.wav" type="audio/wav"></audio><br>4.12/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_dog_barking_c2_car_horn.wav" type="audio/wav"></audio><br>1.3/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_dog_barking_like_car_horn 1.wav" type="audio/wav"></audio><br>1.5/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_dog_barking_c2_car_horn 1.wav" type="audio/wav"></audio><br>2.8/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.3191986083984375.wav" type="audio/wav"></audio><br>–</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_dog_barking_like_car_horn 2.wav" type="audio/wav"></audio><br>–</td>
  </tr>

  <tr>
    <td> behavior of <span class="primary">electric buzz</span> with timbre like <span class="secondary">bee swarm</span ></td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_electric_buzz_like_bee_swarm.wav" type="audio/wav"></audio><br>4.0/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_electric_buzz_c2_bee_swarm.wav" type="audio/wav"></audio><br>2.1/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_electric_buzz_like_bee_swarm 1.wav" type="audio/wav"></audio><br>3.0/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_electric_buzz_c2_bee_swarm 1.wav" type="audio/wav"></audio><br>3.7/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.619140625.wav" type="audio/wav"></audio><br>–</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_electric_buzz_like_bee_swarm 2.wav" type="audio/wav"></audio><br>–</td>
  </tr>

  <tr>
    <td> behavior of <span class="primary">door creaking</span> with timbre like <span class="secondary">zombie groan</span ></td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_door_creaking_open_like_zombie_groan.wav" type="audio/wav"></audio><br>4.0/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_door_creaking_open_c2_zombie_groan.wav" type="audio/wav"></audio><br>1.4/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_door_creaking_open_like_zombie_groan 1.wav" type="audio/wav"></audio><br>2.3/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_door_creaking_open_c2_zombie_groan 1.wav" type="audio/wav"></audio><br>3.5/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.451171875.wav" type="audio/wav"></audio><br>–</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_door_creaking_open_like_zombie_groan 2.wav" type="audio/wav"></audio><br>–</td>
  </tr>

  <tr>
    <td> behavior of <span class="primary">phone ringing</span> with timbre like <span class="secondary">pigeon cooing</span ></td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_phone_ringing_like_pigeon_cooing.wav" type="audio/wav"></audio><br>3.9/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_c1_pigeon_cooing_c2_phone_ringing.wav" type="audio/wav"></audio><br>1.8/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_phone_ringing_like_pigeon_cooing 1.wav" type="audio/wav"></audio><br>1.6/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_c1_pigeon_cooing_c2_phone_ringing 1.wav" type="audio/wav"></audio><br>2.7/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.41619873046875.wav" type="audio/wav"></audio><br>–</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_phone_ringing_like_pigeon_cooing 2.wav" type="audio/wav"></audio><br>–</td>
  </tr>
</table>

<h3><strong><u>Mix2Morph: Least Convincing</u></strong></h3>
_Listener Likert Ratings below audio (if applicable)_


<table class="custom-table">
  <tr>
    <th>Infusion Prompt</th>
    <th>Mix2Morph (ours)</th>
    <th><a href="https://www.arxiv.org/abs/2507.19202">LGrS</a></th>
    <th><a href="https://arxiv.org/abs/2408.07260">MorphFader</a></th>
    <th>Simple Mixing</th>
    <th><a href="https://arxiv.org/abs/2410.02144">SoundMorpher</a></th>
    <th>Base Model</th>
  </tr>

  <tr>
    <td> behavior of <span class="primary">car tire screech</span> with timbre like <span class="secondary">hawk screech</span ></td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_car_tire_screech_like_hawk_screech.wav" type="audio/wav"></audio><br>2.2/5<br><sub>⚠️ Failure case: collapses to single-concept</sub></td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_c1_hawk_screech_c2_car_tire_screech.wav" type="audio/wav"></audio><br>3.0/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_car_tire_screech_like_hawk_screech 1.wav" type="audio/wav"></audio><br>1.4/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_c1_hawk_screech_c2_car_tire_screech 1.wav" type="audio/wav"></audio><br>3.5/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.513427734375.wav" type="audio/wav"></audio><br>–</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1_car_tire_screech_like_hawk_screech 2.wav" type="audio/wav"></audio><br>–</td>
  </tr>

  <tr>
    <td> behavior of <span class="primary">cow mooing</span> with timbre like <span class="secondary">horse neighing</span ></td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_a_cow_mooing_like_horse_neighing.wav" type="audio/wav"></audio><br>2.5/5<br><sub>⚠️ Failure case: sounds like a dynamic morph over a static infusion</sub></td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_a_cow_mooing_c2_horse_neighing.wav" type="audio/wav"></audio><br>2.0/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_a_cow_mooing_like_horse_neighing 1.wav" type="audio/wav"></audio><br>2.2/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_a_cow_mooing_c2_horse_neighing 1.wav" type="audio/wav"></audio><br>2.9/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.50146484375.wav" type="audio/wav"></audio><br>–</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_a_cow_mooing_like_horse_neighing 2.wav" type="audio/wav"></audio><br>–</td>
  </tr>

  <tr>
    <td> behavior of <span class="primary">boot steps</span> with timbre like <span class="secondary">metallic clank on metal</span ></td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_boot_steps_like__magnetic_clank_on_metal.wav" type="audio/wav"></audio><br>2.6/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_boot_steps_c2__magnetic_clank_on_metal.wav" type="audio/wav"></audio><br>1.9/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_boot_steps_like__magnetic_clank_on_metal 1.wav" type="audio/wav"></audio><br>1.1/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_boot_steps_c2__magnetic_clank_on_metal 1.wav" type="audio/wav"></audio><br>2.8/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.872802734375.wav" type="audio/wav"></audio><br>–</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c2likec1__magnetic_clank_on_metal_like_boot_steps.wav" type="audio/wav"></audio><br>–</td>
  </tr>

  <tr>
    <td> behavior of <span class="primary">swords clashing</span> with timbre like <span class="secondary">snare drum hits</span ></td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_sword_clashing_like_snare_drum_hits.wav" type="audio/wav"></audio><br>2.9/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_sword_clashing_c2_snare_drum_hits.wav" type="audio/wav"></audio><br>1.7/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_sword_clashing_like_snare_drum_hits 1.wav" type="audio/wav"></audio><br>1.3/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_sword_clashing_c2_snare_drum_hits 1.wav" type="audio/wav"></audio><br>3.6/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.53955078125.wav" type="audio/wav"></audio><br>–</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_sword_clashing_like_snare_drum_hits 2.wav" type="audio/wav"></audio><br>–</td>
  </tr>

  <tr>
    <td> behavior of <span class="primary">hammering into a door</span> with timbre like <span class="secondary">a marimba</span ></td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_hammering_into_a_door_like__marimba.wav" type="audio/wav"></audio><br>2.9/5<br><sub>⚠️ Failure case: sounds like drums, not marimba (right direction, but not enough to be perceptibly marimba)</sub></td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_hammering_into_a_door_c2__marimba.wav" type="audio/wav"></audio><br>2.4/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_hammering_into_a_door_like__marimba 1.wav" type="audio/wav"></audio><br>1.8/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_c1_hammering_into_a_door_c2__marimba 1.wav" type="audio/wav"></audio><br>3.0/5</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_midpoint_0.7867431640625.wav" type="audio/wav"></audio><br>–</td>
    <td><audio controls class="audioplayer"><source src="/research/mix2morph_markdown/assets/c1likec2_hammering_into_a_door_like__marimba 2.wav" type="audio/wav"></audio><br>–</td>
  </tr>
</table>

### Note: If having trouble viewing samples, please [click here for backup link](https://anniechu.notion.site/mix2morph).
