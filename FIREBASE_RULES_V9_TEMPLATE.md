# Firebase Rules V9 template

The current app uses a custom username/password record and therefore cannot safely enforce admin/member identity with `auth.uid`. For compatibility, development rules may be permissive, but production deployment should migrate the login layer to Firebase Authentication.

After migration, protect these paths with Authentication and membership/admin checks:

- `users/{uid}`
- `tripPlans/{tripId}`
- `userTrips/{uid}`
- `tripInvites/{uid}`
- `passwordResetRequests/{requestId}`
- `chatRooms/{roomId}/messages/{messageId}`

The client-side admin flag is for UI behavior only; it must not be the security boundary.
