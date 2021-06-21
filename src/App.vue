<template>
  <div id="app">
    <Header
    :social="socialLinks"/>
    <main>
      <AboutSection
      title="Inspired By Excellence & Innovation"
      subtitle="We offer a wide range of high quality of teaching and extra-curricular activities."/>
    </main>
    <Footer/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import AboutSection from './components/AboutSection.vue'

export default {
  name: 'App',
  components: {
    Header,
    Footer,
    AboutSection,
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
