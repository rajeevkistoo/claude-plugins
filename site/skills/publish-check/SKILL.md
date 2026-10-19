---
name: publish-check
description: Check a contractor website is ready to go live, fix what is wrong, then walk the user through publishing it on Netlify with their own domain and a working quote form. Use before publishing, or when the user asks "is it ready?", "publish it" or "put it live".
---

# /site:publish-check

Go through the whole site and fix what you can before it goes live. Then walk the user through publishing it. Report in plain words: what you checked, what you fixed, and what only they can fix.

## Check and fix

**Nothing fake or unfinished goes live**
- Search every file for `TODO`, `lorem`, `example.com`, `555-`, `your-domain`, `[`, `XXX`. List each one, and ask the user for the real detail.
- Every review, licence number, year and guarantee matches `brief.md`. Anything that isn't in the brief comes out.

**People can reach them**
- Every phone number is a `tel:` link with the right number, and the number is the same everywhere.
- Every form has `data-netlify="true"`, a unique `name`, the hidden `form-name` input matching that name, the `bot-field` honeypot, and `action="/thank-you/"`.
- `/thank-you/` exists.
- On phones, the bottom Call / Free quote bar shows and works.

**Nothing broken**
- Every internal link and image points at a file that exists.
- Every page has `<meta name="viewport" content="width=device-width, initial-scale=1">`, a `<title>` and a meta description.
- `404.html`, `favicon`, `sitemap.xml` and `robots.txt` exist.
- No image file is over 500 KB. Shrink any that are.
- Pages look right at phone width: no sideways scrolling, and form fields are 16px or bigger.

## Then walk them through publishing

Say each step, wait for them to do it, then go on to the next.

1. **Netlify:** log in at app.netlify.com → **Add new project** → **Deploy manually** → drag this whole folder onto the page. They get a live link ending in `.netlify.app` within seconds.
2. **Turn on forms:** in the project, open **Forms** and click **Enable form detection**. Then drag the folder onto the **Deploys** page once more, so Netlify picks up the forms. Without this, quote requests go nowhere.
3. **Form emails:** **Forms → Form notifications → Add notification → Email**, using the email from the brief.
4. **Test it:** fill in the quote form on their phone. Check that it shows under **Forms** and that the email arrives. **Check the spam folder**: the first one often lands there. Mark it "not spam".
5. **Their domain:** **Domain management → Add a domain**, type the domain, and follow what Netlify shows: either change the DNS at the domain company, or point the domain at Netlify. Netlify adds the padlock (HTTPS) on its own once the domain points at it. That can take a few minutes up to an hour.
6. **Visitors see a login page?** Go to **Project configuration → Access & security → Visitor access** and make sure the live site is public.
7. **Text the link to three people** and ask them to try to break it on their phones.

From now on, every change works the same way: ask the agent, check it in the browser, then drag the folder onto **Deploys** again.
