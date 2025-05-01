<script>
  //Import components
  import { Header, Footer } from "$lib";
  import { page } from "$app/stores";
  import { base } from '$app/paths';
  
  // Check if current page is the portfolio page
  $: isPortfolioPage = $page.url.pathname.startsWith(`${base}/portfolio`);
  </script>
  <!-- Header -->
  <Header />

  <!-- Page Content -->
  <main>
      <slot />
  </main>

  <!-- Footer --> 
     <!-- Footer (hidden on portfolio page) --> 
     {#if !isPortfolioPage}
     <Footer />
 {/if}
  <style>
  main {
  padding: 2rem;
  text-align: left;
  }
  
  .skip-to-main {
    position: absolute;
    left: -9999px;
    z-index: 999;
    padding: 1em;
    background-color: white;
    color: black;
    text-decoration: none;
    font-weight: bold;
  }
  
  .skip-to-main:focus {
    left: 50%;
    transform: translateX(-50%);
    top: 0;
  }
  </style>