<script>
    function scrollToTop() {
        window.scrollTo({
          top: 0,
          behavior: 'smooth'
        });
      }
    </script>
    
    <div class="container">
        <h2 class="title">Game Development</h2>
        <div class="gallery">
            <div class="column">
                <div class="picture">
                    <video 
                        src="/candyland.mov" 
                        autoplay
                        loop
                        muted
                        preload="metadata"
                        poster="/candyland-poster.jpg"
                        playsinline
                        class="video-element">
                        Your browser does not support the video tag.
                    </video>
                </div>
            </div>
            <div class="column">
                <div class="picture">
                    <video 
                        src="/kafka.mp4" 
                        autoplay
                        loop
                        muted
                        preload="metadata"
                        poster="/kafka-poster.jpg"
                        playsinline
                        class="video-element">
                        Your browser does not support the video tag.
                    </video>
                    <img src="/SpaceShooter.jpg" alt="Pixel art space shooter arcade game">
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