# ReeganExE/github-action-telegram-notify

A lightweight github action that posts the current build URL to a group, channel or chat when a job started.

## Usage

```yml
- uses: ReeganExE/github-action-telegram-notify@v1.0
  with:
    token: ${{ secrets.YOUR_BOT_TELEGRAM_TOKEN }}
    chat-id: ${{ secrets.YOUR_TELEGRAM_CHAT_ID }}
```

OR

```yml
- uses: ReeganExE/github-action-telegram-notify@v1.0
  env:
    TELEGRAM_BOT_TOKEN: ${{ secrets.YOUR_BOT_TELEGRAM_TOKEN }}
    TELEGRAM_CHAT_ID: ${{ secrets.YOUR_TELEGRAM_CHAT_ID }}
```

## How to get chat id

Start a chat with your bot, or add bot to a group then send some messages (depends on which chat you want bot to send message).
If your bot was in that group over 1 day, then make sure you set its role as admin (so he can see messages in the group, you can revoke it later).

Replace `$BOT_TOKEN_HERE` with your bot token and visit this URL to get the new messages: https://api.telegram.org/bot$BOT_TOKEN_HERE/getUpdates.



You will see something as the following. Take a look, you will see the chat id.
```yml
{
  "ok": true,
  "result": [
    {
      "message": {
        "chat": {
          "id": -12345666, # This is the chat id (including - )
          "type": "group",
          "all_members_are_administrators": true
        },
        "date": 1654952677,
        "text": "test"
      }
    }
  ]
}
```

API Ref: https://core.telegram.org/bots/api#getupdates

See more: https://stackoverflow.com/questions/32423837/telegram-bot-how-to-get-a-group-chat-id

# LICENSE

AGPL-3.0 License
