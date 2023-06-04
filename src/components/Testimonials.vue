<template>
    <div class="testimonials">
        <div class="heading english" v-if="this.english">
            <span>TESTIMONIALS</span>
            <h3>Check What's My Clients Say About Me</h3>
        </div>
        <div class="heading arabic" v-if="this.arabic">
            <span>التوصيات</span>
            <h3>شاهد ماذا قال العملاء والمتخصصون عني؟</h3>
        </div>
        <div class="people">
            <div class="person xl">
                <div class="img"><img src="../assets/man-1.jpg" alt=""></div>
                <div class="person-details english" v-if="this.english">
                    <p>Excellent Team to work with. Always positive to find the most appropriate solution. Nafie is one of the professional web development agency that provides awesome services</p>
                    <h4>Lonny Corkery</h4>
                    <span>Project Manager</span>
                </div>
                <div class="person-details arabic" v-if="this.arabic">
                    <p>عمل محمد في عدد كبير من المشاريع لأجلنا وكان دائمًا يفوق توقعاتنا. مطور متخصص وموهوب ونسعد دائمًا بالعمل معه.</p>
                    <h4>عباس العنابي</h4>
                    <span>مدير مبيعات</span>
                </div>
            </div>
            <div class="person m">
                <div class="img"><img lazy src="../assets/man-2.jpg" alt=""></div>
                <div class="person-details english" v-if="this.english">
                    <p>Excellent Team to work with. Always positive to find the most appropriate solution. Nafie is one of the professional web development agency that provides awesome services</p>
                    <h4>Lonny Corkery</h4>
                    <span>Project Manager</span>
                </div>
                <div class="person-details arabic" v-if="this.arabic">
                    <p>عمل محمد في عدد كبير من المشاريع لأجلنا وكان دائمًا يفوق توقعاتنا. مطور متخصص وموهوب ونسعد دائمًا بالعمل معه.</p>
                    <h4>عباس العنابي</h4>
                    <span>مدير مبيعات</span>
                </div>
            </div>
            <div class="person xl">
                <div class="img"><img lazy src="../assets/man-3.jpg" alt=""></div>
                <div class="person-details english" v-if="this.english">
                    <p>Excellent Team to work with. Always positive to find the most appropriate solution. Nafie is one of the professional web development agency that provides awesome services</p>
                    <h4>Lonny Corkery</h4>
                    <span>Project Manager</span>
                </div>
                <div class="person-details arabic" v-if="this.arabic">
                    <p>عمل محمد في عدد كبير من المشاريع لأجلنا وكان دائمًا يفوق توقعاتنا. مطور متخصص وموهوب ونسعد دائمًا بالعمل معه.</p>
                    <h4>عباس العنابي</h4>
                    <span>مدير مبيعات</span>
                </div>
            </div>
            <div class="person s">
                <div class="img"><img lazy src="../assets/man-4.jpg" alt=""></div>
                <div class="person-details english" v-if="this.english">
                    <p>Excellent Team to work with. Always positive to find the most appropriate solution. Nafie is one of the professional web development agency that provides awesome services</p>
                    <h4>Lonny Corkery</h4>
                    <span>Project Manager</span>
                </div>
                <div class="person-details arabic" v-if="this.arabic">
                    <p>عمل محمد في عدد كبير من المشاريع لأجلنا وكان دائمًا يفوق توقعاتنا. مطور متخصص وموهوب ونسعد دائمًا بالعمل معه.</p>
                    <h4>عباس العنابي</h4>
                    <span>مدير مبيعات</span>
                </div>
            </div>
            <div class="person m">
                <div class="img"><img lazy src="../assets/man-6jpg.jpg" alt=""></div>
                <div class="person-details english" v-if="this.english">
                    <p>Excellent Team to work with. Always positive to find the most appropriate solution. Nafie is one of the professional web development agency that provides awesome services</p>
                    <h4>Lonny Corkery</h4>
                    <span>Project Manager</span>
                </div>iv>
                <div class="person-details arabic" v-if="this.arabic">
                    <p>عمل محمد في عدد كبير من المشاريع لأجلنا وكان دائمًا يفوق توقعاتنا. مطور متخصص وموهوب ونسعد دائمًا بالعمل معه.</p>
                    <h4>عباس العنابي</h4>
                    <span>مدير مبيعات</span>
                </div>
            </div>
            <div class="person xl">
                <div class="img"><img lazy src="../assets/man-6jpg.jpg" alt=""></div>
                <div class="person-details english" v-if="this.english">
                    <p>Excellent Team to work with. Always positive to find the most appropriate solution. Nafie is one of the professional web development agency that provides awesome services</p>
                    <h4>Lonny Corkery</h4>
                    <span>Project Manager</span>
                </div>iv>
                <div class="person-details arabic" v-if="this.arabic">
                    <p>عمل محمد في عدد كبير من المشاريع لأجلنا وكان دائمًا يفوق توقعاتنا. مطور متخصص وموهوب ونسعد دائمًا بالعمل معه.</p>
                    <h4>عباس العنابي</h4>
                    <span>مدير مبيعات</span>
                </div>
            </div>
            <div class="person s">
                <div class="img"><img lazy src="../assets/man-7.jpg" alt=""></div>
                <div class="person-details english" v-if="this.english">
                    <p>Excellent Team to work with. Always positive to find the most appropriate solution. Nafie is one of the professional web development agency that provides awesome services</p>
                    <h4>Lonny Corkery</h4>
                    <span>Project Manager</span>
                </div>
                <div class="person-details arabic" v-if="this.arabic">
                    <p>عمل محمد في عدد كبير من المشاريع لأجلنا وكان دائمًا يفوق توقعاتنا. مطور متخصص وموهوب ونسعد دائمًا بالعمل معه.</p>
                    <h4>عباس العنابي</h4>
                    <span>مدير مبيعات</span>
                </div>
            </div>
            <div class="person m">
                <div class="img"><img lazy src="../assets/man-8.jpg" alt=""></div>
                <div class="person-details english" v-if="this.english">
                    <p>Excellent Team to work with. Always positive to find the most appropriate solution. Nafie is one of the professional web development agency that provides awesome services</p>
                    <h4>Lonny Corkery</h4>
                    <span>Project Manager</span>
                </div>
                <div class="person-details arabic" v-if="this.arabic">
                    <p>عمل محمد في عدد كبير من المشاريع لأجلنا وكان دائمًا يفوق توقعاتنا. مطور متخصص وموهوب ونسعد دائمًا بالعمل معه.</p>
                    <h4>عباس العنابي</h4>
                    <span>مدير مبيعات</span>
                </div>
            </div>
            <div class="person xl">
                <div class="img"><img lazy src="../assets/man-9.jpg" alt=""></div>
                <div class="person-details english" v-if="this.english">
                    <p>Excellent Team to work with. Always positive to find the most appropriate solution. Nafie is one of the professional web development agency that provides awesome services</p>
                    <h4>Lonny Corkery</h4>
                    <span>Project Manager</span>
                </div>
                <div class="person-details arabic" v-if="this.arabic">
                    <p>عمل محمد في عدد كبير من المشاريع لأجلنا وكان دائمًا يفوق توقعاتنا. مطور متخصص وموهوب ونسعد دائمًا بالعمل معه.</p>
                    <h4>عباس العنابي</h4>
                    <span>مدير مبيعات</span>
                </div>
            </div>
            <div class="person l">
                <div class="img"><img lazy src="../assets/man-10.jpg" alt=""></div>
                <div class="person-details english" v-if="this.english">
                    <p>Excellent Team to work with. Always positive to find the most appropriate solution. Nafie is one of the professional web development agency that provides awesome services</p>
                    <h4>Lonny Corkery</h4>
                    <span>Project Manager</span>
                </div>>
                <div class="person-details arabic" v-if="this.arabic">
                    <p>عمل محمد في عدد كبير من المشاريع لأجلنا وكان دائمًا يفوق توقعاتنا. مطور متخصص وموهوب ونسعد دائمًا بالعمل معه.</p>
                    <h4>عباس العنابي</h4>
                    <span>مدير مبيعات</span>
                </div>
            </div>
            <div class="person l">
                <div class="img"><img lazy src="../assets/man-11.jpg" alt=""></div>
                <div class="person-details english" v-if="this.english">
                    <p>Excellent Team to work with. Always positive to find the most appropriate solution. Nafie is one of the professional web development agency that provides awesome services</p>
                    <h4>Lonny Corkery</h4>
                    <span>Project Manager</span>
                </div>>
                <div class="person-details arabic" v-if="this.arabic">
                    <p>عمل محمد في عدد كبير من المشاريع لأجلنا وكان دائمًا يفوق توقعاتنا. مطور متخصص وموهوب ونسعد دائمًا بالعمل معه.</p>
                    <h4>عباس العنابي</h4>
                    <span>مدير مبيعات</span>
                </div>
            </div>
            <div class="person s">
                <div class="img"><img lazy src="../assets/man-12.jpg" alt=""></div>
                <div class="person-details english" v-if="this.english">
                    <p>Excellent Team to work with. Always positive to find the most appropriate solution. Nafie is one of the professional web development agency that provides awesome services</p>
                    <h4>Lonny Corkery</h4>
                    <span>Project Manager</span>
                </div>>
                <div class="person-details arabic" v-if="this.arabic">
                    <p>عمل محمد في عدد كبير من المشاريع لأجلنا وكان دائمًا يفوق توقعاتنا. مطور متخصص وموهوب ونسعد دائمًا بالعمل معه.</p>
                    <h4>عباس العنابي</h4>
                    <span>مدير مبيعات</span>
                </div>
            </div>
            <div class="person m">
                <div class="img"><img lazy src="../assets/man-13.jpg" alt=""></div>
                <div class="person-details english" v-if="this.english">
                    <p>Excellent Team to work with. Always positive to find the most appropriate solution. Nafie is one of the professional web development agency that provides awesome services</p>
                    <h4>Lonny Corkery</h4>
                    <span>Project Manager</span>
                </div>>
                <div class="person-details arabic" v-if="this.arabic">
                    <p>عمل محمد في عدد كبير من المشاريع لأجلنا وكان دائمًا يفوق توقعاتنا. مطور متخصص وموهوب ونسعد دائمًا بالعمل معه.</p>
                    <h4>عباس العنابي</h4>
                    <span>مدير مبيعات</span>
                </div>
            </div>
            <div class="person l">
                <div class="img"><img lazy src="../assets/man-14.jpg" alt=""></div>
                <div class="person-details english" v-if="this.english">
                    <p>Excellent Team to work with. Always positive to find the most appropriate solution. Nafie is one of the professional web development agency that provides awesome services</p>
                    <h4>Lonny Corkery</h4>
                    <span>Project Manager</span>
                </div>>
                <div class="person-details arabic" v-if="this.arabic">
                    <p>عمل محمد في عدد كبير من المشاريع لأجلنا وكان دائمًا يفوق توقعاتنا. مطور متخصص وموهوب ونسعد دائمًا بالعمل معه.</p>
                    <h4>عباس العنابي</h4>
                    <span>مدير مبيعات</span>
                </div>
            </div>
            <div class="person m">
                <div class="img"><img lazy src="../assets/man-15.jpg" alt=""></div>
                <div class="person-details english" v-if="this.english">
                    <p>Excellent Team to work with. Always positive to find the most appropriate solution. Nafie is one of the professional web development agency that provides awesome services</p>
                    <h4>Lonny Corkery</h4>
                    <span>Project Manager</span>
                </div>>
                <div class="person-details arabic" v-if="this.arabic">
                    <p>عمل محمد في عدد كبير من المشاريع لأجلنا وكان دائمًا يفوق توقعاتنا. مطور متخصص وموهوب ونسعد دائمًا بالعمل معه.</p>
                    <h4>عباس العنابي</h4>
                    <span>مدير مبيعات</span>
                </div>
            </div>
            <div class="person m">
                <div class="img"><img lazy src="../assets/man-16.jpg" alt=""></div>
                <div class="person-details english" v-if="this.english">
                    <p>Excellent Team to work with. Always positive to find the most appropriate solution. Nafie is one of the professional web development agency that provides awesome services</p>
                    <h4>Lonny Corkery</h4>
                    <span>Project Manager</span>
                </div>>
                <div class="person-details arabic" v-if="this.arabic">
                    <p>عمل محمد في عدد كبير من المشاريع لأجلنا وكان دائمًا يفوق توقعاتنا. مطور متخصص وموهوب ونسعد دائمًا بالعمل معه.</p>
                    <h4>عباس العنابي</h4>
                    <span>مدير مبيعات</span>
                </div>
            </div>
            <div class="person s">
                <div class="img"><img lazy src="../assets/man-17.jpg" alt=""></div>
                <div class="person-details english" v-if="this.english">
                    <p>Excellent Team to work with. Always positive to find the most appropriate solution. Nafie is one of the professional web development agency that provides awesome services</p>
                    <h4>Lonny Corkery</h4>
                    <span>Project Manager</span>
                </div>>
                <div class="person-details arabic" v-if="this.arabic">
                    <p>عمل محمد في عدد كبير من المشاريع لأجلنا وكان دائمًا يفوق توقعاتنا. مطور متخصص وموهوب ونسعد دائمًا بالعمل معه.</p>
                    <h4>عباس العنابي</h4>
                    <span>مدير مبيعات</span>
                </div>
            </div>
            <div class="person s">
                <div class="img"><img lazy src="../assets/man-18.jpg" alt=""></div>
                <div class="person-details english" v-if="this.english">
                    <p>Excellent Team to work with. Always positive to find the most appropriate solution. Nafie is one of the professional web development agency that provides awesome services</p>
                    <h4>Lonny Corkery</h4>
                    <span>Project Manager</span>
                </div>>
                <div class="person-details arabic" v-if="this.arabic">
                    <p>عمل محمد في عدد كبير من المشاريع لأجلنا وكان دائمًا يفوق توقعاتنا. مطور متخصص وموهوب ونسعد دائمًا بالعمل معه.</p>
                    <h4>عباس العنابي</h4>
                    <span>مدير مبيعات</span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name:"Testimonials",
        props:["english","arabic"],
    }
