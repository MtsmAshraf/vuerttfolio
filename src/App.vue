<template>
  <div class="app">
    <div class="inner cursor"></div>
    <div class="outer cursor"></div>
    <div class="loader starter">
      <div class="content">
        <div class="logo english" v-if="this.english">Moatasim</div>
        <div class="logo arabic" v-if="this.arabic">معتصم</div>
        <div class="loading-bar"><span></span></div>
      </div>
    </div>
    <a href="#home" class="to-top clickable">
      <svg xmlns="http://www.w3.org/2000/svg" version="1.1" width="160px" height="160px">
        <defs>
            <linearGradient id="GradientColor">
              <stop offset="0%" stop-color="#e91e63" />
              <stop offset="100%" stop-color="#673ab7" />
            </linearGradient>
        </defs>
        <circle cx="20" cy="20" r="20" stroke-linecap="round" />
      </svg>
    <div class="arrow-to-top"><font-awesome-icon icon="fa-solid fa-arrow-up" class="to-top-icon" /></div>
    </a>
    <HeaderComponent class="header" @changelanguagetoarabic="arabic = $event" @changelanguagetoenglish="english = $event"></HeaderComponent>
    <IntroComponent :english="english" :arabic="arabic" id="home"></IntroComponent>
    <AboutSliderComponent :english="english" :arabic="arabic" class="about-slider"></AboutSliderComponent>
    <StatsComponent :english="english" :arabic="arabic"></StatsComponent>
    <AboutComponent :english="english" :arabic="arabic" id="about"></AboutComponent>
    <SkillsComponent :english="english" :arabic="arabic" id="skills"></SkillsComponent>
    <ExperienceComponent :english="english" :arabic="arabic"></ExperienceComponent>
    <WorkComponent :english="english" :arabic="arabic" id="portfolio"></WorkComponent>
    <TestimonialsComponent :english="english" :arabic="arabic" style="display:none"></TestimonialsComponent>
    <ContactComponent :english="english" :arabic="arabic" id="contact"></ContactComponent>                                              
    <FooterComponent :english="english" :arabic="arabic"></FooterComponent>
  </div>
</template>



<script>
import HeaderComponent from "./components/Header.vue"
import IntroComponent from "./components/Intro.vue"
import AboutSliderComponent from "./components/AboutSlider.vue"
import StatsComponent from "./components/Stats.vue"
import AboutComponent from "./components/About.vue"
import SkillsComponent from "./components/Skills.vue"
import ExperienceComponent from "./components/Experience.vue"
import WorkComponent from "./components/Work.vue"
import TestimonialsComponent from "./components/Testimonials.vue"
import ContactComponent from "./components/Contact.vue"
import FooterComponent from "./components/Footer.vue"

import { createApp } from 'vue'
import App from './App.vue'
import { library } from '@fortawesome/fontawesome-svg-core'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
import { faCaretDown , faMoon , faCircle , faTornado , faChevronRight , faLocationDot , faPhone , faComments , faEnvelope , faUser , faXmark , faArrowUp } from '@fortawesome/free-solid-svg-icons'
import { faFacebookF , faTwitter , faLinkedinIn , faYoutube} from '@fortawesome/free-brands-svg-icons'

library.add(faCaretDown, faMoon , faCircle , faTornado , faChevronRight , faLocationDot , faPhone , faComments , faEnvelope , faUser , faXmark , faArrowUp , faFacebookF , faTwitter , faLinkedinIn , faYoutube)

