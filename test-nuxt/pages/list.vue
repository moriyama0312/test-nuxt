<template>
	<div>
		<h3>投稿一覧</h3>
		<ul>
			<li
				v-for="item in items"
				:key="item.id"
			>
				<h4>
					{{ item.title }} by <nuxt-link :to="'/users/' + item.user.id">{{ item.user.id }}</nuxt-link>
				</h4>
				<div>{{ item.body.slice(0, 130) }}....</div>
				<a :ref="item.url">リンクはこちら</a>
			</li>
		</ul>
	</div>
</template>
<script>
import {mapGetters} from 'vuex';

export default {
	head() {
		return {
			title: '投稿一覧 | Nuxt Practice'
		}
	},
	async asyncData({ store }) {
		console.log(`asyncData | server is ${process.server}`);
		if(store.getters.items.length) {
			return;
		}

		await store.dispatch('fetchItems');
	},
	computed: {
		...mapGetters([
			'items'
		])
	},
	created() {
		console.log(`created | server is ${process.server}`);
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
