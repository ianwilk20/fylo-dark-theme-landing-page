# Frontend Mentor - Fylo dark theme landing page solution

This is a solution to the [Fylo dark theme landing page challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/fylo-dark-theme-landing-page-5ca5f2d21e82137ec91a50fd). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
  - [Continued development](#continued-development)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout for the site depending on their device's screen size
- See hover states for all interactive elements on the page

### Screenshot

Desktop:

![Desktop initial state](/design/sol-desktop-init.png)

Mobile: 

![Mobile initial state](/design/sol-mobile-init.png)

### Links

- [Live Site URL](https://fylo-landing-page-ianwilk20.netlify.app/design/)

## My process

### Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Grid
- Mobile-first workflow

### What I learned

An alternative way to create a modal. I saw the obvious way to implement the "Get early access today" modal, by making an absolutely positioned element and tinkering with the testimonials and footer sections in a way for the modal to not cover that content (using margin/padding). To save me trouble of determining the right margin/padding for an absolute positioned element for different screen sizes I tried another approach to design the modal. I created a modal-like appearance and had it follow the flow of the page rather than removed from the flow like absolute positioned elements. I was able to accomplish this by reusing the card from the testimonials section and wrapping it in a container that has a background color split between the lighter blue main color and the darker blue footer color. For the elevated look of typical modals, I gave the card a box-shadow.

How to use a button hover state to trigger a change in another element. For example, the "See how Fylo works" button has an image of an arrow nested inside of it. I wanted the svg of the arrow to change (between a cyan and a white arrow) when the button was hovered. A solution to this, I learned, is to nest both images in the button but the one that will appear when the button is hovered will initally have a display of none. When the button is hovered, the hidden image will have a display of block and the inital image will be hidden. Here's how it looks in code:

```CSS
.btn-how-it-works:hover {
    color: var(--white);
    border-bottom: var(--white) 1px solid;
}

.btn-how-it-works:hover .hover-arrow {
    display: inline-block;
}

.btn-how-it-works:hover .init-arrow {
    display: none;
}

.init-arrow,
.hover-arrow {
    transform: translateY(0.25rem);
    padding-left: 0.2rem;
}

.init-arrow {
    content: url('../images/icon-arrow.svg');
}

.hover-arrow {
    display: none;
    content: url('../images/icon-arrow-white.svg');
}
```


### Continued development

Something that could benefit my CSS is following the BEM naming conventions. At the moment, I gravitate towards naming an elements CSS class based on what it looks like, ex. ```.btn-how-it-works``` is a button with a label "How it works", or what the elements purpose is, ex. ```.img-user-bruce``` is an image tag that for Bruce's profile. Standardizing the


### Useful resources

- [Change an image on hover of an element](https://stackoverflow.com/a/66944264) - This helped me figure out how to use a button hover state to trigger a change in which arrow color is displayed in another element.
- [Transition CSS Property](https://developer.mozilla.org/en-US/docs/Web/CSS/transition) - I read this article to understand how to use the transition property.

## Author

- GitHub - [ianwilk20](https://github.com/ianwilk20)