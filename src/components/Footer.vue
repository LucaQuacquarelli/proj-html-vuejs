<template>
    <footer>
        <div class="footer">
            <div class="container">
                <strong>avada university</strong>
                <div class="info" v-for="(info, index) in infos" :key="index">
                    <i :class="info.icon"></i>
                    <p :class="info.class">{{info.info}}</p>
                </div>
            </div>
            <div class="container">
                <strong>recent posts</strong>
                <div class="posts" v-for="(post, index) in posts" :key="index">
                    <i class="fas fa-chevron-right"></i>
                    <div class="post">
                        <a href="post">{{post.post}}</a>
                        <p>{{post.date}}</p>
                    </div>
                </div>
            </div>
            <div class="links container">
                <div class="links" v-for="(link, index) in links" :key="index">
                    <strong>{{link.category}}</strong>
                    <ul>
                        <li v-for="(link, index) in link.link" :key="index">
                            <a :href="link.url">{{link.name}}</a>
                        </li> 
                    </ul>
                </div>
            </div>
            <div class="container">
                <strong>Upcoming Events</strong>
                <div class="events" v-for="(event, index) in events" :key="index">
                    <div class="calendar">
                        <div class="day">
                            <strong>{{event.date.day}}</strong>
                        </div>
                        <div class="number">
                            <strong>{{event.date.dayNumber}}</strong>
                        </div>
                    </div>
                    <div class="event">
                        <a :href="event.link.url">{{event.link.name}}</a>
                        <p>{{event.duration}}</p>
                        <p>{{event.location}}</p>
                    </div>
                </div>
            </div>
        </div>
        <InfoFooter
        :socials="social"/>
    </footer>
</template>

<script>
import InfoFooter from './InfoFooter.vue'

export default {
  components: {
      InfoFooter
    },
    name: "Footer",
    props: {
        social: Array
    },
    data: function() {
        return {
            infos: [

                {
                    icon: "fas fa-home",
                    info: "Residential Location9521 Broadsberry Avenue Paddington RC7 9ZA",
                    class: "empty"
                },
                {
                    icon: "fas fa-phone",
                    info: "1.800.458.556",
                    class: "empty"
                },
                {
                    icon: "far fa-envelope",
                    info: "info@your-domain.com",
                    class: "mail"
                },
                {
                    icon: "far fa-clock",
                    info: "Monday – Friday: 8:00 AM – 10:00 PM",
                    class: "empty"
                }

            ],
            posts: [
                {
                    post: "What do successful grads think you should study?",
                    date: "March 16th, 2016"
                },
                {
                    post: "Former student discusses success in the fashion industry",
                    date: "March 15th, 2016"
                },
                {
                    post: "How do you best prepare for university?",
                    date: "March 15th, 2016"
                }
            ],
            links: [
                {
                    category: "courses",
                    link: [
                        {
                            name: "Art & Humanities",
                            url: "art-and-humanities"
                        },
                        {
                            name: "Business & Management",
                            url: "business-and-management"
                        },
                        {
                            name: "Engineering & Tecnology",
                            url: "engineering-and-tecnology"
                        },
                        {
                            name: "Life Sciences & Medicine",
                            url: "life-sciences-and-medicine"
                        },
                        {
                            name: "Natural Sciences",
                            url: "natural-sciences"
                        }
                    ]
                },
                {
                    category: "resources",
                    link: [
                        {
                            name: "Campus Directory",
                            url: "campus-directory"
                        },
                        {
                            name: "Academic Calendar",
                            url: "academic-calendar"
                        },
                        {
                            name: "Sport Clubs",
                            url: "sport-clubs"
                        },
                        {
                            name: "Graduate Programs",
                            url: "graduate-programs"
                        },
                        {
                            name: "Faculty & Staff",
                            url: "faculty-and-staff"
                        }
                    ]
                },
                {
                    category: "admissions",
                    link: [
                        {
                            name: "Elegibility",
                            url: "elegibility"
                        },
                        {
                            name: "Application",
                            url: "application"
                        },
                        {
                            name: "Review Process",
                            url: "review-process"
                        },
                        {
                            name: "How to Apply",
                            url: "how-to-apply"
                        },
                    ]
                },
                {
                    category: "quicklinks",
                    link: [
                        {
                            name: "University Library",
                            url: "university-library"
                        },
                        {
                            name: "Campus Services",
                            url: "campus-services"
                        },
                        {
                            name: "Careers",
                            url: "careers"
                        }
                    ]
                }
            ],
            events: [
                {
                    date: {
                        day: "Tue",
                        dayNumber: 22   
                    },
                    link: {
                        name: "Business Seminar",
                        url: "business-seminar"  
                    },
                    duration: "July 1, 2019 @ 8:00 am - July 1, 2021 @ 5:00 pm",
                    location: "United States"

                },
                {
                    date: {
                        day: "Tue",
                        dayNumber: 22   
                    },
                    link: {
                        name: "Politics Seminar",
                        url: "politics-seminar"  
                    },
                    duration: "November 6, 2019 @ 8:00am - November 6, 2021 @ 5:00 pm",
                    location: "United Kingdom"

                }
            ]
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../style/variables";

    .footer {
        display: flex;
        justify-content: space-between;
        padding: 50px;
        background-image: url(../assets/images/university_ft_bg.png);
        background-size: cover;

        .container {
            width: 20%;

            strong {
                text-transform: uppercase;
                color: $font-color;
            }

            i {
                color: $color-theme;
            }

            a {
                color: $color-theme;
            }

            .info {
                display: flex;
                align-items: baseline;
                padding: 15px;
                
                p {
                    margin: 0 10px;

                    &.mail {
                        color: $color-theme;
                    }
                }
            }
            
            .posts {
                display: flex;
                align-items: baseline;
                padding: 15px 0;
                border-bottom: 1px solid $p-color;
                
                .post {
                    margin: 0 10px;

                    p {
                        margin: 10px 0;
                    }
                }
            }

            .events {
                display: flex;
                margin: 10px 0;
                padding: 10px 0; 
                border-bottom: 1px dotted $p-color;

                .calendar {
                    width: 20%;
                    padding: 3px;
                    background-color: $color-theme;

                    .day {
                        display: flex;
                        justify-content: center;
                        align-items: center ;
                        width: 100%;
                        height: 60%;
                        background-color: white;

                        strong {
                            text-transform: uppercase;
                            color: $color-theme;
                        }
                    }
                    
                    .number {
                        display: flex;
                        justify-content: center;
                        align-items: center ;
                        padding: 5px 0;

                        strong {
                            color: white;
                        }
                    }
                }

                .event {
                    width: 80%;
                    margin: 0 10px;

                    p {
                        font-size: 12px;
                        margin: 5px 0;
                    }
                }
            }
        }

        .container.links {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;

            .links {
                width: 45%;
                margin-bottom: 20px;

                li {
                    display: block;
                    margin: 10px 0;
                }

                a {
                    font-size: 12px;
                    
                    &:hover {
                        text-decoration: underline;
                    }
                }

            }
        }
    }
</style>