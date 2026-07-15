# my little corner of the web 🌸

A tiny personal blog that looks like a cute 90s operating system. Posts show up
as little "programs" — click one and it opens in a draggable window.

No build step, no dependencies to install. It's just plain HTML, CSS, and
JavaScript (plus the `avatar.png` and `glasses.svg` assets).

## Running it locally

Open `index.html` in your browser. That's it.

(If your browser is fussy about the web fonts loading from `file://`, run a quick
local server instead: `python3 -m http.server` then visit
<http://localhost:8000>.)

## Editing your info

Open **`index.html`** and edit the `about_me.txt` window near the top:

- the avatar image (`avatar.png`)
- your name and tagline
- the short bio line
- the email / github / linkedin / albert links

## Adding a blog post

Open **`script.js`** and add an object to the `POSTS` array at the top. Copy an
existing one and fill it in:

```js
{
  title: "My New Post",
  slug: "my-new-post",    // used in the shareable URL (see "Linking" below)
  icon: "✨",             // shown as the little program icon
  date: "Aug 2026",
  desc: "One line shown in the list.",
  content: `
    <p>Write your post here. You can use HTML:</p>
    <h3>a subheading</h3>
    <p>paragraphs, <a href="https://example.com">links</a>, lists, etc.</p>
  `,
},
```

Newest posts look best at the **top** of the array.

Swift code blocks get automatic syntax highlighting. Wrap code in
`<pre><code>…</code></pre>`, and remember HTML-escape `<` `>` `&` inside it (e.g.
write `-&gt;` for `->`).

## Linking to a post

Every post has its own shareable URL using the `slug`, for example:

```
https://your-site/#my-new-post
```

Opening that link (or pasting it) opens the post's window automatically, and the
address bar updates to the post's link whenever you open one. If you leave out
`slug`, one is generated from the title — but set an explicit `slug` so the link
stays stable even if you reword the title later.

## Publishing

Because it's plain static files, you can drop the folder onto any static host —
GitHub Pages, Netlify, Vercel, Cloudflare Pages — and it'll just work.
