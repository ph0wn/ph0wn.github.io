# Ph0wn CTF

## Introduction

Ph0wn website is using jekyll and liquid for templating. for the website template we are using a theme called [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/).

In addition to the documentation you have this nice [cheat sheet](https://www.fabriziomusacchio.com/blog/2021-08-11-Minimal_Mistakes_Cheat_Sheet/) to get up to speed with the theme.

## Main Customizations


### CSS

The file `_config.yml` contains the main configurations for the website. however, I have added few customizations to the theme.
All CSS customizations can be found in the file `assets/css/main.scss`.
navigation colors can be modified in the file `assets/css/main.scss`
```scss
.greedy-nav a { /* Navbar links initial color */
	display: block;
	margin: 0 1rem;
	color: white;
	text-decoration: none;
	-webkit-transition: none;
	transition: none;
}

.greedy-nav a:hover {  /* Navbar links hover color */
  color: #A32D21;
  background-color: white;
}

.greedy-nav .visible-links a::before { /* Navbar underline animation color */
	content: "";
	position: absolute;
	left: 0;
	bottom: 0;
	height: 4px;
	background: white;
	width: 100%;
	-webkit-transition: all .2s ease-in-out;
	transition: all .2s ease-in-out;
	-webkit-transform: scaleX(0) translate3d(0, 0, 0);
	transform: scaleX(0) translate3d(0, 0, 0);
}
.greedy-nav .hidden-links { /* Navbar additional links by default represented by 3 horizontal line*/
	position: absolute;
	top: 100%;
	right: 0;
	margin-top: 15px;
	padding: 5px;
	border: 1px solid #bfbfbf;
	border-radius: 4px;
	background: #A32D21;
	-webkit-box-shadow: 0 2px 4px 0 rgba(0,0,0,.16),0 2px 10px 0 rgba(0,0,0,.12);
	box-shadow: 0 2px 4px 0 rgba(0,0,0,.16),0 2px 10px 0 rgba(0,0,0,.12);
}
[..SNUP...]

.toc .nav__title {  /* Toc: Table of content*/
	color: #fff;
	font-size: .75em;
	background: #A32D21;
	border-top-left-radius: 4px;
	border-top-right-radius: 4px;
}


.toc .active a {
  background-color: #d0d3d4;
  color: #3d4144;
}
```


If you are not able to find a specific CSS class, you can use the browser's inspect tool to find the class and override it in the `main.scss` file.

### Navigation
Navigation is defined in the file `_data/navigation.yml`. you can add or remove items from the navigation bar by modifying this file.
but first to add/remove a page, you need to add/remove the page from the `_pages` folder.
feel free to refer to the [documentation](https://mmistakes.github.io/minimal-mistakes/docs/navigation/) for more details.

####  Sponsors
the sponsors images can be found in the folder `assets/images/sponsors/`. to add or modify a sponsor, you need to add the image to the folder and update the file `_pages/sponsors.html`.

for example, under the sponsors variable:

```yaml
sponsors:
  - url: https://www.fortinet.com/
    image_path: /assets/images/sponsors/Fortinet_Logo_Black-Red.png
    alt: "Fortinet"
    title: "Fortinet"
    inline_style_properties: "width: 300px; padding-top: 30%;"
```
To your convenience, you can modify the `inline_style_properties` to adjust the size of the image.

Later in the file, the following code is used to display the sponsors:

```html
{% for sponsor in page.sponsors %}
  <div class="sponsor">
    <a href="{{ sponsor.url }}" target="_blank">
      <img src="{{ sponsor.image_path }}" alt="{{ sponsor.alt }}" title="{{ sponsor.title }}" style="{{ sponsor.inline_style_properties }}">
    </a>
  </div>
{% endfor %}
```
If you want to:
*  modify the layout of the sponsors, you can modify the HTML code above. 
*  or modify the order in which the sponsors are displayed, you can modify the order of the sponsors in the `sponsors` variable.

By default, the sponsors are displayed in a grid layout with 3 columns.

#### Posts 
* The posts as well as the other pages uses the same way to display images. 
* The images are stored in the folder `assets/images/` and are referenced in the front matter of the post/page.
* if you want to add a `toc` to a post, for easier navigation, you can add the following code to the front matter of the post:
    ```yaml
    toc: true
    toc_label: "Ph0wn 2017 Edition"
    toc_icon: "flag"
    toc_sticky: true
    ```
    the `toc_label` is the title of the toc, `toc_icon` is a font awesome icon that will be displayed next to the title, and `toc_sticky` is a boolean to make the toc sticky or not, for more details refer to the [documentation](https://mmistakes.github.io/minimal-mistakes/docs/layouts/#table-of-contents).

#### Contact Page
In the contact page, the steering committee members section is *not* by default part of the theme. so for any big changes of the theme, you might need to modify the HTML code in the file `_pages/contact.html` and update its css.

#### Gallery
regarding the gallery, the images are stored in the folder `assets/images/gallery/`. to add a new image to the gallery, you need to add the image to the folder. the htlml code will automatically display the images in the gallery. please note that for the moment, only **PNG** and **JPG** images are supported. if you would like to add other formats, you can modify the code in the file `_pages/gallery.html`.

## Running the website locally
you will first need to have jeckyll installed on your machine. you can follow the instructions [here](https://jekyllrb.com/docs/installation/).
later you can run the website locally by running the following command in the root directory of the website:

```bash
bundle exec jekyll serve
```

## Theme upgrade
if you want to update the theme, you can follow the instructions [here](https://mmistakes.github.io/minimal-mistakes/docs/upgrading/).







