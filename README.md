# this-is-modrinth-discussion

I've often found messages sent in the Modrinth discord telling people to move off-topic convos in #modrinth-discussion to be mildly amusing.

So I had an idea and created a website compiled with a list of my favorites.

https://thisismodrinthdiscussion.com

Enjoy! (Or don't, I'm not your mom)

## Adding new messages

Two ways:

1. Ask me on Discord
2. Open a pull request

### Opening a pull request for adding new messages

All you need to do is add a new object to the "all" array in `messages.json`, following this format:

```json

{
	"author": "beansquared",
	"username": "smcmo",
	"avatar": "https://avatars.githubusercontent.com/u/65502593?v=4",
	"color": "#ffffff",
	"message": "example message"
},

```

- `author` is the message author's name as it appears on Discord.
- `username` is the message author's Modrinth username. Currently does nothing so you can leave it as an empty string if you want.
- `avatar` is the URL link to the message author's avatar. I use links to the author's Modrinth avatar that I retrieve through the API using [this route](https://docs.modrinth.com/api-spec/#tag/users/operation/getUser).
- `color` is the message author's role color on the Modrinth Discord. For reference Modrinth staff is `#1bd96a` and moderators are `#a95bf8`.
- `message` is the actual message from Discord. If you're copy-pasting directly from Discord you'll likely need to manually add the # in front of channel mentions like `#lounge`

It is recommended more recent messages be added to the top of the list rather than the bottom so they're more visible.
