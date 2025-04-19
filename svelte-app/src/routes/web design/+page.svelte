<script>
    function scrollToTop() {
        window.scrollTo({
          top: 0,
          behavior: 'smooth'
        });
      }
    </script>
    
    <div class="container">
        <h2 class="title">Web design</h2>
        <p>Team project website focused on movies. In this project done in the second year of my Bachelor's degree I took part in the overall design. Later in the development phase I was in charge of the homepage design, theatre movies pages design and the content suggestions page design.</p>
        <div class="gallery">
            <div class="column">
                <div class="picture">
                    
                    <video 
                        src="/homepage.mp4" 
                        autoplay
                        loop
                        muted
                        preload="metadata"
                        poster="/homepage.jpg"
                        playsinline
                        class="video-element">
                        Your browser does not support the video tag.
                    </video>
                    <img src="/nosignal-homepage.png" alt="website homepage">
                    <img src="/nosignal-movies.png" alt="website page">
                    <img src="/nosignal-contact.png" alt="website page">
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
    
        .picture > img,
        .picture > video {
            width: 100%;
            height: auto;
            object-fit: cover;
            border-radius: 5px;
            transition: transform 0.5s ease, opacity 0.5s ease;
        }
    
        /* Set up hover state for the gallery */
        .gallery:hover .picture img,
        .gallery:hover .picture video {
            opacity: 0.6; /* Reduce opacity of all media */
            transform: scale(0.8); /* Slightly shrink all media */
        }
    
        /* When a specific media is hovered, bring it back to full opacity and scale up */
        .gallery .picture img:hover,
        .gallery .picture video:hover {
            transform: scale(1.1);
            opacity: 1; 
            z-index: 1; 
        }
        
        /* Additional video-specific styles */
        .video-element {
            background-color: var(--primary-color);
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.2);
            cursor: pointer;
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