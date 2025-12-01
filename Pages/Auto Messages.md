## **Auto Messages│`/automsg` ** 
-# Auto Messages are automated responses that are sent by the bot when a new thread is created in a forum channel. This feature is particularly useful for providing immediate guidance, instructions, or resources to users when they create new posts.

- When a user creates a new thread in a forum channel with Auto Messages enabled, the bot automatically sends the configured message as the first reply
- Each forum channel can have one auto message

### Character Limits and Message Formatting
When creating auto messages, keep in mind the following:

- Character Limit: Auto messages are limited to 2000 characters maximum
- Message Formatting Variables: You can use special variables in your auto messages for dynamic content:
   - `{user]` or `{op}` to ping the poster.
   - `{line}`, `{ln]` or `\n` to add a line break.
  - `{thread}` to send the name of the post
  - `{guild}` to send the name of the guild
  - `{channel}` to send the name of the forum channel
  - `{reply}` to reply to the first message AKA the "post"
  - `{da=seconds}` automatically deletes the auto message when "seconds" is replaced with a value of seconds
  - `/close` will format to show the bots close command
  - `/delete` will format to show the bots delete command 

:warning:When setting an auto message we will be able to see it in the bot logs, if it contains anything we deem inappropriate we may remotely restrict access to the bot:warning: