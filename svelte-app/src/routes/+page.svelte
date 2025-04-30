<script>
     import { base } from '$app/paths';
    //form
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
<!--hero image and text-->
<div class="hero-container">
    <div class="text-content">
        <div class="hero-text">
        <h1 >Hello there!</h1>
        <h1 id="my-name">My name is Eliska Vrzalova</h1>
        <p>I am a college student aspiring to be UX/ UI Designer, Concept Artist, and just the most creative version of myself.</p>
    </div>
        <a href="{base}/portfolio" class="portfolio-button-link">
        <div class="portfolio-button">
            <button type="button">Explore my portfolio!</button>
        </div></a>
    </div>
  
    <div class="hero-image-container">
        <img src="{base}/hero.png" alt="homepage hero" id="hero">
    </div>
</div>
<!--divider to separate sections better-->
<div class="divider"></div>
<div class="focus-areas">
    <div class="text-focus-areas">
    <h2>I mainly focus on:</h2>
</div>
<div class="icons-focus-areas">
    <div class="focus-item">
        <img src="{base}/front-end-programming.png" alt="front end programming icon">
        <h3>Front-end Development</h3>
    </div>
    <div class="focus-item">
        <img src="{base}/uiux.png" alt="UI and UX design icon">
        <h3>UI/UX Design</h3>
    </div>
    <div class="focus-item">
        <img src="{base}/website-design.png" alt="Web design icon">
        <h3>Web Design</h3>
    </div>
</div>
</div>
<div class="socials">
    <div class="text-socials">
    <h2>Find me on:</h2>
</div>
<!--social media icons with links, opening in new tabs when clicked-->
<div class="icons-socials">
    <a href="https://www.instagram.com/_evrzlv_/" target="_blank" rel="noopener noreferrer">
    <img src="{base}/instagram.png" alt="instagram logo"></a>
    <a href="https://github.com/EliskaVrzalova" target="_blank" rel="noopener noreferrer">
    <img src="{base}/github.png" alt="Github logo"></a>
    <a href="https://discord.com/users/1332386471621165226" target="_blank" rel="noopener noreferrer">
    <img src="{base}/discord.png" alt="Discord logo"></a>
    <a href="https://x.com/vrzalova_eliska" target="_blank" rel="noopener noreferrer">
    <img src="{base}/twitter.png" alt="X (Twitter) logo"></a>
    <a href="mailto:eliska.vrzalovaa@gmail.com">
    <img src="{base}/gmail-logo.png" alt="G-mail logo"></a>
</div>
</div>
<!--container for the form and the pictures-->
<div class="bottom-container">
<div class="butterflies">
    <img src="{base}/butterflies.png" alt="flock of butterflies">
</div>
<div class="contact-me-grid">
<div class="form-picture">
    <img src="{base}/contactPic.png" alt="Eliska next to the contact form">
</div>
<div class="form-container">
    <form on:submit={handleSubmit} class="contact-form">
        <h2>Get in touch with me right here and right now!</h2>
        <!--full width field takes space of the entire form width making in one input row on one line-->
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
    <!--button that return to the top of the page-->
<div class="arrow-buttons">
    <button class="up" on:click={scrollToTop}>↑</button>
</div>

<!--show this modal if the form is filled out and submitted-->
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
/*rainbow gradient border around the button when its hovered*/
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
/*gradient animation*/
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
    border-radius: 30% 40% 60% 30% / 30% 50% 40% 60%; /*creating uneven blob*/
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
/*floating like animation for the blobs*/
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
    width:200px;
}

.focus-item h3 {
    margin-top: 1rem;
    color: var(--text-color);
    transition: opacity 0.5s ease;
    width: 100%;
    word-wrap: break-word;
    hyphens: auto;
    min-height: 3.6rem; /* Accommodates two lines of text */
    display: flex;
    align-items: center;
    justify-content: center;
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
    opacity: 1 !important; /*must be visible*/
    z-index: 1;
}