createApp(App)
.component('font-awesome-icon', FontAwesomeIcon)
.mount('#app')


  export default {
    name:"App",
    data(){
      return{
        nightMode:true,
        english:true,
        arabic:false,
    }
  },
    components:{
      HeaderComponent,
      IntroComponent,
      StatsComponent,
      AboutComponent,
      SkillsComponent,
      ExperienceComponent,
      WorkComponent,
      TestimonialsComponent,
      ContactComponent,
      FooterComponent,
      AboutSliderComponent,
      FontAwesomeIcon
    },
    mounted(){
            setTimeout(() => {
              document.querySelector(".loader").classList.remove("starter")
            }, 3500);
            window.addEventListener("scroll",() => {
              document.querySelectorAll(".scroll-animated").forEach((ele,index) => {
                    if(window.scrollY >= (ele.parentElement.offsetTop - 500)){
                        if(ele.classList.contains("scale")){
                            ele.style.cssText = `
                                // transition-delay: ${0.1 * index}s;
                                opacity: 1;
                                scale: 1;
                            `
                        }else if(ele.classList.contains("translate")){
                            ele.style.cssText = `
                                // transition-delay: ${0.1 * index}s;
                                opacity: 1;
                                transform: translateY(0px);
                            `
                        }
                    }else{
                        if(ele.classList.contains("scale")){
                            ele.style.cssText = `
                                // transition-delay: ${0.1 * index}s;
                                opacity: 0;
                                scale: 0;
                            `
                        }else if(ele.classList.contains("translate")){
                            ele.style.cssText = `
                                // transition-delay: ${0.1 * index}s;
                                opacity: 0;
                                transform: translateY(100px);
                            `
                        }
                    }
                })
                console.log(window.scrollY)
                if(window.scrollY < 220){
                  document.querySelector(".to-top").style.display = "none";
                }else if(window.scrollY >= 220 && window.scrollY < 250){
                  document.querySelector(".to-top").style.display = "flex";
                  document.querySelector(".to-top").style.opacity = "0";
                }else if(window.scrollY >= 250){
                  document.querySelector(".to-top").style.opacity = "1";
                }
                document.querySelector(".to-top circle").style.cssText = `
                  stroke-dashoffset: ${125 - (125 * 1.15 * (window.scrollY/document.body.scrollHeight))};
                `
              }
            )
            
      window.onscroll = () => {
        if(window.scrollY >= 100){
          document.querySelector(".header").style.cssText = `
            box-shadow: 0px 0px 20px 0px rgb(15, 15, 15);
            background-color: var(--lighter-color);
          `
        }else{
          document.querySelector(".header").style.cssText = `
            box-shadow: 0px 0px 20px 0px transparent  ;
            background-color: transparent;
          `
        }
      };
      var innerCursor = document.querySelector(".inner.cursor")
      var outerCursor = document.querySelector(".outer.cursor")
      document.addEventListener("mousemove",(event)=>{
          innerCursor.style.left = `${event.clientX}px`;
          innerCursor.style.top = `${event.clientY}px`;
          outerCursor.style.left = `${event.clientX}px`;
          outerCursor.style.top = `${event.clientY}px`;
      })
      document.querySelectorAll("*").forEach((ele) => {
        ele.addEventListener("mouseover", () => {
          if(ele.classList.contains("clickable")){
            innerCursor.style.cssText = `
              width: 10px;
              height: 10px;
            `
            ele.addEventListener("mouseleave", () => {
              innerCursor.style.cssText = `
                width: 5px;
                height: 5px;
              `
            })
          }else{
            ele.addEventListener("click",(event) => {
              innerCursor.classList.add("animated")
              setTimeout(() => {
                innerCursor.classList.remove("animated")
              }, 2000);
            })
          }
        })
      })
    },
    provide() {
      return {
        providedEnglish: this.english,
        providedArabic: this.arabic,
      }
    },
  }

