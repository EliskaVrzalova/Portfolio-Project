<script>
    
</script>
<nav>
    <ul>
        <li><a href="/portfolio" data-text="portfolio">portfolio</a></li>
        <li><a href="/about me" data-text="about me">about me</a></li>
        <li><a href="/CV" data-text="CV">CV</a></li>
    </ul>
</nav>


<style>
        nav {
        display: flex;                /* Makes nav flexible */
        background-color: var(--primary-color); 
        padding: 0.8rem 1.5rem;       /* Spacing inside purple container */
        border-radius: 25px;          /* Rounded corners */
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
        color:rgb(209, 204, 204);
        font-weight: bold;
        display:inline-block;
        position:relative;
        transition: all 0.3s ease;
    }
 a:before{
        content: attr(data-text);
        color: white;
        position: absolute;
        overflow:hidden;
        white-space: nowrap;
        width:0%;
        transition:all 0.5s;
    }
    a:hover{
        transform:scale(1.2);
    }
    a:hover:before{
        width:100%;
    }

    </style>
