<script>
    let showModal = false;
    let formData = {
        name: '',
        email: '',
        phone: '',
        rating: '',
        message: ''
    };

    function handleSubmit(event) {
        event.preventDefault();
        // Process form data here
        console.log('Form submitted:', formData);
        showModal = true;
    }

    function closeModal() {
        showModal = false;

        formData = {
            name: '',
            email: '',
            phone: '',
            message: ''
        };
    }

    function scrollToTop() {
        window.scrollTo({
            top: 0,
            behavior: 'smooth'
        });
    }
</script>


<!-- Background floating shapes -->
<div class="background-elements">
    <div class="floating-shape shape1"></div>
    <div class="floating-shape shape2"></div>
    <div class="floating-shape shape3"></div>
    <div class="floating-shape shape4"></div>
</div>

<div class="hero-container">
    <div class="text-content">
        <div class="hero-text">
        <h1 >Hello there!</h1>
        <h1 id="my-name">My name is Eliska Vrzalova</h1>
        <p>I am a college student aspiring to be UX/ UI Designer, Concept Artist, and just the most creative version of myself.</p>
    </div>
        <a href="/portfolio" class="portfolio-button-link">
        <div class="portfolio-button">
            <button type="button">Explore my portfolio!</button>
        </div></a>
    </div>
  
    <div class="hero-image-container">
        <img src="/hero.png" alt="homepage hero image" id="hero">
    </div>
</div>
<div class="divider"></div>
<div class="focus-areas">
    <div class="text-focus-areas">
    <h2>I mainly focus on:</h2>
</div>
<div class="icons-focus-areas">
    <div class="focus-item">
        <img src="/front-end-programming.png" alt="front end programming icon">
        <h3>Front-end Development</h3>
    </div>
    <div class="focus-item">
        <img src="/uiux.png" alt="UI and UX design icon">
        <h3>UI/UX Design</h3>
    </div>
    <div class="focus-item">
        <img src="/website-design.png" alt="Web design icon">
        <h3>Web Design</h3>
    </div>
</div>
</div>
<div class="socials">
    <div class="text-socials">
    <h2>Find me on:</h2>
</div>
<div class="icons-socials">
    <img src="/instagram.png" alt="instagram logo">
    <img src="/github.png" alt="instagram logo">
    <img src="/discord.png" alt="instagram logo">
    <img src="/twitter.png" alt="instagram logo">
    <img src="/gmail-logo.png" alt="instagram logo">
</div>
</div>
<div class="bottom-container">
<div class="butterflies">
    <img src="/butterflies.png" alt="flock of butterflies image">
</div>
<div class="contact-me-grid">
<div class="form-picture">
    <img src="/contactPic.png" alt="picture of Eliska next to the contact form">
</div>
<div class="form-container">
    <form on:submit={handleSubmit} class="contact-form">
        <h2>Get in touch with me right here and right now!</h2>
        
        <div class="form-row">
            <div class="form-field full-width">
                <label for="name">Your Name</label>
                <input type="text" id="name" bind:value={formData.name} placeholder="Enter your full name" required />
            </div>
        </div>
        
        <div class="form-row">
            <div class="form-field">
                <label for="email">Your Email</label>
                <input type="email" id="email" bind:value={formData.email} placeholder="Enter your email" required />
            </div>
            <div class="form-field">
                <label for="phone">Your Phone</label>
                <input type="tel" id="phone" bind:value={formData.phone} placeholder="Enter your phone number" />
            </div>
        </div>
        <div class="form-row">
            <div class="form-field full-width">
                <label for="message">Your Message</label>
                <textarea id="message" bind:value={formData.message} placeholder="Type your message here..." rows="5" required></textarea>
            </div>
        </div>
        
        <div class="form-row">
            <button type="submit" class="submit-button">Submit</button>
        </div>
    </form>
</div>
</div>
</div>
<div class="arrow-buttons">
    <button class="up" on:click={scrollToTop}>↑</button>
</div>


