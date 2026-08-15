# Trip Planner V9 – Accounts, Recovery & Chat

- Faiz is the protected administrator account.
- Admin can create traveler/admin accounts from Admin Center.
- Admin can delete other user account records (Faiz is protected).
- Forgot password now creates a Firebase `passwordResetRequests/{requestId}` request. Faiz can approve with a new temporary password or deny it.
- Added Direct Messages and Trip Group Chat using `chatRooms/{roomId}/messages`.
- Chat timestamps render in Malaysia time (`Asia/Kuala_Lumpur`).

## Important security note
This project still uses a custom username/password record in Realtime Database and therefore should not be treated as production-grade authentication. For real deployment, migrate login/admin identity to Firebase Authentication and write owner/member/admin checks into Firebase Realtime Database Security Rules.
