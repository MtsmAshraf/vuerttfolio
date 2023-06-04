<template>
    <div class="footer">
        <div class="container">
            <a href="#" class="logo link clickable">
                <h4 class="english" v-if="this.english">Moatasim</h4>
                <h4 class="arabic" v-if="this.arabic">معتصم</h4>
                <span>.</span>
            </a>
            <div class="copy english" v-if="this.english">
                © 2023 Proudly Made by: <a href="https://moatasim-ashraf.netlify.app/">Moatasim</a>
            </div>
            <div class="copy arabic" v-if="this.arabic">
                © 2023 تم تطويره بواسطة: <a href="https://moatasim-ashraf.netlify.app/">معتصم</a>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        name:"Footer",
        props:["english","arabic"],
    }
</script>

<style scoped>
.footer{
    padding-top: 20px;
    padding-bottom: 20px;
    background-color: var(--lighter-color);
    box-shadow: 0px 0px 20px 0px rgb(15, 15, 15);

}
.footer .container{
    display: flex;
    align-items: center;
    justify-content: space-between;
}
.footer .container .logo{
    display: flex;
    align-items: baseline;
    color: var(--text-color);
    font-size: 30px;
    font-family: "Vina Sans", sans-serif;
    letter-spacing: 2px;
}
.footer .container .logo span{
    color: var(--sec-color);
    font-size: 40px;
}
.footer .container .copy a{
    color: var(--sec-color);
    font-size: 20px;
    font-weight: bold;
}
@media (max-width:600px) {
    .footer .container{
        flex-direction: column;
    }
}
</style>