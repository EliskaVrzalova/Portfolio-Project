<script>
    import { ImageViewer, PortfolioNav } from "$lib";
    
    function scrollToTop() {
        window.scrollTo({
          top: 0,
          behavior: 'smooth'
        });
    }
    
    // Game design content organized by type
    const playerDesigns = [
        {
            src: "/player1-design.png",
            alt: "Design of player space rocket - variant 1",
            description: "First variant of player spacecraft design."
        },
        {
            src: "/player2-design.png",
            alt: "Design of player space rocket - variant 2",
            description: "Second variant of player spacecraft."
        },
        {
            src: "/player3-design.png",
            alt: "Design of player space rocket - variant 3",
            description: "Third variant of player spacecraft."
        }
    ];
    
    const animationAssets = [
        {
            src: "/player idle.gif",
            alt: "Player rocket idle animation",
            description: "Player spacecraft idle animation showing subtle engine effects and stabilizer movements. The animation creates a sense of a ship hovering in space, ready for action."
        },
        {
            src: "/enemy upgrade.gif",
            alt: "Enemy upgrade animation sequence",
            description: "Animation sequence showing an enemy spacecraft powering up. The transformation illustrates how enemies evolve during gameplay, presenting escalating challenges."
        },
        {
            src: "/enemy shoot.gif",
            alt: "Enemy attack animation",
            description: "Enemy attack animation displaying weapon discharge and recoil effects."
        }
    ];
    
    const uiElements = [
        {
            src: "/menu.png",
            alt: "Game menu design",
            description: "Main menu interface design for space-themed game"
        },
        {
            src: "/game-background.png",
            alt: "In-game background environment",
            description: "Space-themed game background. It creates depth and atmosphere while ensuring gameplay elements remain visually distinct."
        }
    ];
</script>
<div class="nav-container">
    <PortfolioNav />
</div>
    <div class="container">
        <h1 class="title">Game Design</h1>
        
        <div class="gallery">

            <div class="column">
                <div class="picture">
                    {#each uiElements as image}
                        <div class="image-wrapper">
                            <ImageViewer 
                                src={image.src} 
                                alt={image.alt} 
                                description={image.description} 
                            />
                        </div>
                    {/each}
                </div>
            </div>
            <div class="column">
                <div class="picture">
                    {#each playerDesigns as image}
                        <div class="image-wrapper">
                            <ImageViewer 
                                src={image.src} 
                                alt={image.alt} 
                                description={image.description} 
                            />
                        </div>
                    {/each}
                </div>
                <div class="picture">
                    {#each animationAssets as image}
                        <div class="image-wrapper">
                            <ImageViewer 
                                src={image.src} 
                                alt={image.alt} 
                                description={image.description} 
                            />
                        </div>
                    {/each}
                </div>
            </div>
        </div>
    </div>
    <div class="arrow-buttons">
        <button class="up" on:click={scrollToTop}>↑</button>
    </div>
    
    
    <style>
        .container{
            max-width:1400px;
            width:90%;
            margin:auto;
            padding:40px 0;
        }
    
        .title{
            margin-bottom: 4rem;
            text-align: center;
        }
        .gallery{
            display:flex;
            gap: 20px;
    
        }
        .column{
            display:flex;
            flex-direction: column;
            gap:20px;
        }

        .picture {
            display: flex;
            flex-direction: column;
            width: 100%;
            gap: 20px;
        }
        
        .image-wrapper {
            width: 100%;
            margin-bottom: 10px;
            border-radius: 5px;
            overflow: hidden;
        }
        
        .arrow-buttons{
            margin-top: 2rem;
            position: relative;
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
    
    
        @media(max-width: 768px){
            .gallery{
                flex-direction: column;
            }
            .title{
            margin-bottom: 2rem;
            text-align: center;
        }
        .arrow-buttons {
        bottom: 20px;
        }
    
        .arrow-buttons button {
        width: 45px;
        height: 40px;
        }
      
        }
    </style>