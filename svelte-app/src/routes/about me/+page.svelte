<div class="about-me-container">
    <div class="image">
        <img src="/aboutme.png" alt="picture of Eliska">
    </div>
    <div class="text">
        <h2>Who am I?</h2>
        <p>Hi! I'm Eliska, an aspiring designer with interest and passion in UI/ UX, animation, concept art and simply any other design you can think of:). <br>
            I always loved being creative- whether it's through drawing, problem-solving or dealing with challenges. Ever since I was a kid, I had design in my mind wondering and observing what it is and how people interact with it.</p>
            <p>Beyond art and design, I'm very active and adventurous person. I love sports, exploring new places and pushing my limits. I do my best to translate the energy to my designs- i want the to feel dynamic, original and full of life.
                I always look around and seek for inspiration because I myself want to become one for others. <br>
                
                Right now, I'm honing my skills, experimenting with different skills, and pushing myself to grow. This portfolio is a reflection of my ideas, creativity and passion for crafting original design that leave a lasting impact.<br>
                
                I hope you will enjoy the experience this website offers you and feel the message I'm sending you. <br>
                <div class="signature">
                <img src="/eliska.png" alt="Eliska's signature">
            </div>
                
                
    </div>
    <div class="SW-skills">
        <img src="/photoshop.png" alt="photoshop icon">
        <img src="/indesign.png" alt="in design icon">
        <img src="/illustrator.png" alt="adobe illustrator icon">
        <img src="/animate.png" alt="adobe animte icon">
        <img src="visualstudio.png" alt="visual studio icon">
        <img src="/inkscape.png" alt="inkscape icon">
        <img src="/canva.png" alt="canva icon">
        <img src="/figma.png" alt="figma icon">
        <img src="/penpot.png" alt="penpot icon">
    </div>
</div>

<style>
    .about-me-container{
        display:grid;
        grid-template-columns: repeat(2,1fr);
        justify-content: center;
        gap:2rem;
        padding:2rem;
        margin-left:10%;
        margin-right: 10%;
    }
    .image >img{
        width:auto;
        height:600px;
        object-fit: contain;
    }
    .image{
        width: fit-content;
        grid-area: 1/1/2/2;
        width: 100%;
        padding:2rem;
        display: flex;
        justify-content:center;
        padding-right: 0; /* Remove any default padding */
    }
    .text{
        width: 100%; 
        max-width: 1400px;
        grid-area: 1/2/3/2;
        background-color: rgb(255, 255, 255,0.2);
        padding:2rem;
        border-radius: 30px;
        font-size: 1rem;
    }
    .signature >img{
        width:auto;
        height:150px;
    }
    .text h2{
        font-size: 3rem;
    }
  
    .SW-skills{
        grid-area: 2/1/2/1;
        display: flex;
        flex-wrap: wrap; /* Makes icons wrap to next line */
        gap: 1rem;
        justify-content:flex-end;
        margin-left:3rem;
        align-items: center;
        width:90%;
        padding-right: 2rem; /* Add padding to prevent icons from touching grid edge */
        margin-top:-2rem;
        border:solid 1px white;
        border-radius: 30px;
        padding-top:1rem;
        padding-bottom: 1rem;
        
    }
    .SW-skills >img{
       width: auto;
        height:65px;
        padding:0.2rem;
        transition: transform 0.3s ease; /* Smooth transition for hover effect */
    }
    .SW-skills > img:hover {
        transform: scale(1.1); /* Adds hover effect */
    }
</style>