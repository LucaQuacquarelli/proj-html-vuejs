<template>
    <div class="card">
        <img :src="require(`../assets/images/${allCards.img}`)" :alt="allCards.courseName"> 
        <a :href="allCards.url">{{allCards.courseName}}</a>
    </div>
</template>

<script>
export default {
    name: "CourseCard",
    props: {
        allCards: Object
    }

}
</script>

<style lang="scss" scoped>
@import "../style/variables";

    .card {
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 20%;
        margin: 25px;

        
        img {
            width: 100%;
        }

        a {
            margin: 10px 0;
            font-size: 20px;
            text-transform: none;
            color: $color-theme;
        }
    }
</style>