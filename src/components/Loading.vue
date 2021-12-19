<template>
    <div v-show="status!=true" class="loading">
        <div class="wave">
            <span style="--i:1">L</span>
            <span style="--i:2">o</span>
            <span style="--i:3">a</span>
            <span style="--i:4">d</span>
            <span style="--i:5">i</span>
            <span style="--i:6">n</span>
            <span style="--i:7">g</span>
            <span style="--i:8">.</span>
            <span style="--i:9">.</span>
            <span style="--i:10">.</span>
        </div>
    </div>
</template>

<script>
export default {
    data:function() {
return {
        status: '',
        };
},
    created(){
        this.status= false;
        setTimeout(()=>{ this.status = true}, 3000);
},
}
</script>

<style scoped>
.loading
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
</style>