<script>
</script>

<footer class="footer">
  <a class="download-cta" href="#" target="_blank"
    ><span class="cta-text">Download <br /> <i>But Head</i></span>
    <div class="arrow-wrap">
      <svg
        class="arrow-icon"
        viewBox="0 0 118 127"
        fill="none"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M0.652344 75.1953L58.6523 125M58.6523 125L116.652 75.1953M58.6523 125V0"
          stroke="var(--clr-text-1)"
          stroke-width="2"
          vector-effect="non-scaling-stroke"
        />
      </svg>
    </div>
  </a>

  <div class="meta">
    <div class="copyright">
      © 2025 Made for people.
      <br />
      Designed by
      <a href="https://github.com/PavelLaptev" target="_blank">Pavel Laptev</a>
      in
      <a href="https://gitbutler.com/" target="_blank">GitButler</a>
    </div>

    <img class="but-pc" src="./but-pc.png" alt="" />
  </div>
</footer>

<style>
  .footer {
    display: grid;
    grid-template-columns: subgrid;
    grid-column: full-start / full-end;
    overflow: hidden;
  }

  .download-cta {
    position: relative;
    grid-column: narrow-start / narrow-end;
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 52px 28px;
    gap: 40px;
    background-color: var(--clr-core-pop-70);
    border: 2px solid var(--clr-text-1);
    color: var(--clr-text-1);
    font-size: 24px;
    text-decoration: none;
    border-radius: 400px;

    transition: filter 0.2s ease;

    &:hover {
      filter: brightness(1.05);
    }
  }

  .cta-text {
    display: flex;
    flex-direction: column;
    align-items: center;
    font-family: "But Head", sans-serif;
    font-size: clamp(3rem, 4vw, 80px);
    line-height: 1;
    flex: 1;
  }

  .arrow-wrap {
    position: absolute;
    right: 80px;
    border-bottom: 2px solid var(--clr-text-1);
  }

  .arrow-icon {
    width: 80px;
    height: auto;
    display: block;
    transform: translateY(-13px);
    animation: bounce 1s ease-in-out infinite;
  }

  @keyframes bounce {
    0%,
    100% {
      transform: translateY(-13px);
    }
    50% {
      transform: translateY(-6px);
    }
  }

  .meta {
    position: relative;
    grid-column: narrow-start / full-end;
    display: flex;
    justify-content: space-between;
    padding-top: 100px;
    align-items: flex-end;
  }

  .copyright {
    padding-bottom: 20px;
  }

  .but-pc {
    position: absolute;
    bottom: 0;
    right: 0;
    width: 180px;
    transform: translateY(10px);
  }

  @media (max-width: 1000px) {
    .download-cta {
      grid-column: full-start / full-end;
      padding: 40px 20px;
      font-size: clamp(2rem, 6vw, 60px);
    }

    .arrow-wrap {
      right: 40px;
    }

    .meta {
      grid-column: full-start / full-end;
      flex-direction: column;
      gap: 20px;
      padding-top: 60px;
      align-items: flex-start;
    }

    .but-pc {
      position: relative;
      transform: translateY(0);
      width: 140px;
      align-self: flex-end;
    }
  }

  @media (max-width: 600px) {
    .download-cta {
      flex-direction: column;
    }

    .arrow-wrap {
      position: static;
    }
  }
</style>
