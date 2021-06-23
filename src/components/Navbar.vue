<template>
    <nav>
        <div class="logo-container">
            <img src="../assets/images/university_logo.png" alt="University Logo">
        </div>
        <div class="menu-container">
            <ul>
                <li v-for="(menulink, index) in menuLinks" :key="index" :class="menulink.dropdown ? 'dropdown': ''"
                @click.prevent="setActiveLink(index)">
                    <a :href="menulink.url" :class="activeIndex == index ? 'active': ''">{{menulink.name}}
                        <span v-if="menulink.addOn" class="addOn">{{menulink.addOn}}</span>
                        <span  class="dropdown" v-if="menulink.dropdown">
                            <i class="fas fa-chevron-down"></i>
                            <div class="courses">
                                <div class="course">
                                    <CourseCard v-for="(card, index) in cards" :key="index"
                                    :allCards="card"/>
                                </div>
                                <div class="mega-menu">
                                    <img src="../assets/images/megamenu_courses_bg.jpg" alt="mega menu">
                                </div>
                            </div>
                        </span>
                    </a>
                </li>
            </ul>
        </div>
    </nav>
</template>

<script>
import CourseCard from './CourseCard.vue'

export default {
  components: {
      CourseCard
    },
    name: "Navbar",
    data: function() {
        return {
            menuLinks: [
                {
                    name: "home",
                    url: "home",
                    addOn: "",
                    dropdown: false
                },
                {
                    name: "about",
                    url: "about",
                    addOn: "",
                    dropdown: false
                },
                {
                    name: "courses",
                    url: "courses",
                    addOn: "new",
                    dropdown: true
                },
                {
                    name: "events",
                    url: "events",
                    addOn: "",
                    dropdown: false
                },
                {
                    name: "facilities",
                    url: "facilities",
                    addOn: "",
                    dropdown: false
                },
                {
                    name: "news",
                    url: "news",
                    addOn: "",
                    dropdown: false
                },
                {
                    name: "admissions",
                    url: "admissions",
                    addOn: "apply",
                    dropdown: false
                },
            ],
            cards: [
                {
                    img: "course_sports_portfolio_feat.jpg",
                    courseName: "Sports Course",
                    url: "sports-course"
                },
                {
                    img: "course_biology_portfolio_feat.jpg",
                    courseName: "Biology Course",
                    url: "biology-course"
                },
                {
                    img: "course_graphic_design_portfolio_feat.jpg",
                    courseName: "Graphic Course",
                    url: "graphic-course"
                },
                {
                    img: "course_physics_portfolio_feat.jpg",
                    courseName: "Physics Course",
                    url: "physics-ourse"
                },
                {
                    img: "english_seminar_event_feat.jpg",
                    courseName: "English Seminar",
                    url: "english-seminar"
                }
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
        justify-content: space-between;
        align-items: center;
        position: fixed;
        top: 40px;
        width: 100%;
        height: 105px;
        padding: 0px 50px;
        background-color: white;
        z-index: 1;
        

        li {
            padding: 40px 0;
        }

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
                font-size: 12px;
            }
            

            span.addOn {
                padding: 3px 10px;
                background-color: #52c7e1;
                color: white;
                border-radius: 5px;
            }
        }
        .dropdown .courses {
            display: flex;
            position: absolute;
            top: 105px;
            left: 2.5%;
            width: 95%;
            background-color: $section-bg;
            visibility: hidden;

            .course {
                display: flex;
                justify-content: center;
                flex-wrap: wrap;
                width: 70%;
                border-top: 5px solid $color-theme;
            }

            .mega-menu {
                width: 30%;

                img {
                    width: 100%;
                    height: 100%;
                }
            }

        }
        .dropdown:hover .courses{
            animation: visible 1s forwards;
            @keyframes visible {
                0% {
                    opacity: 0;
                    visibility: visible;
                }
                100% {
                    opacity: 1;
                    visibility: visible;
                }
            }
        }
    }

</style>