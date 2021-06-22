<template>
  <div id="app">
    <Header
    :social="socialLinks"/>
    <main>
      <AboutSection
      title="Inspired By Excellence & Innovation"
      subtitle="We offer a wide range of high quality of teaching and extra-curricular activities."/>
      <div class="separe">
        <div class="empty-line"></div>
        <div class="line">
          <div class="triangle"></div>
        </div>
      </div>
      <FacilitiesSection/>
    </main>
    <Footer/>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import AboutSection from './components/AboutSection.vue'
import FacilitiesSection from './components/FacilitiesSection.vue'

export default {
  name: 'App',
  components: {
    Header,
    Footer,
    AboutSection,
    FacilitiesSection,
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

.separe {
  height: 100px;

  .empty-line,
  .line {
    height: 50%;
  }
  .line {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #f7f5f4;
    overflow: hidden;
  }

  .triangle{
    width: 0;
    border-top: 50px solid white;
    border-left: 670px solid transparent;
    border-right: 670px solid transparent;
  }

}

</style>
