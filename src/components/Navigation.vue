<template>
    <div id="navigation" :class="classTest">
        <ul>
            <li data-text="Home"><a href="/">Home</a></li>
            <li data-text="About"><a href="About">About</a></li>
            <li data-text="Projects"><a href="Projects">Projects</a></li>
            <li data-text="Portfolio"><a href="Portfolio">Portfolio</a></li>
            <li data-text="Contact"><a href="Contact">Contact</a></li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'Navigation',
    props: {
        classTest: String
    },
}
</script>

<style scoped>
#navigation
{
    position: fixed;
    top: 0;
    right: -400px;
    width: 400px;
    height: 100vh;
    background: red;
    z-index: 1;
    display: grid;
    place-items: center;
    transition: 0.5s;
}

#navigation.active
{
    right: 0;
}

#navigation ul
{
    position: relative;
    display: flex;
    flex-direction: column;
}

#navigation ul li
{
    list-style: none;
}

#navigation ul li:before
{
    content: attr(data-text);
    position: absolute;
    top: 50%;
    right: 450px;
    transform: translate(-50%, -50%);
    color: white;
    font-size: 8em;
    font-weight: 700;
    pointer-events: none;
    opacity: 0;
    letter-spacing: 20px;
    transition: 0.5s;
    white-space: nowrap;
}

#navigation ul li:hover:before
{
    opacity: 0.5;
    letter-spacing: 0px;
}

#navigation ul li a
{
    position: relative;
    display: inline-block;
    padding: 6px 15px;
    text-decoration: none;
    background:red;
    color: white;
    font-size: 2em;
    font-weight: 600;
    text-transform: uppercase;
    letter-spacing: 2px;
    overflow: hidden;
    transition: 0.5s;
    z-index: 1;
}

#navigation ul:hover li a
{
    opacity: 0.4;
    background-blend-mode: darken;
    color: #aa0000;
}

#navigation ul li a:hover
{
    transform: scale(1.4);
    z-index: 1000;
    background: #aa0000;
    color: white;
    opacity: 1;
}

#navigation ul li a:before
{
    content: '';
    position: absolute;
    top: 0;
    left: -100px;
    width: 80px;
    height: 100%;
    background: linear-gradient(90deg, transparent, rgba(255,255,255,0.8),transparent);
    transform: skew(35deg);
    transition: 0s;
}

#navigation ul li a:hover:before
{
    left: calc(100% + 100px);
    transition: 0.5s;
    transition-delay: 0.2s;
}
</style>
