## Tag Management & Managers│`manage` & `tagmanager`
Tag Managers are authorized roles with special permissions to manage tags and post states in forum channels. They have elevated permissions beyond regular users but don't need full moderator privileges.

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

`/authorizetag assign`: Assigns up to 5 tags to the authorized Tag Manager, can be used multiple times and accepts more than 5 tags (i.e. you can have 10 or more tags authorized) - :warning:ADMIN:warning:

`/authorizetag revoke`: Revokes authorization for up to 5 tags from a Tag Manager role - :warning:ADMIN:warning:

`/authorizetag list`: Lists all tags that a Tag Manager role is authorized to manage - :warning:ADMIN:warning:

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