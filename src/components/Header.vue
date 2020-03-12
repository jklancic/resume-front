<template>
  <header class="masthead">
    <div class="container h-100">
      <div class="row h-100 align-items-center justify-content-center text-center">
        <div class="col-lg-10 align-self-end">
          <h1 class="text-uppercase text-white font-weight-bold">{{ fullName }}</h1>
          <h2 class="text-uppercase text-white font-weight-bold">{{ profession }}</h2>
          <hr class="divider my-4">
        </div>
        <div class="col-lg-8 align-self-baseline">
          <p class="text-white-75 font-weight-light mb-5">{{ oneLiner }}</p>
          <a class="btn-primary btn-xl js-scroll-trigger" href="#about">Find Out More</a>
        </div>
      </div>
    </div>
  </header>
</template>

<script>

  export default {
    props: {
      profile: Object
    },

    computed: {
      fullName: function () {
        if (this.profile.firstname ==null || this.profile.lastname == null) {
          return 'Jernej Klancic';
        }

        return this.profile.firstname + ' ' + this.profile.lastname;
      },

      profession: function() {
        if (this.profile.profession == null) {
          return 'Developer';
        }

        return this.profile.profession;
      },

      oneLiner: function() {
        if (this.profile.oneLiner == null) {
          return '';
        }

        return this.profile.oneLiner;
      }
    }
  }

</script>

<style scoped>
</style>