# discord-ext-helpers

A collection of helpers to use with discord.py

## Examples

---

#### `when_mentioned_or_coro`

Signature:
```py
def when_mentioned_or_coro(coro: Callable, force_space: bool) -> Callable:
```

Usage:
```py
from discord.ext import commands, helpers


async def get_prefix(bot: commands.Bot, message) -> str:
    """Get a custom prefix"""

    pass  # Put your own prefix logic here

bot = commands.Bot(command_prefix=helpers.when_mentioned_or_coro(get_prefix))

...

bot.run("your token")
```

If you want to force a space between the end of the mention and the command you can use:

```py
helpers.when_mentioned_or_coro(get_prefix, force_space=True)
```

rather than

```py
helpers.when_mentioned_or_coro(get_prefix)
```

which will mean `@bot command` would work, but `@botcommand` wouldn't.

---
