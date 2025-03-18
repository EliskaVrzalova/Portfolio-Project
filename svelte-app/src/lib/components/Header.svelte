<script>
    // import Navigation.svelte from lib folder
    import { Navigation } from "$lib"
</script>



<header>
    <!-- Logo -->
    <a href="/" class="home-link">
        <div class="profile-picture"></div></a>
    <Navigation />
</header>

<style>
header {
    background-color: var(--primary-color);
    display: flex;
    justify-content: space-between;
    padding: 1rem;
    align-items: center;
    border-radius: 25px;
}

.profile-picture{
    display: block;
    width: 80px;
    height: 80px;
    border-radius: 50%;
    background-image: url('/profilePic.png');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    overflow: hidden;
}

.home-link {
    display: block;
    text-decoration: none;
}

a.home-link:hover .profile-picture {
    transform: scale(1.05);
    transition: transform 0.3s ease;
    box-shadow: 0 0 10px rgba(255,255,255,0.5);
}


@media (max-width: 768px){
    header{
        flex-direction: column;
        text-align: center;
    }
    .profile-picture{
        justify-content: center;
    }
}
</style>