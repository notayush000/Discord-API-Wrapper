
# Discord API Wrapper

This Python API wrapper for Discord is specifically designed to facilitate the implementation of Slash commands and provides essential functionalities to get your Discord bot operational.


## Example

```python
import mylib

client = mylib.Bot(command_prefix='-')

@client.event
def on_ready():
    print(f'Logged in as {client.user.name}')

@client.slash_command(
    description='Show\'s you your/friends avatar.'
)
def avatar(interaction):
    em = mylib.Embed()
    em.set_author(name=f'Avatar for {interaction.user}')
    em.add_field(name='Link', value=f'[Link]({interaction.user.avatar_url})', inline=False)
    em.set_image(url=interaction.user.avatar_url)

    interaction.respond(embed=em)

client.run('token')
```


## Support

Development for this library has been stopped. However i encourage those interested in Discord API integration to explore the official Discord API documentation [here](https://discord.com/developers/docs/reference).

