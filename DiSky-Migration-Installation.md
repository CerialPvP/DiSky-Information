## DiSky Installation

To install DiSky, follow these steps:

1. Download the latest version of DiSky [here](https://github.com/DiSkyOrg/DiSky/releases/latest).
![image](https://user-images.githubusercontent.com/71380797/199337422-16199ea0-a0a2-4218-a6c8-6398e5713311.png)


## DiSky Migration

If you finally decided to switch off of Vixio or from an older version of DiSky, this is your time to shine!

Now, there isn't an automatic migratior, but I will show you code you will need to migrate.

**:warning: Not all syntaxes will be mentioned here, only basic stuff you may need to migrate. :warning:**

### Login

**DiSky v4 (latest) ✅:**
```applescript
# Replace "BOT_NAME" with the name of your Discord bot.
define new bot named "BOT_NAME":
    # A token is a way for Discord bots to log in.
    # You can get your token by going to the Discord Developers page.
    token: TOKEN_HERE
    #! Do not change these settings if you don't know what you're doing.
    intents: default intents
    policy: all
    auto reconnect: true
    compression: none
    #! You can now touch below.
    on ready:
        # This section will be triggered when the bot is online.
        send "The bot is ready." to console
    on guild ready:
        # This section will be triggered when a certain guild is loaded.
        send "The guild %event-guild% is now loaded." to console
```

**DiSky v3 (old) ❌:**
```applescript
# Executes whenever Skript starts up
on skript load:
  # Replace "TOKEN_HERE" with the bot token, and "BOT_NAME" with the name of your bot.
  login to "TOKEN_HERE" with name "BOT_NAME"
```

**Vixio v2.0.7+ (very old) ❌:**
```applescript
# Executes whenever Skript starts up
on skript load:
    # Create a new Vixio bot with all intents
    create vixio bot:
        enable the guild members intent
        enable the guild bans intent
        enable the guild emojis intent
        enable the guild invites intent
        enable the guild voice states intent
        enable the guild presences intent
        enable the guild messages intent
        enable the guild message reactions intent
        enable the direct messages intent
        enable the direct message reactions intent
        enable the direct message typing intent

        # Replace "TOKEN_HERE" with the bot token, and "BOT_NAME" with the name of your bot.
        login to "TOKEN_HERE" with the name "BOT_NAME"
```

### Discord (chat) commands
*I am talking about the prefixed (!example) commands, not the modern slash commands. It should be the same across all the addons.*

**DiSky v4 (latest) ✅:**
```applescript
discord command example:
  prefixes: !
  trigger:
    # your code here
```

**DiSky v3 (old) ❌:**
```applescript
discord command example:
  prefixes: !
  trigger:
    # your code here
```

**Vixio v2.0.7 (very old) ❌:**
```applescript
discord command example:
  prefixes: !
  trigger:
    # your code here
```
