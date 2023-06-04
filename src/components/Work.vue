<template>
    <div class="work">
        <div class="container">
            <div class="box scroll-animated translate">
                <div class="main-text">
                    <div class="main-heading scroll-animated scale">
                        <h4 class="english" v-if="this.english">My Work</h4>
                        <h4 class="arabic" v-if="this.arabic">أعمالي</h4>
                    </div>
                    <h2 class="scroll-animated translate english" v-if="this.english">See My Works Which Will Amaze You!</h2>
                    <h2 class="scroll-animated translate arabic" v-if="this.arabic">شاهد أعمالي التي ستدهشك!</h2>
                    <p class="scroll-animated translate english" v-if="this.english">We develop the best quality website that serves for the long-term. Well-documented, clean, easy and elegant interface helps any non-technical clients.</p>
                    <p class="scroll-animated translate arabic" v-if="this.arabic">أقوم بتطوير أفضل مواقع الويب عالية الجودة والتي تعمل على المدى الطويل. تساعد الواجهة الموثقة جيدًا والنظيفة والسهلة والأنيقة أي عميل غير تقني.</p>
                </div>
                <div class="buttons">
                    <span class="option clickable active scroll-animated scale" @click="selectMethod(),filterWork()">All</span>
                    <span>/</span>
                    <span class="option clickable scroll-animated scale" @click="selectMethod(),filterWork()">html</span>
                    <span>/</span>
                    <span class="option clickable scroll-animated scale" @click="selectMethod(),filterWork()">Angular</span>
                    <span>/</span>
                    <span class="option clickable scroll-animated scale" @click="selectMethod(),filterWork()">Vue</span>
                </div>
            </div>
            <a href="#" filter="html" class="box scroll-animated translate clickable">
                <div class="work-title">Work title one</div>
                <div class="date-completed">May 2023</div>
                <img src="../assets/printer.png" alt="">
            </a>
            <a href="#" filter="html" class="box scroll-animated translate clickable">
                <div class="work-title">Work title</div>
                <div class="date-completed">May 2023</div>
                <img src="../assets/old-computer.png" alt="">
            </a>
            <a href="#" filter="Angular" class="box scroll-animated translate clickable">
                <div class="work-title">Work title</div>
                <div class="date-completed">May 2023</div>
                <img src="../assets/watch.png" alt="">
            </a>
            <a href="#" filter="Angular" class="box scroll-animated translate clickable">
                <div class="work-title">Work title</div>
                <div class="date-completed">May 2023</div>
                <img src="../assets/laptop.png" alt="">
            </a>
            <a href="#" filter="Angular" class="box scroll-animated translate clickable">
                <div class="work-title">Work title</div>
                <div class="date-completed">May 2023</div>
                <img src="../assets/pen-notebook.png" alt="">
            </a>
            <a href="#" filter="Vue" class="box scroll-animated translate clickable">
                <div class="work-title">Work title</div>
                <div class="date-completed">May 2023</div>
                <img src="../assets/bicycle.png" alt="">
            </a>
            <a href="#" filter="Vue" class="box scroll-animated translate clickable">
                <div class="work-title">Work title</div>
                <div class="date-completed">May 2023</div>
                <img src="../assets/calculator.png" alt="">
            </a>
        </div>
    </div>
</template>

<script>
    export default {
        name:"Work",
        props:["english","arabic"],
        data(){
            return{
                selectedOptionIndex:0,
            }
        },
        methods:{
            filterWork(){
                setTimeout(() => {
                    console.log(this.selectedOptionIndex)
                    if(document.querySelectorAll(".buttons .option")[this.selectedOptionIndex].textContent !== "All"){
                        document.querySelectorAll(".box:has(img)").forEach((box) => {
                            box.style.display = "none";
                        })
                        document.querySelectorAll(".box:has(img)").forEach((box) => {
                            if(document.querySelectorAll(".buttons .option")[this.selectedOptionIndex].textContent === box.getAttribute("filter")){
                                box.style.display = "block";
                            }
                        })
                    }else{
                        document.querySelectorAll(".box:has(img)").forEach((box) => {
                            box.style.display = "block";
                        })
                    }
                }, 300);
            },
            selectMethod(){
                document.querySelectorAll(".buttons .option").forEach((option,index) => {
                    console.log(option,index)
                    option.onclick = () => {
                        this.selectedOptionIndex = index
                        document.querySelectorAll(".buttons .option").forEach((option) => {
                            option.classList.remove("active");
                        })
                        option.classList.add("active");
                    }
                })
            }
        },
    }
</script>

<style scoped>
.worK{
    padding-top: 100px;
    padding-bottom: 100px;
}
.work .container{
    display: flex;
    flex-wrap: wrap; 
    gap: 20px;
}
.work .container .box{
    height: fit-content;
    position: relative;
}
.work .container .box img{
    z-index: 1;
}
.work .container .box:has(img) div{
    position: absolute;
    left: 20px;
    background-color: var(--bg-color);
    padding: 5px 10px;
    box-shadow: 0px 0px 10px 0px rgb(15, 15, 15);
    color: var(--text-color);
    transform: translateY(30px);
    transition: var(--main-transition);
    opacity: 0;
    transition-duration: 0.3s;
    border-radius: 6px;
}
.work .container .box:has(img) .work-title{
    bottom: 60px;
    z-index: 3;
    font-weight: bold;    
}
.work .container .box:has(img) .date-completed{
    z-index: 3;
    bottom: 20px;
    transition-delay: 0.1s;
}
.work .container .box:has(img):hover .work-title{
    opacity: 1;
    transform: translateY(0px);
}
.work .container .box:has(img):hover .date-completed{
    opacity: 1;
    transform: translateY(0px);
}
.work .container .box .main-text h2{
    width: 100%;
}
.work .container .box .buttons{
    margin-left: 30px;
    margin-top: 30px;    
    display: flex;
    gap: 10px;
}
.work .container .box .buttons.arabized{
    flex-direction: row-reverse;
}
.work .container .box .buttons .option{
    color: var(--sec-text-color);
}
.work .container .box .buttons .option.active{
    color: var(--sec-color);
}
.work .container .box{
    width: calc(33% - 10px);
    overflow: hidden;
    border-radius: 15px;
}
.work .container .box:not(:first-child){
    display: flex;
    align-items: center;
    justify-content: center;
}
.work .container .box img{
    transform: scale(1.1);
}
@media (max-width:1200px) {
    .work .container .box:first-child{
        width: 100%;
    }
    .work .container .box:not(:first-child){
        width: calc(50% - 10px);
    }
}
</style>