# SCSS Structure

This is intended as a quick SCSS file setup. The file-strucure is based on [a blog post by Matthias Ott](https://matthiasott.com/notes/how-i-structure-my-css). Please check it out if you want more complete info.

### File Reference
[Settings](#scss-settings)  
[Design Tokens](#scss-design-tokens)  
[Tools](#scss-tools)  
[Generic](#scss-generic)  
[Elements](#scss-elements)  
[Skeleton](#scss-skeleton)  
[Components](#scss-components)  
[Utilities](#scss-utilities)  
[Shame](#scss-shame)

### Credits
Full credits go to [Matthias Ott](https://matthiasott.com/notes/how-i-structure-my-css). I highly recommend reading his blog post.

## <a name="scss-settings"></a>Settings
For all general project settings, so for the most basic high-level configuration. This might be a collection of global variables – either as Sass variables or custom properties.

## <a name="scss-design-tokens"></a>Design Tokens
For all styles regarding the visual vocabulary of the site. At this level, we are still not generating any CSS output. It is where we define variables for the typography, colors, spacing, media-queries, or any other attributes which you will use throughout the design. For these visual design attributes, the term design tokens has taken hold. Those design tokens could even be coming from your design system as a single source of truth.

## <a name="scss-tools"></a>Tools
This is where your global Sass mixins and functions live. Maybe you want to manipulate colors with blend modes or set the aspect ratio for a video container? Or clear your float, for example. 

## <a name="scss-generic"></a>Generic
The generic folder is the first one that actually produces CSS. It contains global box-sizing rules, CSS resets, or print styles – anything that should be set right at the beginning of your CSS but isn’t yet project-specific.

## <a name="scss-elements"></a>Elements
Style the building blocks of our front-end: Raw HTML Elements. Mostly without classes, we are now redefining the basic browser styles of headlines, buttons, links, lists, etc. and can make sure that all components in our design are using the same consistent base.

## <a name="scss-skeleton"></a>Skeleton
Any modern web project that is built with components also comes with the need for a higher-level structure in which all the components can live: Wrappers, containers, grids, and all kinds of reusable objects that provide layout patterns. This is the skeleton of your site.

## <a name="scss-components"></a>Components
The beating heart of the project. This is where we design the components of the UI. In a few recent projects, I sometimes distinguished between larger modules and smaller components, but you can also nest components into each other and do without the additional distinction. Use prefixes, if you like, and also [a naming convention like BEM](https://css-tricks.com/bem-101/) can make a lot of sense. I have recently settled on a BEM-like but more simplified naming convention: Just use the simplest but most descriptive class name possible and separate elements within other elements with a simple dash, like .card and .card-content.

## <a name="scss-utilities"></a>Utilities
The utilities folder contains utility and helper classes and, most importantly, states and modifiers like .is-active or .visually-hidden. Those styles override the styles in the previous layers and are often set via JavaScript. I really like [the suggestion by Andy Bell in his CUBE CSS methodology](https://cube.fyi/exception/) to use data-attributes to change the state of components, which is also useful in terms of the higher specificity.

## <a name="scss-shame"></a>Shame
This file is a place for all the shameful CSS solutions like quick fixes and hacky things that might solve a problem for the time being but should be solved properly later. Make sure to document all those nasty hacks with comments, though: Why did you solve it this way? Do you already have an idea on how to solve it better? What is needed to solve it? And so on…