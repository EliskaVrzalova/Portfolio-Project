<script>
    function scrollToTop() {
        window.scrollTo({
          top: 0,
          behavior: 'smooth'
        });
      }
    </script>
    
    <div class="container">
        <h2 class="title">Digital Art</h2>
        <div class="gallery">
            <div class="column">
                <div class="picture">
                    <img src="/oldmansketch.png" alt="Sketches drafts of old man">
                    <img src="/concept-art.jpg" alt="Concept art for fictional character">
                    <img src="/character_turn_around (1).png" alt="Fictional character turn around">
                </div>
            </div>
            <div class="column">
                <div class="picture">
                    <img src="/old man.jpg" alt="Final art of the old man">
                    <img src="/final-art.jpg" alt="Final art of the fictional character">
                    <img src="/metamorphosis assets (1).png" alt="Assets for a videogame">
                </div>
            </div>
        </div>
    </div>
    <div class="arrow-buttons">
        <button class="up" on:click={scrollToTop()}>↑</button>
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
    
        .picture >img{
            width:100%;
            height: auto;
            object-fit: cover;
            border-radius: 5px;
            transition: transform 0.5s ease, opacity 0.5s ease;
        }
    
        /* Set up hover state for the gallery */
        .gallery:hover .picture img {
            opacity: 0.6; /* Reduce opacity of all images */
            transform: scale(0.8); /* Slightly shrink all images */
        }
    
        /* When a specific image is hovered, bring it back to full opacity and scale up */
        .gallery .picture img:hover {
            transform: scale(1.1);
            opacity: 1; 
            z-index: 1; 
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