</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Mulish:wght@300;400;500;600;700;800&family=Tajawal:wght@300;400;500;700;800&family=Vina+Sans&display=swap');
*{
  -webkit-box-sizing: border-box;
  -moz-box-sizing: border-box;
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}
:root{
  --bg-color:#1f1f1f;
  /* --bg-color:#e6e6e6; light */
  --sec-color:#e38445;
  --lighter-color:#2f2f2f;
  /* --lighter-color:#ffffff; */
  --text-color:#ffffff;
  /* --text-color:#1f1f1f; */
  --sec-text-color:#7d9e9e;
  /* --sec-text-color:#5e5e5e; //light */
  --main-transition:all 0.5s 0s ease-out;
  --main-gradient:linear-gradient(to right, var(--sec-color) 20%, red);
}
::selection{
  background-color: var(--sec-color);
  color: var(--text-color);
}
html{
  scroll-behavior: smooth;
  scroll-padding-top: 100px;
}
body{
  font-family: "Mulish",sans-serif;
  background-color: var(--bg-color);
  color:var(--text-color);
  overflow-x: hidden;
  transition: var(--main-transition);
  /* direction: rtl; */
  position: relative;
}
button{
  font-family: inherit;
}
input,
textarea{
  font-family: inherit;
}
input::placeholder,
textarea::placeholder{
  font-family: inherit;
}
.english{
  /* display: none !important; */
}
.arabic{
  font-family: "Tajawal",sans-serif;
}
a,.link{
  text-decoration: none;
}
.clickable{
  cursor: pointer;
}
img,video{
  max-width: 100%;
}
ul{
  list-style: none;
}
.main-btn{
  padding: 10px 20px;
  border: 1px solid var(--text-color);
  color: var(--text-color);
  background-color: transparent;
  text-transform: uppercase;
  font-weight: bold;
  font-size: 17px;
  border-radius: 6px;
  transition: var(--main-transition);
  transition-duration: 0.3s;
  overflow: hidden;
  position: relative;
}
.main-btn.sec-color{
  background-color: var(--sec-color);
}
.main-btn.sec-color:hover{
  background-color: transparent;
}
.main-btn:hover{
  text-shadow: 0px 0px 5px #aaa;
  color: var(--bg-color);
}
.main-btn::before{
  content: "";
  position: absolute;
  left: 50%;
  bottom: 50%;
  background-color: var(--text-color);
  width: 170px;
  height: 170px;
  z-index: -1;
  transform-origin: 0 0;
  transition: var(--main-transition);
  transition-duration: 0.3s;
  transform: rotateZ(45deg) translate(20%, 122%);
}
.main-btn:hover::before{
  transform: rotateZ(45deg) translate(20%, 22%);
}
.main-heading{
  /* position: absolute; */
  text-transform: uppercase;
  color: var(--sec-text-color);
  transform: rotateZ(90deg);
}
.main-heading::before{
  content: "";
  position: absolute;
  top: 50%;
  right: 0;
  transform: translate(120%,-50%);
  width: 30px;
  height: 1px;
  transition: var(--main-transition);
  background-color: var(--sec-text-color);
}
.main-heading p{
  transition: var(--main-transition);
}
.main-heading:hover p{
  color: var(--text-color);
}
.main-heading:hover::before{
  background-color: var(--text-color);
}
.main-text{
  position: relative;
  padding-left: 30px;
}
.main-text .main-heading{
  position: absolute;
  left: 0;
  top: 0;
  transform: rotateZ(90deg) translateY(150%) translateX(50%);
}
.main-text.arabized{
  padding-right: 30px;
  padding-left: 0px;
}
.main-text .main-heading.arabized{
  inset: 0 0 auto auto;
  transform: rotateZ(-90deg) translateY(78%) translateX(-86%);
}
.main-text h2{
  font-size: 30px;
  width: 75%;
  font-weight: 800;
  margin-bottom: 20px;
}
.main-text p{
  color: var(--sec-text-color);
  line-height: 1.6;
}
.scroll-animated{
    opacity: 0;
    transition: var(--main-transition);
}
.scroll-animated.scale{
    scale: 0;
}
.scroll-animated.translate{
    transform: translateY(100px);
}
.container{
  padding-left: 20px;
  padding-right: 20px;
  margin-left: auto;
  margin-right: auto;
}
@media (min-width:767px) {
  .container{
    width: 750px;
  }
}
@media (min-width:992px) {
  .container{
    width: 980px;
  }
}
@media (min-width:1200px) {
  .container{
    width: 1180px;
  }
}
.header{
  position: fixed;
  transition: var(--main-transition);
  transition-duration: 0.3s;
  left: 0;
  top: 0;
  width: 100%;
  z-index: 11;
}
.loader{
  position: fixed;
  width: 100vw;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: var(--lighter-color);
  left: 0;
  top: -150%;
  z-index: 20;
  /* animation: loader 1s ease-in 2s 1 forwards; */
}
.loader.animation{
  animation: loader 3s ease-in 0s 1 reverse;
}
.loader.starter{
  animation: loader-starter 3s ease-in 0s 1 forwards;
}
.loader .content .logo{
  color: var(--text-color);
  font-weight: bold;
  font-size: 40px;
  text-align: center;
  margin-bottom: 20px;
}
.loader .content .logo.english{
  font-family: 'Vina Sans', sans-serif;
}
.loader .content .logo.arabic{
  font-family: "Tajawal",sans-serif;
}
.loader .content .loading-bar{
  background-color: var(--bg-color);
  height: 10px;
  width: 250px;
  margin-right: auto;
  margin-left: auto;
  overflow: hidden;
  position: relative;
}
.loader .content .loading-bar span{
  position: absolute;
  left: -50%;
  top: 50%;
  transform: translateY(-50%);
  background-color: var(--sec-color);
  width: 50%;
  height: 100%;
  border-radius: 10px;
  animation: loading-bar 2s ease-in-out 0s infinite forwards;
}
.about-slider{
    position: fixed;
    left: 0;
    top: 100%;
    z-index: 20;
    transition: all 1s 0s cubic-bezier(0.48, -0.02, 0.84, 0.48);
}
.about-slider.shown{
  top: 0;
}
.cursor{
  position: fixed;
  left: 50%;
  z-index: 30;
  top: 50%;
  transform: translate(-50%,-50%);
  pointer-events: none;
}
.inner.cursor{
  width: 5px;
  height: 5px;
  border-radius: 50%;
  background-color: var(--sec-color);
}
.inner.cursor.animated{
  animation: cursor-animation 0.8s linear 0s 1 alternate;
}
.outer.cursor{
  width: 30px;
  height: 30px;
  border-radius: 50%;
  background-color: transparent;
  z-index: 30;
  border: 1px solid var(--sec-color);
  transition: var(--main-transition);
  transition-duration: 0.1s;
}
.to-top{
  position: fixed;
  right: 100px;
  bottom: 100px;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 5;
  width: 50px;
  height: 50px;
  transition: var(--main-transition);
  opacity: 0;
  display: none;
}
.to-top circle{
  fill: none;
  stroke: var(--sec-color);
  stroke-width: 1px;
  stroke-dasharray: 125;
  stroke-dashoffset: 125;
}
.to-top svg:not(.to-top-icon){
  position: absolute;
  left: 0;
  top: 0%;
  transform: translate(4px,3px);
}
.to-top svg.to-top-icon{
  color: var(--sec-color);
}
@keyframes loader {
  0%,100%{
    top: -120%;
  }
  25%,75%{
    top: 0%;
  }
}
@keyframes loader-starter {
  0%{
    top: 0%;
  }
  25%,75%{
    top: 0%;
  }
  100%{
    top: -120%;
  }
}
@keyframes loading-bar {
  0%{
    left: -50%;
  }
  100%{
    left: 120%;
  }
}
@keyframes cursor-animation {
  0%,100%{
    width: 5px;
    height: 5px;
  }
  50%{
    width: 10px;
    height: 10px;
  }
}
</style>
