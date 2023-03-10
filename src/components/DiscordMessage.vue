<template>
	<div class="discord-message">
		<div class="inner-content">
			<img :src="avatarUrl" alt="" id="author-icon" />
			<div class="text-content">
				<p class="author" :style="`color: ${color}`">{{ author }}</p>
				<p class="message">
					<slot></slot>
				</p>
			</div>
		</div>
	</div>
</template>

<script>
export default {
	props: ['author', 'username', 'color'],
	data() {
		return {
			avatarUrl: '',
			avatarCache: [],
		};
	},
	async created() {
		const cachedData = this.avatarCache.find(
			(thingy) => (thingy.username = this.username)
		);
		if (cachedData) {
			this.avatarUrl = cachedData.avatarUrl;
			return;
		}

		console.log('making api call');
		const data = await fetch(
			`https://api.modrinth.com/v2/user/${this.username}`,
			{
				headers: {
					'user-agent':
						'smcmo/this-is-modrinth-discussion (this-is-modrinth-disscussion.com)',
				},
			}
		);
		const jsonData = await data.json();
		this.avatarCache.push({
			username: this.username,
			avatarUrl: jsonData.avatar_url,
		});
		this.avatarUrl = jsonData.avatar_url;
	},
};
</script>

<style scoped>
.discord-message {
	border-radius: 1rem;
	background-color: var(--vt-c-black-soft);
	margin: 0.5rem 1rem;
}

.inner-content {
	padding: 1.5rem;
	display: flex;
	align-items: center;
}

.text-content {
	margin-left: 1rem;
}

.author {
	color: #1bd96a;
}

#author-icon {
	height: 3rem;
	width: 3rem;
	border-radius: 50%;
}
</style>
