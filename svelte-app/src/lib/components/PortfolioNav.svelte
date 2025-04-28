<script>
    import { page } from '$app/stores';
</script>
<nav role="navigation" aria-label="Portfolio categories">
    <ul role="menubar">
        <li role="none"><a href="/game design" data-text="Game Design" class={$page.url.pathname === '/game%20design' ? 'active' : ''} role="menuitem" aria-current={$page.url.pathname === '/game%20design' ? 'page' : undefined}>Game Design</a></li>
        <li role="none"><a href="/game dev" data-text="Game Development" class={$page.url.pathname ===  '/game%20dev' ? 'active' : ''} role="menuitem" aria-current={$page.url.pathname === '/game%20dev' ? 'page' : undefined}>Game Development</a></li>
        <li role="none"><a href="/digital art" data-text="Digital Art" class={$page.url.pathname === '/digital%20art' ? 'active' : ''} role="menuitem" aria-current={$page.url.pathname === '/digital%20art' ? 'page' : undefined}>Digital Art</a></li>
        <li role="none"><a href="/tattoo design" data-text="Tattoo Design" class={$page.url.pathname === '/tattoo%20design' ? 'active' : ''} role="menuitem" aria-current={$page.url.pathname === '/tattoo%20design' ? 'page' : undefined}>Tattoo Design</a></li>
        <li role="none"><a href="/paintings" data-text="Paintings" class={$page.url.pathname === '/paintings' ? 'active' : ''} role="menuitem" aria-current={$page.url.pathname === '/paintings' ? 'page' : undefined}>Paintings</a></li>
        <li role="none"><a href="/web design" data-text="Web Design" class={$page.url.pathname === '/web%20design' ? 'active' : ''} role="menuitem" aria-current={$page.url.pathname === '/web%20design' ? 'page' : undefined}>Web Design</a></li>
    </ul>
</nav>
<style>
    nav {
    display: flex;  
    position: relative;
    left: 50%;
    transform: translateX(-50%);
    width: 100vw; /* Full viewport width */
    margin-left: calc(-50vw); /* Ensure edge-to-edge width, wide enough I dont see the edges */
    margin-right: calc(-50vw);
    right: 0;
    margin: 0;
    padding: 0.5rem 0; /* Keep vertical padding, remove horizontal */
    justify-content: center; 
    background-color: rgb(115, 54, 181, 0.5);
    border: 1px solid var(--primary-color);
    border-radius: 0; 
    z-index: 10;
    box-sizing: border-box; 
    overflow-x: hidden;
}


nav ul {
    list-style: none;
    padding: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    margin: 0;
    gap: 4rem; 
    padding: 10px 20px; 
    flex-wrap: nowrap; 
    max-width: 1200px; 
    width: 100%; /* Full width */
}
/*links styled the same as the main navigation */
nav ul li a{
        text-decoration: none;
        color: rgb(209, 204, 204);
        font-weight: bold;
        display: inline-block;
        position: relative;
        transition: all 0.3s ease;
    }
    
    /* Active link styling */
    nav ul li a.active {
        color: white;
        transform: scale(1.1);
    }
    
  
    nav ul li a:before {
        content: attr(data-text);
        color: white;
        position: absolute;
        overflow: hidden;
        white-space: nowrap;
        width: 0%;
        transition: all 0.5s ease;
    }
    
  
    nav ul li a.active:before {
        width: 100%;
    }
  
    nav ul li a:hover {
        transform: scale(1.2);
    }
    
    nav ul li a:hover:before {
        width: 100%;
    }
    
 
    /* Focus state */
    nav ul li a:focus {
        color: white;
        text-decoration: none;
        outline: 2px solid white;
        outline-offset: 2px;
        border-radius: 4px;
    }
        /*mobile*/
        @media(max-width: 768px){

            nav ul {
                gap: 1.5rem;
                padding: 4px 20px; 
                white-space: nowrap; 
                justify-content: center;
                width: auto; /* Allow content to determine width */
                max-width: none; /* Remove max-width constraint in mobile */
            }
            nav ul li{
                font-size: var(--font-size-base-smaller);
            }
            nav {
            display: flex;  
            justify-content: flex-start; /* Start alignment for better scrolling experience */
            padding: 0.3rem 0;      
            overflow-x: auto; /* Allow horizontal scrolling if needed */
            -webkit-overflow-scrolling: touch; /* Smooth scrolling on iOS */
            scroll-behavior: smooth; /* Smooth scrolling behavior */
            scrollbar-color: rgba(255, 255, 255, 0.3) transparent; /* Firefox */
            }
            
            /* Custom scrollbar styling for webkit browsers */
            nav::-webkit-scrollbar {
                height: 3px;
            }
            
            nav::-webkit-scrollbar-track {
                background: transparent;
            }
            
            nav::-webkit-scrollbar-thumb {
                background-color: rgba(255, 255, 255, 0.3);
                border-radius: 20px;
            }
            
            
        }
        /*tablet devices*/
    @media (min-width: 769px) and (max-width: 1024px) {
        nav ul {
                gap: 2rem;
                padding: 6px 25px; 
                width:100%;
                white-space: nowrap; 
                justify-content: center;
                width: auto; /* Allow content to determine width */
                max-width: none; /* Remove max-width constraint in mobile */
            }
            nav ul li{
                font-size: var(--font-size-base);
            }
            nav {
            display: flex;  
            justify-content: flex-start; /* Start alignment for better scrolling experience */
            padding: 0.2rem 0;      
            overflow-x: auto; /* Allow horizontal scrolling if needed */
            -webkit-overflow-scrolling: touch; /* Smooth scrolling on iOS */
            scroll-behavior: smooth; /* Smooth scrolling behavior */
            scrollbar-color: rgba(255, 255, 255, 0.3) transparent; /* Firefox */
            }
            
            /* Custom scrollbar styling for webkit browsers */
            nav::-webkit-scrollbar {
                height: 3px;
            }
            
            nav::-webkit-scrollbar-track {
                background: transparent;
            }
            
            nav::-webkit-scrollbar-thumb {
                background-color: rgba(255, 255, 255, 0.3);
                border-radius: 20px;
            }
    }

</style>