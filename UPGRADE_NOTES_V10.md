# Trip Planner V10 – Everyone Chat + Personal Messaging

- Chat is explicitly available to every signed-in user.
- Added a Community Lounge (`chatRooms/community_lounge/messages`) for all users.
- Personal 1:1 chats remain available with every other registered user, independent of trip membership.
- Trip group chats remain available for the user’s shared trips.
- Added a New chat shortcut and clearer chat scope labels.
- Chat timestamps remain Malaysia time (`Asia/Kuala_Lumpur`).

Important: because the app still uses custom username/password records instead of Firebase Authentication, production Firebase Rules must be configured deliberately. The client UI is not a security boundary.
