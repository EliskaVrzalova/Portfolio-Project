<script>
    import { ImageViewer, VideoViewer, PortfolioNav } from "$lib";
    
    function scrollToTop() {
        window.scrollTo({
          top: 0,
          behavior: 'smooth'
        });
    }
    
    // Website content organized by sections
    const videoContent = {
        src: "/homepage.mp4",
        poster: "/homepage.jpg",
        alt: "Website homepage interaction video",
        description: "Interactive demonstration of the movie website homepage. This video showcases the responsive navigation, and dynamic content that creates an engaging user experience."
    };
    
    const websiteScreenshots = [
        {
            src: "/nosignal-homepage.png",
            alt: "NoSignal website homepage",
            description: "Homepage design for the No Signal Media website. The layout features a clean, dark aesthetic with high-contrast elements to highlight featured content and improve readability. The navigation system provides intuitive access to all site sections."
        },
        {
            src: "/nosignal-movies.png",
            alt: "NoSignal movies listing page",
            description: "Theatre movies listing page showcasing the grid layout of film selections. Each card displays key information including release date, rating, and genre tags."
        },
        {
            src: "/nosignal-contact.png",
            alt: "NoSignal contact and suggestions page",
            description: "Content suggestions and contact page, featuring an interactive form for user feedback and movie recommendations. The design maintains consistency with the site's overall aesthetic while providing clear input fields and submission controls."
        }
    ];
</script>
<div class="nav-container">
    <PortfolioNav />
</div>
    <div class="container">
        <h2 class="title">Web Design</h2>
        <h3 class="second-title">Team project: website focused on movies</h3>
        <p>In this project done in the second year of my Bachelor's degree I took part in the overall design. Later in the development phase I was in charge of the homepage design, theatre movies pages design and the content suggestions page design.</p>
        
        <div class="gallery">
            <div class="column">
                <div class="video-wrapper">
                    <VideoViewer 
                        src={videoContent.src}
                        poster={videoContent.poster}
                        alt={videoContent.alt}
                        description={videoContent.description}
                    />
                </div>
                
                <div class="picture">
                    {#each websiteScreenshots as image}
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
        p{
            text-align: center;
            margin-bottom: 4rem;
            font-size: 1.5rem;
            max-width: 900px;
            margin-left: auto;
            margin-right: auto;
            line-height: 1.6;
        }
        .second-title{
            text-align: center;
            font-size: 2.2rem;
            color: var(--primary-color);
            margin: 0;
        }
        .gallery{
            display:flex;
            gap: 20px;
        }
        
        .column{
            display:flex;
            flex-direction: column;
            gap:20px;
            flex: 1;
        }
        
        
        .picture {
            display: flex;
            flex-direction: column;
            width: 100%;
            gap: 20px;
        }
        
        .image-wrapper,
        .video-wrapper {
            width: 100%;
            margin-bottom: 10px;
            border-radius: 5px;
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