<template>
    <section>
        <a v-for="(section, index) in sections" :key="index"
        class="container"
        :class="section.class"
        :href="section.url">
            <h4>{{section.title}}</h4>
            <hr>
            <span>View More</span>
        </a>
    </section>
</template>

<script>
export default {
    name: "CourseSection",
    data: function() {
        return {
            sections: [
                {
                    title: "courses",
                    class: "course",
                    url: "more-courses"
                },
                {
                    title: "events",
                    class: "events",
                    url: "more-events"
                },
                {
                    title: "latest news",
                    class: "news",
                    url: "more-news"
                }
            ]
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../style/variables";

    section {
        display: flex;
        height: 700px;
        padding: 50px 0;
        background-color: $section-bg;

        .container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            width: 33.333%;
            height: 100%;
            background-size: cover;
            cursor: pointer;
            background-position: center;

            &:hover {
                animation: scale 1.5s forwards;
                @keyframes scale {
                    0% {
                        background-size: 100%;
                    }
                    100% {
                        background-size: 120%;
                    }
                }
            }

            h4 {
                text-transform: uppercase;
            }

            hr {
                width: 50px;
                margin: 25px 0;
                border: 1px solid $color-theme;
            }
        }

        .course {
            background-image: url(../assets/images/home_courses_section_bg.jpg);
        }
        .events {
            background-image: url(../assets/images/home_events_section_bg.jpg);
        }
        .news {
            background-image: url(../assets/images/home_latest_news_section_bg.jpg);
        }

    }
</style>