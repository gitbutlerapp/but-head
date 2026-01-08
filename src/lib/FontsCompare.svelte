<script>
  let containerEl;
  let offsets = {
    img1: { x: 0, y: 0 },
    img2: { x: 0, y: 0 },
    img3: { x: 0, y: 0 }
  };

  function handleMouseMove(e) {
    if (!containerEl) return;

    const rect = containerEl.getBoundingClientRect();
    const centerX = rect.width / 2;
    const centerY = rect.height / 2;

    const x = e.clientX - rect.left - centerX;
    const y = e.clientY - rect.top - centerY;

    // Different parallax intensities for each image
    offsets.img1 = { x: x * 0.03, y: y * 0.03 };
    offsets.img2 = { x: x * 0.06, y: y * 0.06 };
    offsets.img3 = { x: x * 0.09, y: y * 0.09 };
  }

  function handleMouseLeave() {
    offsets = {
      img1: { x: 0, y: 0 },
      img2: { x: 0, y: 0 },
      img3: { x: 0, y: 0 }
    };
  }
</script>

<section class="compare">
  <div
    class="image-comparison"
    role="img"
    bind:this={containerEl}
    onmousemove={handleMouseMove}
    onmouseleave={handleMouseLeave}
  >
    <img
      class="compare-item"
      src="./compare-xanh.svg"
      alt=""
      style="transform: translate({offsets.img1.x}px, {offsets.img1.y}px)"
    />
    <img
      class="compare-item"
      src="./compare-instrument.svg"
      alt=""
      style="transform: translate({offsets.img2.x}px, {offsets.img2.y}px)"
    />
    <img
      class="compare-item"
      src="./compare-buthead.svg"
      alt=""
      style="transform: translate({offsets.img3.x}px, {offsets.img3.y}px)"
    />

    <div class="legend">
      <div class="legend-item">
        <div class="color-box but-head"></div>
        <span class="font-label"> But Head </span>
      </div>
      <div class="legend-item">
        <div class="color-box instrument"></div>
        <span class="font-label"> Instrument </span>
      </div>
      <div class="legend-item">
        <div class="color-box xanh-mono"></div>
        <span class="font-label"> Xanh Mono </span>
      </div>
    </div>
  </div>

  <p class="description-text">
    High-contrast fonts often have fragile horizontal lines that disappear on
    screen. We increased the density so you don't have to over-scale the text
    just to make it readable.
  </p>

  <div class="better-together">
    <img class="rooster" src="./rooster.png" alt="" />
    <h2 class="title">Better <br /><i> together</i></h2>
  </div>

  <p class="description-text">
    A strong italic is crucial for serif fonts. Using both styles allows for
    better visual hierarchy and emphasis in your text.
  </p>
</section>

<style>
  .compare {
    display: grid;
    grid-template-columns: subgrid;
    grid-column: full-start / full-end;
    padding-top: 40px;
    padding-bottom: 40px;
  }

  .image-comparison {
    grid-column: narrow-start / narrow-end;
    position: relative;
    width: 100%;

    &:hover .compare-item:not(:first-child) {
      opacity: 0.6;
    }
  }

  .compare-item {
    position: absolute;
    width: 100%;
    top: 0;
    left: 0;
    transition:
      opacity 0.2s ease,
      transform 0.1s ease-out;

    &:first-child {
      position: relative;
    }
  }

  .legend {
    position: absolute;
    bottom: 24px;
    left: 0;
    display: flex;
    gap: 24px;
  }

  .legend-item {
    display: flex;
    align-items: center;
    gap: 12px;
  }

  .color-box {
    width: 24px;
    height: 16px;
    border: 1px solid var(--clr-text-1);
  }

  .color-box.but-head {
    background-color: #ffccfd;
  }

  .color-box.instrument {
    background-color: #f4ffac;
  }

  .color-box.xanh-mono {
    background-color: #63e2ff;
  }

  .font-label {
    font-size: 1rem;
  }

  .better-together {
    grid-column: narrow-start / narrow-end;
    display: flex;
    align-items: center;
    gap: 40px;
    margin-top: 40px;
  }

  .rooster {
    width: 240px;
    margin-left: -30px;
  }

  @media (max-width: 1000px) {
    .compare {
      padding-top: 0;
    }

    .image-comparison {
      grid-column: full-start / full-end;
    }

    .legend {
      position: relative;
      flex-direction: column;
      gap: 10px;
      /* padding-top: 20px; */
    }

    .better-together {
      grid-column: full-start / full-end;
      /* flex-direction: column; */
      /* align-items: flex-start; */
      /* text-align: center; */
      gap: 20px;
    }

    .rooster {
      width: 120px;
      /* margin-left: 0; */
    }
  }

  @media (max-width: 600px) {
    .legend {
      padding-top: 20px;
    }
  }
</style>
