# Koblenz Telugu Families · మన కుటుంబాలు

A members-only map for Telugu families in Koblenz and nearby towns.
Put your family on the map, see who lives close by, connect, and share news and events with the community.

**Open the map:** https://mohanmanideep.github.io/telugu-community-map/

Works in any phone or computer browser. Nothing to install.

---

## What you can do

- **Add your family's flag.** Search your address or tap the spot on the map, then drag to fine-tune.
- **Share only what you want.** Name, work, interests, languages, kids, "about us": every detail is optional.
- **Find families nearby.** Search by name, job or interest and the map jumps to the best match.
- **Connect.** Send a request with a short note. Once it's accepted, you both see each other's full address, contact and directions (Google Maps or Apple Maps).
- **Community board.**
  - Messages stay up for 1 to 14 days, then disappear on their own.
  - Events have a date, a place, an optional pin on the map and an "I'm going" button.
- **Notifications.** The bell shows connection requests, answers, and who's going to your events.
- **Suggest an idea.** Send ideas or problems straight to the admins.
- **Leave any time.** Deleting your account removes your flag, details, posts and connections right away.

## Privacy

- Only logged-in members can see the map.
- Everyone on the map sees your family name, street and postcode, and the details you chose to share.
- Exact location, full address and contact: for each one, you choose between everyone and only families you've connected with.
- If you hide your exact location, your flag is moved about 50 m away and house numbers are hidden on the map.
- Admins can see all details so they can keep the map safe and tidy. Everyone can see who the admins are.
- No ads, and no data is sold or shared.

## Built with

| Part | What it uses |
|---|---|
| App | One file, `index.html` (plain HTML, CSS and JavaScript, no build step) |
| Map | [MapLibre GL JS](https://maplibre.org/), with tiles from [OpenFreeMap](https://openfreemap.org/) and [OpenStreetMap](https://www.openstreetmap.org/copyright) data |
| Address search | OpenStreetMap [Nominatim](https://nominatim.org/) |
| Login and data | [Firebase](https://firebase.google.com/) Authentication (email and password) and Cloud Firestore |
| Security | [`firestore.rules`](firestore.rules) decide who can read and change what |
| Hosting | GitHub Pages |

### About the Firebase key in `index.html`

The Firebase web config is meant to be public, and GitHub may flag it as a secret anyway.
It isn't one: it only identifies the project. Access to the data is controlled by the security rules in `firestore.rules`, plus the list of authorized domains in Firebase.

## Run your own copy

1. **Firebase:** create a project and turn on **Authentication → Email/Password**.
2. **Firestore:** create a database (for example in `europe-west3`, Frankfurt).
3. **Config:** add a Web app in Project settings and paste its config into `FIREBASE_CONFIG` near the top of `index.html`.
4. **Publish the site:** push to GitHub and turn on **Settings → Pages** (branch `main`, folder `/`).
5. **Allow logins:** in **Firebase → Authentication → Settings → Authorized domains**, add `your-name.github.io`.
6. **Make yourself the owner:**
   1. Sign up on your site.
   2. Copy your ID from **Menu → How it works & privacy → Your user ID**.
   3. Put it in `OWNER_UID` in `index.html` and in `isOwner()` in `firestore.rules`.
7. **Rules:** paste `firestore.rules` into **Firestore → Rules** and click **Publish**.

The owner can make other families admins from **Menu → Admins**.

### Publishing changes

Change the `app-version` value at the top of `index.html` every time you publish. Open browsers pick up the new version and refresh by themselves.

## Feedback

Members can use **Suggest an idea** in the app's menu.

---

Map data © OpenStreetMap contributors.
