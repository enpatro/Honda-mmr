# Honda MMR - GitHub Pages + Firebase Realtime Bundle

## Files to upload to GitHub repository
- `index.html` - main user app
- `admin.html` - admin control page
- `firebase-config.js` - Firebase web config (must edit)
- `firebase-rules.json` - Realtime Database security rules
- `machines_template.csv`, `parts_template.csv`
- `mmr_backup_example.json`, `mmr_backup_blank.json`

## Why this is needed
GitHub Pages is static hosting only. LocalStorage data is per browser, so 10 users cannot see each other's data unless a shared backend database is used.
This bundle uses Firebase Realtime Database so all connected users see the same live data.

## Setup steps
1. Create Firebase project.
2. Enable Authentication > Email/Password.
3. Create the 10 users in Firebase Authentication.
4. Create Realtime Database.
5. Paste `firebase-rules.json` into Firebase Realtime Database Rules.
6. Edit `firebase-config.js` with your Firebase web app config.
7. Upload all files to GitHub repo root.
8. Open `https://enpatro.github.io/Honda_MMR/`.

## First admin setup
1. Login once from `index.html` using your admin email.
2. Firebase will create `/userProfiles/UID`.
3. Copy the UID.
4. In Firebase Realtime Database, manually add:

```json
userRoles/{UID}/role = "admin"
```

5. Open `admin.html`. Now the admin can assign roles and delete records.

## Role logic
- User: can read, upload/merge JSON, add/update machine/part/history.
- User: cannot delete records.
- Admin: can delete any record and clear master/history.

## Important
If users must not update existing records either, rules can be tightened further. Current rules allow create/update but prevent deletion for non-admin users.
