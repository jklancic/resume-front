<template>
  <section class="page-section" id="services">
    <div class="container">
      <h2 class="text-center mt-0">At Your Service</h2>
      <hr class="divider my-4">
      <div class="row">
        <div v-for="skill in skills" v-bind:key="skill.uuid" class="col-lg-3 col-md-6 text-center">
          <div class="mt-5">
            <i v-bind:class="fontAwesomeDecorator(skill)"></i>
            <h3 class="h4 mb-2">{{ skill.type }}</h3>
            <p class="text-muted mb-0">{{ skillLevel(skill) }}</p>
          </div>
        </div>
        <div class="col-lg-3 col-md-6 text-center">
          <div class="mt-5">
            <i class="fas fa-4x fa-laptop-code text-primary mb-4"></i>
            <h3 class="h4 mb-2">Other</h3>
            <p class="text-muted mb-0">Always eager to learn new language or framework</p>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>

  export default {
    props: {
      profile: Object
    },

    computed: {
      skills: function () {
        if (this.profile.favoriteExpertise == null) {
          return [];
        }

        return this.profile.favoriteExpertise.proficient.slice(0, 3);
      }
    },

    methods: {

      fontAwesomeDecorator: function(skill) {
        var style = ['fab', 'fa-4x', 'text-primary', 'mb-4'];
        var uppercase = skill.type.toUpperCase();

        if (uppercase === 'JAVA') {
          style.push('fa-java');
        }

        if(uppercase === 'JAVASCRIPT') {
          style.push('fa-js');
        }

        if(uppercase === 'ANDROID') {
          style.push('fa-android');
        }

        return style;
      },

      skillLevel: function(skill) {

        switch(skill.rating) {
          case 10:
            return `Living and breathing ${skill.type} code`;
          case 9:
            return `${skill.type} marksmen`;
          case 8:
            return `Bug slayer in the ${skill.type} realm`;
          case 7:
            return `${skill.type} fanboy`;
          case 6:
            return `Level ${skill.rating} ${skill.type} wizard`;
          case 5:
            return `${skill.type} nerd`;
          default:
            return `${skill.type} motivator stage ${skill.type}`;
        }
      }
    }
  }

</script>

<style scoped>
</style>