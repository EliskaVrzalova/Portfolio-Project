<script>
    import { page } from '$app/stores';
    import { onMount } from 'svelte';
    
    // State for mobile menu
    let mobileMenuOpen = false;
    
    // Toggle mobile menu
    function toggleMobileMenu() {
        mobileMenuOpen = !mobileMenuOpen;
        
        // When menu is open, prevent body scrolling
        if (mobileMenuOpen) {
            document.body.style.overflow = 'hidden';
        } else {
            document.body.style.overflow = '';
        }
    }
    
    // Close menu when clicking on a link
    function closeMenu() {
        mobileMenuOpen = false;
        document.body.style.overflow = '';
    }

</script>

<!-- Desktop Navigation -->
<nav class="desktop-nav">
    <ul>
        <li><a href="/portfolio" data-text="portfolio" class={$page.url.pathname === '/portfolio' ? 'active' : ''}>portfolio</a></li>
        <li><a href="/about me" data-text="about me" class={$page.url.pathname ===  '/about%20me' ? 'active' : ''}>about me</a></li>
        <li><a href="/CV" data-text="CV" class={$page.url.pathname === '/CV' ? 'active' : ''}>CV</a></li>
    </ul>
</nav>

<!-- Mobile Navigation -->
<div class="mobile-nav-container">
    <!-- Hamburger Button -->
    <button 
        class="hamburger-btn" 
        class:open={mobileMenuOpen} 
        on:click={toggleMobileMenu}
        aria-label="Toggle navigation menu"
    >
        <span></span>
        <span></span>
        <span></span>
    </button>
    
    <!-- Overlay Menu -->
    <div class="mobile-menu-overlay" class:open={mobileMenuOpen} on:click={closeMenu}>
        <!-- Prevent clicks on menu from closing -->
        <nav class="mobile-menu" on:click|stopPropagation>
            <ul>
                <li>
                    <a 
                        href="/portfolio" 
                        class={$page.url.pathname === '/portfolio' ? 'active' : ''}
                        on:click={closeMenu}
                    >
                        portfolio
                    </a>
                </li>
                <li>
                    <a 
                        href="/about me" 
                        class={$page.url.pathname === '/about%20me' ? 'active' : ''}
                        on:click={closeMenu}
                    >
                        about me
                    </a>
                </li>
                <li>
                    <a 
                        href="/CV" 
                        class={$page.url.pathname === '/CV' ? 'active' : ''}
                        on:click={closeMenu}
                    >
                        CV
                    </a>
                </li>
            </ul>
        </nav>
    </div>
</div>


