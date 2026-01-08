<script>
  const letters = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";
  const numbersAndSymbols = "0123456789!@#$%^&*()_+";

  let selectedStyle = $state("regular");
</script>

<section class="alphabet-section">
  <div class="style-switcher">
    <button
      class="switcher-button"
      class:active={selectedStyle === "regular"}
      onclick={() => (selectedStyle = "regular")}
    >
      Regular
    </button>
    <button
      class="switcher-button"
      class:active={selectedStyle === "italic"}
      onclick={() => (selectedStyle = "italic")}
    >
      <i>Italic</i>
    </button>
  </div>

  <div class="alphabet-wrap" class:italic={selectedStyle === "italic"}>
    <span class="alphabet-letters">
      {letters}
    </span>
    <span class="alphabet-letters lowercase">
      {letters}
    </span>
    <span class="alphabet-letters">
      {numbersAndSymbols}
    </span>
  </div>
</section>

<style>
  .alphabet-section {
    display: grid;
    grid-template-columns: subgrid;
    grid-column: full-start / full-end;
    padding-top: 40px;
  }

  .style-switcher {
    grid-column: narrow-start / narrow-end;
    display: inline-flex;
    width: fit-content;
    transform: translateY(24px);
  }

  .switcher-button {
    padding: 8px 14px;
    border: 2px solid var(--clr-core-pop-30);
    background: var(--clr-bg-2);
    color: var(--clr-core-pop-30);
    font-size: 24px;

    &:first-child {
      padding-left: 20px;
      border-top-left-radius: 100px;
      border-bottom-left-radius: 100px;
    }

    &:last-child {
      padding-right: 20px;
      border-top-right-radius: 100px;
      border-bottom-right-radius: 100px;
    }
  }

  .switcher-button.active {
    background-color: var(--clr-core-pop-30);
    color: var(--clr-core-pop-90);
  }

  .alphabet-wrap {
    display: flex;
    grid-column: full-start / full-end;
    font-size: clamp(5rem, 8vw, 130px);
    text-wrap: balance;
    line-height: 1.1;
    font-family:
      But Head,
      sans-serif;
    transition: font-style 0.2s ease;
  }

  .alphabet-wrap.italic {
    font-style: italic;
  }

  .alphabet-letters {
    text-align: center;
    word-break: break-word;
    border-top: 2px solid var(--clr-core-pop-30);
    border-bottom: 2px solid var(--clr-core-pop-30);
    padding: 30px;
    padding-top: 40px;

    &:first-child {
      border-left: 2px solid var(--clr-core-pop-30);
    }

    &:last-child {
      border-right: 2px solid var(--clr-core-pop-30);
    }

    &:not(:last-child) {
      border-right: 2px solid var(--clr-core-pop-30);
    }
  }

  .alphabet-letters.lowercase {
    text-transform: lowercase;
  }

  @media (max-width: 1000px) {
    .alphabet-section {
      padding-top: 0;
    }

    .alphabet-wrap {
      flex-direction: column;
      font-size: clamp(4rem, 10vw, 100px);
    }

    .alphabet-letters {
      padding-top: 30px;
      border-left: 2px solid var(--clr-core-pop-30);
      border-right: 2px solid var(--clr-core-pop-30);

      &:first-child {
        padding-top: 50px;
      }

      &:not(:last-child) {
        border-bottom: none;
      }
    }

    .style-switcher {
      grid-column: full-start / full-end;
      padding-left: 20px;
      transform: translateY(28px);
    }
  }
</style>
