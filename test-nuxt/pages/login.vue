<template>
	<div class="contents">
		<div class="contents__inner">
			<h2 class="title">ログイン</h2>
			<div class="btns">
				<button class="button--grey" type="button" @click="login">ログイン</button>
				<nuxt-link class="button--grey" to="/">トップへ</nuxt-link>
			</div>
		</div>
	</div>
</template>

<script>
import Cookies from 'universal-cookie';

export default {
	layout: 'login',
	methods: {
		login() {
			const cookies = new Cookies();
			cookies.set('credential', 'true', {maxAge: 90});
			this.$router.push('/');
		}
	}
};
</script>

<style scoped>
.contents {
	display: flex;
	justify-content: center;
	align-items: center;
	width: 100%;
	height: 100vh;
}

.contents__inner {
	width: 480px;
	border: 1px solid #302f2f;
	border-radius: 5px;
	padding: 20px 10px;
}

.title {
	font-size: 28px;
	text-align: center;
}

.btns {
	display: flex;
	justify-content: center;
	align-items: center;
	margin-top: 20px;
}
</style>
