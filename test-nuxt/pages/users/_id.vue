<template>
	<div>
		<p>ID is {{ userId }}</p>
	</div>
</template>
<script>
export default {
	data() {
		return {
			userId: this.$route.params.id
		};
	},
	head() {
		return {
			title: `${this.$route.params.id} | Nuxt Practice`
		}
	},
	async asyncData({ app }) {
		console.log(`asyncData | server is ${process.server}`);
	},
	created() {
		console.log(`created | server is ${process.server}`);
	}
};
</script>
