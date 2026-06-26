# Honda MMR Complete Firebase Admin Reset Bundle

## Upload to GitHub root
Upload all files in this bundle to your repository root.

Files:
- index.html
- admin.html
- firebase-config.js
- firebase-rules.json
- machines_template.csv
- parts_template.csv
- mmr_backup_blank.json
- mmr_backup_example.json

## First Admin
Email: e.patro@honda.hmsi.in

Password is NOT stored in GitHub files. Set password in Firebase Authentication.

## Firebase Setup
1. Firebase Console > Authentication > Sign-in method > Enable Email/Password.
2. Authentication > Users > Add user > e.patro@honda.hmsi.in > set password.
3. Project Settings > General > Your Apps > copy Web App config.
4. Paste Web App config into firebase-config.js.
5. Realtime Database > Rules > paste firebase-rules.json > Publish.
6. Upload all files to GitHub and open admin.html.

## Forgot Password
The admin.html and index.html both include Forgot Password button. It sends Firebase password reset email.

## Roles
- user: can view/upload/add/update.
- admin: can delete and assign roles.

## Important
If login does not happen, check:
- firebase-config.js has actual apiKey, not placeholder.
- Email/Password sign-in method is enabled.
- User is created in Firebase Authentication.
- Realtime Database rules are published.
