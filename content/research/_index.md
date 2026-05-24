---
_title: Research
cms_exclude: true
banner:
  caption: ''
  image: ''
cascade:
  build:
    list: never
---
<style>
  /* /research/ landing only — widen the content column past the site-wide
     760 px cap so three figures can sit side-by-side. */
  main .container,
  main > article,
  main section > .container,
  .prose,
  .max-w-prose {
    max-width: 1100px !important;
  }

  /* Smaller font for the intro paragraphs so the gallery fits above the fold. */
  .research-intro {
    font-size: 0.9rem;
    line-height: 1.55;
    margin-bottom: 1rem;
  }
</style>

<p class="research-intro">
  AI needs a lot of power to think, but our current computer parts are as tiny and fast as they can possibly get. To build better computers in the future, new microelectronic materials are needed. My research uses first-principles calculations, symmetry analysis, and crystal-physics/chemistry models to simulate solid-state materials at the atomic scale, with the goal of understanding their underlying physics and <em>designing</em> new materials. The work runs along various materials classes:
</p>

<div class="research-grid" style="display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem; margin: 1.5rem 0;">

<div class="research-card">
    <a href="/research/direct-bandgap-semiconductors/" style="display: block;">
      <img src="/research/direct-bandgap-semiconductors/research_semiconductor.png"
           alt="Semiconductors"
           loading="lazy"
           style="width: 100%; aspect-ratio: 5 / 3; object-fit: contain; background: #ffffff; border-radius: 4px; display: block;">
    </a>
    <h3 style="margin: 0.75rem 0 0.4rem; font-size: 1.05rem;">
      <a href="/research/direct-bandgap-semiconductors/" style="text-decoration: none; color: inherit;">Semiconductors</a>
    </h3>
    <p style="font-size: 0.85rem; line-height: 1.5; color: #444; margin: 0 0 0.5rem;">
      The maturity of CMOS technology ensures continued reliance on silicon platforms. To maximize the potential of electronic materials – such as ferroelectric materials – they need to be integrated with semiconductors. Yet, this integration faces challenges: lattice mismatch, bonding incompatibilities, interface defects, and unstable ferroic states in thin films. Addressing these challenges requires atomic-level understanding of materials and a reliable, innovative way to do high-fidelity simulations of materials and devices.
    </p>
    <a href="/research/direct-bandgap-semiconductors/" style="font-size: 0.85rem;">Read more →</a>
  </div>

<div class="research-card">
    <a href="/research/magnetism/" style="display: block;">
      <img src="/research/magnetism/research_nrss-afm.png"
           alt="Novel magnetic materials"
           loading="lazy"
           style="width: 100%; aspect-ratio: 5 / 3; object-fit: contain; background: #ffffff; border-radius: 4px; display: block;">
    </a>
    <h3 style="margin: 0.75rem 0 0.4rem; font-size: 1.05rem;">
      <a href="/research/magnetism/" style="text-decoration: none; color: inherit;">Novel magnetic materials</a>
    </h3>
    <p style="font-size: 0.85rem; line-height: 1.5; color: #444; margin: 0 0 0.5rem;">
      Antiferromagnets (AFMs) offer zero stray fields and terahertz spin dynamics, making them ideal for ultrafast, energy-efficient spintronics. Yet, their spin-degenerate bands have limited practical use. Recent works have uncovered a new class of AFMs — certain collinear and noncollinear AFMs — that exhibit momentum-dependent net spin splitting from a specific combination of magnetic order and crystal symmetry. The strict symmetry criteria for this class narrow the materials pool and exclude many promising candidates.
    </p>
    <a href="/research/magnetism/" style="font-size: 0.85rem;">Read more →</a>
  </div>

<div class="research-card">
    <a href="/research/ferroic-materials/" style="display: block;">
      <img src="/research/ferroic-materials/research_multiferroic-nitride.gif"
           alt="Ferroic materials"
           loading="lazy"
           style="width: 100%; aspect-ratio: 5 / 3; object-fit: contain; background: #ffffff; border-radius: 4px; display: block;">
    </a>
    <h3 style="margin: 0.75rem 0 0.4rem; font-size: 1.05rem;">
      <a href="/research/ferroic-materials/" style="text-decoration: none; color: inherit;">Ferroic materials</a>
    </h3>
    <p style="font-size: 0.85rem; line-height: 1.5; color: #444; margin: 0 0 0.5rem;">
      Ferroic materials, with intrinsic bistability and fast switching dynamics, have been pursued for decades as a pathway toward nonvolatile logic and memory, significantly reducing the energy cost while transferring data back and forth between memory and processor. Nonetheless, how structural instability, covalency, and correlation cooperate or compete to stabilize a ferroic phase remains a rich source for advancing fundamental materials theory. Despite decades of research, materials that combine multiple ferroic orders — such as ferroelectricity and magnetism — remain rare, and their integration into practical devices is still limited.
    </p>
    <a href="/research/ferroic-materials/" style="font-size: 0.85rem;">Read more →</a>
  </div>

</div>
