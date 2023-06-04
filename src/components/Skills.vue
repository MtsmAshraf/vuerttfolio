<template>
    <div class="skills">
        <div class="container">
            <div class="text">
                <div class="main-text">
                    <div class="main-heading scroll-animated scale">
                        <h4 class="english" v-if="this.english">My Skills</h4>
                        <h4 class="arabic" v-if="this.arabic">مهاراتي</h4>
                    </div>
                    <h2 class="scroll-animated translate english" v-if="this.english">What My Programming Skills Included?</h2>
                    <h2 class="scroll-animated translate arabic" v-if="this.arabic">ماذا تضمنت مهارات البرمجة الخاصة بي؟</h2>
                    <p class="scroll-animated translate english" v-if="this.english">I develop simple, intuitive and responsive user interface that helps users get things done with less effort and time with those technologies.</p>
                    <p class="scroll-animated translate arabic" v-if="this.arabic">أقوم بتطوير واجهات مستخدم رائعة وبسيطة وسريعة الاستجابة حتى تساعد المستخدمين على إنجاز المهام بأقل وقت وجهد من خلال هذه التقنيات.</p>
                </div>
                <div class="buttons toggle clickable scroll-animated scale english" v-if="this.english">
                    <span>Skills</span>
                    <span>Tools</span>
                </div>
                <div class="buttons toggle clickable scroll-animated scale arabic" v-if="this.arabic">
                    <span>مهارات</span>
                    <span>أدوات</span>
                </div>
            </div>
            <div class="cards">
                <div class="card scroll-animated translate" text-content="html"><img src="../assets/html5-logo.png" alt=""></div>
                <div class="card scroll-animated translate" text-content="css"><img src="../assets/css-logo.png" alt=""></div>
                <div class="card scroll-animated translate" text-content="javascript"><img src="../assets/javascript-39404.png" alt=""></div>
                <div class="card scroll-animated translate" text-content="typescript"><img src="../assets/ts-logo-256.png" alt=""></div>
                <div class="card scroll-animated translate" text-content="jquery"><img src="../assets/jquery.png" alt=""></div>
                <div class="card scroll-animated translate" text-content="bootstrap"><img src="../assets/bootstrap.png" alt=""></div>
                <div class="card scroll-animated translate" text-content="angular"><img src="../assets/angular.png" alt=""></div>
                <div class="card scroll-animated translate" text-content="react"><img src="../assets/react.png" alt=""></div>
                <div class="card scroll-animated translate" text-content="vue"><img src="../assets/vue.png" alt=""></div>
                <div class="card scroll-animated translate" text-content="firebase"><img src="../assets/firebase.png" alt=""></div>
                <div class="card scroll-animated translate" text-content="pugjs"><img src="../assets/pugjs_logo.png" alt=""></div>
                <div class="card scroll-animated translate" text-content="sass"><img src="../assets/sass.png" alt=""></div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Skills",
        props:["english","arabic"],
        //  mounted(){
        //     window.addEventListener("scroll",() => {
        //         console.log("scroll")
        //         document.querySelectorAll(".scroll-animated").forEach((ele,index) => {
        //             if(window.scrollY >= ele.parentElement.offsetTop - 600){
        //                 console.log("reached")
        //                 if(ele.classList.contains("scale")){
        //                     ele.style.cssText = `
        //                         transition-delay: ${0.1 * index}s;
        //                         opacity: 1;
        //                         scale: 1;
        //                     `
        //                 }else if(ele.classList.contains("translate")){
        //                     ele.style.cssText = `
        //                         transition-delay: ${0.1 * index}s;
        //                         opacity: 1;
        //                         transform: translateY(0px);
        //                     `
        //                 }
        //             }else{
        //                 if(ele.classList.contains("scale")){
        //                     ele.style.cssText = `
        //                         transition-delay: ${0.1 * index}s;
        //                         opacity: 0;
        //                         scale: 0;
        //                     `
        //                 }else if(ele.classList.contains("translate")){
        //                     ele.style.cssText = `
        //                         transition-delay: ${0.1 * index}s;
        //                         opacity: 0;
        //                         transform: translateY(100px);
        //                     `
        //                 }
        //             }
        //         })
        //     }
        //     )
        //  }
    }
</script>

