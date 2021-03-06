---
theme: apple-basic
layout: intro
titleTemplate: '%s - Ilham Wahabi'
colorSchema: 'dark'
favicon: /images/favicon.png
---

# Into Accessibility

Let's create a better web for everyone!

<div class="absolute bottom-10">
  <span class="font-700">
    Ilham Wahabi, June 25 2021
  </span>
</div>

---

# Who is the speaker???

<br>
<br>

- 😀 **Name:** - Ilham Wahabi
- 📝 **Role:** - Frontend Developer
- 👨‍💻 **Hobby:** - Hacking at [iwgx.io](https://iwgx.io)
- 🧑‍ **Currently:** - CTO Bersihin.co

<br>
<br>

Follow me on [Twitter](https://twitter.com/ilhamwahabigx) and [Github](https://github.com/iwgx) 👋

---
layout: statement
---

# What is Web Accessibility?

---
layout: quote
---

# "Web accessibility means that people with disabilities can use the web."

---
layout: statement
---

# What is Disability?

---
layout: quote
---

# "A disability is any medical condition that makes it more difficult for a person to do certain activities or effectively interact with the world around them (socially or materially)"

---
layout: bullets
---

# Type of Disabilities (total or partial)

<br>

* Attention-Deficit/Hyperactivity Disorders
* Blindness or Low Vision
* Brain Injuries
* Deaf/Hard-of-Hearing
* Learning Disabilities
* Physical Disabilities
* Speech and Language Disabilities

<style>
li {
  line-height: 2.5rem;
}
</style>

---
layout: statement
---

# Why Accessibility Important?

---
layout: quote
---

# "About 30.38 million Indonesians — 14.2 percent of population — had a disability in 2018 "
Survei Sosial Ekonomi Nasional Indonesia

---
layout: quote
---

# "About 56.7 million Americans — 19 percent of the population — had a disability in 2010"
U.S. Census Bureau

---
layout: quote
---

# "An estimated 7.9 million persons (age 6 and older) have difficulty seeing words and letters in ordinary newspaper print"
Lighthouse International Research Study

---
layout: quote
---

# "Currently around 10 per cent of the total world's population, or roughly 650 million people, live with a disability."
Disabled World

---
layout: statement
---

# Developer Should Care

<br>

<v-clicks>

## We're making it inaccessible
## Human rights
## Legal issue
## To reach a larger audience

</v-clicks>

<style>
h2 {
  line-height: 3rem;
}
</style>

---
layout: statement
---

# Another Way to Browsing

---
layout: intro-image-right
image: '/images/head-wand.jpg'
---

# Head Wand

---
layout: intro-image-right
image: '/images/mouth-stick.jpg'
---

# Mouth Stick

---
layout: intro-image-right
image: '/images/single-switch.jpg'
---

# Single Switch

---
layout: intro-image-right
image: '/images/screen-reader.jpg'
---

# Screen Reader

---
layout: statement
---

# Any Complaints?

---
layout: quote
---

# "Amazon were sued in 2018 on claims that their website was inaccessible to the blind and visually impaired"


### The lawsuit claimed that the website Amazon.com did not provide text alternatives for non-text content on its website, blocking screen-reading software from presenting information to visually impaired users


---
layout: quote
---

# "Burger King was subject to an ADA lawsuit in 2018."

### It explained that every time the claimant visited the website, they experienced problems that prevented from accessing key information about their goods and services.

---
layout: quote
---

# "In 2012, it was claimed that Netflix, failed to provide adequate closed captioning on its 'Watch Instantly' program."

### A settlement was agreed and Netflix agreed to quickly provide captions on newly released content.

---

## the list goes on:

<v-clicks>

* Apple
* Nike
* Hulu
* Bank of America
* Rolex
* eHarmony
* NBA
* and many more ...

</v-clicks>

<br>
<br>
<br>

<v-click>

# (Y)our company next ???

</v-click>

---
layout: statement
---

# Let's Prevent That

---

## Image Alt Text ( \<img alt="..." \/\> )

<v-clicks>

- Make it accurate
- Make it concise
- Don't be redundant
- Don't use "image of" or "graphic of"
- If just decorative, use empty string to make it ignored

</v-clicks>

<br>

<v-click>

```html{1-2|4-5|7-8|10-11|all}
<!-- Bad example, no alt text ❌ -->
<img src="bandung.jpg" />

<!-- Bad example, we already know that was a picture ❌ -->
<img alt="Picture of Bandung" src="bandung.jpg" />

<!-- Good example ✅ -->
<img alt="The heavy traffic of Bandung city" src="bandung.jpg" />

<!-- Good example, if it's just decorative image ✅ -->
<img alt="" src="pattern.jpg" />
```

</v-click>

---

## Semantic HTML

<v-clicks>

- Always prefer appropriate native element
- Use headings hierarchically (h1-h6)
- Use landmarks (header, footer, etc)
- If you have to, use proper attributes to mimic it

</v-clicks>

<br>

<v-click>

```html{1-2|4-5|7-11|13-14|all}
<!-- Bad example, prefer "button" instead ❌ -->
<div onclick="btnClicked()">Click Me</div>

<!-- Bad example, prefer "h1" instead ❌ -->
<p class="header-1" />

<!-- Bad example, heading should used hierarchically ❌ -->
<main>
  <h1>Ilham Blogs</h1>
  <h6>Getting Started in React</h6>
</main>

<!-- Good example, use tag properly ✅ -->
<a href="twitter.com">Navigate to Twitter</a>
```

</v-click>

---
layout: intro-image-right
image: '/images/contrast.png'
---

# Color Contrast
- Element color and background color should have clear differentiation
- You can check in dev tools or using browser extension

<br>

---
layout: intro-image-right
image: '/images/focus.png'
---

# Focus Management
- KEEP the focus ring
- Make interactive element can be focused (button, link, input, etc)

---

## ARIA Attributes
- Accessible Rich Internet Applications
- ARIA is a set of attributes you can add to HTML elements that define ways to make web content and applications accessible to users with disabilities who use assistive technologies

<br>

<v-click>

```jsx {all|2|3|all}
// Declare that a element is hidden 
<div id="popup" tabindex="-1" aria-hidden="true">
  <p>I'm hidden</p>
</div>
```

</v-click>

<v-click>

```html {all|3|2|all}
<!-- Adding a label to button without text -->
<button aria-label="Login button">
  <icon>mdi_login</icon>
</button>
```

</v-click>

---

## Announcements
- User know what happened / changed
- Example usage: error message and adding items to the cart

<br>

```jsx {all|3-5|all}
// Notify user if there is error
<div
  aria-live="assertive"
  aria-atomic="true"
  aria-relevant="additions text"
>
  { isValid ? '' : errorText }
</div>
```

<br>

---
layout: section
---

# actually many more...

<br>
<br>
<br>

<v-click>

## let's save it for the next occasion :)

</v-click>

---
layout: fact
---

# THAT'S ALL

<v-click>

Let's Discuss!

</v-click>