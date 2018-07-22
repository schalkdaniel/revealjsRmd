# Rmd revealjs Template

This template collects and combines some great frameworks (all open source) to create one good looking `HTML` presentation via `rmarkdown`. The idea is to dynamically create presentations with `R` as back-end to render graphics, create analyses, or include applications such as shiny. For an introduction to `rmarkdown` see [here](https://rmarkdown.rstudio.com/lesson-1.html). The front-end is a [`revealjs`](https://revealjs.com/) presentation with some adaptions to the `css` to get a nice looking and easy customizeable presentation framework. 

## Credits

This template highly depends on the great work others have already done:

- [**revealjs**](https://revealjs.com/)
- [**Font-Awesome:**](https://www.google.com)
- [**rmarkdown**](https://rmarkdown.rstudio.com/)
- [**revealjs (R Package)**](https://cran.r-project.org/web/packages/revealjs/index.html)
- [**reveal.js-menu**](https://github.com/denehyg/reveal.js-menu)
- [**Google Fonts**](https://fonts.google.com/)

## How to Use

### Download required files

#### Step by step initialization

First clone the repository:
```
# ssh
git clone git@github.com:schalkdaniel/revealjsRmd.git

# https
git clone https://github.com/schalkdaniel/revealjsRmd.git
```

Initialize the submodules:
```
git submodule init
git submodule update
```

#### Add all (submodules) at once

The shortcut to install all at once would be:
```
# ssh
git clone --recurse-submodules git@github.com:schalkdaniel/revealjsRmd.git

# https
git clone --recurse-submodules https://github.com/schalkdaniel/revealjsRmd.git
```

### Structure of the template

- `template.Rmd`: This is the main file which is rendered by `rmarkdown`. To use the template as is the YAML header must include the `header.html`,  `after.html`, and `myreveal.css`. The header could look like this (with some ohter options):
    ---
    title: "<code>My Presentation</code>"
    subtitle: "This is a revealjs presentation"
    author: "Created by <a href='' target='_blank'>My Name</a>"
    date: "March 22, 2005"
    output:
      revealjs::revealjs_presentation:
        css: myreveal.css
        transition: slide
        includes:
          in_header: header.html
          after_body: after.html
        self_contained: false
        reveal_options:
          controls: true
          center: true
          slideNumber: true
    ---
- `myreveal.css`: This file cares about coloring and appearence (e.g. the font-family).
- `in_header`: The heaer includes some additional stuff like Google Fonts or the path to the Font-Awesome directory (which is included as submodule).
- `after_body`: This file includes some `revealjs` customizations which cannot be done directly within the YAML header.

## Customize Template

### Color theme

The `myreveal.css` has some variables which are defined at the beginning. Those variables can be specyfied to use another color scheme:
- `--main-color`: This color is used to set accents like `<a>` coloring, the process bar, or the control arrows.
- `--main-hover-color`: Color when hovering over an `<a>` tagged text.
- `--main-discreet-color`: Color, which is used to discreetly put objects out of focus (such as inactive arrows).

### Background image/color

The background image can be customized or removed by changing or removing the `parallaxBackgroundImage` initialization in `after.html`.

### Use Google Fonts

To use a custom Google Fonts for the font face go to the [Google Fonts website](https://fonts.google.com/) and:
- Search for a font you like.
- Select the font and copy the `HTML` code to include the font into the header.
- Paste the code into `header.html`.
- Adjust the font-family variable `--main-font-family` in `myreveal.css`.

### Customize reveal.js-menu