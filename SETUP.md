# Going live: setup in 6 steps

Everything here can be done in a browser on a phone or iPad. No terminal needed. Allow about 20 minutes.

Until step 4 is done, the app runs in **demo mode**: it shows the example companies and sign-up is off.

## 1. Create a Firebase project
1. Go to https://console.firebase.google.com and sign in with your Google account.
2. Tap **Create a project**. Give it a name. Keep it separate from your other Google Cloud projects.
3. You can turn Google Analytics off. Stay on the free **Spark** plan.

## 2. Create the database
1. In the left menu open **Build → Firestore Database** and tap **Create database**.
2. Pick a Canadian location (Montréal `northamerica-northeast1` or Toronto `northamerica-northeast2`). This cannot be changed later.
3. Choose **Start in production mode**.
4. Open the **Rules** tab, delete what is there, paste the whole contents of `firestore.rules` from this repo, and tap **Publish**.

## 3. Turn on sign-in
1. Open **Build → Authentication** and tap **Get started**.
2. Under **Sign-in method**, enable **Email/Password**.
3. Enable **Google** as well and pick your support email.

## 4. Add the keys to the app
1. Open **Project settings** (gear icon) → **General** → **Your apps** → tap the web icon `</>`.
2. Give the app a nickname and tap **Register app**. Skip Firebase Hosting.
3. Copy the `firebaseConfig` values shown.
4. In this repo on GitHub, open `firebase-config.js`, tap the pencil to edit, replace `null` with your values in the shape shown in that file, and commit.

## 5. Put the site online with GitHub Pages
1. In this repo go to **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**, branch **main**, folder **/ (root)**, and save.
3. After a minute or two the site is live at `https://lazyprogrammer9033.github.io/Startupapp/`.
4. Back in Firebase: **Authentication → Settings → Authorized domains → Add domain** and add `lazyprogrammer9033.github.io`. Without this, sign-in is refused.

## 6. Make yourself the admin
1. Open the live site and create your account.
2. In Firebase open **Authentication → Users** and copy your **User UID**.
3. In **Firestore Database** tap **Start collection**, name it `admins`, and use your User UID as the **Document ID**. Add one field, for example `role` = `owner`.
4. Reload the site. Under **Profile** you now see **Admin tools**. Tap **Load example companies** if you want the examples in the live directory. As admin you can also mark startups as verified or remove a listing from any startup's page.

## Good to know
- **Cost.** This uses only the free parts of Firebase (sign-in and the Firestore database). Free limits change, so check Firebase's pricing page before a big launch.
- **Logos** are shrunk to a small square and stored in the database, so no file storage plan is needed.
- **Custom domain.** You can point your own domain at GitHub Pages later. Add that domain to Firebase's authorized domains too.
- **Before a public launch** add a privacy policy and terms of use, and get legal advice before adding any feature that handles investments.
