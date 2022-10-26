%title: Time traveling through HTML rendering
%author: lfberge
%date: 2022-10-27

-> # dev/🍺 <-

-> ## Time traveling through HTML rendering <-

-> _Where should we create our HTML?_ <-

---

-> # whoami <-

```
 -----------
< lfberge   >
< 34ish     >
< developer >
 -----------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
```

---

-> # 1991: The beginning <-

Where the developer was the Static Site Generator (SSG)
and everything was Server side Rendered (SSR)

---

-> # 1995ish: Javascript <-

Brendan Eich at Netscape changed the world
But the world hadn't realized yet
Also _php_

The haydays of SSR enriched javascript at the client

---

-> # 2005ish: The integrated servers <-

Ruby on Rails, AST.net and so on brings lots of new stuff
Dreamweaver and FrontPage changed the way we created HTML

jQuery begins to utilize the power of JS to actually change the world

---

-> # 2010ish: The frameworks <-

We've reached client side with Backbone.js, Knockout.js, Angular.js, React
(and perhaps a few more)

Multi page application (MPA) and SSR was so old
Single page application (SPA) with client side rendering (CSR) 🫶

Honestly speaking, this is now. Strim.Play is a SPA with CSR

---

-> # 2010ish continue <-

Lets demo this in 2022 form

[https://rendertime-client-side.vercel.app/](https://rendertime-client-side.vercel.app/)

---

-> # 2016ish: The meta-frameworks <-

Vercel starts a server hosting platform
and figures wouldn't we make a lot more money
if we move most of the work from the client
to our server farm?

And Next.js was born

---

-> # 2016ish continue <-

So lets run our JS code on the server SSR and/or SSG,
and sending the HTML over the wire,
then hydrate the JS so the app works

New open strim.no webapp does this

[https://rendertime-server-side.vercel.app/](https://rendertime-server-side.vercel.app/)

---

-> # 2020ish: The islands <-

What if doing both SSR and CSR is double the work?
Maybe we don't always need a SPA? Was 1991 right all along?

Bring in the island architecture

Instead of hydrating the entire app, why on only hydrate the dynamic parts?

---

-> # 2020ish <-

I'll be using Astro for this, but if you are really cool
maybe you think 13 year old Node.js C/C++ isn't hype enough..

Deno Fresh might be for you, thats only 4 years old and written in rust ❤️

[https://rendertime-islands.vercel.app/](https://rendertime-islands.vercel.app/)

---

-> # 2022ish: The future? <-

So how could we improve over islands?

How about just using HTML?

[https://rendertime.pages.dev/](https://rendertime.pages.dev/)

---

-> # What to use when <-

| What                 |                      When                      |
| -------------------- | :--------------------------------------------: |
| HTML/CSS             |              You live in the past              |
| jQuery               |                 You like pain                  |
| backbone/knockout/.. |             You have a legacy app              |
| React/Vue/Angular    |           Performance doesn't matter           |
| Next.js/Remix        |            Kinda the default choice            |
| Astro/Deno Fresh     | You have a partial static partial dynamic site |
| qwik                 | You like the bleeding edge, also mostly static |

---

-> # Wrapitup continue <-

The code:

- [https://github.com/lfbergee/rendertime](https://github.com/lfbergee/rendertime)

The slides:

- [https://github.com/lfbergee/presentations](https://github.com/lfbergee/presentations)

The apps:

- [https://rendertime-client-side.vercel.app/](https://rendertime-client-side.vercel.app/)
- [https://rendertime-server-side.vercel.app/](https://rendertime-server-side.vercel.app/)
- [https://rendertime-islands.vercel.app/](https://rendertime-islands.vercel.app/)
- [https://rendertime.pages.dev/](https://rendertime.pages.dev/)
