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