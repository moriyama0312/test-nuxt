<template>
	<div>
		<p>ID is {{ userId }}</p>
	</div>
</template>
<script lang="ts">
export default {
	data() {
		return {
			userId: this.$route.params.id
		};
	}
};
</script>
