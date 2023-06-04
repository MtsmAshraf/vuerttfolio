<template>
    <div class="about">
        <div class="container">
            <div class="img scroll-animated scale about-img"><img src="../assets/man-7.jpg" alt=""></div>
            <div class="text">
                <div class="main-text">
                    
                    <div class="main-heading img scroll-animated scale">
                        <h4 class="english" v-if="this.english">About Me</h4>
                        <h4 class="arabic" v-if="this.arabic">من أنا؟</h4>
                    </div>
                    <h2 class="scroll-animated translate h2 english" v-if="this.english">Need a Creative Product? I can Help You!</h2>
                    <h2 class="scroll-animated translate h2 arabic" v-if="this.arabic">هل تحتاج إلى منتج إبداعي؟ أنا أستطيع مساعدتك!</h2>
                    <p class="scroll-animated translate english" v-if="this.english">Hi! I’m Muhammad Mabrouk, and I’m a developer who has passion for building clean web applications with intuitive functionality. I enjoy the process of turning ideas into reality using creative solutions. I’m always curious about learning new skills, tools, and concepts. In addition to working on various solo full stack projects, I have worked with creative teams, which involves daily stand-ups and communications, source control, and project management.</p>
                    <p class="scroll-animated translate arabic" v-if="this.arabic">مرحبا! أنا محمد مبروك ، مطور لديه شغف لإنشاء تطبيقات ويب نظيفة بوظائف عالية. أستمتع بتحويل الأفكار إلى واقع باستخدام الحلول الإبداعية. لدي فضول دائمًا بشأن تعلم مهارات وأدوات ومفاهيم جديدة. بالإضافة إلى العمل في العديد من المشاريع الفردية الكاملة ، فقد عملت مع فرق إبداعية ، وكان لدينا اجتماعات واتصالات يومية وتحكم في الاصدارات وإدارة المشاريع.</p>
                </div>
                <div class="buttons scroll-animated translate english" v-if="this.english">
                    <button class="main-btn clickable sec-color">Hire Me</button>
                    <button class="main-btn clickable">Download CV</button>
                </div>
                <div class="buttons scroll-animated translate arabic" v-if="this.arabic">
                    <button class="main-btn clickable sec-color">وظفني</button>
                    <button class="main-btn clickable">تحميل السيرة الذاتية</button>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name:"About",
        props:["english","arabic"],
        // mounted(){
        //     console.log(document.querySelector(".h2").offsetTop)
        //     console.log(document.querySelector(".about-img").offsetTop)
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
        // }
    }
</script>

<style scoped>
.about{
    padding-top: 100px;
    padding-bottom: 100px;
}

.about .container{
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
}
.about .container > *{
    width: 50%; 
}
.about .container .text .buttons{
    margin-top: 20px;
    padding-left: 40px;
    display: flex;
    align-items: center;
    gap: 20px;
}
@media (max-width:992px) {
    .about .container{
        flex-direction: column;
    }
    .about .container > *{
        width: 100%;
    }
}
</style>