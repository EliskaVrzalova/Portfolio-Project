<div class="cv-grid">
	<div class="left-col"></div>
    <div class="image">
        <img src="/cv-me.png" alt="picture of eliska on CV">
    </div>
	<div class="info">
        <h2>Eliska Vrzalova</h2>
        <p>student<br>
        Ireland, Carlow<br>
        <br>
        eliska.vrzalovaa@gmail.com<br>
        c00301768@setu.ie<br>
        <br>
        +420 777 021 208<br>
        +353 87 487 5520</p><br>
    
    </div>
	<div class="skills">
        <h2>skills</h2>
        <p>Vector based softwares<br>
        Bitmap based softwares<br>
        UI/UX Design<br>
        Prototyping<br>
        Programming<br>
        Web development<br>
        Sketching<br>
        Creativity<br>
        Adaptability<br>
        Ability to multitask<br>
        Fast Learner<br>
        Microsoft office<br>
        Team work<br>
        Communication Skills</p><br>
    </div>
	<div class="references">
        <h2>references</h2>
        <p>Emílie Vrzalová from pension and restaurant Falk <br>
        +420 731 567 129 <br>
        <br>
        Petr Matouch from EkviTech, Ltd. <br>
        matouch@ekvitech.cz <br>
        +420 776 732 282 <br>
        <br>
        František Bittner from MAKRO Cash and Carry <br>
        Ltd. st08.cs@makro.cz <br>
        +420 475 302 518</p><br>
    
    </div>
	<div class="profile">
        <h2>profile</h2>
        <p>Motivated and communicative international student who is eager to learn new 
            things and meet new people. My employment history is very diverse. Each of 
            my previous employers was satisfied with my work and performance.</p>
    </div>
	<div class="education">
        <h2>education</h2>
        <h3>South East Technological University, Carlow</h3>
            <p>SEPTEMBER 2023 — PRESENT <br>
            Computing in Interactive Digital Art and Design</p><br>
            
          <h3> Business Academy and the Language School with the right of the state
           examination, Ústí nad Labem</h3>
            <p>SEPTEMBER 2019 — JUNE 2023 <br>
            Graduated with distinction <br>
            Graduation subjects: Czech, English, Accounting, Economics, Social Sciences</p><br>
    
    </div>
	<div class="employment-history">
        <h2>employment-history</h2>
        <h3>Ski and snowboard instructor at Ski school Telnice, Telnice, Czech 
        Republic</h3>
        <p>NOVEMBER 2021 — MARCH 2022 <br>
        Taught children and adults how to ski and snowboard in Czech, 
        English and German language.</p><br>
         
        <h3>Internship at EkviTech, Ltd., Ústí nad Labem, Czech Repulic</h3>
         <p>MAY 2023 — MAY 2023 <br>
         Helping with administration work. <br>
         Gaining knowledge about contracts, accounting and the company 
        organization and leadership.</p> <br>
         
        <h3>Cleaning maid at pension and restaurant Falk, Hrensko, Czech 
        Republic</h3>
        <p> JULY 2022 — JULY 2023<br>
         Preparing apartments for guests, all kinds of cleaning task.</p><br>
         
        <h3>Salesperson at Kebab Maidum, Ústí nad Labem, Czech Republic</h3>
         <p>JULY 2023 — JULY 2023<br>
         Short-term<br>
         Familiar with kitchen tasks, manipulation with food and serving, 
        using cash register and selling.</p><br>
         
        <h3>Employee - Goods Department at MAKRO Cash & Carry, Ltd., Ústí 
        nad Labem </h3>
         <p>AUGUST 2023 — AUGUST 2023 <br>
         Unpacking and displaying goods in a wholesale store and operating 
        with pallet jack.</p><br>
         
        <h3>Instore worker- Domino's Pizza, Inc., Carlow, Ireland</h3>
         <p>AUGUST 2024- PRESENT<br>
         Handling all instore tasks such as food manipulation and customer 
        service.</p><br>
    </div>
	
</div>
<style>
    .cv-grid {
	display: grid;
	grid-template-columns: repeat(6, 1fr);
	gap: 0px 20px;
	width: 100%;
	height: 100%;
}
    .cv-grid > div {
    padding: 0.5rem 2rem;
}
.cv-grid > div h3{

    border-bottom: 3px solid var(--primary-color);
}
.cv-grid > div p{
    font-size:var(--font-size-base);
}

.info {
	grid-area: 1 / 1 / 1 / 2;
    margin-top: 20px;
}
.skills {
	grid-area: 3 / 1 / 5 / 3;
    
}
.skills p{
    line-height: 2.5rem;
}
.references {
	grid-area: 5 / 1 / 7 / 3;
    border-bottom-left-radius: 30px;
    border-bottom-right-radius: 30px;
}
.profile {
	grid-area: 2 / 1 / 3 / 3;
    background-color: rgb(255, 255, 255, 0.2);
   
}
.education {
	grid-area: 1 / 3 / 2 / 7;
    margin-top: 20px;
}
.employment-history {
	grid-area: 2 / 3 / 7 / 7;

}
.image {
    display:flex;
    justify-content: flex-end;
	grid-area: 1 / 1 / 2 / 3;
    background-color: var(--primary-color,0.7);
    border-top-left-radius: 30px;
    border-top-right-radius: 30px;
	
}
.image > img{
    width:auto;
    height:530px;
    position:relative;
    top:0;
    left:10%;
}
.left-col {
	grid-area: 1 / 1 / 9 / 3;
	background-color: var(--secondary-color);
    opacity:0.7;
    z-index: -1;
    border-radius: 30px;
   
}
    /*mobile*/
    @media(max-width: 768px){
        .cv-grid {
	display: flex;
	flex-direction: column;
	gap: 0;
	justify-content: center;
    }
    .cv-grid > div {
    padding: 0.3rem 1rem;
    }
    .cv-grid > div p{
        font-size: 1.1rem;
    }
.cv-grid > div h3{
    border-bottom: 2px solid var(--primary-color);
    }
    .image > img{
display: none;
}
.image {
    display: none;
    
}
.skills p{
    line-height: 2.2rem;
}
.references{
    order:1;
}
.info, .skills{
    background-color: var(--primary-color);
}
.info{
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
}
.profile{
    border-bottom-left-radius: 10px;
    border-bottom-right-radius: 10px;
    background-color: var(--secondary-color);
}
.left-col {
    display: none; /* Hide the left column completely */
}
    }
/*tablet devices*/
    @media (min-width: 769px) and (max-width: 1024px) {
        .cv-grid{
            display:grid;
            grid-template-columns: repeat(2,1fr);
        }
        .cv-grid > div {
    padding: 0.5rem 1rem;
    }
    .cv-grid > div p{
        font-size:var(--font-size-base);
    }
.cv-grid > div h3{

    border-bottom: 3px solid var(--primary-color);
    }
    .image > img{
    width:auto;
    height:500px;
    margin-top:2rem;
}
.info p{
    color:rgb(192, 192, 192);
}
.image {
    display: flex;
    justify-content: flex-end; 
    margin: 0 auto; /* Center the container */
    width: 100%; 
    z-index: -1;
}
    }

</style>
