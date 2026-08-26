# 🌸 AniBlossom

> **Kitsunee's polished Next.js frontend** × **AniBlossom's Firebase backend & blossom UI theme**

AniBlossom is an anime streaming site built on the [Kitsunee](https://kitsunee.moe) frontend architecture, redesigned with a cherry-blossom aesthetic and powered by Google Firebase for auth and user profiles.

---

## ✨ What's Combined

| Feature | Source |
|---|---|
| Next.js 15 app router, React Query | Kitsune |
| Anime API (HiAnime / Miruro) | Kitsune |
| Video player (ArtPlayer + HLS) | Kitsune |
| Anime schedule, search, carousel | Kitsune |
| Watch history & bookmarks | Kitsune |
| Comments system | Kitsune |
| **Firebase Auth** (email + Google) | AniBlossom |
| **Firebase Firestore** user profiles | AniBlossom |
| **Firebase Storage** avatar uploads | AniBlossom |
| **Blossom pink colour palette** | AniBlossom |
| **Playfair Display + Plus Jakarta Sans** fonts | AniBlossom |
| AniBlossom logo & branding | AniBlossom |

---

## 🚀 Getting Started

```bash
# 1. Install deps
npm install

# 2. Copy the env (already pre-filled with your Firebase project)
cp .env.local.example .env.local
# → Add your NEXT_PUBLIC_API_URL from Kitsune if needed

# 3. Run dev server
npm run dev
```

Open [http://localhost:3000](http://localhost:3000)

---

## 🔑 Environment Variables

| Variable | Description |
|---|---|
| `NEXT_PUBLIC_FIREBASE_*` | Your Firebase project config (already set) |
| `NEXT_PUBLIC_API_URL` | Anime API base URL (Miruro/HiAnime proxy) |
| `NEXT_PUBLIC_POCKETBASE_URL` | **Optional** – not used; Firebase replaces PocketBase |

---

## 🌸 Blossom Theme Tokens

```css
--blossom:       #ffb7d5   /* light petal pink */
--blossom2:      #ff8cc8   /* mid petal */
--blossom-pink:  #e86db0   /* primary accent */
--blossom-deep:  #c94d94   /* deep cherry */
--gold:          #f5c842   /* star/score colour */
```

---

## 📁 Key File Locations

```
src/
  lib/firebase.ts          ← Firebase app init (auth, db, rtdb, storage)
  store/auth-store.ts      ← Zustand auth store (Firebase-shaped IAuth)
  components/
    navbar.tsx             ← Blossom navbar w/ Firebase auth sync
    login-popover-button.tsx ← Email + Google sign-in / sign-up
    navbar-avatar.tsx      ← User menu with Firebase signOut
    hero-section.tsx       ← Blossom hero carousel
    anime-card.tsx         ← Blossom anime cards
    footer.tsx             ← AniBlossom footer
  app/
    layout.tsx             ← Root layout (dark forced, AniBlossom meta)
    page.tsx               ← Home page
    profile/[username]/    ← Firebase-backed public profiles
  app/globals.css          ← Blossom CSS variables & utilities
  tailwind.config.ts       ← Blossom colour extensions
```

---

## 👤 Profile / Avatar

- Profile pages are public at `/profile/[username]`
- Avatar upload goes to **Firebase Storage** → `avatars/{uid}/{filename}`
- Firestore user document: `users/{uid}` with `username`, `photoURL`, `autoSkip`, `createdAt`
- Photo URL is also synced to Firebase Auth `displayName` / `photoURL`

---

## 📜 License

AniBlossom is for personal/educational use. The underlying anime data is sourced from third-party APIs.
