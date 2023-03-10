<template>
	<div class="discord-message">
		<div class="inner-content">
			<img :src="avatar" alt="" id="author-icon" />
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
	props: ['author', 'username', 'color', 'avatar'],
};
</script>

<style scoped>
.discord-message {
	border-radius: 1rem;
	background-color: var(--color-background-mute);
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

#author-icon {
	height: 3rem;
	width: 3rem;
	border-radius: 50%;
}
</style>
