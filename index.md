---
layout: default
title: Home
---

<style>
  .container p {
    /* line-height: 1.4; */
    /* margin-bottom: 1.0em; was 25 px  */
  }

  .photo-magazine {
    position: relative;
    float: left;
    /* margin: 4px 1.5rem 1rem 1rem; */
    margin: 0 1.5rem 1rem 0;
    width: 185px;
  }

  .photo-magazine img {
    display: block;
    width: 100%;
    /* filter: saturate(0.20) brightness(1.15) contrast(0.85) sepia(0.40); */
  }

  .photo-magazine::after {
    content: '';
    position: absolute;
    inset: 0;
    background: rgba(230, 218, 190, 0.30);
    mix-blend-mode: multiply;
    pointer-events: none;
  }

</style>

<section class="intro">
  <svg style="display:none">
    <defs>
      <filter id="grain">
        <feTurbulence type="fractalNoise" baseFrequency="0.65" numOctaves="3" stitchTiles="stitch" result="noise"/>
        <feColorMatrix type="saturate" values="0" in="noise" result="grayNoise"/>
        <feBlend in="SourceGraphic" in2="grayNoise" mode="overlay" result="blended"/>
        <feComposite in="blended" in2="SourceGraphic" operator="in"/>
      </filter>
    </defs>
  </svg>
  <div class="container">
    <h4 class="lead">Hello!</h4>
    <div class="photo-magazine">
      <img src="/assets/images/me.jpg" alt="Annie Chu" />
    </div>
    <p class="lead">
      I'm Annie (she/her), a 4th year PhD student at Northwestern University in the <a href="https://tsb.northwestern.edu/">Technology & Social Behavior</a> program, a dual PhD program in Computer Science and Communications.
    </p>
    <p class="lead">
      I'm currently at the <a href="https://interactiveaudiolab.github.io/">Interactive Audio Lab</a>, advised by Dr. Bryan Pardo. My research interests lie at the intersection of audio, deep learning, human-computer interaction, and computational musicology.
    </p>
    <p class="lead">
      Previously, I completed my B.S. in Electrical & Computer Engineering with a concentration in Media Arts at <a href="https://www.olin.edu/">Olin College of Engineering</a>. In my free time, you can find me walking around record shops, watching stand up, or playing bananagrams. As a native New Yorker (Queens!!!), I am also on the hunt for the best bagel in Chicago. Please email me if you find it.
    </p>
    <p class="lead">
      You can reach me at anniechu [at] u.northwestern.edu
    </p>
  </div>
</section>

<section class="research-updates">
  <div class="container">
    <h4 class="lead">Updates</h4>
    <!--class "r" for research, "g" for general. -->
    <div class="timeline">
      <div class="tl-row tl-head"><div class="r">papers</div><div></div><div class="g">general</div></div>
      <div class="tl-row g">
        <div class="tl-date">Sep 2026</div>
        <div class="tl-item">I wrote a book review of Seth Long’s <em>The Last Mixtape: Physical Media and Nostalgic Cycles</em> for the <a href="https://iaspmjournal.net/" target="_blank">IASPM Journal</a>.</div>
      </div>
      <div class="tl-row g">
        <div class="tl-date">Aug 2026</div>
        <div class="tl-item">Taught <a href="teaching/cs352/">CS352: Machine Perception of Music & Audio</a> as Instructor of Record (Summer 2026)</div>
      </div>
      <div class="tl-row r">
        <div class="tl-date">July 2026</div>
        <div class="tl-item">Our work <em>Smorph: Playable Sound Morphing with Diffusion Models</em> was accepted to ISMIR 2026!</div>
      </div>
      <div class="tl-row r">
        <div class="tl-date">July 2026</div>
        <div class="tl-item"><em>D-Composer: Language Modeling for Simultaneous Drum Transcription and Sound Event Decomposition</em>, work led by <a href="https://oreillyp.github.io/">Patrick O'Reilly</a> was accepted to ISMIR 2026! Check out the <a href="https://d-composer.github.io/">demo page.</a></div>
      </div>
      <div class="tl-row r">
        <div class="tl-date">April 2026</div>
        <div class="tl-item">Our work <em>FXplorer</em> was accepted to NIME 2026! Learn more <a href="fxplorer/">here</a>.</div>
      </div>
      <div class="tl-row r">
        <div class="tl-date">Jan 2026</div>
        <div class="tl-item">Our work <em>Mix2Morph: Learning Sound Morphing from Noisy Mixes</em> was accepted at ICASSP 2026 (to be presented May 2026 in Barcelona!). See <a href="mix2morph/">demo page</a>.</div>
      </div>
      <div class="tl-row r">
        <div class="tl-date">Sep 2025</div>
        <div class="tl-item">Our work <em>Listening in the Age of the Algorithm: Bridging Musicology and HCI Methodologies</em> was accepted at Clouds, Streams, and Ground (Truths) Conference, in March 2026.</div>
      </div>
      <div class="tl-row g">
        <div class="tl-date">Summer 2025</div>
        <div class="tl-item">Interned at Adobe SODA (Sound Design AI group)</div>
      </div>
      <div class="tl-row r">
        <div class="tl-date">July 2025</div>
        <div class="tl-item"><em>Sound Check: Auditing Recent Audio Dataset Practices</em>, work led by <a href="https://sites.google.com/view/williamagnew?usp=sharing">William Agnew</a> was accepted into AIES 2025. Check out the <a href="https://arxiv.org/abs/2410.13114">paper.</a></div>
      </div>
      <div class="tl-row r">
        <div class="tl-date">June 2025</div>
        <div class="tl-item"><em>The Rhythm In Anything (TRIA): Audio-prompted Drums generation with masked language modeling</em>, work led by <a href="https://oreillyp.github.io/">Patrick O'Reilly</a>, was accepted at ISMIR 2025. Check out the <a href="https://therhythminanything.github.io/">demo page.</a></div>
      </div>
      <div class="tl-row r">
        <div class="tl-date">April 2025</div>
        <div class="tl-item">Presented our work <em>Text2FX</em> at ICASSP 2025! Check out the <a href="https://arxiv.org/abs/2409.18847">paper (arXiv)</a> and the <a href="text2fx/">demo page</a>.</div>
      </div>
    </div>
  </div>
</section>