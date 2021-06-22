<template>
    <section>
        <div class="section-title">
            <img src="../assets/images/page-logo-1.png" alt="university logo">
            <h2>{{title}}</h2>
            <p>{{subtitle}}</p>
            <hr>
        </div>
        <div class="section-content">
            <div class="text">
                <h3>why choose avada university?</h3>
                <p>
                    We offer a range of training packages in a range of subject areas and can offer blended learning opportunities to best meet your needs. If sitting in a room with a trainer and having the opportunity for discussion with other learners sounds good to you then we can offer this.
                </p>
                <p>
                    If you prefer to study in your own time and at your own speed then one of our world class facilities. If you prefer to study in your own time and at your own speed then one of our e-learning packages may be right up your street. There is a third option, which is you like the sound of both but perhaps can’t attend all training sessions, this is when blended learning comes into its own.
                </p>
            </div>
            <div class="video">
                <iframe src="https://player.vimeo.com/video/80567526" allowfullscreen></iframe>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: "AboutSection",
    props: {
        title: String,
        subtitle: String
    }
}
</script>

<style lang="scss" scoped>
@import "../style/variables";

    section {
        padding: 50px;

        .section-title {
            display: flex;
            flex-direction: column;
            align-items: center;

            h2 {
                margin: 15px 0;
                color: $font-color;
            }

            p {
                font-size: 20px;
            }

            hr {
                width: 100px;
                margin: 25px 0;
                border: 1px solid $color-theme;
            }

        }

        .section-content {
            display: flex;
            justify-content: space-around;
            margin: 40px 0;

            .text {
                width: 50%;

                h3 {
                    text-transform: uppercase;
                    color: $font-color;
                }

                p {
                    margin: 20px 0;
                }
            }

            .video {
                width: 30%;
                height: 200px;
                margin: 20px 0;

                iframe {
                    width: 100%;
                    height: 100%;
                    border: 0;
                }

            }
        }

    }
</style>