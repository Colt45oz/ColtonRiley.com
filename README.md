# coltonriley.com

Personal branding website for Colton Riley — built with pure HTML/CSS/JS, deployed via GitHub Pages.

---

## File Structure

```
coltonriley.com/
├── index.html          ← Homepage (required root file for GitHub Pages)
├── about.html
├── work.html
├── contact.html
├── private.html        ← Password-gated private dashboard
├── style.css           ← Shared stylesheet
└── README.md
```

---

## Before You Push

### 1. Add your photo
- Save your headshot as `photo.jpg` in the root folder
- Replace the placeholder in `index.html` and `about.html`:
  ```html
  <!-- Find this: -->
  <span style="font-size:3rem;">🌿</span>
  <!-- Replace with: -->
  <img src="photo.jpg" alt="Colton Riley" />
  ```

### 2. Set your private dashboard password
- Open `private.html`
- Find this line near the bottom:
  ```js
  const PASSWORD = 'changeme2025';
  ```
- Change `changeme2025` to your desired password
- ⚠️ Remember: since this repo is public, the password is visible in source code. This protects against casual visitors only.

### 3. Add Strava embed
- Go to strava.com on desktop → open an activity
- Click `...` → Share → Embed on Blog
- Copy the embed code
- Open `index.html`, find the Strava placeholder comment, and replace with your embed code

### 4. Enable the contact form (optional)
- Sign up free at [formspree.io](https://formspree.io)
- Create a form, get your endpoint URL
- In `contact.html`, change the `<form>` tag:
  ```html
  <form action="https://formspree.io/f/YOUR_ID" method="POST">
  ```
- Remove the `onsubmit="handleSubmit(event)"` attribute and the handleSubmit script

### 5. Add your resume PDF (optional)
- Save your resume as `Colton_Riley_Resume_2025.pdf` in the root folder
- The download buttons in `about.html` and `work.html` will work automatically

---

## Deploying to GitHub Pages

### Step 1: Push to GitHub
```bash
git init
git add .
git commit -m "Initial site launch"
git remote add origin https://github.com/Colt45oz/coltonriley.com.git
git push -u origin main
```

### Step 2: Enable GitHub Pages
1. Go to your repo on GitHub
2. Click **Settings** → **Pages** (left sidebar)
3. Under "Build and deployment" → Source → select **Deploy from a branch**
4. Branch: `main`, folder: `/ (root)` → Save
5. Your site will be live at `https://colt45oz.github.io/coltonriley.com/`

---

## Connecting coltonriley.com via Bluehost

### Step 1: Set custom domain in GitHub
1. In repo Settings → Pages → Custom domain
2. Type `coltonriley.com` → Save
3. This creates a `CNAME` file in your repo automatically

### Step 2: Add DNS records in Bluehost
1. Log in to Bluehost → **Domains** → **coltonriley.com** → **DNS**
2. Delete any existing A records for `@`
3. Add 4 new **A records**:
   - Host: `@`  →  Value: `185.199.108.153`
   - Host: `@`  →  Value: `185.199.109.153`
   - Host: `@`  →  Value: `185.199.110.153`
   - Host: `@`  →  Value: `185.199.111.153`
4. Add 1 **CNAME record**:
   - Host: `www`  →  Value: `colt45oz.github.io`
5. Save all records

### Step 3: Enforce HTTPS
- After DNS propagates (up to 48 hours, usually ~1-4 hrs)
- Return to GitHub Settings → Pages
- Check ✅ **Enforce HTTPS**

### Verify DNS is working
```bash
dig coltonriley.com +noall +answer -t A
# Should return the 4 GitHub IP addresses above
```

---

## Future Additions (Planned)

- `stocks.html` — Live stock price tracker
- `pace.html` — Running pace calculator
- Resume PDF upload

---

© 2025 Colton Riley · cr@coltonriley.com
