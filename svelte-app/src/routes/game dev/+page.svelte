<script>
    import { base } from '$app/paths';
    import { ImageViewer, VideoViewer, PortfolioNav } from "$lib";
    
    function scrollToTop() {
        window.scrollTo({
          top: 0,
          behavior: 'smooth'
        });
    }
    
    // Game development projects
    const gameProjects = [
        {
            title: "Candyland Adventure",
            description: "Second year tudent project- great practice for me to familiarize myself with JavaScript",
            video: {
                src: `${base}/candyland.mov`,
                poster: `${base}/candyland-poster.jpg`,
                alt: "Candyland Adventure gameplay footage",
                description: "Gameplay demonstration showcasing player movement, environmental interactions, and the candy-themed map design. The game features assest I created."
            }
        },
        {
            title: "Kafka's Metamorphosis",
            description: "An experimental narrative game inspired by Franz Kafka's novella. This project was done in the first year of my degree course in a team. For this project I took the role of concept artist and designer",
            video: {
                src: `${base}/kafka.mp4`,
                poster: `${base}/kafka-poster.jpg`,
                alt: "Kafka's Metamorphosis game footage",
                description: "Metamorphosis gameplay which together with the dark aesthetics to Franz Kafka's story. "
            }
        },
        {
            title: "Space Shooter Arcade",
            description: "A retro-inspired pixel art space shooter created with custom sprite work and classic arcade gameplay mechanics. My final first year project.",
            image: {
                src: `${base}/SpaceShooter.jpg`,
                alt: "Pixel art space shooter arcade game",
                description: "Instruction screen for the space shooter game."
            }
        }
    ];
</script>
<div class="nav-container">
    <!--import portfolio navigation component-->
    <PortfolioNav />
</div>
    <div class="container">
        <h1 class="title">Game Development</h1>
        
        <div class="gallery">
            <div class="column">
                <!-- First column: Candyland Adventure -->
                <div class="project-card">
                    <h3 class="project-title">{gameProjects[0].title}</h3>
                    <p class="project-description">{gameProjects[0].description}</p>
                    
                    <div class="media-container">
                        <!--manually renders all the data from the first([0]) project in the gameProjects array-->
                        {#if gameProjects[0].video}
                            <VideoViewer 
                                src={gameProjects[0].video.src}
                                poster={gameProjects[0].video.poster}
                                alt={gameProjects[0].video.alt}
                                description={gameProjects[0].video.description}
                            />
                        {:else if gameProjects[0].image}
                            <ImageViewer 
                                src={gameProjects[0].image.src}
                                alt={gameProjects[0].image.alt}
                                description={gameProjects[0].image.description}
                            />
                        {/if}
                    </div>
                </div>
            </div>
            
            <div class="column">
                <!-- Second column: Kafka and Space Shooter -->
                {#each gameProjects.slice(1) as project} <!--.slice(1) excludes the first project so Candyland is not taken into account-->
                    <div class="project-card">
                        <h3 class="project-title">{project.title}</h3>
                        <p class="project-description">{project.description}</p>
                        <!--when checked for video Kafka game is rendered. when for image Space Shooter is rendered-->
                        <div class="media-container">
                            {#if project.video}
                                <VideoViewer 
                                    src={project.video.src}
                                    poster={project.video.poster}
                                    alt={project.video.alt}
                                    description={project.video.description}
                                />
                            {:else if project.image}
                                <ImageViewer 
                                    src={project.image.src}
                                    alt={project.image.alt}
                                    description={project.image.description}
                                />
                            {/if}
                        </div>
                    </div>
                {/each}
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
            margin-bottom: 2rem;
            text-align: center;
        }
        
        
        .gallery {
            display: flex;
            gap: 20px;
        }
        
        .column {
            display: flex;
            flex-direction: column;
            gap: 20px;
            flex: 1;
        }
        
        .project-card {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
            margin-bottom: 20px;
        }
        
        .project-title {
            color: var(--primary-color);
            margin: 0;
        }
        
        .project-description {
            font-size: var(--font-size-base);
            line-height: 1.6;
            margin: 0 0 1rem;
        }
        
        .media-container {
            width: 100%;
            border-radius: 8px;
            overflow: hidden;
        }
        
        .arrow-buttons {
            margin-top: 4rem;
            position: relative;
            text-align: center;
            width: 100%;
            bottom: 30px;
        }
        
        .arrow-buttons button{
            width:50px;
            height:45px;
            border-radius: 20px;
            border:none;
            margin: 0 5px;
            transition: 0.3s;
            cursor: pointer;
        }
    
        .arrow-buttons button:hover{
            transform: scale(1.1);
            background-color: var(--primary-color);
            color: white;
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
            .project-title {
                text-align: center;
            }
            .project-description{
                text-align: center;
            }
        }

    </style>
