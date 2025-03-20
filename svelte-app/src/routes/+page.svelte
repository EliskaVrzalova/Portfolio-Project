<!-- Background floating shapes -->
<div class="background-elements">
    <div class="floating-shape shape1"></div>
    <div class="floating-shape shape2"></div>
    <div class="floating-shape shape3"></div>
    <div class="floating-shape shape4"></div>
</div>

<div class="hero-container">
    <div class="text-content">
        <h1 >Hello there!</h1>
        <h1 id="my-name">My name is Eliska Vrzalova</h1>
        <p>I am a college student aspiring to be UX/ UI Designer, Concept Artist, and just the most creative version of myself.</p>
        <a href="/portfolio" class="portfolio-button-link">
        <div class="portfolio-button">
            <button type="button">Explore my portfolio!</button>
        </div></a>
    </div>
  
    <div class="hero-image-container">
        <img src="/hero.png" alt="homepage hero image" id="hero">
    </div>
</div>

<style>
    body{
      background-color:rgb(220, 220, 215);
        
    }
    #my-name {
        position: relative;
        display: inline-block;
    }
    #my-name::before{
        content:'My name is Eliska Vrzalova';
        color: var(--primary-color);
        overflow:hidden;
        position:absolute;
        left: 0;
        top: 0;
        white-space: nowrap;
        width:0%;
        transition:all 0.5s;
    }
    
    #my-name:hover::before{
        width:100%;
    }
   .hero-container{
    padding:1rem;
    margin:0;
    display:flex;
    justify-content: space-between;
    align-items:flex-start;
   }
   .hero-image-container{
     justify-content: flex-start;
     transform: scale(0.7);
     margin-top: -8rem;
     filter: drop-shadow(0px 10px 15px rgba(0, 0, 0, 0.7));
   }
   .text-content{
    padding-left:6rem;
   }
   .portfolio-button {
    position: relative;
    display: inline-block;
    margin-top: 2rem;
   }
   
   .portfolio-button button{
    position: relative;
    padding: 20px 40px;
    border:none;
    border-radius: 50px;
    font-family: "DynaPuff", serif;
    font-size: var(--font-size-base);
    background-color: var(--primary-color);
    color:white;
    cursor:pointer;
    z-index: 1;
    transition: transform 0.3s ease; /*for scaling to be smooth*/
   }
   .portfolio-button button:after {
  content: '>>';
  position: absolute;
  margin-left: 5px;
  transition: 0.5s; /*for opacity trasition when the arrow appears*/
  opacity: 0;

}
.portfolio-button::before {
    content: '';
    position: absolute;
    top: -4px;
    left: -16px;
    right: -16px;
    bottom: -4px;
    background: linear-gradient(45deg, #ff0000, #ff7300, #fffb00, #48ff00, #00ffd5, #002bff, #7a00ff, #ff00c8, #ff0000);
    background-size: 400%;
    border-radius: 50px; /*matches button shape*/
    z-index: 0;
    filter: blur(8px);
    opacity: 0;
    transition: opacity 0.5s ease-in-out;
    animation: animateGlow 20s linear infinite;
}
.portfolio-button:hover::before {
    opacity: 1; /*gradient visible on hover*/
}
.portfolio-button button:hover{
   transform: scale(1.1);
   
}
.portfolio-button button:hover:after {
  opacity: 1;
}

@keyframes animateGlow {
    0% {
        background-position: 0 0;
    }
    50% {
        background-position: 400% 0;
    }
    100% {
        background-position: 0 0;
    }
}

/* Floating background shapes styles */
.background-elements {
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    pointer-events: none;
    z-index: -1;
    overflow: hidden;
}

.floating-shape {
    position: absolute;
    border-radius: 50%;
    opacity: 0.5;
    animation: float 20s infinite ease-in-out;
}

.shape1 {
    width: 300px;
    height: 300px;
    background: var(--primary-color);
    top: 10%;
    left: 30%;
    z-index: -1;
    animation-delay: 0s;
    border-radius: 30% 40% 60% 30% / 30% 50% 40% 60%;
}

.shape2 {
    width: 300px;
    height: 300px;
    background: var(--secondary-color);
    top: 65%;
    right: 25%;
    animation-delay: -5s;
    border-radius:  40% 50% 60% 50%;
}

.shape3 {
    width: 250px;
    height: 250px;
    background: var(--primary-color);
    bottom: 10%;
    left: 10%;
    animation-delay: -10s;
    border-radius: 60% 40% 30% 70% / 60% 30% 70% 40%;
}

.shape4 {
    width: 280px;
    height: 280px;
    background: var(--secondary-color);
    top: 15%;
    right: 15%;
    animation-delay: -15s;
    border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
}

@keyframes float {
    0%, 100% { transform: translate(0, 0) rotate(0deg); }
    25% { transform: translate(20px, 20px) rotate(5deg); }
    50% { transform: translate(-20px, 40px) rotate(-5deg); }
    75% { transform: translate(-40px, -20px) rotate(2deg); }
}

</style>
