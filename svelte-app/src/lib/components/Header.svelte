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
    border-bottom: 2px groove rgb(0, 0, 0);
    margin:0;
    display: flex;
    justify-content: space-between;
    padding: 1rem;
    margin-left: 1rem;
    margin-right: 1rem;
    align-items: center;
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
    box-shadow: 0 0 10px rgb(115, 54, 181, 0.9);
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