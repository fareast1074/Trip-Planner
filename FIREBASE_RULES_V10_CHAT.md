# Firebase rules guidance – V10 chat

The app uses custom username/password records. For production, migrate login to Firebase Authentication and use `auth.uid` for security.

Chat data paths introduced/used by V10:

- `chatRooms/community_lounge/messages/{messageId}` – community chat.
- `chatRooms/dm_{sortedUserA}__{sortedUserB}/messages/{messageId}` – personal 1:1 chat.
- `chatRooms/trip_{tripId}/messages/{messageId}` – shared trip group chat.

Desired policy after Firebase Auth migration:

1. Authenticated users may read/write the community lounge.
2. Authenticated users may read/write a DM only when their UID is one of the two participants encoded by the room.
3. Authenticated users may read/write a trip chat only when they are members of the corresponding trip.
4. Validate message fields server-side where possible (sender UID, text length, createdAt).
