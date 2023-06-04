<template>
    <div class="contact">
        <div class="container">
            <div class="text">
                <div class="main-text">
                    <div class="main-heading scroll-animated scale">
                        <h4 class="english" v-if="this.english">Contact</h4>
                        <h4 class="arabic" v-if="this.arabic">اتصل بي</h4>
                    </div>
                    <h2 class="scroll-animated translate english" v-if="this.english">Have You Any Project? Please Drop a Message</h2>
                    <h2 class="scroll-animated translate arabic" v-if="this.arabic">هل لديك اي مشروع؟ الرجاء ترك رسالة</h2>
                    <p class="scroll-animated translate english" v-if="this.english">Get in touch and let me know how i can help. Fill out the form and i’ll be in touch as soon as possible.</p>
                    <p class="scroll-animated translate arabic" v-if="this.arabic">تواصل معي واسمح لي أن أعرف كيف يمكنني المساعدة. املأ النموذج وسأكون على تواصل في أقرب وقت ممكن.</p>
                </div>
                <ul class="contacts">
                    <li class="scroll-animated translate">
                        <div class="icon"><font-awesome-icon icon="fa-solid fa-location-dot" /></div>
                        <div class="contact-text">
                            <h4 class="english" v-if="this.english">Address:</h4>
                            <h4 class="arabic" v-if="this.arabic">العنوان:</h4>
                            <p class="english" v-if="this.english">941 Saqrqorish Road, alandalos, grnata, wa 47122-4194</p>
                            <p class="arabic" v-if="this.arabic">941 طريق صقر قريش ، الأندلس ، غرناطة ، WA 47122-4194</p>
                        </div>
                    </li>
                    <li class="scroll-animated translate">
                        <div class="icon"><font-awesome-icon icon="fa-solid fa-phone" /></div>
                        <div class="contact-text">
                            <h4 class="english" v-if="this.english">Phone:</h4>
                            <h4 class="arabic" v-if="this.arabic">الهاتف:</h4>
                            <p>(02) 966 202 290</p>
                            <p>(02) 966 202 291</p>
                        </div>
                    </li>
                    <li class="scroll-animated translate">
                        <div class="icon"><font-awesome-icon icon="fa-solid fa-envelope" /></div>
                        <div class="contact-text">
                            <h4 class="english" v-if="this.english">Email:</h4>
                            <h4 class="arabic" v-if="this.arabic">البريد الإلكتروني:</h4>
                            <p>mo32000a@gmail.com</p>
                            <p>mo32000a@gmail.com</p>
                        </div>
                    </li>
                </ul>
                <div class="social-media">
                    <a href="#" class="social-icon scroll-animated translate"><font-awesome-icon icon="fa-brands fa-facebook-f" /></a>
                    <a href="#" class="social-icon scroll-animated translate"><font-awesome-icon icon="fa-brands fa-twitter" /></a>
                    <a href="#" class="social-icon scroll-animated translate"><font-awesome-icon icon="fa-brands fa-linkedin-in" /></a>
                    <a href="#" class="social-icon scroll-animated translate"><font-awesome-icon icon="fa-brands fa-youtube" /></a>
                </div>
            </div>
            <div class="msg">
                <form class="scroll-animated translate" action="">
                    <div>
                        <label class="scroll-animated translate english" v-if="this.english" for="">Name</label>
                        <label class="scroll-animated translate arabic" v-if="this.arabic" for="">الاسم الكامل</label>
                        <div class="input scroll-animated translate english" v-if="this.english">
                            <font-awesome-icon class="input-icon" icon="fa-solid fa-user" />
                            <input type="text" placeholder="e.g. John Doe" required>
                        </div>
                        <div class="input scroll-animated translate arabic" v-if="this.arabic">
                            <font-awesome-icon class="input-icon" icon="fa-solid fa-user" />
                            <input type="text" placeholder="مثال: فلان الفلاني" required>
                        </div>
                    </div>
                    <div>
                        <label class="scroll-animated translate english" v-if="this.english" for="">Email</label>
                        <label class="scroll-animated translate arabic" v-if="this.arabic" for="">البريد الالكتروني</label>
                        <div class="input scroll-animated translate english" v-if="this.english">
                            <font-awesome-icon class="input-icon" icon="fa-solid fa-envelope" />
                            <input type="email" placeholder="e.g. JohnDoe@gmail.com" required>
                        </div>
                        <div class="input scroll-animated translate arabic" v-if="this.arabic">
                            <font-awesome-icon class="input-icon" icon="fa-solid fa-envelope" />
                            <input type="email" placeholder="مثل: JohnDoe@gmail.com" required>
                        </div>
                    </div>
                    <div>
                        <label class="scroll-animated translate english" v-if="this.english" for="">Phone <span>(Optional)</span></label>
                        <label class="scroll-animated translate arabic" v-if="this.arabic" for="">الهاتف <span>(اختياري)</span></label>
                        <div class="input scroll-animated translate english" v-if="this.english">
                            <font-awesome-icon class="input-icon" icon="fa-solid fa-phone" />
                            <input type="text" placeholder="Phone Number">
                        </div>
                        <div class="input scroll-animated translate arabic" v-if="this.arabic">
                            <font-awesome-icon class="input-icon" icon="fa-solid fa-phone" />
                            <input type="text" placeholder="رقم الهاتف">
                        </div>
                    </div>
                    <div>
                        <label class="scroll-animated translate english" v-if="this.english" for="">Message</label>
                        <label class="scroll-animated translate arabic" v-if="this.arabic" for="">الرسالة</label>
                        <div class="input scroll-animated translate english" v-if="this.english">
                            <font-awesome-icon class="input-icon" icon="fa-solid fa-comments" />
                            <textarea type="text" placeholder="Write Message..." required></textarea>
                        </div>
                        <div class="input scroll-animated translate arabic" v-if="this.arabic">
                            <font-awesome-icon class="input-icon" icon="fa-solid fa-comments" />
                            <textarea type="text" placeholder="اكتب رسالتك..." required></textarea>
                        </div>
                    </div>
                    <input type="submit" class="scroll-animated translate english" v-if="this.english" value="Submit">
                    <input type="submit" class="scroll-animated translate arabic" v-if="this.arabic" value="إرسال">
                </form>
            </div>
        </div>
    </div>
