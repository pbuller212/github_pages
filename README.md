## Hugo Notes

### Commands

#### Create a new site

```hugo new site <<Project Name>>```

Set variables in the hugo.toml file

#### Run the server

```hugo server```

Can now goto http://localhost:1313 to view the site.

#### Write hugo's generated content to disk

```hugo --cleanDestinationDir```

#### Create a new page

```hugo new about.md```

### Layouts and Content Types

In hugo, __layouts__ are the skeletons that define boilerplate code. __Content__ pages are combined with a layout to generate the web page. Layouts apply to certain type of content.

Example:
* Home page __layout__
   * Home page
* Single page __template__
   * Product page
   * Another product page
   * About page
* List __layout__
   * Product list

### Templates

Double curly braces define where content goes  
{{ .Site.Title }} - Pulls the Title variable from the config.toml file   
{{ .Content }} line displays the content for the page. This comes from the __content__ folder.

### Archetypes

Hugo uses archetypes to define this default content. Example is archetypes/default.md, which is a markdown file with front matter variables, such as _draft_, _title_, _date_. These are used to populate the variables when generating new content files.

If the draft field set to true, Hugo will skip the page.

### Content Blocks and Partials

These are generated when a theme is created. They are located in themes/patrick/layouts/_default/, where patrick is the name of the theme generated.

__baseof.html__ will be the base of every layout created. This pulls in _partials_ which are building blocks. 

Hugo automatically creates some of these, but they are blank. THey are located in ` themes/patrick/layouts/partials/`. These created blocks are: 
* head.html
* header.html
* footer.html
Each of these is referenced in baseof.html.

#### Including a partial

```{{- partial "head.html" . -}}```

Not the braces _and the dash_. The dash suppresses whitespace in the output. 

When hugo creates a page such as index.html, it will use content/_index.md, theme/layouts/index.html and baseof.html to bring it all together. Same with a single page, but using theme/layouts/_default/single.html.

### Tasks completed

Tasks:
* Chapter 1 - kicking the tires
  * created layouts/index.html
  * created the content/_index.md file  <= This supplies the `.Content` to layouts/index.html
  * created about page with `hugo new about.md`
  * created layouts/_default/single.html
* Chapter 2 - Building a basic theme
  * `hugo new theme patrick` to create a theme
  * moved layout files into theme
    * `mv layouts/index.html themes/patrick/layouts/index.html`
    * `mv layouts/_default/single.html themes/patrick/layouts/_default/single.html`
  * added the theme to hugo.toml
  * created partials head.html, header.html, and footer.html
  * included these in the baseof.html
  * created index.html layout in the theme