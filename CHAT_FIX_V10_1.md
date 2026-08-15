# Trip Planner V10.1 – Chat Fix

The V10 chat issue was caused by the chat listener being started and then immediately stopped by the general data-sync routine. V10.1 fixes the startup order so the user directory and message listeners remain active.

Chat supports:
- Community Lounge for all signed-in users.
- Personal 1-to-1 chat with any other registered user.
- Shared trip group chat for trip members.

## Firebase Realtime Database
Use the included `database.rules.json` for the current custom username/password app if your database currently rejects reads/writes under `chatRooms/`.

These rules are intentionally permissive for compatibility with the existing custom-auth client. For production, migrate to Firebase Authentication and enforce permissions with `auth.uid`.
