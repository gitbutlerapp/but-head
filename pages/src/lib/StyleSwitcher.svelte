<script>
  let { selectedStyle = $bindable("regular"), fullWidth = false } = $props();
</script>

<div class="style-switcher" class:full-width={fullWidth}>
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

<style>
  .style-switcher {
    display: inline-flex;
    width: fit-content;

    &.full-width {
      width: 100%;
    }
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
</style>
