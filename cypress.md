%title: Cypress
%author: lfberge
%date: 2022-02-16

-> # dev/lett/øl <-

-> ## Cypress <-

-> _Make everybody like testing_ <-

---

-> # About <-

I am more or less an idiot, 
so this presentation is in the terminal

This talk is written with humor in good spirit,
please do not be offended even if you love Java,
Selenium, TestComplete or testing in general

Also when i say testing, i usually refer to 
**manual testing**, unless otherwise specified

_I mean no harm_

---

-> # This is how it works <-

> This blocks represent "you"

...maybe a snarky, iconic and a stupid version of "you"

And I will try to respond to "you" and you, so please
**interupt** if you have something to share

---

-> # whoami <-

```
 -----------
< lfberge   >
< 30ish     >
< developer >
 -----------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
```

---

-> # Lets go <-

> I don't like testing

Yes, _nobody_ likes testing

So how do we deal with that?
- Don't do it
- Power through and do better
- Hire someone

---

-> # Or we automate <-

> But e2e test are flaky, slow and hard to maintain

## HOWEVER

- Cypress is not _Selenium_
- Cypress is not _Puppeteer_
- Cypress is definitely not **TestComplete**

---

-> # But... <-

> its slow

Kinda yeah, but manual regression testing is even slower
and incredible boring and hard to do right

Also, shipping errors to users are both boring, slow and
embarrassing 

Also also, it might be faster than you think, and you could
split the tests on as many containers as you have tests

---

-> # But... <-

> its flaky

Well. Not like Selenium. No `stale reference error`
Random errors are close to 0 in properly configured envs.

But if your UI changes, you must update the UI tests

---

-> # But... <-

> I don't wanna
or 
> I don't make mistakes

Really?? 
Testing is unfortunately everyone's responsibility, 
so don't be that guy (or gal)

And yes, even you do make mistakes
... or at least a colleague

---

-> # Alright you have convinced me <-

NICE

Lets look at component testing

---

-> # Component testing <-

"Traditionally" (read since 2018) we've used Jest with JSDOM for this

However testing React component in a synthetic environment has some pitfalls

- Boilerplate code for days
- Super easy to test implementations, not features
- Do you actually test the component or the synthetic environment?
- Also, do you test functionality that matters for
  the user or are you pleasing the test-coverage gods?

## Why not test in the browser?

> But Karma...

> > yeah, but it's 2022 com'on people

---

-> # Component testing <-

> Jest has snapshot testing, no boilerplate, no effort

Yes, but also almost no value for React Components
You only verify that the code is the same
not that it works, and definitely not
that our users can get their s**t done

---

-> # Component testing <-

There is no synthetic environment, its your browser

- Almost no boilerplate
- You test where you users are
- You tests act as users
- Screenshots, videos, snapshots, snapshots of screenshots 🤯

---

-> # Alright you have convinced me again <-

NICE

But not so fast, before you rewrite all your tests
- It's not for unit testing
- It's not fast compared to even Jest
  - Not to speak of uvu, ava or vitest
- Maybe you don't even need it?

---

-> # Client testing <-

Components are easy, apps are hard
Lets emulate our users, test as they use our apps

- Inbuilt network intercepts
- Intuitive getters, asserts and actions
- Extendable, pluginable, customizable
- Familiar to web devs
    - `(java|type)script`
    - mocha-syntax
    - chai expecters
    - jQuery (its still a thing, and a quite good thing)
    - **NO JAVA** or python or ruby (looking at you Selenium)
- Screenshots, videos, snapshots, snapshots of screenshots 🤯
- Documentation and onboarding 🤯

-> # Client testing <-

## DX

- It's actually quite fun
- It provides value immediately
- It takes off the pressure off
  - critical releases
  - large refactors
  - core dependency updates

---

-> # Interesting, but how? <-

In Strim.Play app we have test for almost 
all permutation of activation flows.

Login and all services are mocked,
thus we can have destructive tests

On posts we capture the request and expect
the data matches shape and content wise

---

-> # SHOW ME! <-

```
describe('no external provider, user has Strim MINI', () => {
  it('my account', () => {
    cy.mockLogin();
    cy.mockCustomer({ viaplay: false, hbo: false, tv2play: false });
    cy.customerWithStrimMINI();

    cy.visit('/account');
    cy.getByDataId('tilganger').should('not.exist');
  });
})
```

---

-> # Conclusion <-

I guess we all agree:
1. Testing is horrible!
2. Test automation is great!
3. Cypress is awesome!

> [Everything is awesome!](https://www.youtube.com/watch?v=StTqXEQ2l-Y)

---

-> # Demo please <-

And references:
- [https://www.cypress.io/](https://www.cypress.io/)
- [Accordion test in design system](https://git.rikstv.no/rikstv/shared/rikstv.designsystem/-/blob/master/shared-components/src/components/accordion/Accordion.test.tsx)
- [Cypress code in Strim.Play](https://git.rikstv.no/rikstv/apps-team/RiksTV.App.WebApps/-/tree/master/packages/tooling/cypress)
- I also want to be cool and have my presentation in the [terminal](https://github.com/visit1985/mdp)
