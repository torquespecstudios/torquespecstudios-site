# torquespecstudios.com website

Static site, no build step. The files are:

- `index.html`: studio home page, featuring Swervy.
- `privacy.html`: the Swervy privacy policy (`#privacy`) and support page (`#support`).
- `img/`: the icon and screenshots.

## Contact email
Both pages use support@torquespecstudios.com. To change it later, replace it in both HTML files.

## Host it free on GitHub Pages
1. Create a free GitHub account, then a **public** repository named `torquespecstudios-site`.
2. Choose **Add file → Upload files**, drag in everything in this folder (keep the `img` folder), and commit.
3. Go to **Settings → Pages**, set Source to **Deploy from a branch**, choose **main** and **/ (root)**, and save. After a minute it's live at `https://<your-username>.github.io/torquespecstudios-site/`.

## Point torquespecstudios.com at it (Namecheap)
1. In GitHub, go to **Settings → Pages → Custom domain**, enter `torquespecstudios.com` and save.
2. In Namecheap, go to **Domain List → Manage** (next to torquespecstudios.com) → **Advanced DNS**.
3. Delete the parking records Namecheap added: the **CNAME `www` → parkingpage.namecheap.com** and the **URL Redirect `@`**.
4. Add these records (Host / Value, TTL Automatic):
   - **A Record** `@` → `185.199.108.153`
   - **A Record** `@` → `185.199.109.153`
   - **A Record** `@` → `185.199.110.153`
   - **A Record** `@` → `185.199.111.153`
   - **CNAME Record** `www` → `<your-github-username>.github.io.`
5. Wait 10–60 minutes (sometimes up to a day). Then, back in GitHub Pages, tick **Enforce HTTPS**.

### Free email on your domain (optional)
In Namecheap, go to **Domain List → Manage → Redirect Email**. Add `hello` (or `support`) forwarding to support@torquespecstudios.com. Mail sent to support@torquespecstudios.com then lands in your Gmail.

## Generic DNS steps (any registrar)
1. In **Settings → Pages → Custom domain**, enter `torquespecstudios.com` and save.
2. At your domain registrar, add these DNS records:
   - four **A** records for `@`: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - one **CNAME** record for `www` pointing to `<your-username>.github.io`
3. Back in GitHub Pages, tick **Enforce HTTPS** once it becomes available (DNS can take up to a day).

## URLs for App Store Connect
- Marketing URL: `https://torquespecstudios.com/`
- Support URL: `https://torquespecstudios.com/privacy.html#support`
- Privacy Policy URL: `https://torquespecstudios.com/privacy.html#privacy`
