# R.C. Langlands — Author Website

## File Structure

```
rc-langlands-site/
├── index.html          ← Main homepage
├── post.html           ← Individual journal post page
├── css/
│   └── style.css       ← All site styles
├── js/                 ← (empty, for future scripts)
├── images/
│   └── author-photo.jpg
├── posts/
│   └── posts.json      ← All journal posts (edit this to publish)
└── admin/
    └── index.html      ← Admin panel (password protected)
```

---

## How to go live: GitHub + Netlify

### Step 1 — Upload to GitHub

1. Go to [github.com](https://github.com) and create a free account if you don't have one
2. Click **New repository**, name it `rc-langlands-site`, set it to **Public**, click Create
3. On the next screen, click **uploading an existing file**
4. Drag the entire contents of this folder into the upload area
5. Click **Commit changes**

### Step 2 — Connect to Netlify

1. Go to [netlify.com](https://netlify.com) and sign up (free) — use your GitHub account to sign in
2. Click **Add new site → Import an existing project → GitHub**
3. Select your `rc-langlands-site` repository
4. Leave all settings as default and click **Deploy site**
5. Your site will be live at a URL like `rc-langlands-abc123.netlify.app`

### Step 3 — Add a custom domain (optional)

1. Buy a domain at [namecheap.com](https://namecheap.com) (e.g. `rclanglands.com`)
2. In Netlify: Site settings → Domain management → Add custom domain
3. Follow Netlify's instructions to point your domain — takes about 10 minutes

---

## How to write and publish journal posts

### Using the admin panel

1. Go to `yoursite.netlify.app/admin` in your browser
2. Password: `seasons2026` ← **change this in admin/index.html before going live**
3. Click **+ New post**, write your post, click **Publish**
4. The admin will automatically download a new `posts.json` file
5. Go to your GitHub repo → `posts/posts.json` → click the pencil (edit) icon
6. Select all the existing text, paste in your new `posts.json` content, click **Commit changes**
7. Netlify redeploys automatically — your post is live in about 30 seconds

### Changing your admin password

Open `admin/index.html` and find this line near the top of the script:
```javascript
const ADMIN_PASSWORD = 'seasons2026';
```
Change `seasons2026` to whatever you'd like, save, and re-upload to GitHub.

---

## Updating the site

Any time you want to change something:
1. Edit the relevant file (e.g. `index.html` for homepage content, `css/style.css` for styling)
2. Go to GitHub, find the file, click the pencil icon, paste your changes, commit
3. Netlify redeploys automatically

Or ask me (Claude) to make changes and I'll give you updated files to re-upload.
