# R.C. Langlands — Author Website

## File Structure

```
rclanglands/
├── index.html          ← Main homepage
├── post.html           ← Individual Musings post page
├── success.html        ← Newsletter signup thank-you page
├── favicon.svg          ← Browser tab icon
├── robots.txt           ← Search engine crawling rules
├── sitemap.xml           ← Search engine sitemap
├── wrangler.jsonc        ← Cloudflare Workers configuration
├── css/
│   └── style.css       ← All site styles
├── content/
│   ├── site.json        ← Hero and About section text
│   └── books.json       ← The four Seasons books' details
├── images/
│   └── author-photo.jpg
├── posts/
│   └── posts.json      ← All Musings posts (edit this to publish)
└── admin/
    └── index.html      ← Admin panel for writing posts (password protected)
```

---

## How the site is deployed

This site is hosted on **Cloudflare Workers** (not Netlify), connected directly to this GitHub repository. Every time you commit a change to the `main` branch here on GitHub, Cloudflare automatically detects it and redeploys the live site — usually within a minute or two, no manual steps needed.

Live site: https://rclanglands.rileslanglands.workers.dev

If you ever want to add a custom domain (e.g. `rclanglands.com`):
1. Buy the domain from a registrar (e.g. Namecheap, GoDaddy)
2. In the Cloudflare dashboard, go to your Worker's settings → Domains & Routes → Add a custom domain
3. Follow Cloudflare's instructions to point your domain — usually takes 10–30 minutes to propagate

---

## How to write and publish Musings posts

### Using the admin panel

1. Go to `yoursite.workers.dev/admin` in your browser (replace with your actual domain)
2. Log in with your admin password (see "Changing your admin password" below)
3. Click **+ New post**, write your post using the toolbar (bold, italic, headings, alignment, fonts, images), click **Publish**
4. The admin panel will download a new `posts.json` file to your computer containing all your posts
5. Go to your GitHub repo → `posts/posts.json` → click the pencil (edit) icon
6. Select all the existing text, paste in the newly downloaded `posts.json` content, click **Commit changes**
7. Cloudflare redeploys automatically — your post is live within a minute or two

### Adding a photo to a post

1. Upload the image file to `images/musings/` in your GitHub repo (create the folder if it doesn't exist yet)
2. In the admin panel's content box, type: `![A short description of the photo](images/musings/your-filename.jpg)`

### Changing your admin password

**This should be treated as a priority, not optional.** The password currently lives in plain, readable text in `admin/index.html` — and since this repository is public, anyone can view that file and read it directly.

Open `admin/index.html` and find this line:
```javascript
const ADMIN_PASSWORD = 'your-current-password-here';
```
Change the text between the quotes to a new password only you know, save, and commit. For genuinely secure protection (recommended before or shortly after launch), consider using Cloudflare Access to put a real login wall in front of the `/admin` path instead — ask Claude to help set this up.

---

## Updating the site

Any time you want to change something:
1. Edit the relevant file (e.g. `index.html` for homepage structure, `content/site.json` for bio/hero text, `css/style.css` for styling)
2. Go to GitHub, find the file, click the pencil icon, paste your changes, commit
3. Cloudflare redeploys automatically

Or ask Claude to make the changes and provide you with updated files or exact edits to apply.
