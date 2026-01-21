<script>
  import "@gitbutler/design-core/core";
  import Hero from "./lib/Hero.svelte";
  import AllLetters from "./lib/AllLetters.svelte";
  import NoGaps from "./lib/NoGaps.svelte";
  import FontsCompare from "./lib/FontsCompare.svelte";
  import Editor from "./lib/Editor.svelte";
  import ExampleGallery from "./lib/ExampleGallery.svelte";
  import Footer from "./lib/Footer.svelte";
</script>

<main>
  <Hero />
  <AllLetters />
  <NoGaps />
  <FontsCompare />
  <Editor />
  <ExampleGallery />
  <Footer />
</main>

<style>
  main {
    display: grid;
    align-items: flex-start;
    grid-template-columns:
      [full-start] repeat(2, 1fr) [narrow-start] repeat(8, 1fr)
      [narrow-end] 1fr [off-center] 1fr [full-end];
    gap: 20px;
    padding: 0 60px;
    max-width: 1600px;
    margin: 0 auto;
  }

  @media (max-width: 1000px) {
    main {
      padding: 0 20px;
      grid-template-columns: [full-start] repeat(4, 1fr) [full-end];
    }
  }
</style>
