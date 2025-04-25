<script>
    import { ImageViewer, PortfolioNav } from "$lib";
    
    function scrollToTop() {
        window.scrollTo({
          top: 0,
          behavior: 'smooth'
        });
    }
    
    // Paintings data with descriptions
    const column1Images = [
        {
            src: "/London.jpg",
            alt: "Painting: London city street",
            description: "London street, Acrylic on canvas."
        },
        {
            src: "/japan.jpg",
            alt: "Painting: abstract autoportrait",
            description: "An abstract self-portrait influenced by Japanese artistic styles."
        }
    ];
    
    const column2Images = [
        {
            src: "/astronaut.jpg",
            alt: "Painting: Astronaut in space",
            description: "A surreal depiction of an astronaut floating in space, Acrylic on wooden desk."
        },
        {
            src: "/jacket.jpg",
            alt: "Painting: abstract portrait of a man",
            description: "An abstract portrait of a man. Acrylic on jacket."
        }
    ];
</script>
<div class="nav-container">
    <PortfolioNav />
</div>
    <div class="container">
        <h1 class="title">Paintings</h1>
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