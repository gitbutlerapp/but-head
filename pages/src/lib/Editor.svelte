<script>
  import RangeSlider from "./RangeSlider.svelte";
  import StyleSwitcher from "./StyleSwitcher.svelte";

  let fontSize = $state(100);
  let selectedStyle = $state("regular");
  let ratio = $state(1);

  function updateRatio() {
    const width = window.innerWidth;
    if (width >= 1400) {
      ratio = 1;
    } else {
      // Scale ratio down for smaller screens (0.6 at 768px, 0.8 at 1024px, etc.)
      ratio = Math.max(0.5, width / 1400);
    }
  }

  $effect(() => {
    updateRatio();
    window.addEventListener("resize", updateRatio);
    return () => window.removeEventListener("resize", updateRatio);
  });
</script>

<section class="editor">
  <div
    contenteditable="true"
    class="editable-text"
    style="font-size: {Math.max(
      40,
      fontSize * ratio
    )}px; font-style: {selectedStyle};"
  >
    Yes, the font name is real. <i>Start typing</i>.
  </div>

  <div class="controls">
    <RangeSlider bind:value={fontSize} min={100} max={150} />
    <div class="style-switcher">
      <StyleSwitcher bind:selectedStyle />
    </div>
  </div>
</section>

<style>
  .editor {
    display: flex;
    flex-direction: column;
    grid-template-columns: subgrid;
    grid-column: narrow-start / narrow-end;
    overflow: hidden;
    border: 2px solid var(--clr-text-1);
    border-radius: 20px;
    background: var(--clr-bg-1);
  }

  .editable-text {
    flex: 1;
    padding: 40px;
    font-family: "But Head", sans-serif;
    line-height: 1;
    outline: none;
    min-height: 200px;
    color: var(--clr-text-1);
  }

  .controls {
    display: flex;
    gap: 16px;
    padding: 20px;
    border-top: 2px solid var(--clr-text-1);
    background: var(--clr-bg-2);
  }

  .style-switcher {
    display: flex;
    width: fit-content;
  }

  @media (max-width: 1000px) {
    .editor {
      grid-column: full-start / full-end;
    }
  }

  @media (max-width: 600px) {
    .controls {
      flex-direction: column-reverse;
    }

    .style-switcher {
      margin-top: -48px;
    }

    .editable-text {
      padding: 20px;
      padding-bottom: 50px;
    }
  }
</style>
