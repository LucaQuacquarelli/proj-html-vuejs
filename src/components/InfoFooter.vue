<template>
    <div class="info-container">
        <div class="info">
            <ul>
                <li v-for="(credit, index) in credits" :key="index">{{credit.name}}<span :class="credit.class ? 'none' : ''">|</span></li>
            </ul>
        </div>
        <div class="social-links">
            <ul>
                <li v-for="(social, index) in socials" :key="index">
                    <a :href="social.url"><i :class="`fab fa-${social.icon}`"></i></a>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: "InfoFooter",
    props: {
        socials: Array
    },
    data: function() {
        return {
            credits: [

                {
                    name: "© Theme Fusion",
                    class: false
                },
                {
                    name: "All Rights Reserved",
                    class: false
                },
                {
                    name: "Powered by Wordpress",
                    class: false
                },
                {
                    name: "support@theme-fusion.com",
                    class: false
                },
                {
                    name: "1.800.555.6789",
                    class: true
                }

            ]
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../style/variables";

    .info-container {
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 20px 50px;
        border-top: 1px solid $p-color;

        li {
            color: $p-color;
            font-size: 12px;
        }

        a {
            display: flex;
            align-items: center;
            transition: 0.3s;  
            color: $p-color;

            i {
                margin: 0 5px;
            }

            &:hover {
                color: rgba($p-color, 0.5);
            }
        }

        .info {
            li {
                margin: 0;

                span {
                    margin: 0 20px;

                    &.none {
                        display: none;
                    }
                }
            }
        }
    }

</style>