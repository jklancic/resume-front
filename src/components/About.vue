<template>
  <section class="page-section bg-primary" id="about">
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-lg-8 text-center">
          <h2 class="text-white mt-0">About</h2>
          <hr class="divider light my-4">
          <p class="text-white-50 mb-5">{{ aboutMe }}</p>
          <a class="btn-light btn-xl js-scroll-trigger" href="#services">Expertise</a>
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
      aboutMe: function () {
        if (this.profile.aboutMe == null) {
          return '';
        }

        return this.profile.aboutMe;
      }
    }
  }

</script>

<style scoped>
</style>