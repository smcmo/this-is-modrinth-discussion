<template>
	<div class="opening-text">
		<h1>Hey, this is <span class="green title">#modrinth</span>!</h1>
		<div class="message-box">
			<DiscordMessage author="Emma (triphora)" username="triphora" avatar="https://avatars.githubusercontent.com/u/60205699?v=4" color="#1bd96a">
				Oh, you're new here, so you haven't even seen https://thisismodrinthdiscussion.com/
			</DiscordMessage>
		</div>
		<p>If you're reading this, you've likely been caught red-handed talking about non-Modrinth stuff in the #modrinth channel! 😲</p>
		<p>
			Do you have any idea what you've done!? The Modrinth team works hard to keep that channel on-topic! Who do you think you are, just waltzing on in and
			talking about something that's not Modrinth?? Just look how hard they have to work to keep this channel a civilized place:
		</p>
	</div>
	<div class="message-box">
		<DiscordMessage
			v-for="message in featuredMessages"
			:key="message"
			:author="message.author"
			:username="message.username"
			:avatar="message.avatar"
			:color="message.color"
		>
			{{ message.message }}
		</DiscordMessage>
	</div>
	<p>I mean...ok. So it's really not all that serious mostly.</p>
	<p>And the purpose of this website is not to scold you for accidentally drifting into other topics, as Emma aptly explains:</p>
	<div class="message-box">
		<DiscordMessage author="Emma (triphora)" username="triphora" avatar="https://avatars.githubusercontent.com/u/60205699?v=4" color="#1bd96a">
			y'all he's not saying we're banning people who go offtopic<br />
			if that were the case we would be banning the entire server
		</DiscordMessage>
	</div>
	<p>
		This is actually mostly just a repository of my personal favorite messages from the Modrinth staff (mostly Emma/triphora) telling people they've gone
		off-track. Hey, maybe you'll enjoy them as much as I do. Enjoy a nice fat list!
	</p>
	<p>
		Also quick disclaimer: you may see many of the messages here referring to a channel called #modrinth-discussion, this is what the #modrinth channel was
		originally called prior to a server channel restructuring in early 2024.
	</p>
	<div class="message-box">
		<DiscordMessage
			v-for="message in allMessages"
			:key="message"
			:author="message.author"
			:username="message.username"
			:avatar="message.avatar"
			:color="message.color"
		>
			{{ message.message }}
		</DiscordMessage>
		<p>#SaveTriphoraFromHavingToType#Lounge20TimesADay</p>
	</div>
	<p>
		Hey, you scrolled all the way down! You should
		<a href="https://discord.gg/fm88jhzEbt">join my Discord</a> and see what other cool stuff I make!
	</p>
	<footer>
		Made in 2 hours with Vue and probably not enough sleep. By
		<a href="https://github.com/smcmo">beansquared (smcmo)</a>. This site is not associated or endorsed by Modrinth, Rinth Inc or any of it's staff.
	</footer>
</template>

<script>
import DiscordMessage from './components/DiscordMessage.vue'
import messages from '../messages.json'
export default {
	components: {
		DiscordMessage,
	},
	data() {
		return {
			featuredMessages: [],
			allMessages: [],
		}
	},
	created() {
		this.featuredMessages = messages.featured
		this.allMessages = messages.all
	},
}
</script>

<style scoped>
h1,
p {
	text-align: center;
	padding: 0.5rem 0;
	margin: 0 0.25rem;
}

.title {
	margin: 0 0 0 0.25rem;
}

.opening-text {
	margin-top: 5rem;
}

.message-box {
	margin: 3rem 0;
}

footer {
	background-color: var(--color-background-mute);
	padding: 1rem;
	width: 100%;
	text-align: center;
}
</style>
