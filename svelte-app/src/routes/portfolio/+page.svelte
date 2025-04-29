<script>
    import { onMount } from 'svelte';

    onMount(() => {
        //arrow buttons that control the menu scrolling
        const next = document.querySelector('.next');
        const previous = document.querySelector('.previous');
        
        next?.addEventListener('click', () => {
            const items = document.querySelectorAll('.item');
            if (items.length > 0) {
                const firstItem = items[0];
                const card = document.querySelector('.card');
                if (card && firstItem) {
                    card.appendChild(firstItem);
                    updateTextDisplay();
                }
            }
        });

        previous?.addEventListener('click', () => {
            const items = document.querySelectorAll('.item');
            if (items.length > 0) {
                const lastItem = items[items.length - 1];
                const card = document.querySelector('.card');
                if (card && lastItem) {
                    card.prepend(lastItem);
                    updateTextDisplay();
                }
            }
        });

        // Function to update which text is displayed
        function updateTextDisplay() {
            // Hide all text elements
            document.querySelectorAll('.item .text').forEach(text => {
                text.style.display = 'none';
            });
            
            // Show text for the second item (index 1)
            const secondItem = document.querySelectorAll('.item')[1];
            if (secondItem) {
                const text = secondItem.querySelector('.text');
                if (text) {
                    text.style.display = 'block';
                }
            }
        }
    });
</script>


<div class="overlay"></div>
<div class="container">
    <!--portfolio sections with their bg images, titles and brief description-->
    <div class="card">
        <div class="item" style="background-image: url('/web-design.png');"  aria-label="Web design background">
            <div class="text">
                <div class="title">Web design and Development</div>
                <div class="description">Design meets code. I learn how to bring websites to life with HTML, CSS, and JavaScript — clean, creative, and built with users in mind.</div>
                <button><a href="/web design">See More</a></button>
            </div>
        </div>
        <div class="item" style="background-image: url('/game-design.png');"  aria-label="Game design background">
            <div class="text">
                <div class="title">Game Design</div>
                <div class="description">Visual side of game design — using pixel art, UI, and atmosphere to bring worlds to life and guide the player’s experience.</div>
                <button><a href="/game design">See More</a></button>
            </div>
        </div>
        <div class="item" style="background-image: url('/game-development (2).png');" aria-label="Game development background">
            <div class="text">
                <div class="title">Game Development</div>
                <div class="description">Game development in C++ — I coded few gameplay systems, mechanics, and worlds from scratch with original game assets.<br> All my games are available at my Github.</div>
                <button><a href="/game dev">See More</a></button>
            </div>
        </div>
        <div class="item" style="background-image: url('/digital-art.png');" aria-label="Digital art background">
            <div class="text">
                <div class="title">Digital Art</div>
                <div class="description">I’m refining my digital art skills, working with software like Photoshop and more including 3D to create detailed, dynamic pieces that push my creativity and technique.</div>
                <button><a href="/digital art">See More</a></button>
            </div>
        </div>
        <div class="item" style="background-image: url('/tattoo-design.png');"  aria-label="Tattoo design background">
            <div class="text">
                <div class="title">Tattoo Design</div>
                <div class="description">I design tattoos for friends and anyone looking for something personal and meaningful. I love turning ideas and stories into designs that people carry with them forever.</div>
                <button><a href="/tattoo design">See More</a></button>
            </div>
        </div>
        <div class="item" style="background-image: url('/paintings.png');"  aria-label="Paintings background">
            <div class="text">
                <div class="title">Paintings</div>
                <div class="description">I started with painting. That creative foundation now inspires my work in game design, pixel art, and UI.</div>
                <button><a href="/paintings">See More</a></button>
            </div>
        </div>
    </div>
    
</div>
<!--arrow buttons to control the portfolio menu-->
<div class="arrow-buttons">
    <button class="previous" aria-label="Previous project">←</button>
    <button class="next" aria-label="Next project">→</button>
</div>

