<script>
  // Generate random border radius for each image
  const borderRadii = [10, 50, 30, 10, 20, 60];
</script>

<section class="example-gallery-wrap">
  <div class="example-images">
    <img
      src="./example-images/but-example-1.webp"
      alt="But Head font example 1"
      style="border-radius: {borderRadii[0]}px"
    />

    <img
      src="./example-images/but-example-4.webp"
      alt="But Head font example 4"
      style="border-radius: {borderRadii[3]}px"
    />
    <img
      src="./example-images/but-example-3.webp"
      alt="But Head font example 3"
      style="border-radius: {borderRadii[2]}px"
    />
    <img
      src="./example-images/but-example-2.webp"
      alt="But Head font example 2"
      style="border-radius: {borderRadii[1]}px"
    />
    <img
      src="./example-images/but-example-6.webp"
      alt="But Head font example 6"
      style="border-radius: {borderRadii[5]}px"
    />
    <img
      src="./example-images/but-example-5.webp"
      alt="But Head font example 5"
      style="border-radius: {borderRadii[4]}px"
    />
  </div>
</section>

<style>
  .example-gallery-wrap {
    grid-column: full-start / full-end;
    padding: 60px 0;
  }

  .example-images {
    column-count: 2;
    column-gap: 1em;

    & img {
      width: 100%;
      margin-bottom: 1em;
    }
  }
</style>
