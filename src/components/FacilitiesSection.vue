<template>
    <section>
        <div class="content">
            <div class="facilities-container">
                <h3>world class facilities</h3>
                <p>Avada University is devoted to excellence in teaching, learning, and research, and developing leaders in many disciplines who make a difference globally.</p>
                <div class="facilities" v-for="(facility, index) in facilities" :key="index">
                    <i :class="facility.icon"></i>
                    <strong>{{facility.name}}</strong>
                    <p>- {{facility.target}}</p>
                </div>
                <p>If you prefer to study in your own time and at your own speed then one of our e-learning packages may be right up your street.</p>
            </div>
            <div class="our-values">
                <h3>our values</h3>
                <div class="task" v-for="(task, index) in tasks" :key="index">
                    <div class="btn" @click="openTask(index)">
                        <i class="fas" :class="task.status ? 'fa-times' : 'fa-plus'"></i>
                        <strong>our {{task.name}}</strong>
                    </div>
                    <div class="text" v-if="task.status">{{task.task}}</div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    name: "FacilitiesSection",
    data: function() {
        return {
            facilities: [
                {
                    icon: "fas fa-globe",
                    name: "International focus",
                    target: "our students come from across the globe"
                },
                {
                    icon: "fas fa-graduation-cap",
                    name: "Residential courses",
                    target: "we encourage learning and growth"
                },
                {
                    icon: "far fa-address-book",
                    name: "People not profits",
                    target: "education is a right not a privilege"
                }
            ],
            tasks: [
                {
                    name: "mission",
                    task: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Omnis sint non maxime facere in tenetur quibusdam molestiae asperiores. Aspernatur nesciunt praesentium magni fugit dolorum, quasi ullam expedita, dignissimos quaerat ad sint! Unde modi provident reiciendis ab totam. Consequuntur fugiat minima dolore eligendi. Quam sed ullam quas voluptatem? Maiores, suscipit impedit.",
                    status: false
                },
                {
                    name: "philosophy",
                    task: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Omnis sint non maxime facere in tenetur quibusdam molestiae asperiores. Aspernatur nesciunt praesentium magni fugit dolorum, quasi ullam expedita, dignissimos quaerat ad sint! Unde modi provident reiciendis ab totam. Consequuntur fugiat minima dolore eligendi. Quam sed ullam quas voluptatem? Maiores, suscipit impedit.",
                    status: false
                },
                {
                    name: "commitment",
                    task: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Omnis sint non maxime facere in tenetur quibusdam molestiae asperiores. Aspernatur nesciunt praesentium magni fugit dolorum, quasi ullam expedita, dignissimos quaerat ad sint! Unde modi provident reiciendis ab totam. Consequuntur fugiat minima dolore eligendi. Quam sed ullam quas voluptatem? Maiores, suscipit impedit.",
                    status: false
                },
                {
                    name: "promise",
                    task: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Omnis sint non maxime facere in tenetur quibusdam molestiae asperiores. Aspernatur nesciunt praesentium magni fugit dolorum, quasi ullam expedita, dignissimos quaerat ad sint! Unde modi provident reiciendis ab totam. Consequuntur fugiat minima dolore eligendi. Quam sed ullam quas voluptatem? Maiores, suscipit impedit.",
                    status: false
                },
                {
                    name: "values",
                    task: "Lorem ipsum dolor sit amet consectetur adipisicing elit. Omnis sint non maxime facere in tenetur quibusdam molestiae asperiores. Aspernatur nesciunt praesentium magni fugit dolorum, quasi ullam expedita, dignissimos quaerat ad sint! Unde modi provident reiciendis ab totam. Consequuntur fugiat minima dolore eligendi. Quam sed ullam quas voluptatem? Maiores, suscipit impedit.",
                    status: false
                },
            ]
            
        }
    },
    methods: {
        openTask: function(index) {
            this.tasks[index].status = !this.tasks[index].status
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../style/variables";

    section {
        padding: 50px;
        background-color: $section-bg;

        .content {
            display: flex;
            justify-content: space-around;

            .facilities-container,
            .our-values {
                width: 45%;
                height: 100%;

                h3 {
                    margin-bottom: 15px ;
                    text-transform: uppercase;
                    color: $font-color;
                }


                .facilities {
                    display: flex;
                    align-items: center;

                    i {
                        margin: 0 10px;
                        color: $color-theme;
                    }

                    strong {
                        margin: 0 10px;
                        color: $font-color;
                    }

                    p {
                        margin: 15px 0;
                    } 
                }

                .task {
                    margin-bottom: 10px;
                    padding: 15px 25px;
                    background-color: white;
                    color: $color-theme;
                    
                    .btn {
                        cursor: pointer;

                        strong {
                            margin: 0 15px;
                            text-transform: uppercase;
                        }
                    }


                    .text {
                        margin: 10px 0;
                        color: #7e8890;
                    }

                }

            } 

        }
    }
</style>