</script>

<style scoped>
.testimonials{
    padding-top: 100px;
    padding-bottom: 100px;
}
.testimonials .heading{
    width: fit-content;
    text-align: center;
    margin-right: auto;
    margin-left: auto;
    margin-bottom: 30px;
}
.testimonials .heading span{
    color: var(--sec-text-color);
}
.testimonials .heading h3{
    margin-top: 20px;
    font-size: 30px;
    font-weight: 800;
    width: 400px;
}
.testimonials .people{
    position: relative;
    min-height: 100vh;
    overflow: hidden;
}
.testimonials .people .person{
    position: absolute  ;
    aspect-ratio: 1/1;
    border-radius: 50%;
    box-shadow: 0px 0px 20px 10px rgb(15, 15, 15);
    animation: person-animation 10s linear 0s infinite alternate;
}
.testimonials .people .person:nth-child(1){
    left: 40px;
    top: 100px;
    animation-delay: 2s;
}
.testimonials .people .person:nth-child(2){
    left: 200px;
    animation-delay: 1s;
    top: 20px;
}
.testimonials .people .person:nth-child(3){
    animation-delay: 4s;
    left: 500px;
    top: 20px;
}
.testimonials .people .person:nth-child(4){
    right: 200px;
    animation-delay: 2s;
    top: 70px;
}
.testimonials .people .person:nth-child(5){
    left: 800px;
    animation-delay: 4s;
    top: 20px;
}
.testimonials .people .person:nth-child(6){
    animation-delay: 1s;
    left: 700px;
    top: 250px;
}
.testimonials .people .person:nth-child(7){
    animation-delay: 2s;
    left: 300px;
    top: 300px;
}
.testimonials .people .person:nth-child(8){
    left: 40px;
    animation-delay: 4s;
    top: 330px;
}
.testimonials .people .person:nth-child(9){
    animation-delay: 2s;
    right: 400px;
    top: 330px;
}
.testimonials .people .person:nth-child(10){
    left: 440px;
    animation-delay: 4s;
    top: 270px;
}
.testimonials .people .person:nth-child(11){
    right: 50px;
    animation-delay: 2s;
    top: 300px;
}
.testimonials .people .person:nth-child(12){
    bottom:40px;
    animation-delay: 1s;
    left: 100px;
}
.testimonials .people .person:nth-child(13){
    bottom:40px;
    animation-delay: 3s;
    left:400px;
}
.testimonials .people .person:nth-child(14){
    bottom:40px;
    animation-delay: 3s;
    right: 150px;
}
.testimonials .people .person:nth-child(15){
    animation-delay: 3s;
    bottom: 100px;
    right: 400px;
}
.testimonials .people .person:nth-child(16){
    bottom:200px;
    animation-delay: 3s;
    left:200px;
}
.testimonials .people .person:nth-child(17){
    right: 250px;
    animation-delay: 0s;
    top: 200px;
}
.testimonials .people .person:nth-child(18){
    bottom: 100px;
    animation-delay: 1s;
    right: 700px;
}
.testimonials .people .person .img{
    overflow: hidden;
    border-radius: 50%;
    width: 100%;
    aspect-ratio: 1/1;
    display: flex;
    align-items: center;
    justify-content: center;
}   
.testimonials .people .person .img img{
    transform: scale(1.5);
}
.testimonials .people .person.xl{
    width: 200px;
}
.testimonials .people .person.l{
    width: 150px;
}
.testimonials .people .person.m{
    width: 100px;
}
.testimonials .people .person.s{
    width: 70px;
}
.testimonials .people .person .person-details{
    display: none;
}
@media (max-width:1400px) {
    .testimonials .people{
        display: grid;
        grid-template-columns: repeat(4,1fr);
        place-items: center;
        gap: 20px;
    }
    .testimonials .people .person{
        position: initial;
        animation: none;
        display: flex;
        justify-content: center;
        align-items: center;
    }
}
@media (max-width:992px) {
    .testimonials .people{
        grid-template-columns: repeat(3,1fr);
    }
}
@media (max-width:767px) {
    .testimonials .people{
        grid-template-columns: repeat(2,1fr);
    }
    .testimonials .people .person.xl{
        width: 150px;
    }
}
@keyframes person-animation {
    0%{
        transform: translate(0px,10px);
    }
    25%{
        transform: translate(10px,10px);
    }
    50%{
        transform: translate(0px,-10px);
    }
    100%{
        transform: translate(0px,0px);
    }
}
</style>