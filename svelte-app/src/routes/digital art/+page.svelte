<script>
    import { ImageViewer, PortfolioNav } from "$lib";
    
    function scrollToTop() {
        window.scrollTo({
          top: 0,
          behavior: 'smooth'
        });
    }
    
    // Image data with descriptions
    const column1Images = [
        {
            src: "/oldmansketch.png",
            alt: "Sketches drafts of old man",
            description: "Early concept sketches of an elderly character. These drafts explore different facial features and expressions to capture the essence of age and wisdom."
        },
        {
            src: "/concept-art.jpg",
            alt: "Concept art for fictional character",
            description: "Character concept art showing various design iterations. These explorations helped establish the final visual direction for this fictional character."
        },
        {
            src: "/character_turn_around (1).png",
            alt: "Fictional character turn around",
            description: "Character turnaround sheet showing the character from multiple angles. This reference ensures consistency when viewed from different perspectives.Later used for animation"
        }
    ];
    
    const column2Images = [
        {
            src: "/old man.jpg",
            alt: "Final art of the old man",
            description: "Final art of the elderly character."
        },
        {
            src: "/final-art.jpg",
            alt: "Final art of the fictional character", 
            description: "Completed character illustration showing the final design with detailed shading, texturing, and color treatment typical for comics and anime style."
        },
        {
            src: "/metamorphosis assets (1).png",
            alt: "Assets for a video game",
            description: "Game asset collection for 'Metamorphosis', featuring various elements designed for the game environment."
        }
    ];
</script>
<div class="nav-container">
    <PortfolioNav />
</div>
    <div class="container">
        <h2 class="title">Digital Art</h2>
        <div class="gallery">
            <div class="column">
                <div class="picture">
                    {#each column1Images as image}
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
                    {#each column2Images as image}
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
            font-size: 4rem;
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
        }
    </style>