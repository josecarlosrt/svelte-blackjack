<script>
  import Cards from './lib/Cards.svelte';
</script>

<main>
  <div>
    <a href="#"> 
      <img src="/bj-logo.png" class="logo" alt="Logo" />
    </a>
  </div>
  <div class="card">
    <Cards />
  </div>
</main>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #ED1C24);
  }

  .read-the-docs {
    color: #888;
  }
</style>
