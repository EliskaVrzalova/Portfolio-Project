<script>
    
</script>
<nav>
    <ul>
        <li><a href="/portfolio">portfolio</a></li>
        <li><a href="/about me">about me</a></li>
        <li><a href="/CV">CV</a></li>
    </ul>
</nav>


<style>
        nav {
        display: flex;                /* Makes nav flexible */
        background-color: var(--secondary-color);  /* Purple background for nav */
        padding: 0.8rem 1.5rem;       /* Spacing inside purple container */
        border-radius: 25px;          /* Rounded corners */
    }


    nav ul {
        list-style: none;
        padding: 0;
        display: flex;
        justify-content: right;
        margin:0;
        
    }
    
    nav ul li {
    }

    nav ul li a{
        text-decoration: none;
        color:rgb(209, 204, 204);
        font-weight: bold;
        padding-left: var(--spacing-large);
    }
 a:before{
        content:'portfolio';
        color:white;
        position: absolute;
        overflow:hidden;
        width:0%;
        transition:all 0.5s;
    }
    a:hover:before{
        width:100%;
    }

    </style>
