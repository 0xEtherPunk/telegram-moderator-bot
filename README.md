# Telegram Moderator Bot

[Русская версия](README.ru.md)

>Telegram chat moderation bot that automatically removes messages containing profanity.

## Features

- **🔍 Monitoring messages for profanity**
- **🗑️ Automatic removal of messages containing swear words**
- **⚠️ Sending warnings to violators**
- **🔄 Support for checking edited messages**
- **🔡 Detection of masked profanity (transliteration, similar symbols)**

## Installation

##### 1. **Clone the repository**:
```
git clone https://github.com/0xEtherPunk/telegram-moderator-bot.git
cd telegram-moderator-bot
```

##### 2. **Install dependencies**:
```
pip install aiogram transliterate
```

##### 3. Edit `conf.py`:
```
bot_token = "YOUR_BOT_TOKEN" # Get from @BotFather
group_id = "YOUR_GROUP_ID" # Your group ID
```

## Launch

```
python main.py
```

---

## Configuration

#### Bot Permissions
- Bot must be a group administrator
- Delete message permissions required

#### Editing Word Lists
In `filters/words.py` you can configure:
- `bad_words` - list of forbidden words
- `not_bad_words` - list of exceptions
- `en_ru_map` - symbol replacement rules

### How it Works

1. Bot monitors all new messages in the group
2. When profanity is detected:
   - Deletes the message
   - Sends a warning to the user
   - Removes the warning after 5 seconds
3. The system checks various masking methods:
   - Transliteration
   - Similar symbols
   - Mixed alphabets

> [!important] 
> ### Requirements
> 
> - Python 3.7+
> - aiogram
> - transliterate


