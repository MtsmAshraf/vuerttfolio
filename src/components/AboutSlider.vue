<template>
    <div class="about-slider">
        <div class="x-mark clickable" @click="showAboutSlider()">
            <font-awesome-icon class="x-mark-icon" icon="fa-solid fa-xmark" />
        </div>
        <div class="container english" v-show="this.english">
            <h4>I love making things simple, intuitive and expertly crafted!</h4>
            <p>Product is the vital essence of what i do, truly great product is born of meticulous planning and process. This is where i specialized!</p>
            <ul>
                <li>
                    <h3>Email</h3>
                    <a href="#" class="clickable">mo32000a@gmail.com</a>
                </li>
                <li>
                    <h3>Address</h3>
                    <a href="#" class="clickable">941 saqrqorish Road, alandalos, grnata, wa 47122-4194</a>
                </li>
                <li>
                    <h3>Phone</h3>
                    <a href="#" class="clickable">(02) 966 202 290</a>
                    <a href="#" class="clickable">(02) 966 202 290</a>
                </li>
            </ul>
        </div>
        <div class="container arabic" v-show="this.arabic">
            <h4>أحب جعل الأشياء بسيطة وبديهية ومصممة بخبرة!</h4>
            <p>المنتج هو الجوهر الحيوي لما أفعله ، المنتج الرائع حقًا يولد من التخطيط الدقيق. هذا هو المكان والأمر الذي تخصصت فيه!</p>
            <ul>
                <li>
                    <h3>البريد الإلكتروني</h3>
                    <a href="#" class="clickable">mo32000a@gmail.com</a>
                </li>
                <li>
                    <h3>العنوان</h3>
                    <a href="#" class="clickable">941 طريق صقر قريش ، الأندلس ، غرناطة ، WA 47122-4194</a>
                </li>
                <li>
                    <h3>الهاتف</h3>
                    <a href="#" class="clickable">(02) 966 202 290</a>
                    <a href="#" class="clickable">(02) 966 202 290</a>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';

    export default {
        name:"About-Slider",
        props:["english","arabic"],
        components:{
            FontAwesomeIcon
        },
        methods:{
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
        },
    }
</script>

<style scoped>
.about-slider{
    background-color: var(--lighter-color);
    height: 100vh;
    width: 100%;
}
.x-mark{
    position: absolute;
    top: 50px;
    right: 50px;
}
.x-mark .x-mark-icon{
    color: var(--text-color);
    font-size: 24px;
    z-index: 21;
}
.about-slider .container{
    display: flex;
    justify-content: center;
    flex-direction: column;
    height: 100%;
}
.about-slider .container *{
    transition: var(--main-transition);
    transition-delay: 1.3s;
}
.about-slider .container h4{
    font-weight: normal;
    opacity: 0;
}
.about-slider.shown .container h4{
    opacity: 1;
}
.about-slider .container > p{
    font-size: 40px;
    font-weight: bold;
    margin-top: 30px;
    margin-bottom: 60px;
    opacity: 0;
    transform: translateY(20px);
}
.about-slider.shown .container > p{
    opacity: 1;
    transform: translateY(0px);
}
.about-slider .container ul{
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.about-slider .container ul li{
    display: flex;
    flex-direction: column;
}
.about-slider .container ul li h3{
    font-size: 24px;
    font-weight: 800;
    margin-bottom: 20px;
    position: relative;
    overflow: hidden;
    width: fit-content;
    color: var(--lighter-color);
    transition: var(--main-transition);
    transition-delay: 1.7s;
    transition-duration: 0s;
}
.about-slider .container ul li h3::before{
    position: absolute;
    content: "";
    top: 0;
    left: -100%;
    height: 100%;
    width: 100%;
    transition: var(--main-transition);
    transition-delay: 1.5s;
    background-color: var(--sec-color);
}
.about-slider.shown .container ul li h3{
    color: var(--text-color);
}
.about-slider.shown .container ul li h3::before{
    left: 100%;
}
.about-slider .container ul li a{
    opacity: 0;
    transform: translateY(10px);
    color: var(--sec-text-color);
}
.about-slider.shown .container ul li a{
    opacity: 1;
    transform: translateY(0px);
}
@media (max-width:992px) {
    .about-slider .container ul{
        flex-wrap: wrap;
    }
    .about-slider .container ul li{
        width: 50%;
        margin-bottom: 20px;
    }
}
@media (max-width:767px) {
    .about-slider{
        height: 120vh !important;
        padding-top: 100px;
    }
    .about-slider .x-mark{
        right: 20px;
        top: 20px;
    }
    .about-slider .container{
        justify-content: flex-start;
    }
    .about-slider .container > p{
        font-size: 30px;
    }
    .about-slider .container ul{
        flex-wrap: wrap;
    }
    .about-slider .container ul li{
        width: 100%;
        margin-bottom: 20px;
    }
}
</style>