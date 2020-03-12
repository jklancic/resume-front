<template>
  <section class="page-section" id="contact">
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-lg-8 text-center">
          <h2 class="mt-0">Let's Get In Touch!</h2>
          <hr class="divider my-4">
          <p class="text-muted mb-5">Ready to start your next project with me? Give me a call or send me an email and I will get back to you as soon as possible!</p>
        </div>
      </div>
      <div class="row">
        <div class="col-lg-4 ml-auto text-center mb-5 mb-lg-0">
          <i class="fas fa-phone fa-3x mb-3 text-muted"></i>
          <div>{{ userContact.phone }}</div>
        </div>
        <div class="col-lg-4 mr-auto text-center">
          <i class="fas fa-envelope fa-3x mb-3 text-muted"></i>
          <!-- Make sure to change the email address in anchor text AND the link below! -->
          <a class="d-block" href="mailto:contact@yourwebsite.com">{{ userContact.email }}</a>
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
      userContact: function () {
        if (this.profile.userContact == null) {
          return { };
        }

        return this.profile.userContact;
      }
    }
  }

</script>

<style scoped>
</style>