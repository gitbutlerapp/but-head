<section class="hero">
  <svg
    class="gb-logo"
    viewBox="0 0 45 47"
    fill="none"
    xmlns="http://www.w3.org/2000/svg"
  >
    <path d="M0 0V47L22.4647 26.4197L45 47V0L22.4647 20.5091L0 0Z" />
  </svg>

  <h1 class="page-title">B<i>u</i>t Head</h1>

  <div class="hero-content">
    <nav class="nav-links">
      <a
        href="https://github.com/gitbutlerapp/but-head/raw/refs/heads/main/font/but-head.zip"
        target="_blank">Download font</a
      >
      <a href="https://github.com/gitbutlerapp/but-head" target="_blank"
        >Source</a
      >
      <a href="https://blog.gitbutler.com/but-head-font" target="_blank"
        >Read more</a
      >
    </nav>

    <p class="description-text">
      A display typeface born from technical precision and editorial flair.
      <br />
      Built specifically to command attention in headlines and interfaces.
      <br />
      Monospace foundations, magazine aesthetics.
    </p>
  </div>

  <div class="gradient-1"></div>
  <div class="gradient-2"></div>
</section>

<style>
  .hero {
    display: grid;
    grid-template-columns: subgrid;
    grid-column: full-start / full-end;
    padding-top: 40px;
    gap: 20px;
    min-height: 900px;
  }

  .gb-logo {
    width: 45px;
    grid-column: narrow-start / narrow-end;
    fill: var(--clr-text-1);
    margin-bottom: 120px;
  }

  .hero-content {
    display: flex;
    flex-direction: column;
    gap: 20px;
    grid-column: narrow-start / narrow-end;
    gap: 20px;
  }

  .page-title {
    grid-column: full-start / full-end;
    width: 100%;
    font-size: clamp(3rem, 27vw, 450px);
    line-height: 0.8;
    letter-spacing: -0.02em;
    font-family: But Head;
    text-align: center;
    margin: 0;

    & i {
      font-style: italic;
    }
  }

  .nav-links {
    display: flex;
    gap: 28px;
    margin: 20px 0;

    & a {
      color: var(--clr-core-pop-30);
      text-decoration: underline;
      font-size: 1.3rem;
      text-decoration-thickness: 1.5px;
      text-underline-offset: 4px;

      &:hover {
        text-decoration-style: wavy;
      }
    }
  }

  .gradient-1,
  .gradient-2 {
    position: absolute;
    width: 800px;
    height: 1400px;
    background: radial-gradient(
      50% 50% at 50% 50%,
      var(--clr-core-pop-70) 80%,
      transparent 100%
    );
    transform: rotate(-40deg);
    z-index: -1;
  }

  .gradient-1 {
    top: -30%;
    right: 350px;
  }
  .gradient-2 {
    top: -40%;
    right: -250px;
  }

  @media (max-width: 1000px) {
    .hero {
      min-height: 700px;
      padding-top: 20px;
    }

    .gb-logo {
      margin-bottom: 80px;
      grid-column: full-start / full-end;
    }

    .hero-content {
      grid-column: full-start / full-end;
    }

    .page-title {
      text-align: left;
      font-size: clamp(3rem, 40vw, 250px);
    }

    .gradient-1,
    .gradient-2 {
      width: 500px;
      height: 900px;
    }

    .gradient-1 {
      top: -40%;
      right: 100px;
    }
    .gradient-2 {
      top: -50%;
      right: -150px;
    }
  }

  @media (max-width: 600px) {
    .hero {
      min-height: auto;
    }

    .nav-links {
      flex-direction: column;
      gap: 12px;
    }
  }
</style>
