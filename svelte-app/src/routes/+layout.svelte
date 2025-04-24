<script>
    //Import components
    import { Header, Footer } from "$lib";
    import { page } from "$app/stores";
    
    // Check if current page is the portfolio page
    $: isPortfolioPage = $page.url.pathname.startsWith("/portfolio");
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
    </style>