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

  /* Phone (<=640px, Tailwind sm breakpoint): collapse 3-column gallery
     to a single stacked column; drop the 1100px override; widen image
     crop slightly since each card is now full-bleed. */
  @media (max-width: 640px) {
    main .container,
    main > article,
    main section > .container,
    .prose,
    .max-w-prose {
      max-width: 100% !important;
      padding-left: 1rem !important;
      padding-right: 1rem !important;
    }
    .research-grid {
      grid-template-columns: 1fr !important;
      gap: 1.25rem !important;
      padding-left: 0 !important;
      padding-right: 0 !important;
    }
    .research-card img {
      aspect-ratio: 16 / 9 !important;
    }
    .research-intro {
      font-size: 1rem;
      line-height: 1.55;
    }
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
      Modern optoelectronic integration on chips needs materials that can emit light directly on a silicon platform. Group-IV semiconductors (Si, Ge) are intrinsically indirect-bandgap, with extremely low luminescence efficiency — a problem that has blocked CMOS-monolithic on-chip light sources for half a century.
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
      Antiferromagnets (AFMs) offer zero stray fields and terahertz spin dynamics, making them ideal for ultrafast, energy-efficient spintronics. Yet, their spin-degenerate bands have limited practical use. 
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
      Ferroic materials, with intrinsic bistability and fast switching dynamics, have been pursued for decades as a pathway toward nonvolatile logic and memory. Despite decades of research, materials that combine multiple ferroic orders remain rare.
    </p>
    <a href="/research/ferroic-materials/" style="font-size: 0.85rem;">Read more →</a>
  </div>

</div>
