<template>
    <div id="portifolio">
        <section :class="banner" id="sect"> 
        <header>
            <a href="#" class="logo">Kayo</a>
            <div id="toggle" @click="muda"></div>
        </header>
        <div class="content">
            <h2>Portfolio<br>I'm <span>Kayo Sávio</span></h2>
            <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Placeat ducimus accusamus
                 ad tempore aut consectetur cumque impedit provident soluta amet sint in earum porro,
                  doloribus deleniti quos excepturi perspiciatis. Iusto.</p>         
            <a href="#">Know More</a>
            <div class="share"><svg id="Camada_1" data-name="Camada 1" xmlns="http://www.w3.org/2000/svg" viewBox="-5 -1 45 40">
                <path d="M17,24.49,32,12.26,17,0V7.62S11.56,9,8.57,11.34C6.64,12.87,0,16.34,0,32c0,0,4-15.1,17-15.1Z"/></svg>
            </div>
        </div>
        </section>
        <Navigation :class="active"/>
        <Footer/>
    </div>
</template>

<script>
import Footer from "../components/Footer";
import Navigation from "../components/Navigation";

export default{
    data() {
    return {
        banner: 'banner',
        active: '',
    };
},
    methods:{
        muda(){
            if(this.banner != 'banner active'){
                this.banner = 'banner active';
                this.active = 'active';
                }
            else{
                this.banner = 'banner';
                this.active = '';          
                } 
        }
},
    name: 'Home',
    components: {
    Footer,
    Navigation,
  },
}
</script>

<style scoped>
* 
{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: 'Poppins', sans-serif;
}

body 
{
    min-height: 100vh;
    margin: 0px;
}

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

header 
{
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    padding: 40px 100px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    z-index: 8;
    transition: 0.6s;
}

header #toggle 
{
    position: relative;
    width: 30px;
    height: 30px;
    cursor: pointer;
}

header #toggle::before 
{
    content: '';
    position: absolute;
    top: 7px;
    width: 100%;
    height: 2px;
    background: white;
}

header #toggle::after 
{
    content: '';
    position: absolute;
    bottom: 7px;
    width: 100%;
    height: 2px;
    background: white;
}

.new
{
    position: absolute;
    width: 100%;
    min-height: 100vh;
    padding: 100px;
    background: url('../assets/desing.jpg');
    background-size: cover;
    display: flex;
    align-items: center;
    justify-content: center;
    opacity: .9;
    z-index: 9;
}

.wave
{
    -webkit-box-reflect: below -84px linear-gradient(transparent, rgba(0,0,0,0.2));
    display: flex;
    justify-content: center;
    align-items: center;
    position: relative;
    z-index: 10;
}

.wave span
{
    position: relative;
    display: inline-block;
    color: white;
    font-size: 5em;
    text-transform: uppercase;
    animation: animate 1s ease-in-out infinite;
    animation-delay: calc(0.1s * var(--i));
}

@keyframes animate
{
    0%
    {
        transform: translateY(0px);
    }
    20%
    {
        transform: translateY(-20px);
    }
    40%, 100%
    {
        transform: translateY(0px);
    }
}

.banner.active header #toggle::before
{
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%) rotate(45deg);
}

.banner.active header #toggle::after
{
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%) rotate(-45deg);
}

.banner
{
    position: relative;
    width: 100%;
    min-height: 100vh;
    padding: 100px;
    background: url('../assets/desing.jpg');
    background-size: cover;
    display: flex;
    align-items: center;
    transition: 0.5s;
    z-index: 0;
}

.banner.active
{
    transform: translateX(-400px);
}

.content
{
    max-width: 600px;
}

.content h2
{
    color: white;
    font-size: 2.5em;
}

.content h2 span
{
    color: red;
    font-size: 1.2em;
}

.content p
{
    font-size: 1.2em;
    color: white;
    font-weight: 300;
}

.content a{
    position: relative;
    display: inline-block;
    text-decoration: none;
    margin-top: 20px;
    background: transparent;
    border: 1px solid white;
    color: white;
    padding: 10px 30px;
    text-decoration: none;
    font-size: 1.2em;
    font-weight: 500;
}

.content a:hover{
    border: none;
    background: red;
    border: 1px solid red;
    color: white;
    padding: 10px 30px;
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
    background: red;
}

.social li a img
{
    max-width: 100%;
}

header .logo 
{   
    position: relative;
    color: white;
    font-weight: 700;
    text-decoration: none;
    font-size: 2em;
    text-transform: uppercase;
    letter-spacing: 2px;
    z-index: 0;
}

.content .share
{
    margin-top: 20px;
    width: 50px;
    stroke-dasharray: 115;
    stroke-dashoffset: 0;
}

.content .share path
{
    fill: transparent;
    stroke-width: 1.5;
    stroke: red;

}

.content .share:hover path
{
    animation: animate-share 1.5s linear forwards
}

@keyframes animate-share
{
    0%
    {
        stroke-dashoffset: 0;
    }
    40%
    {
        stroke-dashoffset: 115;
    }
    80%
    {
        stroke-dashoffset: 230;
        fill: transparent;
    }
    100%
    {
        stroke-dashoffset: 230;
        fill: red;
    }
}

@media(max-width: 767px)
{
    header
    {
        padding: 20px 50px;
    }
    .banner
    {
        padding: 100px 50px 150px;
    }
    .banner h2
    {   
        justify-content: baseline;
        font-size: 1.8em;
    }
    .banner .content p,
    .banner .content a
    {
        font-size: 1em;
    }
    .banner.active
    {
        transform: translateX(-250px);
    }
    
    .social
    {
        position: absolute;
        bottom: 50px;
        display: flex;
        right: initial;
        flex-direction: row;
    }
    .social li a
    {
        margin: initial;
        margin-right: 10px;
    }
}
</style>