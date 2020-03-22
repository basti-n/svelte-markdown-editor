<script>
  import marked from "marked";

  let source = "# new Document";
  let markdown = marked(source);
</script>

<style lang="scss">
  .header {
    .header-title {
      color: lavender;
    }
  }
</style>

<main>
  <header class="header">
    <h1 class="header-title">Markdown Editor (made with Svelte)</h1>
  </header>

  <p>{source}</p>
  <p>{markdown}</p>
</main>
