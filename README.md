# CA — Class Apart Singapore
## ICAI Singapore Chapter · Annual Compendium 2026–27

**Live site:** https://ganeshcal.github.io/icai-sg-compendium-2026/  
**Repo:** https://github.com/ganeshcal/icai-sg-compendium-2026

---

## Quick Reference

| What you want to do | Where to go |
|---|---|
| Edit text/content on the page | Log in as Admin on the live site |
| Add or remove an editor account | Edit `EDITOR_USERS` in `index.html` on GitHub |
| Update content and publish | Edit `index.html` on GitHub → Commit |
| View the live site | https://ganeshcal.github.io/icai-sg-compendium-2026/ |

---

## Part 1 — How to Edit Page Content (No Code Needed)

The compendium has a built-in browser editor. Any text with a gold outline can be clicked and edited directly.

### Step 1 — Open the live site
Go to: https://ganeshcal.github.io/icai-sg-compendium-2026/

### Step 2 — Log in as Admin
Click the **Admin** button in the top-right corner of the navigation bar.

Enter your credentials:
- **Username:** your assigned username  
- **Password:** your assigned password

> The master admin username is `icaiadmin`. Keep this secure.

### Step 3 — Edit content
Once logged in, a gold admin bar appears at the top. Every piece of text on the page that has a gold dashed outline can be clicked and edited directly — headlines, body text, sponsor names, event details, member quotes, package prices, everything.

Changes are **auto-saved every 1.5 seconds** to your browser's local storage.

### Step 4 — Save & Exit
Click **Save & Exit** in the admin bar when done.

> ⚠️ **Important:** Browser auto-save only keeps your changes on that specific browser and device. To make changes permanent and visible to everyone, you must also update `index.html` on GitHub (see Part 2).

---

## Part 2 — How to Publish Changes to the Live Site

Every time you want your edits to go live for all visitors, you update the `index.html` file on GitHub. There is only ever **one file** — no versions, no branches to worry about.

### Method A — Update via GitHub Web Editor (Recommended)

1. Go to https://github.com/ganeshcal/icai-sg-compendium-2026
2. Click on **`index.html`** in the file list
3. Click the **pencil icon ✏️** (top right of the file content area)  
   *(If you're not logged into GitHub, sign in first)*
4. Make your changes in the editor
5. Scroll to the bottom — you'll see **"Commit changes"**
6. Add a short note in the description field, e.g. `Updated sponsor section`
7. Select **"Commit directly to the `main` branch"**
8. Click **"Commit changes"**
9. Wait **30–60 seconds** then refresh the live site — your changes are live

### Method B — Download, Edit Locally, Re-upload

1. Go to https://github.com/ganeshcal/icai-sg-compendium-2026
2. Click on `index.html` → click the **⬇️ download** icon (or right-click Raw → Save As)
3. Open the file in any text editor (Notepad, VS Code, etc.)
4. Make your changes
5. Go back to the GitHub repo → click **"Add file"** → **"Upload files"**
6. Drag your updated `index.html` into the upload area
7. GitHub will warn you the file already exists — that's fine, it will overwrite
8. Click **"Commit changes"** — live in ~30 seconds

---

## Part 3 — How to Manage Editor Accounts

The compendium supports up to **10 user accounts** total:
- **Slot 01** — Master Admin (`icaiadmin`) — always active, hardcoded
- **Slots 02–10** — Editor slots — you fill these in as needed

All accounts are stored directly inside `index.html`, so they work on any machine, any browser.

### Viewing current accounts

Log in as the master admin → click **"Manage Users"** in the admin bar. You'll see a table showing all 10 slots with their status (MASTER / ACTIVE / empty).

### Adding a new editor account

1. Open `index.html` in the GitHub web editor (see Method A above)
2. Press **Ctrl+F** (Windows) or **Cmd+F** (Mac) to open search
3. Search for: `EDITOR_USERS`
4. You'll find this block:

```javascript
const EDITOR_USERS = [
  /* slot 02 */ null,
  /* slot 03 */ null,
  /* slot 04 */ null,
  /* slot 05 */ null,
  /* slot 06 */ null,
  /* slot 07 */ null,
  /* slot 08 */ null,
  /* slot 09 */ null,
  /* slot 10 */ null,
];
```

5. Replace a `null` with the new account details. For example, to activate slot 02:

```javascript
const EDITOR_USERS = [
  /* slot 02 */ { u: 'sanjay', p: 'MyPass@123', n: 'CA Sanjay Gattani' },
  /* slot 03 */ null,
  ...
```

6. Commit the changes — the new account is live immediately

### Removing / deactivating an account

Replace the slot entry back with `null`:

```javascript
  /* slot 02 */ null,
```

Commit — that account can no longer log in.

### Password rules
- Username: letters and numbers only, no spaces, minimum 3 characters
- Password: minimum 6 characters, use a mix of letters, numbers and symbols for security
- Do not reuse the master admin username `icaiadmin`

### Changing the master admin password

1. Open `index.html` in GitHub editor
2. Search for `MASTER =`
3. You'll find: `const MASTER = { u: 'icaiadmin', p: 'ICAI@SG2026', n: 'Chapter Admin' };`
4. Change `ICAI@SG2026` to your new password
5. Commit changes

> 🔐 Share credentials privately (WhatsApp/email). Do not store passwords in the GitHub commit message.

---

## Part 4 — Adding Photos to Profiles

Currently, chairman and profile photos show placeholder initials. To replace with real photos:

1. Upload the photo to a public image host (e.g. [imgbb.com](https://imgbb.com), Google Drive with public sharing, or add the image file to the GitHub repo itself)
2. Get the direct image URL (ending in `.jpg` or `.png`)
3. In `index.html`, find the `photo-placeholder` div for that person
4. Replace the `<div class="photo-placeholder">` block with:

```html
<img src="YOUR_IMAGE_URL_HERE" style="width:100%;aspect-ratio:4/5;object-fit:cover;object-position:top;" alt="CA Name">
```

5. Commit changes

---

## Part 5 — File Structure

This is a **single-file site**. Everything — HTML, CSS, JavaScript — lives in one file:

```
icai-sg-compendium-2026/
├── index.html        ← The entire compendium (edit this)
└── README.md         ← This guide
```

No build process. No dependencies. No npm. Just one HTML file.

---

## Part 6 — Troubleshooting

| Problem | Fix |
|---|---|
| Site not updating after commit | Wait 60 seconds and do a hard refresh (Ctrl+Shift+R) |
| Admin login not working | Check username has no spaces; check caps lock |
| Edits not saving | Make sure you clicked "Save & Exit" and then updated GitHub |
| Page looks broken | Check that you didn't accidentally delete an HTML tag while editing |
| GitHub Pages shows 404 | Go to Settings → Pages → confirm source is set to `main` branch `/root` |

---

## Contact

**ICAI Singapore Chapter**  
#19-03, High Street Centre, 1 North Bridge Road, Singapore 179094  
admin@icai.org.sg · icai.org.sg

---

*This compendium was designed exclusively for placement in accounting and professional services firm receptions across Singapore.*
