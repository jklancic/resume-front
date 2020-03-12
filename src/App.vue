<template>
  <div id="app">
    <Navigation />
    <Header :profile="profile" />
    <About :profile="profile" />
    <Services :profile="profile" />
    <ResumeLink :profile="profile" />
    <Contact :profile="profile"/>
  </div>
</template>

<script>
import Navigation from './components/Navigation.vue'
import Header from './components/Header.vue'
import About from './components/About.vue'
import Services from './components/Services.vue'
import ResumeLink from './components/ResumeLink.vue'
import Contact from './components/Contact.vue'

export default {
  name: 'app',
  components: {
    Navigation,
    Header,
    About,
    Services,
    ResumeLink,
    Contact
  },

  data() {
    return {
      profile: { }
    }
  },

  created() {
    this.getUserProfile()
  },

  methods: {
    getUserProfile: async function() {
      try {
        const response = await fetch('http://localhost:7070/v1/home');
        const data = await response.json();
        this.profile = data;
      } catch (error) {
        this.console.error(error);
      }
    }
  }

}

</script>

<style>
</style>
