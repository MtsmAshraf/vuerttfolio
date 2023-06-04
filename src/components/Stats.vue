<template>
    <div class="stats">
        <div class="container">
            <a href="#" class="card clickable scroll-animated translate">
                <div class="img"><img src="../assets/cup.jpg" alt=""></div>
                <div class="text">
                    <h4>+2</h4>
                    <p class="english" v-if="this.english">Years Of Experience</p>
                    <p class="arabic" v-if="this.arabic">سنوات الخبرة</p>
                </div>
                <div class="card-icon"><font-awesome-icon icon="fa-solid fa-chevron-right" /></div>
            </a>
            <a href="#" class="card clickable scroll-animated translate">
                <div class="img"><img src="../assets/check.jpg" alt=""></div>
                <div class="text">
                    <h4>+20</h4>
                    <p class="english" v-if="this.english">Completed Projects</p>
                    <p class="arabic" v-if="this.arabic">مشاريع منجزة</p>
                </div>
                <div class="card-icon"><font-awesome-icon icon="fa-solid fa-chevron-right" /></div>
            </a>
            <a href="#" class="card clickable scroll-animated translate">
                <div class="img"><img src="../assets/group.jpg" alt=""></div>
                <div class="text">
                    <h4>+20</h4>
                    <p class="english" v-if="this.english">Happy Clients</p>
                    <p class="arabic" v-if="this.arabic">عميل سعيد</p>
                </div>
                <div class="card-icon"><font-awesome-icon icon="fa-solid fa-chevron-right" /></div>
            </a>
        </div>
    </div>
</template>

<script>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome'

    export default {
        nams:"Stats",
        components:{
            FontAwesomeIcon
        },
        props:["english","arabic"],
    }
</script>

<style scoped>
.stats .container{
    padding-top: 50px;
    padding-bottom: 100px;
}
.stats .container{
    display: grid;
    grid-template-columns: repeat(3,minmax(120px,1fr));
    gap:20px;
    padding-right: 40px;
    padding-left: 40px;
}
.stats .container .card{
    color: var(--text-color);
    background-color: var(--lighter-color);
    box-shadow: 0px 0px 20px 0px rgb(15, 15, 15);
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 30px;
    border-radius: 10px;
    transition: var(--main-transition);
    transition-duration: 0.3s;
    border: 1px solid transparent;
    transform: translateY(100px);
}
.stats .container .card:hover{
    transform: translateY(-20px);
    box-shadow: 0px 0px 20px 0px var(--sec-color);
    border: 1px solid var(--sec-color);
}
.stats .container .card .img{
    width: 70px;
    height: 70px;
    border-radius: 50%;
    overflow: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
}
.stats .container .card .text{
    text-align: center;
}
.stats .container .card .text h4{
    font-size: 30px;
    font-weight: bold;
    color: var(--sec-color);
    margin-bottom: 10px;
}
.stats .container .card .text p{
    font-weight: bold;
}
.stats .container .card .card-icon{
    color: var(--sec-text-color);
    transition: var(--main-transition);
    transition-duration: 0.3s;
}
.stats .container .card .card-icon.arabized{
    transform: rotateZ(180deg);
}
.stats .container .card:hover .card-icon {
    color: var(--text-color);
}
@media (max-width:992px) {
    .stats .container{
        grid-template-columns: repeat(2,minmax(120px,1fr));
    }
}
@media (max-width:767px) {
    .stats .container{
        padding-top: 0px;
        grid-template-columns: repeat(1,minmax(120px,1fr));
    }
}
</style>