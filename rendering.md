%title: A travel through rendering
%author: lfberge
%date: 2022-03-16

-> # dev/lett/øl <-

-> ## A travel through rendering <-

-> _Where should we turn javascript to HTML?_ <-

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

-> # 1991 <-

Where the developer was the Static Site Generator (SSG)
and everything was Server side Rendered (SSR)

---

-> # 1995ish <-

Brendan Eich at Netscape changed the world
But the world hadn't realised yet
Also _php_

The haydays of SSR enriched javascript at the client

---

-> # 2010ish <-

We've reached client side with Backbone.js, Knockout.js, Angluar.js, React 
(and perhaps a few more)

Multi page applicaiton (MPA) and SSR was so old
Single page application (SPA) with client side rendering (CSR) :heart:

Honestly speaking, this is now. Strim.Play is a SPA with CSR

---

-> # 2010ish continue <-

Lets demo this in 2022 form

[https://rendertime-client-side.vercel.app/](https://rendertime-client-side.vercel.app/)

---

-> # 2016ish <-

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

[https://vercel.com/lfbergee/rendertime-server-side](https://vercel.com/lfbergee/rendertime-server-side)

---

-> # 2020ish <-

What if doing both SSR and CSR is double the work?
Maybe we don't always need a SPA? Was 1991 right all along?

Bring in the island architecture

Instead of hydrating the entire app, why on only hydrate the dynamic parts?

---

-> # 2020ish <-

I'll be using Astro for this, but if you are really cool
maybe you think 13 year old Node.js C/C++ isn't hype enough..

Deno Fresh might be for you, thats only 4 years old and written in rust :love:

[https://rendertime-islands.vercel.app/](https://rendertime-islands.vercel.app/)

---

-> # 2022ish <-

So how could we improve over islands?

How about just using HTML?

[https://rendertime.pages.dev/](https://rendertime.pages.dev/)

---

-> # Wrapitup <-

It's time to rewrite everything then?

---

-> # Wrapitup contine <-

No

---

-> # Wrapitup contine <-

But we have a lot of tools we can use now
So we can tailor our apps based on our customers needs
without sacreficing the DX

---

-> # Wrapitup contine <-

The code:

[https://github.com/lfbergee/rendertime](https://github.com/lfbergee/rendertime)

The slides:

[https://github.com/lfbergee/presentations](https://github.com/lfbergee/presentations)
