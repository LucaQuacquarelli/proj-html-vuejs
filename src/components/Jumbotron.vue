<template>
    <div class="jumbotron">
        <h1>{{title}}</h1>
        <h3>{{subtitle}}</h3>
        <div class="btn-container">
            <button class="find">find a course</button>
            <button class="apply">apply now</button>
        </div>
    </div>
</template>

<script>
export default {
    name: "Jumbotron",
    props: {
        title: String,
        subtitle: String
    }
}
</script>

<style lang="scss" scoped>
@import "../style/variables";

    .jumbotron {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        height: 100%;
        margin-top: 145px;
        background-image: url(../assets/images/home_main_slider_bg.jpg);
        background-size: cover;
        background-attachment: fixed;

        h1 {
            font-size: 70px;
        }

        h3 {
            font-size: 25px;
        }

        .btn-container {
            margin: 25px 0;

            button {
                margin: 0 15px;
                padding: 10px 20px;
                text-transform: uppercase;
                border: 0;
                cursor: pointer;
                color: white;
                transition: 0.3s;

                &.find {
                    background-color: $color-theme;
                }

                &.find:hover {
                    background-color: $font-color;
                }

                &.apply {
                    background-color: #00bcd4;
                }

                &.apply:hover {
                    background-color: white;
                    color: $font-color;
                }

            }

        }

    }

</style>