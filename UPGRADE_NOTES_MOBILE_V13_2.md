# Trip Planner V13.2 – Create Event Visibility Fix

- Fixed Create Plan persistence/visibility flow.
- New trips are added to the local calendar immediately after Firebase write succeeds.
- Active user's userTrips index is updated locally before realtime listener refresh.
- Calendar jumps to the month containing the newly created trip.
- Save errors now display the Firebase error message instead of a generic failure.
- PWA cache bumped to v13.2.
