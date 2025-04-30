<script>
    import { base } from '$app/paths';
    import { ImageViewer, PortfolioNav } from "$lib";
    
    function scrollToTop() {
        window.scrollTo({
          top: 0,
          behavior: 'smooth'
        });
    }
    
    // Tattoo design images with descriptions
    const column1Images = [
        {
            src: `${base}/kenjaku.JPG`,
            alt: "Tattoo design: Kenjaku, Jujutsu Kaisen",
            description: "Custom tattoo design featuring Kenjaku from Jujutsu Kaisen. This design captures the character's sinister essence through detailed linework and shading techniques ideal for body art."
        },
        {
            src: `${base}/dragon.png`,
            alt: "Tattoo design from first draft to final design on body: japanese dragon",
            description: "Evolution of a Japanese dragon tattoo design from initial concept to final application. This traditional-inspired piece showcases the dynamic flow and scale patterns characteristic of Eastern dragon mythology."
        }
    ];
    
    const column2Images = [
        {
            src: `${base}/fox.JPG`,
            alt: "Tattoo design: japanese fox Kitsune",
            description: "Japanese Kitsune (fox) tattoo design blending traditional and contemporary styles. The mythological fox spirit is depicted with flowing nine tails and mystical elements representing wisdom and cunning."
        },
        {
            src: `${base}/choso (1).png`,
            alt: "Multiple design drafts: Choso, Jujutsu Kaisen",
            description: "Exploratory drafts for a Choso (Jujutsu Kaisen) tattoo design. These sketches experiment with different poses and compositional elements to capture the character's unique abilities and personality."
        },
        {
            src: `${base}/choso (2).JPG`,
            alt: "Tattoo design: Choso, Jujutsu Kaisen",
            description: "Finalized tattoo design of Choso from Jujutsu Kaisen. This refined illustration features clean linework and balanced composition optimized for skin application while preserving the character's distinct features."
        }
    ];
</script>
<div class="nav-container">
     <!--import portfolio navigation component-->
    <PortfolioNav />
</div>
<div class="container">
    <h1 class="title">Tattoo Design</h1>
    <div class="gallery">
        <!--two images in column1 and three images in column2-->
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
        /*one column layout for mobile devices*/
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