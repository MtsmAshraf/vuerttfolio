<template>
    <header>
        <div class="container">
            <a href="#" class="logo link clickable">
                <h4 class="english" v-show="english">Moatasim</h4>
                <h4 class="arabic" v-show="arabic">معتصم</h4>
                <span>.</span>
            </a>
            <nav class="english" v-show="this.english">
                <a href="#home" class="clickable">Home.</a>
                <a href="#about" class="clickable">About.</a>
                <a href="#skills" class="clickable">Skills.</a>
                <a href="#portfolio" class="clickable">Portfolio.</a>
                <a href="#contact" class="clickable">Contact.</a>
            </nav>
            <nav class="arabic" v-show="this.arabic">
                <a href="#home" class="clickable">الرئيسية.</a>
                <a href="#about" class="clickable">من أنا؟.</a>
                <a href="#skills" class="clickable">مهاراتي.</a>
                <a href="#portfolio" class="clickable">أعمالي.</a>
                <a href="#contact" class="clickable">اتصل بي.</a>
            </nav>
            <div class="options">
                <div class="language">
                    <div class="button clickable">
                        <span class="english" v-show="this.english">EN</span>
                        <span class="arabic" v-show="this.arabic">ع</span>
                        <font-awesome-icon icon="fa-solid fa-caret-down" />
                    </div>
                    <div class="list">
                        <span class="clickable" @click="changeLanguageToEnglish(),loader()">EN</span>
                        <span class="clickable" @click="changeLanguageToArabic(),loader()">ع</span>
                    </div>
                </div>
                <div class="theme clickable" @click="changeTheme()">
                    <div class="theme-icon">
                        <font-awesome-icon icon="fa-solid fa-moon" />
                        <font-awesome-icon icon="fa-solid fa-circle"/>
                    </div>
                </div>
                <div class="side-menu-btn clickable" @click="showAboutSlider()">
                    <font-awesome-icon icon="fa-solid fa-tornado" />
                </div>
            </div>
        </div>
    </header>
</template>

