<template>
    <header>
        <InfoHeader
        :socials="social"/>
        <Navbar/>
        <Jumbotron
        title="Inspiring Tomorrows Leaders"
        subtitle="The Future Belongs To Those Who See Possibilities Today"/>
    </header>
</template>

<script>
import InfoHeader from './InfoHeader.vue'
import Jumbotron from './Jumbotron.vue'
import Navbar from './Navbar.vue'

export default {
  components: {
    InfoHeader,
    Navbar,
    Jumbotron
  },
  props: {
      social: Array
  },
    name: "Header"
}
</script>

<style lang="scss" scoped>
    header {
        height: 100vh;
        background-color: green;
    }
</style>