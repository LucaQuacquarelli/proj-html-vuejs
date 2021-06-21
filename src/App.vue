<template>
  <div id="app">
    <Header
    :social="socialLinks"/>
    <Main/>
    <Footer/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Main from './components/Main.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'App',
  components: {
    Header,
    Main,
    Footer,
  },
  data: function() {
    return {
      socialLinks: [
        {
          icon: "facebook-f",
          url: "facebook"
        },
        {
          icon: "twitter",
          url: "twitter"
        },
        {
          icon: "youtube",
          url: "youtube"
        },
        {
          icon: "instagram",
          url: "instagram"
        }
      ]
    }
  }
}   
</script>

<style lang="scss">
@import "./style/general";

</style>