<script>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'
// import { faCaretDown } from '@fortawesome/free-solid-svg-icons'
    export default {
        name:"HeaderComponent",
        data(){
            return{
                nightMode:true,
                english:true,
                arabic:false,
            }
        },
        components:{
            FontAwesomeIcon
        },
        methods:{
            changeTheme(){
                console.log("THEME")
                if(this.nightMode === false){
                    this.nightMode = true;
                    document.querySelector("header .container .options .theme .theme-icon").style.cssText = `
                        transform: translateX(calc(100% - 20px));
                    `
                    document.querySelector("header .container .options .theme .theme-icon > *:first-child").style.cssText = `
                        opacity: 0;
                    `
                    document.querySelector("header .container .options .theme .theme-icon > *:last-child").style.cssText = `
                        opacity: 1;
                    `
                    document.documentElement.style.setProperty('--bg-color', '#e6e6e6');
                    document.documentElement.style.setProperty('--lighter-color', '#ffffff');
                    document.documentElement.style.setProperty('--text-color', '#1f1f1f');
                    document.documentElement.style.setProperty('--sec-text-color', '#5e5e5e');
                }else{
                    this.nightMode = false;
                    document.querySelector("header .container .options .theme .theme-icon").style.cssText = `
                        transform: translateX(0);
                    `
                    document.querySelector("header .container .options .theme .theme-icon > *:first-child").style.cssText = `
                        opacity: 1;
                    `
                    document.querySelector("header .container .options .theme .theme-icon > *:last-child").style.cssText = `
                        opacity: 0;
                    `
                    document.documentElement.style.setProperty('--bg-color', '#1f1f1f');
                    document.documentElement.style.setProperty('--lighter-color', '#2f2f2f');
                    document.documentElement.style.setProperty('--text-color', '#ffffff');
                    document.documentElement.style.setProperty('--sec-text-color', '#7d9e9e');
                }
            },
            addArabizedClassName(selector){
                document.querySelectorAll(selector).forEach((ele) => {
                    ele.classList.add("arabized");
                })
            },
            removeArabizedClassName(selector){
                document.querySelectorAll(selector).forEach((ele) => {
                    ele.classList.remove("arabized");
                })
            },
            changeLanguageToArabic(){
                    setTimeout(() => {
                        document.querySelector("body").style.cssText = `
                            direction: rtl;
                        `
                        this.addArabizedClassName(".stats .container .card .card-icon");
                        this.addArabizedClassName(".main-text");
                        this.addArabizedClassName(".main-text .main-heading");
                        this.addArabizedClassName(".skills .container .text .buttons");
                        this.addArabizedClassName(".skills .container .text .buttons:hover::before");
                        this.addArabizedClassName(".skills .container .text .buttons::before");
                        this.addArabizedClassName(".experience .container .years .year");
                        this.addArabizedClassName(".experience .container .text .main-heading");
                        this.addArabizedClassName(".work .container .box .buttons");
                        this.english = false;
                        this.arabic = true;
                        console.log("english",this.english)
                        console.log("arabic",this.arabic)
                        this.$emit("changelanguagetoenglish", this.english);
                        this.$emit("changelanguagetoarabic", this.arabic);
                    }, 2000);
                    setTimeout(() => {
                        document.querySelectorAll(".year .year-detail").forEach((detail) => {
                            detail.style.opacity = "0"
                            detail.style.display = "none"
                            console.log("details should be NOT displayed")
                        })
                    }, 2200);
            },
            changeLanguageToEnglish(){
                    setTimeout(() => {
                        this.removeArabizedClassName(".stats .container .card .card-icon");
                        this.removeArabizedClassName(".main-text");
                        this.removeArabizedClassName(".main-text .main-heading");
                        this.removeArabizedClassName(".skills .container .text .buttons");
                        this.removeArabizedClassName(".skills .container .text .buttons:hover::before");
                        this.removeArabizedClassName(".skills .container .text .buttons::before");
                        this.removeArabizedClassName(".experience .container .years .year");
                        this.removeArabizedClassName(".experience .container .text .main-heading");
                        this.removeArabizedClassName(".work .container .box .buttons");
                        document.querySelector("body").style.cssText = `
                            direction: ltr;
                        `
                        this.english = true;
                        this.arabic = false;
                        console.log("english",this.english)
                        console.log("arabic",this.arabic)
                        this.$emit("changelanguagetoenglish", this.english);
                        this.$emit("changelanguagetoarabic", this.arabic);
                    }, 2000);
                    setTimeout(() => {
                        document.querySelectorAll(".year .year-detail").forEach((detail) => {
                            detail.style.opacity = "0"
                            detail.style.display = "none"
                            console.log("details should be NOT displayed")
                        })
                    }, 2200);
            },
            loader(){
                document.querySelector(".loader").classList.add("animation")
                setTimeout(() => {
                    document.querySelector(".loader").classList.remove("animation")
                }, 3500);
            },
            showAboutSlider(){
                document.querySelector(".about-slider").classList.toggle("shown");
                console.log(document.querySelector(".about-slider").classList)
                setTimeout(() => {
                    if(document.querySelector(".about-slider").classList.contains("shown")){
                        document.querySelector(".about-slider").style.cssText = `
                            transition-delay: 1.8s;
                        `    
                        console.log("delay should be 1.8")
                    }else{
                        document.querySelector(".about-slider").style.cssText = `
                            transition-delay: 0s;
                        `
                        console.log("delay should be 0")
                    }
                }, 1800);
            }
        }
    }
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Mulish:wght@300;400;500;600;700;800&family=Tajawal:wght@300;400;500;700;800&family=Vina+Sans&display=swap');
header{
    padding-top: 20px;
    padding-bottom  : 20px;
}
header .container{
    display: flex;
    align-items: center;
    justify-content: space-between;
}
header .container .logo{
    display: flex;
    align-items: baseline;
    color: var(--text-color);
    font-size: 30px;
    font-family: "Vina Sans", sans-serif;
    letter-spacing: 2px;
}
header .container .logo span{
    color: var(--sec-color);
    font-size: 40px;
}
header .container nav{
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
    font-weight: bold;
}
header .container nav a{
    position: relative;
    color: var(--text-color);
    transition:var(--main-transition);
    transition-duration: 0.3s;
}
header .container nav a::before{
    content: "";
    position: absolute;
    left: -4px;
    top: 50%;
    transform: translate(-0%,-50%);
    width: 0%;
    height: 2px;
    background-color: var(--sec-color);
    transition:var(--main-transition);
    transition-duration: 0.3s;
}
header .container nav a:hover{
    color: var(--sec-text-color);
}
header .container nav a:hover::before{
    width: 110%;
}
header .container .options{
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 10px;
}
header .container .options .language{
    position: relative;
    color: var(--sec-text-color);
    font-weight: bold;
}
header .container .options .language .button{
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 5px;
}
header .container .options .language .list{
    position: absolute;
    transition: var(--main-transition);
    left: 50%;
    transform: translateX(-50%) translateY(50%);
    opacity: 0;
    display: flex;
    flex-direction: column;
    background-color: var(--lighter-color);
    border-radius: 6px;
    overflow: hidden;
}
header .container .options .language .list span{
    text-align: center;
}
header .container .options .language .list span:first-child{
    padding: 10px 10px 5px;
}
header .container .options .language .list span:nth-child(2){
    padding: 5px 10px 10px;
}
header .container .options .language:hover .list{
    transform: translateX(-50%) translateY(10%);
    opacity: 1;
}
header .container .options .theme{
    background-color: var(--lighter-color);
    padding: 0px 10px;
    width: 60px;
    height: 25px;
    font-size: 22px;
    border-radius: 20px;
    position: relative;
}
header .container .options .theme .theme-icon{
    position: relative;
    transition: var(--main-transition);
    width: 40px;
    height: 100%;
}
header .container .options .theme .theme-icon > *{
    position: absolute;
    top:50%;
    left: 0;
    transform: translateY(-50%);
    transition: var(--main-transition);
}
header .container .options .theme .theme-icon > *:first-child{
    opacity: 1;
}
header .container .options .theme .theme-icon > *:last-child{
    opacity: 0;
    color: yellow;
}
/* header .container .options .theme:hover .theme-icon{
    transform: translateX(calc(100% - 20px));
}
header .container .options .theme:hover .theme-icon > *:first-child{
    opacity: 0;
}
header .container .options .theme:hover .theme-icon > *:last-child{
    opacity: 1;
} */
@media (max-width:767px) {
    header .container nav{
        display: none;
    }
}
</style>