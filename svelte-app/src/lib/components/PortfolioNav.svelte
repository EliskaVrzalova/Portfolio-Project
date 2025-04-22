<script>
    import { page } from '$app/stores';
</script>
<nav>
    <ul>
        <li><a href="/game design" data-text="Game Design" class={$page.url.pathname === '/game%20design' ? 'active' : ''}>Game Design</a></li>
        <li><a href="/game dev" data-text="Game Development" class={$page.url.pathname ===  '/game%20dev' ? 'active' : ''}>Game Development</a></li>
        <li><a href="/digital art" data-text="Digital Art" class={$page.url.pathname === '/digital%20art' ? 'active' : ''}>Digital Art</a></li>
        <li><a href="/tattoo design" data-text="Tattoo Design" class={$page.url.pathname === '/tattoo%20design' ? 'active' : ''}>Tattoo Design</a></li>
        <li><a href="/paintings" data-text="Paintings" class={$page.url.pathname === '/paintings' ? 'active' : ''}>Paintings</a></li>
        <li><a href="/web design" data-text="Web Design" class={$page.url.pathname === '/web%20design' ? 'active' : ''}>Web Design</a></li>
    </ul>
</nav>
<style>
    nav {
    display: flex;  
    justify-content: center; 
    background-color:rgb(115, 54, 181, 0.5);          /* Makes nav flexible */
    border: 2px solid var(--primary-color); 
    padding: 0.5rem 2rem;       /* Spacing inside purple container */
    border-radius: 25px;          /* Rounded corners */
    z-index: 10;
}


nav ul {
    list-style: none;
    padding: 0;
    display: flex;
    align-items: center;
    margin:0;
    gap: 4rem;
    padding: 10px 5px;
    
}
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
        outline: none;
    }
    
        /*mobile*/
        @media(max-width: 768px){
            nav ul {
                gap: 2rem;
                padding: 5px 0px;
    
            }
            nav ul li{
                font-size: 1rem;
            }
        }

</style>