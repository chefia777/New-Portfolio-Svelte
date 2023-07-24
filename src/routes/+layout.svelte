<script>
  import Header from "./Header.svelte";
  import Background from "./Background.svelte";
  import Socials from "./Socials.svelte";
  import "./styles.css";
  import "../app.css";
  import { scrollTo, scrollRef, scrollTop } from 'svelte-scrolling'
</script>

<div class="app">
  <div class="header">
    <Header />
  </div>
  <Background />
  <main>
    <slot />
    
  </main>
  <div class="socials">
    <Socials />
  </div>
  
  
  <footer />
</div>

<style lang="postcss">
  .socials {
    flex: 1;
    display: flex;
    flex-direction: column;
    padding: 1rem;
    width: 100%;
    max-width: 64rem;
    margin: 0 auto;
    box-sizing: border-box;
  }

  .header {
    z-index: 9999;
  }

 
  @keyframes spin {
    from {
      transform: translate(-50%, -50%);
    }
    to {
      transform: translate(-50%, -50%) rotate(-360deg);
    }
  }

  :global(body) {
    background: black;
    overflow-x: hidden;
    overflow-y: auto;
  }

  .app {
    display: flex;
    flex-direction: column;
    min-height: 100vh;
  }

  main {
    flex: 1;
    display: flex;
    flex-direction: column;
    padding: 1rem;
    width: 100%;
    max-width: 64rem;
    margin: 0 auto;
    box-sizing: border-box;
  }

  footer {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 12px;
  }

  footer a {
    font-weight: bold;
  }

  @media (min-width: 480px) {
    footer {
      padding: 12px 0;
    }
  }
</style>
