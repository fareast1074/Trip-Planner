# Trip Planner V11 — Automatic Trip Group Chat

When a traveler is invited to a trip, the trip chat room is created/updated automatically and includes the inviter and invitee.

When the invitation is accepted, the user is added to the trip membership and the group chat membership is synchronized with all current trip members.

Trip group chats use `chatRooms/trip_<tripId>/members/<username>` for membership metadata and `chatRooms/trip_<tripId>/messages` for messages.
