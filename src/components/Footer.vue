<template>
    <footer>
        <ul class="social">
            <li><a href="https://wa.me/message/B2GV4UOOUHSJK1"><img src="@/assets/icons/whats.svg"></a></li>
            <li><a href="https://www.instagram.com/kayosavio/"><img src="@/assets/icons/insta.svg"></a></li>
            <li><a href="https://www.linkedin.com/in/kayo-savio-348892129/"><img src="@/assets/icons/linkedin.svg"></a></li>
        </ul>
    </footer>
</template>

<script>
export default {
    name: 'Footer',
}
</script>

<style scoped>
footer
{
    position: absolute;
    bottom: 30px;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 7;
    transition: 0.6s;
}
.social{
    display: flex;
    flex-direction: row;
}
.social li
{
    list-style: none;
    box-shadow: 2px black;    
    border-radius: 25px;   
}

.social li a
{
    position: relative;
    display: flex;
    right: initial;
    flex-direction: row;
    place-items: center;
    width: 60px;
    height: 60px;
    text-decoration: none;
    margin-left: 30px;   
    border-radius: 40px;
    z-index: 5; 
}

.social li a:hover
{
    background: #1abc9c;
}

.social li a img
{
    max-width: 100%;
}
</style>