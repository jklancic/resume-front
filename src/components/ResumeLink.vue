<template>
	<section class="page-section bg-dark text-white" id="career">
	<div class="container text-center">
		<h2 class="mb-5">Take a closer look at my accomplishments</h2>
		<a class="btn-light btn-xl" v-bind:href="pdfLink">Download resume</a>
	</div>
	</section>
</template>

<script>

	export default {
		props: {
			profile: Object
		},

		computed: {
			pdfLink: function () {
			if (this.profile.pdfLink == null) {
				return '';
			}

			return this.profile.pdfLink;
			}
		}
		}

</script>

<style scoped>
</style>