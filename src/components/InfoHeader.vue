<template>
    <div class="info-container">
        <div class="info">
            <ul>
                <li v-for="(info, index) in infos" :key="index">
                    <a :href="info.url"><i :class="`fas fa-${info.icon}`"></i>{{info.nameLink}} <span v-if="info.available">{{info.available}}</span> </a>
                </li>
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
    name: "InfoHeader",
    data: function() {
        return {
            infos: [
                {
                    icon: "phone",
                    nameLink: "1.800.567.8910",
                    url: "phone",
                    available: "24hrs"
                },
                {
                    icon: "envelope",
                    nameLink: "Contact Us",
                    url: "mail",
                    available: ""
                },
                {
                    icon: "graduation-cap",
                    nameLink: "Alumni",
                    url: "alumni",
                    available: ""
                },
                {
                    icon: "landmark",
                    nameLink: "Campus",
                    url: "campus",
                    available: ""
                },

            ]
        }
    },
    props: {
      socials: Array
    },

}
</script>

<style lang="scss" scoped>
@import "../style/variables";
@import "~@fortawesome/fontawesome-free/css/all.min.css";

    .info-container {
        display: flex;
        justify-content: space-around;
        align-items: center;
        height: 40px;
        background-color: $color-theme;

            a {
                display: flex;
                align-items: center;
                transition: 0.3s;
                font-size: 12px;

                i {
                    margin: 0 5px;
                }

                span {
                    margin: 0 5px;
                    padding: 3px 8px;
                    background-color: rgba(0, 0, 0, 0.1);
                    border-radius: 5px;
                    font-size: 10px;
                }

                &:hover {
                    color: rgba(255, 255, 255, 0.8);
                }
            }
        
    }

</style>