.focus-item:hover img {
    transform: scale(1.2) !important; /*must scale up*/
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
        font-size:var(--font-size-base);
        transition: all 0.3s ease;
        box-shadow: 0 2px 5px rgb(157, 45, 198);
    }
    /*if the form field is clicked to type in, it lifts up slightly*/
    input:focus, textarea:focus {
        outline: none;
        transform: translateY(-2px);
    }
    label{
        margin-bottom:0.25rem;
        margin-top:0.25rem;
        font-size: var(--font-size-base);
    }
    .submit-button{
        position:relative;
        text-align: center;
        font-size: var(--font-size-base);
        font-family:"DynaPuff", serif;
        padding:10px 20px 10px 20px;
        border-radius:50px;
        margin-top:0.8rem;
        border:none;
        transition: all .4s ease-in-out;
       background-color: #a779bb;
       overflow: hidden;
    }
    /*submitr button hover effect*/
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
    /*two colum layout 1 colum image 2 colum form*/
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
        width: 300px;
        height: 500px;
        margin-right: -5px; /* Increased negative margin to move image closer to form */
        
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
    /*backgroun picture*/
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
        height: 350px;
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
        padding: 4rem;
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


    /* Responsive Styles */
    @media screen and (max-width: 768px) {
        /* Hero section */
        .hero-container {
            margin-top: 4rem;
            width:100%;
            flex-direction: column;
            height: auto;
            padding: 1rem;
            align-items: center;
        }

        .hero-text p{
        font-size: 1.2rem;
        }

        .text-content {
            padding: 1rem;
            text-align: center;
            order: 2;
        }

        .hero-image-container > img {
           display:none;
        }

        /* Focus areas and socials */
        .focus-areas, .socials {
            width: 90%;
            padding: 1rem;
            margin: 0.5rem auto;
        }
        .focus-areas{
            min-height:auto;
        }

        .icons-focus-areas {
            justify-content: center;
            align-items: center;
            gap: 1.5rem;
        }
        .socials{
            margin-top: 4rem;
            min-height: auto;
        }
        /*horizonatl scrolling through social icons on mobile devices*/
        .icons-socials {
            flex-direction: row;
            flex-wrap: nowrap;
            overflow-x: auto;
            gap: 2rem;
            height: auto;
            margin-top: 1rem;
            justify-content: flex-start;
            -webkit-overflow-scrolling: touch;
            scrollbar-width: none; /* Firefox */
        }
        .icons-socials::-webkit-scrollbar {
            display: none; /* Chrome, Safari, Edge */
        }

        .icons-socials img, .icons-focus-areas img {
            width: 100px;
            height: 100px;
        }

        .text-socials h2 , .text-focus-areas h2 {
            margin-bottom: 0.5rem;
        }
        

        .focus-item h3 {
            margin-top: 0.5rem;
        }


        /* Contact form */
        .contact-me-grid {
            grid-template-columns: 1fr;
            padding: 1rem;
            justify-content: center;
            align-items: center;
            width:100%;
        }

        .form-picture {
            display: none;
        }

        .form-container {
            padding: 0;
        }

        .form-row {
            flex-direction: column;
            gap: 1rem;
        }

     
        .submit-button{
        font-size: 1.2rem;
        padding:5px 10px 5px 10px;
        border-radius:50px;
        width:50%;
        margin: 0.8rem auto;
     
    }


        /* Modal */
        .modal {
            width: 90%;
            height: auto;
        }

        .modal-content {
            padding: 1rem;
        }

        /* Background shapes */
        .shape1 {
    width: 180px;
    height: 180px;
    top: 10%;
    left: 30%;

    }

    .shape2 {
        width: 180px;
        height: 180px;
        z-index: -1;
        top: 60%;
        right: 10%;
    }

    .shape3 {
        width: 210px;
        height: 210px;
        top: 80%;
        left: 10%;
    }

    .shape4 {
        width: 200px;
        height: 200px;
        top: 35%;
        left:20%;
 
    }

        .portfolio-button button {
            padding: 15px 30px;
            font-size: 1rem;
        }

        .butterflies{
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .butterflies > img{
        width:auto;
        height:500px;
        opacity: 0.7;
    }
    }

     /* Tablet styles (between 769px and 1024px) */
     @media screen and (min-width: 769px) and (max-width: 1024px) {
        .hero-container {
           
            margin: -4rem auto 0 auto; /* Negative margin to move it up */
            width: 95%;
            display: flex;
            margin-bottom: 2rem;
            flex-direction: column;
            height: auto;
            padding: 2rem 1rem;
            align-items: center;
            justify-content: center;
        }

        .text-content {
            padding: 1rem;
            text-align: center;
            margin-bottom: 4rem;
           
        }

        .hero-image-container > img {
            display: none;
        }

        .hero-text p {
            font-size: 1.5rem;
        }
        .focus-item h3 {
            width:90%;
        }
        .focus-areas, .socials {
            display:flex;
            justify-content: center;
            align-items: center;
            width: 90%;
            padding: 1rem;
            margin: 0.5rem auto;
            height: auto;
            min-height: auto;
        }

        .focus-areas {
            margin-bottom: 0;
        }

        .socials {
            margin-top: 0;
            width:100%;
        }

        .icons-focus-areas {
            flex-direction: row;
            gap: 1.5rem;
            padding: 0.5rem;
            justify-content: center;
            margin: 0;
            height: auto;
        }

        .icons-socials {
            flex-direction: row;
            flex-wrap: wrap;
            gap: 2rem;
            height: auto;
            margin: 0;
            justify-content: center;
            padding: 0.5rem;
        }

        .icons-socials img, 
        .icons-focus-areas img {
            width: 120px;
            height: 120px;
        }

        .text-socials, 
        .text-focus-areas {
            margin-bottom: 0.5rem;
        }

        .contact-me-grid {
            grid-template-columns: 1fr 1fr;
            padding: 1rem;
            align-items: center;
            justify-content: center;
                }

        .form-picture {
            display: flex;
        }

        .form-picture > img {
            width: 250px;
            height: auto;
        }
   

        .butterflies{
            display: flex;
            justify-content: center;
            align-items: center;
        }
        .butterflies > img{
      width:auto;
      height:800px;
       opacity: 0.7;
    }
    .shape1 {
    width: 250px;
    height: 250px;
    top: 10%;
    left: 10%;

    }

    .shape2 {
        width: 230px;
        height: 230px;
        z-index: -1;
        top: 40%;
        right: 10%;
    }

    .shape3 {
        width: 210px;
        height: 210px;
        top: 50%;
        left: 10%;
    }

    .shape4 {
        width: 250px;
        height: 250px;
        top: 15%;
        right:30%;
        z-index: -1;
 
    }
    }
    </style>
