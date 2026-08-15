# Trip Planner — collaborative trip-detail upgrade

## What changed
- Trip Toolkit is now embedded directly inside **Trip details**. The separate Trip Toolkit navigation page was removed.
- Opening any trip shows its countdown, budget, packing list, expenses, itinerary, and shared notes in the same trip-detail modal.
- Toolkit data is now stored under `tripPlans/{tripId}/toolkit` in Firebase Realtime Database, so every trip member sees the same data.
- Every member listed in `tripPlans/{tripId}/members` can edit the shared trip details and toolkit from the UI.
- Existing local toolkit data from the previous build is automatically migrated to the shared Firebase toolkit the first time that trip is opened by its owner/account.
- Each toolkit item records the username/time that created it where appropriate, and the trip stores `toolkitUpdatedBy` / `toolkitUpdatedAt`.
- Added shared-toolkit reset, JSON export, and print actions directly inside trip details.

## Collaboration note
The current app uses its own username/password records rather than Firebase Authentication. That means Firebase Realtime Database rules cannot securely identify the custom `activeUsername` value. The UI therefore grants editing to users who are members of the trip, and the existing Firebase rules must allow the trip-plan writes. For production-grade security, migrate sign-in to Firebase Authentication and write rules against `auth.uid`.

## Run
Serve the folder from a local web server or deploy it to Firebase Hosting / another static host. The app uses Firebase modules from the Google CDN.


## Trip management update
- Added Edit and Delete actions directly to every trip card.
- Added a Delete trip action inside Trip details. Deleting a trip removes the trip and its membership links for every member.
- Any member listed on the trip can edit or delete it in the UI.
- Trip details now automatically show availability for **other members only**; the current user is excluded.
- The availability panel is read-only and does not show the current user's own availability.
- Shared trip edits and deletions still depend on your Firebase Realtime Database rules allowing the corresponding writes.

## V6 feature upgrade
- Added a dedicated **Saved Inspiration** workspace with search, category filters, favorites, remove, and "Use for a trip" actions.
- Added Firebase-backed inspiration storage at `userInspiration/{username}` with starter ideas shown for new accounts.
- Added a new Inspiration section to the sidebar and a richer Saved inspiration area on Overview.
- Added Overview stats for active trips, upcoming travel days, travel partners, and saved ideas.
- Added My Trips search, Upcoming/Past/Shared/Solo filters, sorting, and archived-trip visibility.
- Added **Duplicate** and **Archive/Restore** actions to trip cards. Duplicating keeps the shared members and toolkit as a starting template.
- Bumped the PWA cache to v6 so installed copies refresh to the upgraded UI.

## Firebase paths used by this upgrade
- `userInspiration/{username}/{inspirationId}` — personal saved destination ideas.
- Existing shared trip data remains under `tripPlans/{tripId}` and `userTrips/{username}/{tripId}`.