<style>
    /*darker effect*/
          .overlay {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background: linear-gradient(to bottom, 
            rgba(0,0,0,0.1) 0%,
            rgba(0,0,0,0.2) 60%, 
            rgba(0,0,0,0.4) 100%);
        z-index: 0;
        pointer-events: none; /* Allows clicks to pass through */
    }
    
    .container{
        position: fixed;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100vh;
        z-index: -1; /* Keep background images below the overlay */
        box-shadow: 0 30px 40px #ffffff;
    }
    /*upcoming cards*/
    .container .card .item{
        width:300px;
        height:200px;
        position: absolute;
        top:65%;
        transform: translate(0, -50%);
        border-radius:20px;
        box-shadow: 0 7px 15px rgb(255, 255, 255,0.5);
        background-position: 50% 50%;
        background-size: cover;
        display: inline-block;
        transition: 0.5s;

    }

/*calculating the gaps between the cards based on the width (300px) and gap(20px) of each card*/
/*second child visible first*/
    .card .item:nth-child(1),
     .card .item:nth-child(2){
        top:0;
        left:0;
        transform: translate(0, 0);
        width:100%;
        height:100%;
        border-radius: 0;
    }
    .card .item:nth-child(3){
        left:50%;
    }
    .card .item:nth-child(4){
        left: calc(50% + 320px);
    }
    .card .item:nth-child(5){
        left: calc(50% + 640px);
    }
    .card .item:nth-child(n+6){
        left:calc(50% + 960px);
        opacity:0;
    }

    .item .text{
        position: absolute;
        top: 50%;
        left:100px;
        width:500px;
        height:400px;
        text-align: left;
        color:white;
        background-color: rgb(115, 54, 181,0.8);
        border-radius: 30px;
        box-shadow: 0 7px 15px rgb(255, 255, 255,0.5);
        padding:10px 30px;
        transform: translate(0, -50%);
        display:none;
        z-index: 1;
    }
    /*text for the second child visible first*/
    .card .item:nth-child(2) .text{
        display:block;
    }

    /*reveal animation effect applied on everything inside the text container*/
    .text .title{
        font-size:var(--font-size-h2);
        font-weight: bold;
        opacity:0;
        animation: reveal 1s ease-in-out 1 forwards;
        margin-top: 10px;
    }

    .text .description{
        font-size:var(--font-size-base);
        margin-top: 30px;
        margin-bottom: 20px;
        opacity:0;
        animation: reveal 1s ease-in-out 0.3s 1 forwards;
    }

    .text button{
        margin-top: 30px;
        padding: 10px 20px;
        border:none;
        opacity: 0;
        animation: reveal 1s ease-in-out 0.6s 1 forwards;
        transition: all .4s ease-in-out;
        background-color: #ffffff;
        overflow: hidden;
        font-size: var(--font-size-base);
        font-family:"DynaPuff", serif;
        padding:10px 20px 10px 20px;
        border-radius:50px;
    }
    /*button hover effect*/
    .text button::before {
        content: '';
        position: absolute;
        top: 0;
        left: -100%;
        width: 50%;
        height: 100%;
        background: linear-gradient(
            to right,
            transparent,
            rgba(157, 45, 198, 0.7),
            transparent
        );
        transform: skewX(-25deg);
        transition: left 0.5s ease;
    }

    .text button:hover::before {
        left: 150%; /* Move past the button */
        transition: left 0.5s ease;
       
    }


    @keyframes reveal{
        from{
            opacity:0;
            transform: translate(0, 100px);
            filter:blur(30px);
        }
        to{
            opacity:1;
            transform: translate(0);
            filter:blur(0);
        }
    }
    .arrow-buttons{
        position: absolute;
        text-align: center;
        width:100%;
        bottom:30px;
    }
    .arrow-buttons button{
        width:50px;
        height:45px;
        border-radius: 20px;
        border:none;
        margin: 0 5px;
        transition: 0.3s;
    }

    .arrow-buttons button:hover{
        transform: scale(1.1);
        background-color: var(--primary-color);
    }

       /*mobile*/
       @media(max-width: 768px){
    .container{
        display: flex;
        justify-content: center;
        align-items: center;
        top: 0;
        left: 0;
        width: 100%; 
        height: 100%;
        overflow: hidden;
    }
    .item .text{
        position: absolute;
        top: 50%;
        left: 50%; /* Center horizontally */
        width: 85%; 
        max-width: 400px; 
        height: auto; 
        min-height: 280px; 
        padding: 15px 20px; /* Increased padding for better spacing */
        transform: translate(-50%, -50%); /* Center both horizontally and vertically */
        display: none;
        z-index: 1;
    }
    
    .text .title{
        margin-top: 5px;
    }

    .text .description{
        font-size:var(--font-size-base-smaller);
        line-height: 1.5rem;
        margin-top: 15px;
        margin-bottom: 10px;
    }
    .text button {
        margin-top: 15px;
        padding: 8px 16px;
        font-size: 1rem;
    }
    @keyframes reveal{
        from{
            opacity:0;
            transform: translate(0, 50px);
            filter:blur(30px);
        }
        to{
            opacity:1;
            transform: translate(0);
            filter:blur(0);
        }
    }
     
 
    .arrow-buttons {
        bottom: 20px;
    }
    
    .arrow-buttons button {
        width: 45px;
        height: 40px;
    }
    .card .item:nth-child(3),
    .card .item:nth-child(4),
    .card .item:nth-child(5),
    .card .item:nth-child(n+6) {
        top: 75%; /* Move items lower */
        width: 220px; /* Make items smaller */
        height: 120px; /* Make items smaller */
        box-shadow: 0 10px 20px rgba(255, 255, 255, 0.5);
    }
    .card .item:nth-child(3){
        left:20%;
    }
    .card .item:nth-child(4){
        left: calc(20% + 240px);
    }
    .card .item:nth-child(5){
        left: calc(20% + 480px);
    }
    .card .item:nth-child(n+6){
        left:calc(20% + 720px);
        opacity:0;
    }
       }
    /*tablet devices*/
    @media (min-width: 769px) and (max-width: 1024px) {
        .container{
        display: flex;
        justify-content: center;
        align-items: center;
        top: 0;
        left: 0;
        width: 100%; 
        height: 100%;
        overflow: hidden;
    }
    .item .text{
        position: absolute;
        top: 50%;
        left: 50%; /* Center horizontally */
        width: 85%; 
        max-width: 600px; 
        height: auto; 
        min-height: 320px; 
        padding: 20px 25px; /* Increased padding for better spacing */
        transform: translate(-50%, -50%); /* Center both horizontally and vertically */
        display: none;
        z-index: 1;
    }
    
    .text .title{
        margin-top: 10px;
    }

    .text .description{
        line-height: 2.5rem;
        margin-top: 20px;
        margin-bottom: 15px;
    }
    .text button {
        margin-top: 25px;
        padding: 10px 18px;
        font-size:var(--font-size-base);
    }
    @keyframes reveal{
        from{
            opacity:0;
            transform: translate(0, 80px);
            filter:blur(30px);
        }
        to{
            opacity:1;
            transform: translate(0);
            filter:blur(0);
        }
    }
     
 
    .arrow-buttons {
        bottom: 25px;
    }
    
    .arrow-buttons button {
        width: 50px;
        height: 45px;
    }
    .card .item:nth-child(3),
    .card .item:nth-child(4),
    .card .item:nth-child(5),
    .card .item:nth-child(n+6) {
        top: 80%; /* Move items lower */
        margin-top: 2rem;
        width: 320px; /* Make items smaller */
        height: 220px; /* Make items smaller */
        box-shadow: 0 10px 20px rgba(255, 255, 255, 0.5);
    }
    .card .item:nth-child(3){
        left:30%;
    }
    .card .item:nth-child(4){
        left: calc(30% + 340px);
    }
    .card .item:nth-child(5){
        left: calc(30% + 680px);
    }
    .card .item:nth-child(n+6){
        left:calc(30% + 1020px);
        opacity:0;
    }
    }
</style>