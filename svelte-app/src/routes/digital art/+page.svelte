<script>
     import { base } from '$app/paths';
    import { ImageViewer, PortfolioNav } from "$lib";
    //button at the end of the page allowing user to return back to the top without having to scroll
    function scrollToTop() {
        window.scrollTo({
          top: 0,
          behavior: 'smooth'
        });
    }
    
    // Image data with descriptions
    // two columns
    const column1Images = [
        {
            src: `${base}/oldmansketch.png`,
            alt: "Sketches drafts of old man",
            description: "Early concept sketches of an elderly character. These drafts explore different facial features and expressions to capture the essence of age and wisdom."
        },
        {
            src: `${base}/concept-art.jpg`,
            alt: "Concept art for fictional character",
            description: "Character concept art showing various design iterations. These explorations helped establish the final visual direction for this fictional character."
        },
        {
            src: `${base}/character_turn_around (1).png`,
            alt: "Fictional character turn around",
            description: "Character turnaround sheet showing the character from multiple angles. This reference ensures consistency when viewed from different perspectives.Later used for animation"
        }
    ];
    
    const column2Images = [
        {
            src: `${base}/old man.jpg`,
            alt: "Final art of the old man",
            description: "Final art of the elderly character."
        },
        {
            src: `${base}/final-art.jpg`,
            alt: "Final art of the fictional character", 
            description: "Completed character illustration showing the final design with detailed shading, texturing, and color treatment typical for comics and anime style."
        },
        {
            src: `${base}/metamorphosis assets (1).png`,
            alt: "Assets for a video game",
            description: "Game asset collection for 'Metamorphosis', featuring various elements designed for the game environment."
        }
    ];
</script>
<!--import portfolio navigation component-->
<div class="nav-container">
    <PortfolioNav />
</div>

    <div class="container">
        <h1 class="title">Digital Art</h1>
        <!--each image is part of gallery, in one of the columns with ImageViewer imported allowing images to expand and reveal their description-->
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
    <!--button that return to the top of the page-->
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
        /*responsive flexbox gallery*/
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
        /*scroll buttons scales up and changes colour when hovered*/
        .arrow-buttons button:hover{
            transform: scale(1.1);
            background-color: var(--primary-color);
        }
    
    
        @media(max-width: 768px){
            /*only one column for mobile devices*/
            .gallery{
                flex-direction: column;
            }
            .title{
            text-align: center;
            font-size: 2rem;
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