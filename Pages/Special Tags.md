## Special Tags│`/specialtags`
Special Tags are custom behaviour modifiers that affect how a post with the tag behaves. These tags can be applied to any forum post, changing how users can interact with the post.

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