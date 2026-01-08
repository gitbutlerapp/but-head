<script>
  let { value = $bindable(100), min = 24, max = 200 } = $props();
</script>

<input type="range" {min} {max} bind:value class="size-slider" />

<style>
  .size-slider {
    -webkit-appearance: none;
    appearance: none;
    flex: 1;
    height: 56px;
    background: transparent;
    outline: none;
    cursor: pointer;
  }

  /* Track */
  .size-slider::-webkit-slider-runnable-track {
    width: 100%;
    height: 56px;
    background: var(--clr-bg-2);
    border: 2px solid var(--clr-text-1);
    border-radius: 28px;
    padding: 0 6px;
    box-sizing: border-box;
  }

  .size-slider::-moz-range-track {
    width: 100%;
    height: 56px;
    background: var(--clr-bg-2);
    border: 2px solid var(--clr-text-1);
    border-radius: 28px;
    box-sizing: border-box;
  }

  /* Thumb */
  .size-slider::-webkit-slider-thumb {
    -webkit-appearance: none;
    appearance: none;
    width: 40px;
    height: 40px;
    background: var(--clr-core-pop-30);
    border-radius: 50%;
    cursor: pointer;
    margin-top: 6px;
  }

  .size-slider::-moz-range-thumb {
    width: 40px;
    height: 40px;
    background: var(--clr-core-pop-30);
    border: none;
    border-radius: 50%;
    cursor: pointer;
  }
</style>
