# LaunchNorth (working name)

A hub for Canadian startups. Founders post what they are building and their plan, find other founders who can help, and investors see who is raising.

## Features
- **Accounts:** sign up with email and password or with Google
- **Startup directory:** search and filter by province, sector, stage, asks, demo, hiring, verified
- **Company profiles:** logo, pitch, 12-month plan, traction, website, LinkedIn, demo links (YouTube links play inside the app), team, open roles, progress updates
- **Raising now:** who is fundraising and how much, with a private watchlist
- **Investor directory:** cheque size, stages, sectors and thesis
- **Messaging:** an intro request opens a private conversation; both sides reply inside the app
- **Email verification:** people must confirm their email before publishing or messaging
- **Admin tools:** mark startups as verified, remove listings, load example companies

## How it is built
- `index.html` — the whole app: HTML, CSS and JavaScript in one file, no build step
- `firebase-config.js` — your Firebase keys (empty = demo mode)
- `firestore.rules` — database security rules: who can read and write what
- `seed.json` — made-up example startups and investors
- `SETUP.md` — step-by-step guide to going live

Sign-in and the database are provided by Firebase (Authentication and Cloud Firestore). The site itself is static files, so it can be hosted free on GitHub Pages.

## Status
The code is complete but has not yet been run against a real Firebase project. It was tested in a browser against a stand-in for Firebase, so the screens and flows are checked while the security rules are not. Follow `SETUP.md`, then try sign-up, publishing a profile and sending an intro request before inviting anyone.

## Not built yet
- Email notifications for new messages (this needs Firebase's paid plan or an outside email service)
- Reporting and blocking for spam
- French language support
- Paging for very large directories (fine for hundreds of companies)
