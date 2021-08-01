<template>
	<div>
		<h3>投稿一覧</h3>
		<ul>
			<li
				v-for="item in items"
				:key="item.id"
			>
				<h4>{{ item.title }}</h4>
				<div>{{ item.body.slice(0, 130) }}....</div>
				<a :ref="item.url">リンクはこちら</a>
			</li>
		</ul>
	</div>
</template>
<script>
export default {
	async asyncData({ app }) {
		const items = await app.$axios.$get('https://qiita.com/api/v2/items?query=tag:nuxt.js')
		console.log(items);

		return { items }
	}
}
</script>
<style scoped>
ul {
	list-style: none;
}

li + li {
	margin-top: 50px;
}
</style>