<style scoped>
.skills{
    padding-top: 100px;
    padding-bottom: 100px;
}
.skills .container{
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
}
.skills .container > *{
    width: 50%;
}
.skills .container .text .buttons{
    margin-left: 40px;
    margin-top: 30px;
    background-color: var(--lighter-color);
    width: 150px;
    padding-top: 5px;
    padding-bottom: 5px;
    padding: 10px 20px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    flex-direction: row-reverse;
    border-radius: 20px;
    box-shadow: 0px 0px 10px 0px rgb(15, 15, 15);
    position: relative;
}

.skills .container .text .buttons::before{
    content: "";
    position: absolute;
    inset: 50% auto auto 0;
    transform: translate(0%,-50%);
    height: 100%;
    width: 50%;
    background-color: var(--sec-color);
    border-radius: 20px;
    z-index: 1;
    transition: var(--main-transition);
    transition-duration: 0.3s;
}
.skills .container .text .buttons:hover::before{
    transform: translate(100%,-50%);
}
.skills .container .text .buttons span{
    z-index: 2;
    font-weight: bold;
}
.skills .container .text .buttons.arabized{
    width: 180px;
}
.skills .container .text .buttons.arabized::before{
    transform: translate(0%,-50%);
    inset: 50% 0 auto auto;
}
.skills .container .text .buttons.arabized:hover::before{
    transform: translate(-100%,-50%);
}
.skills .container .cards{
    display: grid;
    grid-template-columns: repeat(6,minmax(70px,1fr));
    gap: 20px;
}
.skills .container .cards .card{
    aspect-ratio: 1;
    background-color: var(--lighter-color);
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 6px;
    box-shadow: 0px 0px 10px 0px rgb(15, 15, 15);
    transition: var(--main-transition);
    transition-duration: 0.3s;
    position: relative;
}
.skills .container .cards .card:nth-child(1),
.skills .container .cards .card:nth-child(2),
.skills .container .cards .card:nth-child(3),
.skills .container .cards .card:nth-child(4),
.skills .container .cards .card:nth-child(5),
.skills .container .cards .card:nth-child(6){
    z-index: 3;
}
.skills .container .cards .card:nth-child(7),
.skills .container .cards .card:nth-child(8),
.skills .container .cards .card:nth-child(9),
.skills .container .cards .card:nth-child(10),
.skills .container .cards .card:nth-child(11),
.skills .container .cards .card:nth-child(12){
    z-index: 2;
}
.skills .container .cards .card::before{
    /* content: attr("text-content"); */
    content:attr(text-content);
    position: absolute;
    left: 50%;
    top: 0;
    /* transform: translate(-50%, -150%); */
    transform: translate(-50%, -210%);
    background-color: var(--sec-color);
    color: var(--text-color);
    min-width: 100%;
    height: 40px;
    display: flex;
    align-items: center;
    justify-content: center;
    border-radius: 6px;
    box-shadow: 0px 0px 10px 0px rgb(15, 15, 15);
    font-weight: bold;
    transition: var(--main-transition);
    transition-duration: 0.3s;
    opacity: 0; 
    font-size: 14px;
    text-transform: uppercase;
    padding-left: 10px;
    padding-right: 10px;
}
.skills .container .cards .card::after{
    content:"";
    position: absolute;
    left: 50%;
    top: 0;
    /* transform: translate(-50%, -105%); */
    transform: translate(-50%, -229%);
    background-color: var(--sec-color);
    width: 0px;
    height: 0px;
    border-width: 10px;
    border-style: solid;
    border-color: var(--sec-color) var(--bg-color) var(--bg-color); 
    transition: var(--main-transition);
    transition-duration: 0.3s;
    opacity: 0;
}
.skills .container .cards .card:hover{
    z-index: 3;
    box-shadow: 0px 0px 10px 0px var(--sec-color);
}
.skills .container .cards .card:hover::before{
    opacity: 1;
    transform: translate(-50%, -150%);
}
.skills .container .cards .card:hover::after{
    opacity: 1;
    transform: translate(-50%, -105%);
}
.skills .container .cards .card img{
    width: 40px;
}
@media (max-width:1200px) {
    .skills .container{
        flex-direction: column;
    }
    .skills .container > *{
        width: 100%;
    }
    .skills .container .text .buttons{
        margin-left: auto;
        margin-right: auto;
    }
    .skills .container .cards .card img{
        width: 70%;  
    }
}
@media (max-width:1200px) {
    
    .skills .container .cards{
        grid-template-columns: repeat(4,minmax(70px,1fr));
    }
}
</style>
