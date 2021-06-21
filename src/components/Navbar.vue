<template>
    <nav>
        <div class="logo-container">
            <img src="../assets/images/university_logo.png" alt="University Logo">
        </div>
        <div class="menu-container">
            <ul>
                <li v-for="(menulink, index) in menuLinks" :key="index"
                @click.prevent="setActiveLink(index)">
                    <a :href="menulink.url" :class="activeIndex == index ? 'active': ''">{{menulink.name}}<span v-if="menulink.addOn">{{menulink.addOn}}</span></a>
                </li>
            </ul>
        </div>
    </nav>
</template>

<script>
export default {
    name: "Navbar",
    data: function() {
        return {
            menuLinks: [
                {
                    name: "home",
                    url: "home",
                    addOn: ""
                },
                {
                    name: "about",
                    url: "about",
                    addOn: ""
                },
                {
                    name: "courses",
                    url: "courses",
                    addOn: "new"
                },
                {
                    name: "events",
                    url: "events",
                    addOn: ""
                },
                {
                    name: "facilities",
                    url: "facilities",
                    addOn: ""
                },
                {
                    name: "news",
                    url: "news",
                    addOn: ""
                },
                {
                    name: "admissions",
                    url: "admissions",
                    addOn: "apply"
                },
            ],
            activeIndex: 0
        }
    },
    methods: {
        setActiveLink: function(newIndex) {
            this.activeIndex = newIndex
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../style/variables";
    nav {
        display: flex;
        justify-content: space-around;
        align-items: center;
        height: 120px;
        padding: 20px 0;
        background-color: white;

        a {
            display: flex;
            align-items: center;
            text-transform: uppercase;
            font-size: 14px;
            font-weight: 700;
            color: $font-color;
            transition: 0.3s;

            &:hover {
                color: $color-theme;
            }
            &.active{
                color: $color-theme;
            }

            span {
                margin: 0 5px;
                padding: 3px 10px;
                font-size: 12px;
                background-color: #52c7e1;
                color: white;
                border-radius: 5px;
            }
        }
    }

</style>