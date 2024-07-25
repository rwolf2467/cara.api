
## Cara API

### Python Package developed by Red_wolf2467

<hr>

This package is designed to make it easier for you to work with the Cara API (developed by CatC_guy). The package is based on the data found on the [API doc page](https://cara.twinklerealm.net/api/index.html) of the [BOT](https://cara.twinklerealm.net) / API.

<br>
<hr>
Now follow sample codes that you can simply copy / paste and use.

#### Chatfilter
````python
from cara_api import CaraAPI

caraAPI = CaraAPI("YOUR API-KEY")

bad_word_list = ["word1", "word2"]

request = caraAPI.chatfilter(message=message.content, levenshtein=2 ,FilteredWords=bad_word_list, GuildID=message.guild.id,

ChannelID=message.channel.id, AuthorID=message.author.id, MessageID=message.id,

GuildName=message.guild.name, ChannelName=message.channel.name, AuthorName=message.author.name, log=True)
# OnlyASCII = OPTIONAL; True = Delete non ASCII symbols, False = Ignore non ASCII symbols
# GoodWords = OPTIONAL; List of words that are allowed (for words that are misrecognized, structure as in "bad_word_list ")

 
print(request.result) # INT
# OK = 0, //Not filtered
# CustomBadWord = 1, //Direct Match
# Levenshtein = 2, //Disguised Bad Word
# Leet = 3, //Levenshtein + Leet
# NSFW = 4, //NSFW Content (not returned yet)
# BannedMessage = 5, //Registered Spam Message
# SuspiciousActivity = 6, //User was flagged for suspicious activity
# BotActivity = 7, //Bot activity
# SpammerNotAllowed = 8 //Registered spammer, not allowed on server

  
print(request.reason) # STRING
````

### Uer
````python
from cara_api import CaraAPI

caraAPI = CaraAPI("YOUR API-KEY")
request = caraAPI.get_user(user_id=message.author.id)

print(request.user_name)
print(request.isSpammer)
print(request.reason)
````
