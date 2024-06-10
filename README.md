# Ph0wn CTF

## Introduction

Ph0wn website is using jekyll and liquid for templating. for the website template we are using a theme called [Minimal Mistakes](https://mmistakes.github.io/minimal-mistakes/).

in addition to the documentation you have this nice [cheat sheet](https://www.fabriziomusacchio.com/blog/2021-08-11-Minimal_Mistakes_Cheat_Sheet/) to get up to speed with the theme.

## Main Customizations


### CSS

the file `_config.yml` contains the main configurations for the website. however, I have added few customizations to the theme.
All CSS customizations can be found in the file `assets/css/main.scss`.

if you are not able to find a specific CSS class, you can use the browser's inspect tool to find the class and override it in the `main.scss` file.

### Navigation
navigation is defined in the file `_data/navigation.yml`. you can add or remove items from the navigation bar by modifying this file.
but first to add/remove a page, you need to add/remove the page from the `_pages` folder.
feel free to refer to the [documentation](https://mmistakes.github.io/minimal-mistakes/docs/navigation/) for more details.

####  Sponsors
the sponsors images can be found in the folder `assets/images/sponsors/`. to add or modify a sponsor, you need to add the image to the folder and add the following code to the file `_pages/sponsors.html`:
under the sponsors variable:

```yaml
sponsors:
  - url: https://www.fortinet.com/
    image_path: /assets/images/sponsors/Fortinet_Logo_Black-Red.png
    alt: "Fortinet"
    title: "Fortinet"
    inline_style_properties: "width: 300px; padding-top: 30%;"
```
to your convenience, you can modify the `inline_style_properties` to adjust the size of the image.
later in the file, the following code is used to display the sponsors:

```html
{% for sponsor in page.sponsors %}
  <div class="sponsor">
    <a href="{{ sponsor.url }}" target="_blank">
      <img src="{{ sponsor.image_path }}" alt="{{ sponsor.alt }}" title="{{ sponsor.title }}" style="{{ sponsor.inline_style_properties }}">
    </a>
  </div>
{% endfor %}
```
so if you want to:
*  modify the layout of the sponsors, you can modify the HTML code above. 
*  or modify the order in which the sponsors are displayed, you can modify the order of the sponsors in the `sponsors` variable.

By default, the sponsors are displayed in a grid layout with 3 columns.

#### Posts 
* The posts as well as the other pages uses the same way to display images. 
* The images are stored in the folder `assets/images/` and are referenced in the front matter of the post/page.
* if you want to add toc to a post, for easier navigation, you can add the following code to the front matter of the post:
    ```yaml
    toc: true
    toc_label: "Ph0wn 2017 Edition"
    toc_icon: "flag"
    toc_sticky: true
    ```
    the `toc_label` is the title of the toc, `toc_icon` is the icon that will be displayed next to the title, and `toc_sticky` is a boolean to make the toc sticky or not, for more details refer to the [documentation](https://mmistakes.github.io/minimal-mistakes/docs/layouts/#table-of-contents).

#### Contact Page
in the contact page, the steering committee members section is *not* by default part of the theme. so for any big changes of the theme, you might need to modify the HTML code in the file `_pages/contact.html`.

## Running the website locally
you will first need to have jeckyll installed on your machine. you can follow the instructions [here](https://jekyllrb.com/docs/installation/).
later you can run the website locally by running the following command in the root directory of the website:

```bash
bundle exec jekyll serve
```

## Theme upgrade
if you want to update the theme, you can follow the instructions [here](https://mmistakes.github.io/minimal-mistakes/docs/upgrading/).







