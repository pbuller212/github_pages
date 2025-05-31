This is a git repo intended to be published to github pages.

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

### Tasks completed

Tasks:
* Chapter 1 - kicking the tires
  * created layouts/index.html
  * created the content/_index.md file  <= This supplies the `.Content` to layouts/index.html
  * created about page with `hugo new about.md`
  * created layouts/_default/single.html