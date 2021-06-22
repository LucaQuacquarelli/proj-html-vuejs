<template>
    <section>
        <div class="section-title">
            <img src="../assets/images/page-logo-1.png" alt="university logo">
            <h2>{{title}}</h2>
            <p>{{subtitle}}</p>
            <hr>
        </div>
        <div class="section-content">
            <div class="news-card" v-for="(news, index) in newsCards" :key="index"  @click.prevent="setCount(index)">
                <img :src="require(`../assets/images/${news.img}`)" :alt="`${news.author} photo`">
                <div class="share">
                    <div class="icon">
                        <i class="fas fa-link"></i>
                        <i class="fas fa-search"></i>
                    </div>
                </div>
                <div class="info-news">
                    <div class="title">
                        <h3>{{news.title}}</h3>
                        <p>By <span>{{news.author}}</span> | {{news.date}}</p>
                    </div>
                    <div class="read">
                        <a href="read-more">Read More ></a>
                        <i class="far fa-comments"><span>{{news.readCount}}</span></i>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: "NewsSection",
    props: {
        title: String,
        subtitle: String
    },
    data: function() {
        return {
            newsCards: [
                {
                    img: "news_single_post_header_1.jpg",
                    title: "What do successful grads think you should study?",
                    author: "admin",
                    date: "March 16th, 2016",
                    readCount: 0
                },
                {
                    img: "news_single_post_header_2.jpg",
                    title: "Former student discusses success in the fashion industry",
                    author: "admin",
                    date: "March 15th, 2016",
                    readCount: 0
                },
                {
                    img: "news_single_post_header_3.jpg",
                    title: "How do you best prepare for university?",
                    author: "admin",
                    date: "March 15th, 2016",
                    readCount: 0
                },
            ]
            
        }
    },
    methods: {
        setCount: function(index) {
            this.newsCards[index].readCount = this.newsCards[index].readCount + 1
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../style/variables";
@import "../style/mixins";

    section {
        background-color: $section-bg;
        @include section-default;

        .section-content {
            display: flex;
            justify-content: space-between;
            margin: 40px 0;

            .news-card {
                position: relative;
                width: 30%;
                height: 100%;
                background-color: white;
                cursor: pointer;

                &:hover .share {
                    display: block;
                }
                
                img {
                    width: 100%;
                }
                
                .share {
                    display: none;
                    position: absolute;
                    top: 0;
                    width: 100%;
                    height: 55%;
                    background-color: rgba($color-theme, 0.8);

                        
                    .icon {
                        position: absolute;
                        top: 50%;
                        left: 50%;
                        transform: translate(-50%, -50%);
                        
                        i {
                            margin: 0 5px ;
                            font-size: 20px;
                        }
                    }

                }

                .info-news {
                    padding: 20px;
                    color: $color-theme;

                    p {
                        margin: 15px 0;

                        span {
                            color: $color-theme;
                        }
                    }
                    
                    .read {
                        display: flex;
                        justify-content: space-between;

                        a {
                            color: $color-theme;

                            &:hover {
                                text-decoration: underline;
                            }
                        }

                        span {
                            margin-left: 5px;
                        }
                        
                        
                    }
                }


            }
        }
    }    
</style>