# ApplyKaLang — Job Application Tracker

Static HTML/CSS/JavaScript app using Firebase Authentication and Cloud Firestore. No build step required.

## Run locally

Serve the folder over HTTP (do not open `index.html` with `file://`). For example:

```sh
python3 -m http.server 5500
```

Open http://localhost:5500.

## Deploy to Vercel

Upload this folder to a GitHub repository and import it into Vercel. Select **Other** framework, leave the build command blank, and set the output directory to `.` (or leave Vercel's default for a static site). Deploy.

In Firebase Console > Authentication > Settings > Authorized domains, add the Vercel deployment hostname (without `https://`). Add custom domains there as well. Firebase may require you to add localhost manually for local testing.

## Database

This app writes to `users/{uid}/applications/{documentId}`. Firestore must be enabled and the published security rules must allow users to read/write their own application documents.

## Security

The Firebase web configuration is public by design. Do not put service-account keys in frontend files. Keep Firestore security rules enabled. For a public launch, tighten field validation and enable Firebase App Check / abuse protection as appropriate.

## Notes

Follow-up dates are shown in the app only; this version does not send notifications or emails. The 'Applied' count counts applications currently in the Applied stage, not every application ever submitted.
