<script>
    import { base } from '$app/paths';
    // import Navigation.svelte from lib folder
    import { Navigation } from "$lib"
</script>



<header>
    <!-- Profile picture icon as homepage link -->
    <a href="{base}/" class="home-link">
        <div class="profile-picture" style="background-image: url('{base}/profilePic.png');"></div></a>
    <Navigation />
</header>

<style>
header {
    position: relative;
    margin: 0;
    display: flex;
    justify-content: space-between;
    padding: 1rem 1rem 1.2rem 1rem;
    margin-left: 1rem;
    margin-right: 1rem;
    align-items: center;
}
/*divider*/
header::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 5px;
    border-radius: 30px;
    background: linear-gradient(to right,#7336b5, #bc82eb, #7336b5);
   
}

.profile-picture {
    display: block;
    width: 80px;
    height: 80px;
    border-radius: 50%;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    overflow: hidden;
    transition: transform 0.3s ease;
}

.home-link {
    text-decoration: none;
    color: inherit;
    display: inline-block;
}
/*profile picture icon gets slightly bigger when hovered*/
.home-link:hover .profile-picture {
    transform: scale(1.1);
}
/*responsive design*/
/*mobile devices*/
@media (max-width: 768px) {
    header {
        text-align: center;
        padding-bottom: 1.2rem;
    }
 
    
    .profile-picture {
        justify-content: left;
        width: 60px;
        height: 60px;
    }
    
    header::after {
        height: 3px;
    }
}
</style>
