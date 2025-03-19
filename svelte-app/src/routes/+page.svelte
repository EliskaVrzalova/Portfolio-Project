
<div class="hero-container">
    <div class="text-content">
        <h1 >Hello there!</h1>
        <h1 id="my-name">My name is Eliska Vrzalova</h1>
        <p>I am a college student aspiring to be UX/ UI Designer, Concept Artist, and just the most creative version of myself.</p>
        <div class="portfolio-button">
            <button type="button">Explore my portfolio!</button>
        </div>
    </div>
  
    <div class="hero-image-container">
        <img src="/hero.png" alt="homepage hero image" id="hero">
    </div>
</div>

<style>
    body{
      background-color:rgb(220, 220, 215);
        
    }
    #my-name::before{
        content:'My name is Eliska Vrzalova';
        color: var(--primary-color);
        overflow:hidden;
        position:absolute;
        width:0%;
        transition:all 0.5s;
    }
    
    #my-name:hover::before{
        width:100%;
    }
   .hero-container{
    padding:0;
    margin:0;
    display:flex;
    justify-content: space-between;
    align-items:flex-start;
   }
   .hero-image-container{
     justify-content: flex-start;
     transform: scale(0.7);
     margin-top: -8rem;
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
    background-color: var(--secondary-color);
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

</style>
