<script>
  import marked from "marked";

  let source = "# new Document";
  $: markdown = marked(source);
</script>

<style lang="scss">
  .header {
    height: 10vh;
    display: flex;
    justify-content: center;
    align-items: center;

    .header-title {
      margin: 0;
    }
  }

  .markdown-editor {
    display: flex;
    justify-content: space-evenly;
    align-items: flex-start;
    width: 100%;

    .markdown-editor__left-panel,
    .markdown-editor__right-panel {
      width: 50%;
      border: 1px solid black;
      height: 90vh;
    }

    .markdown-editor__source {
      border: none;
      width: 100%;
      height: 100%;

      &:focus {
        outline: none;
      }
    }

    .markdown-editor__result {
      width: 100%;
      padding: 0 2em;
    }
  }
</style>

<main>
  <header class="header">
    <h1 class="header-title">Markdown Editor (made with Svelte)</h1>
  </header>

  <div class="markdown-editor">
    <div class="markdown-editor__left-panel">
      <textarea 
      bind:value={source}
      class="markdown-editor__source" />
    </div>
    <div class="markdown-editor__right-panel">
      <div class="markdown-editor__result">{@html markdown}</div>
    </div>
  </div>
</main>
