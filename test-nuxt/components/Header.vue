<template>
	<header>
		<nuxt-link to="/">Top</nuxt-link>
		<div class="menu">
			<nuxt-link to="/list">リスト</nuxt-link>
			<nuxt-link to="/login">ログイン</nuxt-link>
		</div>
	</header>
</template>

<script>
export default {
	name: 'Header'
};
</script>

<style scoped>
header {
	background: #000000;
	position: fixed;
	top: 0;
	left: 0;
	width: 100%;
	display: flex;
	justify-content: space-between;
	align-items: center;
	padding: 10px;
	border-bottom: 1px solid #302f2f;
	color: #ffffff;
}
</style>
