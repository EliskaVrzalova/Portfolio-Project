<script>
    import { page } from '$app/stores';
</script>
<nav>
    <ul>
        <li><a href="/portfolio" data-text="portfolio" class={$page.url.pathname === '/portfolio' ? 'active' : ''}>portfolio</a></li>
        <li><a href="/about me" data-text="about me" class={$page.url.pathname ===  '/about%20me' ? 'active' : ''}>about me</a></li>
        <li><a href="/CV" data-text="CV" class={$page.url.pathname === '/CV' ? 'active' : ''}>CV</a></li>
    </ul>
</nav>


<style>
        nav {
        display: flex;                /* Makes nav flexible */
        background-color: var(--primary-color); 
        padding: 0.8rem 1.5rem;       /* Spacing inside purple container */
        border-radius: 25px;          /* Rounded corners */
        z-index: 10;
    }


    nav ul {
        list-style: none;
        padding: 0;
        display: flex;
        justify-content: right;
        margin:0;
        gap: 4rem;
        padding: 10px 5px;
        
    }
    
    nav ul li {
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
    

    </style>