</template>

<script>
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
    export default {
        name:"Contact",
        components:{
            FontAwesomeIcon
        },
        props:["english","arabic"],
    }
</script>

<style scoped>
.contact{
    padding-top: 100px;
    padding-bottom: 100px;
}
.contact .container{
    display: flex;
    align-items: center;
    justify-content: space-between;
    gap: 20px;
}
.contact .container > div:first-child{
    width: 60%;
}
.contact .container > div:last-child{
    width: 40%;
}
.contact .container .text ul{
    margin-top: 30px;
    margin-bottom: 30px;
    display: flex;
    flex-direction: column;
    gap: 20px;
}
.contact .container .text ul li{
    display: flex;
    gap: 15px;
}
.contact .container .text ul li .icon{
    color: var(--sec-text-color);
    font-size: 22px;
}
.contact .container .text ul li .contact-text h4{
    font-weight: 800;
    margin-bottom: 10px;
}
.contact .container .text ul li .contact-text p{
    color: var(--sec-text-color);
    margin-bottom: 5px;
}
.contact .container .text .social-media{
    display: flex;
    align-items: center;
    gap: 20px;
}
.contact .container .text .social-media > *{
    background-color: var(--text-color);
    width: 35px;
    aspect-ratio: 1/1;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    color: var(--bg-color);
    transition: var(--main-transition);
    transition-duration: 0.3s;
}
.contact .container .text .social-media > *:hover{
    background-color: var(--sec-color);
    color: var(--text-color);
}
.contact .container form{
    margin-left: auto;
    margin-right: auto;
    width: 450px;
    max-width: 100%;
    box-shadow: 0px 0px 20px 0px rgb(15, 15, 15);
    background-color: var(--lighter-color);
    padding: 20px;
    border-radius: 15px;
}
.contact .container form div{
    margin-bottom: 20px;
}
.contact .container form div label{
    font-size: 14px;
    font-weight: 800;
    margin-bottom: 10px;
    display: block;
}
.contact .container form div label span{
    color: var(--sec-text-color);
    font-style:italic;
}
.contact .container form div .input{
    position: relative;
}
.contact .container form div .input .input-icon{
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    left: 10px;
    z-index: 2;
}
.contact .container form div .input:has(textarea) .input-icon{
    top: 10px;
    transform: translateY(0%);
}
.contact .container form div .input input,
.contact .container form div .input textarea{
    width: 100%;
    padding: 10px 20px 10px 40px;
    background-color: var(--bg-color);
    border-radius: 10px;
    border: none;
    transition: var(--main-transition);
    transition-duration: 0.2s;
    color: var(--text-color);
    font-size: 16px;
}
.contact .container form div .input textarea{
    height: 100px;
    resize: none;
}
.contact .container form div .input input:focus{
    outline: none;
    box-shadow: 0px 0px 0px 1px var(--sec-color);
}
.contact .container form input[type="submit"]{
    width: 100%;
    background-color: var(--text-color);
    color: var(--bg-color);
    border-radius: 10px;
    cursor: pointer;
    padding: 10px 20px;
    font-weight: bold;
    text-transform: uppercase;
}
.contact .container form textarea:focus,
.contact .container form input[type="submit"]:focus{
    outline: none;
    box-shadow: 0px 0px 0px 1px var(--sec-color);
}
@media (max-width:767px) {
    .contact .container{
        flex-direction: column;
        gap: 40px;
    }
    .contact .container > div:first-child{
        width: 100%;
    }
    .contact .container > div:last-child{
        width: 100%;
    }
    .contact .container .text ul {
        text-align: center;
    }
    .contact .container .text ul li{
        width: 100%;
        justify-content: center;
        flex-direction: column;
    }
    .contact .container .text .social-media{
        margin-left: auto;
        margin-right: auto;
        width: fit-content;
    }
}
</style>