{#if showModal}
<div class="modal">
    <div class="modal-content">
        <h3>Thank you for your message!</h3>
        <p>I will respond as soon as possible</p>
        <button on:click={closeModal} class="close-modal">Close</button>
    </div>
</div>
{/if}
<style>
    .hero-text h1{
        font-size:3rem;
    }
    .hero-text p{
        font-size: 1.8rem;
    }
    #my-name {
        position: relative;
        display: inline-block;
    }
 
   .hero-container{
   width:100vw;
   height:100vh;
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

   .divider {
            height: 5px;
            border-radius: 30px;
            background: linear-gradient(to right,#7336b5, #bc82eb, #7336b5);
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
    top: 25%;
    left: 30%;
    z-index: -1;
    animation-delay: 0s;
    border-radius: 30% 40% 60% 30% / 30% 50% 40% 60%;
}

.shape2 {
    width: 300px;
    height: 300px;
    background: var(--secondary-color);
    top: 70%;
    right: 30%;
    animation-delay: -5s;
    border-radius:  40% 50% 60% 50%;
}

.shape3 {
    width: 250px;
    height: 250px;
    background: var(--secondary-color);
    bottom: 10%;
    left: 10%;
    animation-delay: -10s;
    border-radius: 60% 40% 30% 70% / 60% 30% 70% 40%;
    z-index:-2;
}

.shape4 {
    width: 280px;
    height: 280px;
    background: var(--primary-color);
    top: 20%;
    right: 10%;
    animation-delay: -15s;
    border-radius: 30% 70% 70% 30% / 30% 30% 70% 70%;
}

@keyframes float {
    0%, 100% { transform: translate(0, 0) rotate(0deg); }
    25% { transform: translate(20px, 20px) rotate(5deg); }
    50% { transform: translate(-20px, 40px) rotate(-5deg); }
    75% { transform: translate(-40px, -20px) rotate(2deg); }
}
.socials{
    display: flex;
    flex-direction: column;
    width: 100vw; 
    max-width: 1400px; /* max-width for large screens */
    height:auto;
    min-height: 500px;
    background-color: rgb(255, 255, 255, 0.2);
    border-radius: 30px;
    box-shadow: 0 10px 5px #9d2dc6;
    margin: 0 auto 2rem auto; /* Center horizontally and add bottom margin */
    padding: 1rem 2rem; 
    justify-content:flex-start;
    align-items: center; /* Center content horizontally */
    box-sizing: border-box; 
}
.focus-areas{
    display: flex;
    flex-direction: column;
    width: 100vw; 
    max-width: 1400px; /* max-width for large screens */
    height:auto;
    min-height: 500px;
    margin: 0 auto 2rem auto; /* Center horizontally and add bottom margin */
    padding: 1rem 2rem; 
    justify-content:flex-start;
    align-items: center; /* Center content horizontally */
    box-sizing: border-box; 
}
.text-socials,
 .text-focus-areas{
    text-align: center; 
    font-size:2rem;
    margin-bottom: 2rem;
}
.icons-socials,
 .icons-focus-areas{
    display: flex;
    justify-content: center; /* Center icons horizontally */
    align-items: center; /* Center icons vertically */
    gap: 2rem; 
    width: 100%; 
    padding: 0.5rem 1rem; 
    margin-top:4rem;
    height: 100px; 
    overflow: visible; /* Allow hover effects to extend beyond container */
}
.icons-focus-areas{
    gap:4rem;
}

.focus-item {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    transition: transform 0.5s ease;
}

.focus-item h3 {
    margin-top: 1rem;
    font-size: 1.5rem;
    color: var(--text-color);
    transition: opacity 0.5s ease;
}

.icons-socials img,
 .icons-focus-areas img {
    width: 200px; 
    height: 200px; 
    padding: 0; 
    transition: transform 0.5s ease, opacity 0.5s ease; /* Smooth transitions */
    object-fit: contain; /* Maintain aspect ratio */
}

/* When the parent container is hovered, fade all icons slightly */
/* When the parent container is hovered, fade all icons slightly */
.icons-socials:hover img {
    opacity: 0.6; /* Reduce opacity of all icons */
    transform: scale(0.9); /* Slightly shrink all icons */
}

/* When a specific icon is hovered, bring it back to full opacity and size or larger */
.icons-socials img:hover {
    transform: scale(1.2);
    opacity: 1; 
    z-index: 1; 
}

/* Focus areas hover effects */
.icons-focus-areas:hover .focus-item {
    opacity: 0.6;
}

.icons-focus-areas:hover .focus-item img {
    transform: scale(0.9);
}

.focus-item:hover {
    opacity: 1 !important;
    z-index: 1;
}

.focus-item:hover img {
    transform: scale(1.2) !important;
    opacity: 1;
}




/*form*/

.form-container h2{
    text-align: center;
    grid-area: 1/ 2/ 1 / 2;
    
}
.form-row {
        display: flex;
        justify-content: center;
        gap: 1.5rem;
        width: 100%;
    }

    .form-field {
        flex: 1;
        display: flex;
        flex-direction: column;
        gap: 0.5rem;
    }

    .full-width {
        width: 100%;
    }

    input, textarea {
        padding: 0.8rem 1rem;
        border-radius: 8px;
        border: 1px solid rgb(255, 255, 255, 0.7);
        background: rgb(157, 45, 198,0.2);
        color: white;
        font-size: 1rem;
        transition: all 0.3s ease;
        box-shadow: 0 2px 5px rgb(157, 45, 198);
    }

    input:focus, textarea:focus {
        outline: none;
        transform: translateY(-2px);
    }
    label{
        margin-bottom:0.25rem;
        margin-top:0.25rem;
    }
    .submit-button{
        position:relative;
        text-align: center;
        font-size: 1.5rem;
        font-family:"DynaPuff", serif;
        padding:10px 20px 10px 20px;
        border-radius:50px;
        margin-top:0.8rem;
        border:none;
        transition: all .4s ease-in-out;
       background-color: #a779bb;
       overflow: hidden;
    }

    .submit-button::before {
        content: '';
        position: absolute;
        top: 0;
        left: -100%;
        width: 50%;
        height: 100%;
        background: linear-gradient(
            to right,
            transparent,
            rgba(157, 45, 198, 0.7),
            transparent
        );
        transform: skewX(-25deg);
        transition: left 0.5s ease;
    }

    .submit-button:hover::before {
        left: 150%; /* Move past the button */
        transition: left 0.5s ease;
       
    }
    .submit-button:hover{
        transform: scale(1.1);
    }

    .contact-me-grid{
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 0; /* Remove default gap */
        align-items: center;
        max-width:1400px;
        padding: 2rem;
        width: 100%;
        position: relative;
        align-items: center;
        left: 50%;
        transform: translateX(-50%);
        margin: 0 auto;
    }
    .form-picture {
        display: flex;
        justify-content: flex-end;
        align-items: center;
    }

    .form-picture > img{
        width: 280px;
        height: 450px;
        margin-right: -5px; /* Increased negative margin to move image closer to form */
        margin-bottom: 40px;
    }

    .form-container {
        padding-left: 10px; /* Reduced padding to bring form closer to image */
    }
    .bottom-container{
        position: relative;
        width: 100%;
        display: flex;
        justify-content: center;
    }
    .butterflies {
        position: absolute;
        z-index: -1;
        top: 50%;
        left: 35%;
        transform: translate(-50%, -50%);
    }
    .butterflies > img{
      width:100%;
      height:1000px;
       opacity: 0.7;
    }
    .modal {
        position: fixed;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        width: 500px;
        height: 250px;
        border-radius: 50px;
        background:var(--primary-color);
        border: solid 3px white;
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 10;
    }
    .close-modal {
        align-items: center;
        padding: 0.9rem 2.5rem;
        border: none;
        border-radius: 10px;
        border: 1px solid white;
        background-color: var(--secondary-color);
        color: rgb(255, 255, 255);
        font-size: 1.1rem;
        font-weight: 600;
        cursor: pointer;
        transition: all 0.3s ease;
        box-shadow: 0 5px 15px rgba(255, 255, 255, 0.2);
        position: relative;
        overflow: hidden;
    }

    .close-modal:hover {
        color: var(--secondary-color);
        background-color: #ffffff;
        transform: translateY(-3px) scale(1.2);
        box-shadow: 0 10px 20px rgba(255, 255, 255, 0.2);
    }

    .close-modal:active {
        transform: translateY(1px);
    }

    .modal-content {
        padding: 2rem;
        text-align: center;
        border-radius: 15px;
        max-width: 500px;
        width: 90%;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 1.5rem;
    }

    /*go back to the top fo the page*/
    .arrow-buttons{
        margin-top: 4rem;
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


</style>