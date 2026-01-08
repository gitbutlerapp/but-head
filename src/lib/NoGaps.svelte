<script>
</script>

<section class="nogaps">
  <div class="look-ma">
    <div class="example">
      <p class="title sample-text xanh-mono">Mommy, I'm wide...</p>
      <span class="font-label"> Xanh Mono — Monospace </span>
    </div>

    <div class="example">
      <p class="title sample-text">Look Ma, <i>no</i> gaps!</p>
      <span class="font-label"> But Head — No Gaps </span>
    </div>

    <img class="bowtie" src="/bowtie-pink.png" alt="" />
    <div class="oval"></div>
  </div>

  <p class="description-text">
    We took Xanh Mono and Instrument and smashed them together.
    <br />
    We broke the monospace grid. It looks like code, but it reads like a magazine.
  </p>
</section>

<style>
  .nogaps {
    display: grid;
    grid-template-columns: subgrid;
    grid-column: full-start / full-end;
    padding-top: 40px;
  }

  .example {
    z-index: 2;
    position: relative;
    display: flex;
    flex-direction: column;
    gap: 20px;
  }

  .look-ma {
    position: relative;
    display: flex;
    flex-direction: column;
    gap: 40px;
    grid-template-columns: subgrid;
    grid-column: narrow-start / narrow-end;
    margin: 80px 0;
  }

  .oval {
    position: absolute;
    top: -100px;
    left: -150px;
    width: calc(100% + 300px);
    height: calc(100% + 200px);
    transform: rotate(-10deg);
    border-radius: 100%;
    background: radial-gradient(
      50% 50% at 50% 50%,
      var(--clr-core-pop-70) 80%,
      transparent 100%
    );
    z-index: 0;
  }

  .bowtie {
    z-index: 1;
    position: absolute;
    top: -90px;
    right: 50%;
    width: 130px;
    z-index: 2;
    transform: rotate(-10deg) translateX(50%);
    transform-origin: center right;
  }

  .xanh-mono {
    font-family: "Xanh Mono", monospace;
  }

  @media (max-width: 1000px) {
    .look-ma {
      grid-column: full-start / full-end;
      margin: 40px 0;
      gap: 30px;
    }

    .bowtie {
      display: none;
    }

    .oval {
      top: -50px;
      left: -50px;
      width: calc(100% + 100px);
      height: calc(100% + 100px);
    }
  }
</style>
