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
      <CourseSection/>
      <NewsSection
      title="Today’s Univeristy News"
      subtitle="Covering topics from classes to politics and student organization events."/>
      <FormSection/>
    </main>
    <Footer
    :social="socialLinks"/>
    <div class="up">
      <a href="#app"><i class="fas fa-chevron-up"></i></a>
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import AboutSection from './components/AboutSection.vue'
import FacilitiesSection from './components/FacilitiesSection.vue'
import CourseSection from './components/CourseSection.vue'
import NewsSection from './components/NewsSection.vue'
import FormSection from './components/FormSection.vue'

export default {
  name: 'App',
  components: {
    Header,
    Footer,
    AboutSection,
    FacilitiesSection,
    CourseSection,
    NewsSection,
    FormSection,
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
@import "./style/variables";

#app {
  position: relative;
}

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

.up {
  display: flex;
  justify-content: center; 
  position: fixed; 
  bottom: 0;
  right: 15px;
  padding: 5px 15px;
  border-radius: 5px 5px 0 0;
  background-color: $font-color;
  z-index: 1;
  cursor: pointer;
  
  &:hover i {
    scale: 1.2;
  }
}

</style>
