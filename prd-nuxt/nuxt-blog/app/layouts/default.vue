<template>
	<div>
		<TheHeader />
		<div class="wrapper">
			<Nuxt class="container" />
		</div>
	</div>
</template>

<script>
import TheHeader from '~/components/TheHeader';

export default {
	components: {
		TheHeader
	}
}
</script>
