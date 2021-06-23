<template>
    <section>
        <div class="title-container">
            <h2>Joing Over <span>500,000 Students</span> Enjoying Avada Education now</h2>
            <p>Become Part of Avada University to Further Your Career.</p>
            <div class="curve"></div>
        </div>
        <div class="form-container">
            <input type="text" placeholder="Name" v-model="name">
            <input type="email" placeholder="Email" v-model="email">
            <input type="phone" placeholder="Telephone" v-model="phone">
            <span @click="send">apply now</span>
        </div>
    </section>
</template>

<script>
export default {
    name: "FormSection",
    data: function() {
        return {
            name: "",
            email: "",
            phone: ""
        }
    },
    methods: {
        send: function() {
            this.name = ""
            this.email = ""
            this.phone = ""
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../style/variables";

    section {
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 50px;
        background-color: #333c4e;

        .title-container {
            display: flex;
            flex-direction: column;
            align-items: center;
            position: relative;
            margin: 15px 0;

            span {
                color: $color-theme;
            }

            p {
                margin: 10px 0;
            }

            .curve {
                position: absolute;
                top: 35px;
                left: 125px;
                width: 30%;
                padding: 10px;
                transform: rotate(-3deg);
                border-top: 3px solid $color-theme;
                border-radius: 50%;
            }
            
        }
        
        .form-container {
            display: flex;
            align-items: center;
            margin: 15px 0;

            input {
                margin: 0 5px;
                padding: 10px ;
                background-color: $font-color;
                color: white;
                border: 0;
                outline: none;
            }

            span {
                padding: 5px 50px;
                background-color: $color-theme;
                text-transform: uppercase;
                transition: 0.3s;
                cursor: pointer;

                &:hover {
                    background-color: $font-color;
                }

            }
        }
    }
</style>