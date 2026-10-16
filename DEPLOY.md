# Deploying diathermtech.com

Pick ONE option.

## Option A: Netlify (easiest, no Git needed)
1. Go to app.netlify.com/drop and drag the `diatherm-site` folder in.
2. Site settings > Domain management > Add custom domain > `www.diathermtech.com`.
3. In Namecheap > Domain List > diathermtech.com > Advanced DNS, delete the default parking records and add:
   - `A Record` | Host `@` | Value `75.2.60.5`
   - `CNAME Record` | Host `www` | Value `<your-site-name>.netlify.app`
4. Back in Netlify, enable HTTPS (Let's Encrypt, automatic once DNS resolves).

## Option B: GitHub Pages
1. Create a public repo (e.g. `diatherm-site`), upload `index.html` and `CNAME`.
2. Settings > Pages > Source: `main` branch, root. Custom domain: `www.diathermtech.com`.
3. In Namecheap Advanced DNS add:
   - 4x `A Record`, Host `@`: `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - `CNAME Record` | Host `www` | Value `<your-github-username>.github.io`
4. Tick "Enforce HTTPS" once the certificate is issued.

DNS usually propagates in 5 to 60 minutes.

## Email (later)
No email is on the site yet. Once you have a verified address, add it back in the Contact section of `index.html`.
- Free: Namecheap > Domain > Redirect Email > forward e.g. `hello@` to your inbox.
- Proper mailbox: Google Workspace or Zoho Mail (needs MX records in Advanced DNS).
