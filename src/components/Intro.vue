<template>
    <div class="intro">
            <div class="bg-img profile"><img src="../assets/profile-removebg-preview.png" alt=""></div>
            <div class="bg-img splash"></div>
            <div class="text">
                <h2 class="english" v-show="this.english">We Design & Build Creative Products</h2>
                <h2 class="arabic" v-show="this.arabic">أنا أصمم وأبني منتجات إبداعية</h2>
                <button class="main-btn clickable english" v-show="this.english">Get in touch</button>
                <button class="main-btn clickable arabic" v-show="this.arabic">تواصل معي</button>
            </div>
            <a href="#about" class="scroll clickable main-heading">
                <p class="english" v-show="this.english">scroll</p>
                <p class="arabic" v-show="this.arabic">إلى الأسفل</p>
            </a>
            <div class="links main-heading">
                <ul>
                    <li class="clickable"><a href="#"><font-awesome-icon icon="fa-brands fa-facebook-f" /></a></li>
                    <li class="clickable"><a href="#"><font-awesome-icon icon="fa-brands fa-twitter" /></a></li>
                    <li class="clickable"><a href="#"><font-awesome-icon icon="fa-brands fa-linkedin-in" /></a></li>
                </ul>
            </div>
    </div>
</template>

<script>

import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
// import { faCaretDown } from '@fortawesome/free-solid-svg-icons'
    export default {
        name:"Intro",
        props:["english","arabic"],
        components:{
            FontAwesomeIcon
        },
        mounted(){
            document.querySelector(".intro").onmouseover = () => {
                document.querySelector(".intro").onmousemove = (e) => {
                    document.querySelectorAll(".intro .bg-img").forEach((img) => {
                        img.style.cssText = `
                            transform: scale(1.1) translate(calc(-50% + (${(e.clientX) / 30}px)),calc(-50% + (${(e.clientY) / 30}px)));
                        `
                    })
                }
            }
            document.querySelector(".intro").onmouseleave = () => {
                    document.querySelectorAll(".intro .bg-img").forEach((img) => {
                        img.style.cssText = `
                            transform: scale(1) translate(-50%,-50%);
                        `
                    })
            }
        }
    }
</script>

<style scoped>
.intro{
    min-height: 100vh;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
}
.intro > *:not(.text){
    position: absolute;
}
.intro .bg-img{
    left: 50%;
    top: 50%;
    transform: translate(-50%,-50%);
    display: flex;
    align-items: center;
    justify-content: center;
    transition: var(--main-transition);
}

.intro .bg-img.profile{
    z-index: 2;
}
.intro .bg-img.profile img{
    width: 600px;
}
.intro .bg-img.splash{
    z-index: 1;
    width: 500px;
    height: 500px;
    border-radius: 50%;
    background-image: var(--main-gradient);
}
.intro .text{
    text-align: center;
    width: 500px;
    margin-left: auto;
    margin-right: auto;
    padding-top: 200px;
    z-index: 4;
}
.intro .text h2{
    font-size: 50px;
    margin-bottom: 30px;
    text-shadow: 0px 0px 5px #888;
}
.intro .scroll{
    right: 100px;
    bottom: 100px;
}
.intro .links{
    left: 100px;
    bottom: 100px;
}
.intro .links::before{
  transform: translate(250%,-50%);
}
.intro .links ul{
    transform: rotateZ(-90deg);
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 5px;
    font-size: 20px;
}
.intro .links ul a{
    color: var(--sec-text-color);
    transition: var(--main-transition);
}
.intro .links ul a:hover{
    color: var(--text-color);
}
@media (max-width:992px) {
    .intro .bg-img.splash{
        width: 300px;
        height: 300px;
    }
    .intro .text{
        padding-top: 300px;
        padding-left: 30px;
        padding-right: 30px;
    }
    .intro .text h2{
        font-size: 30px;
    }
    .intro .text .main-btn{
        font-size: 14px;
    }
}
@media (max-width:767px) {
    .intro .bg-img{
        left: 50%;
        top: 50%;
        transform: translate(-50%,-100%);
    }
    .intro .bg-img.splash{
        width: 200px;
        height: 200px;
    }
    .intro .links,
    .intro .scroll{
        display: none;
    }
}
</style>