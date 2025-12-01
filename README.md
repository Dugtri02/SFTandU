# SFTandU

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

## **Auto Tags│`/autotag` **
-# Auto Tags are automatically applied to new posts in a forum channel. Each forum channel can have one auto tag.

- To set an auto tag you'll first need **pre-made tags** available in the forum channel.
- When a post is made the bot will attempt to add the tag you specified to that forum post, but it may fail if the bot does not have `Manage Posts` enabled.

## **Toggle Tags│`/togtags` **
-# Toggle Tags are special tags that can be toggled on or off in a forum post when a user sends a message in the Post.

How Toggle Tags Work
- Each forum channel can have up to 2 toggle tags.
- Toggle tags are useful for marking posts as "Pending", "In Progress", "Solved", etc.
- When a Close Tag is applied to a post (/close), any active Toggle Tags on that post are automatically removed.

Example usage:
- Set a toggle tag -> "In-Progress"
- User B (non-OP) sends a message which will have the bot "toggle" the tag onto the post. subsequent messages don't toggle it off.
- User A (OP) uses /close and the "In-Progress" is removed and replaced by the configured "Close" tag

## **Special Tags│`/specialtags` **
-# Special Tags are custom behaviour modifiers that affect how a post with the tag behaves. These tags can be applied to any forum post, changing how users can interact with the post.

NOTE: These tags rely on the tag's name. The tag must be added to a forum post either by manually adding a tag with the exact same name as the Special Tag created, or by using the `/specialtags` add command.

- `Read Only`: Makes the post read-only. No one can reply to the post except for the OP, collaborators and Forum Staff.
- `Images`: When enabled, forces users to post images in the post, can be combined with 'Videos' and 'Links'. OP, collaborators and Forum Staff bypass this restriction.
- `Videos`: When enabled, forces users to post videos in the post, can be combined with 'Images' and 'Links'. OP, collaborators and Forum Staff bypass this restriction.
- `Links`: When enabled, forces users to post links in the post, can be combined with 'Images' and 'Videos'. OP, collaborators and Forum Staff bypass this restriction.
- `Reinforce Lock`: Reinforces post locked state, if unlocked and a message is sent the message is deleted and the post is locked. Also locks the post on creations.
- `Administrators Only`: Only administrators can interact with posts having this tag, deletes Regular Users and Moderators messages and keeps the post locked.
- `Prevent Close`: If closed, it is re-opened.
- `Lock on Close`: Automatically locks the post when it gets closed.
- `Delete on Close`: Automatically deletes the post when it gets closed.

Property Conflicts
Some properties conflict with each other and will be automatically adjusted when combined:

- Read Only overrides all other properties. If enabled, all other properties will be automatically disabled.
- Administrators Only takes precedence over Reinforce Lock. If both are enabled, only Administrators Only will remain active.
- Prevent Close takes precedence over Lock On Close. If both are enabled, only Prevent Close will remain active.
- Delete On Close takes precedence over both Prevent Close and Lock On Close. If Delete On Close is enabled along with either of these properties, only Delete On Close will remain active.

These conflict resolutions are handled automatically when creating or editing tags.

## **Close Tag│`/admin defclosetag` **
-# Close Tags are automatically applied when using the /close command, which is available to the Original Poster (OP), users with Tag Manager roles, and Forum Staff.

- When a post is closed (using the /close command), the configured close tag is applied.
- Each forum channel can have one close tag.
- This tag must be one of the tags available in that Discord forum channel.
- It will toggle off any present Toggle Tags.

Close tags can be combined with special tag properties like "Delete on Close" for thread management.

## **Tag Management & Managers│`manage` & `tagmanager` **
-# Tag Managers are authorized roles with special permissions to manage tags and post states in forum channels. They have elevated permissions beyond regular users but don't need full moderator privileges.

Tag Manager Permissions
Users with Tag Manager roles can:
- Close forum posts using the /close command
- Access the /manage commands to add, remove, and replace tags
- Lock and or Close forum posts when using /manage add/remove/replace commands
- Provide reasons for their actions that are visible to other users

Authorized Tags
Administrators must specify which tags a Tag Manager role can manage:
- By default, Tag Managers cannot manage any tags until they are specifically authorized
- Administrators must configure Authorized Tags to grant Tag Managers permissions to manage specific tags
- Different Tag Manager roles can be authorized for different sets of tags

`/authorizetag assign`: Assigns up to 5 tags to the authorized Tag Manager, can be used multiple times and accepts more than 5 tags (i.e. you can have 10 or more tags authorized) - **:warning:ADMIN:warning:**

`/authorizetag revoke`: Revokes authorization for up to 5 tags from a Tag Manager role - **:warning:ADMIN:warning:**

`/authorizetag list`: Lists all tags that a Tag Manager role is authorized to manage - **:warning:ADMIN:warning:**

Available Commands
`/close [tag]`: Closes the post and applies a tag. If a default close tag is configured, it will be applied automatically. You can specify an override tag parameter to use a different tag than the default. A default close tag is not required for this command to work.

`/manage add`: Adds a specific tag to the post with an optional reason and options to close and lock the post.

`/manage remove`: Removes a specific tag from the post with an optional reason and options to close and lock the post.

`/manage replace`: Replaces one tag with another on the post with an optional reason and options to close and lock the post.

Tag Managers are managed through the following commands:
`/tagmanager add`: Adds a role as a Tag Manager (remember that roles must be authorized before they can manage any tags)

`/tagmanager remove`: Removes a role from Tag Managers

`/tagmanager list`: Lists all roles configured as Tag Managers

Assign the Tag Manager role to trusted roles and remember to authorize specific tags for these roles using the /authorizetag commands.
