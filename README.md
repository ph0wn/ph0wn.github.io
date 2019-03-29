# Ph0wn CTF

This is the website for **Ph0wn CTF**.

It is based on the Jekyll theme [Stylish Portfolio Bootstrap](https://vidhyav656.github.io/startbootstrap-stylish-portfolio-jekyll/)

## Main customizations

Changing theme color: in `assets/css/stylish-portfolio.css`

```css
.bg-primary {
background-color: #A32D21 !important;
}
 
 .text-primary {
 color: #A32D21 !important;
 }
```

Creating service icons with my theme's color: in `assets/css/stylish-portfolio.css`

```css
.service-icon {
   background-color: #fff;
   color: #A32D21;
   height: 7rem;
   width: 7rem;
   display: block;
```   

Using theme's color in the navigation bar on the right:

```css
/* Side Menu */
#sidebar-wrapper {
  position: fixed;
  z-index: 2;
  right: 0;
  width: 250px;
  height: 100%;
  -webkit-transition: all 0.4s ease 0s;
  transition: all 0.4s ease 0s;
  -webkit-transform: translateX(250px);
  transform: translateX(250px);
  background: #A31D21;
  border-left: 1px solid rgba(255, 255, 255, 0.1);
}
```

Using the theme's color in the social link images (in the footer): `assets/css/stylish-portfolio.css`

```css
footer.footer .social-link {
   width: 4rem;
   line-height: 4.3rem;
   font-size: 1.5rem;
  background-color: #A32D21;
  ...
```  


Updating the navigation bar: in `_includes/navigation.html`
Updating the header or footer: in `_includes/footer.html` (or header.html)

Creating a dark button:

```html
<a class="btn btn-primary btn-xl js-scroll-trigger" href="#participate">How to participate</a>
```

Creating a button with the theme's color:

```html
 <a class="btn btn-primary btn-xl js-scroll-trigger" href="#about">Find Out More</a>
``` 

The `index.html` page is organized in *sections*.

```html
<section class="..." id="nameofsection">
...
</section>
```

Do not print the *date* at the top of posts: use *default* layout:

```
---
layout: default
title:  "Ph0wn 2018"
tags: 2018 archive write-up video
---
```


## To do

I am using `stylish-portfolio.css` instead of the minified version in `_layouts/default.html`