<style>
    /* Desktop Navigation Styles */
    .desktop-nav {
        display: flex;                /* Makes nav flexible */
        background-color: var(--primary-color); 
        padding: 0.8rem 1.5rem;       /* Spacing inside purple container */
        border-radius: 25px;          /* Rounded corners */
        z-index: 10;
    }

    .desktop-nav ul {
        list-style: none;
        padding: 0;
        display: flex;
        justify-content: right;
        margin:0;
        gap: 4rem;
        padding: 10px 5px;
    }

    .desktop-nav ul li a{
        text-decoration: none;
        color: rgb(209, 204, 204);
        font-weight: bold;
        display: inline-block;
        position: relative;
        transition: all 0.3s ease;
    }
    
    /* Active link styling */
    .desktop-nav ul li a.active {
        color: white;
        transform: scale(1.1);
    }
    
    .desktop-nav ul li a:before {
        content: attr(data-text);
        color: white;
        position: absolute;
        overflow: hidden;
        white-space: nowrap;
        width: 0%;
        transition: all 0.5s ease;
    }
    
    .desktop-nav ul li a.active:before {
        width: 100%;
    }
  
    .desktop-nav ul li a:hover {
        transform: scale(1.2);
    }
    
    .desktop-nav ul li a:hover:before {
        width: 100%;
    }
    
    /* Focus state */
    .desktop-nav ul li a:focus {
        color: white;
        text-decoration: none;
        outline: none;
    }
    
    /* hamburger menu hidden on a desktop*/
    .mobile-nav-container {
        display: none;
    }
    
    /* Mobile Navigation Styles */
    @media (max-width: 768px) {
        /* Hide desktop navigation */
        .desktop-nav {
            display: none;
        }
        
        /* Show mobile navigation container */
        .mobile-nav-container {
            display: block;
            top: 45px;
            margin-right: 1rem;
            z-index: 1000;
        }
        
        /* Hamburger Button */
        .hamburger-btn {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            width: 40px;
            height: 40px;
            background: var(--primary-color);
            border: none;
            border-radius: 5px;
            padding: 8px;
            cursor: pointer;
            z-index: 1001;
            transition: all 0.3s ease;
        }
        
        .hamburger-btn span {
            width: 100%;
            height: 3px;
            background: white;
            border-radius: 2px;
            transition: all 0.3s ease;
        }
        
        /* Hamburger Button Animation */
        /*first line of the icon*/
        .hamburger-btn.open span:nth-child(1) {
            transform: translateY(10px) rotate(45deg);
        }
        /*second line*/
        .hamburger-btn.open span:nth-child(2) {
            opacity: 0;
        }
        /*third line*/
        .hamburger-btn.open span:nth-child(3) {
            transform: translateY(-10px) rotate(-45deg);
        }
        
        /* Mobile Menu Overlay */
        .mobile-menu-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 999;
            opacity: 0;
            visibility: hidden;
            transition: all 0.4s ease;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        
        .mobile-menu-overlay.open {
            opacity: 1;
            visibility: visible;
        }
        
        /* Mobile Menu */
        .mobile-menu {
            background-color: var(--primary-color);
            padding: 2rem;
            border-radius: 20px;
            width: 80%;
            max-width: 350px;
            transform: translateY(20px);
            opacity: 0;
            transition: transform 0.4s ease, opacity 0.4s ease;
        }
        
        /* When overlay is open, animate the menu in */
        .mobile-menu-overlay.open .mobile-menu {
            transform: translateY(0);
            opacity: 1;
        }
        
        .mobile-menu ul {
            list-style: none;
            padding: 0;
            margin: 0;
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 2rem;
        }
        
        .mobile-menu ul li {
            width: 100%;
            text-align: center;
            opacity: 0;
            transform: translateY(10px);
            transition: opacity 0.3s ease, transform 0.3s ease;
        }
        
        /* Staggered animations for menu items */
        .mobile-menu-overlay.open .mobile-menu ul li:nth-child(1) {
            transition-delay: 0.1s;
            opacity: 1;
            transform: translateY(0);
        }
        
        .mobile-menu-overlay.open .mobile-menu ul li:nth-child(2) {
            transition-delay: 0.3s;
            opacity: 1;
            transform: translateY(0);
        }
        
        .mobile-menu-overlay.open .mobile-menu ul li:nth-child(3) {
            transition-delay: 0.5s;
            opacity: 1;
            transform: translateY(0);
        }
        
        .mobile-menu ul li a {
    display: inline-block;
    text-decoration: none;
    font-size:var(--font-size-base);
    font-weight: bold;
    padding: 1rem 0;
    position: relative;
    transition: all 0.3s ease;
    color: rgb(209, 204, 204); /* Match desktop color */
}

.mobile-menu ul li a::before {
    content: attr(data-text);
    color: white;
    position: absolute;
    top: 0;
    left: 0;
    white-space: nowrap;
    overflow: hidden;
    width: 0%;
    transition: all 0.5s ease;
    pointer-events: none; /* Prevent interference */
}

.mobile-menu ul li a:hover {
    transform: scale(1.2);
    color: white;
}

.mobile-menu ul li a:hover::before {
    width: 100%;
}
        
  
        
        /* Small mobile adjustments */
        @media (max-width: 480px) {
            .mobile-nav-container {
                top: 15px;
                right: 15px;
            }
            
            .hamburger-btn {
                width: 55px;
                height: 45px;
                padding: 10px;
            }
            
            .mobile-menu {
                padding: 1.5rem;
                width: 90%;
            }
            
            .mobile-menu ul {
                gap: 1.5rem;
            }
            
            .mobile-menu ul li a {
                font-size:var(--font-size-base-smaller);
                padding: 0.8rem 0;
            }
        }
    }
</style>
