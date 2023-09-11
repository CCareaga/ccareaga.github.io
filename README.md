# dev repo for Chris's site
This repo started as a local implementation of https://github.com/riggraz/no-style-please, but has been edited to add some more customized style.

## file structure
* _data: contains menu.yml, which dictates how the homepage is formatted (some content)
* _includes: HTML (and Liquid templating) templates that can be included in layouts and includes. They specify the formatting of sections of pages
* _layouts: HTML (and Liquid templating) templates that can be used by any page in your site and wrap around page content
* _news: all markdown files for news posts
* _research: all markdown files for research posts
* _sass: contains the no-style-please.scss stylesheet
* assets: a "css" directory which contains more customized, non-"no-stype-please" styling. Also all images for the site
* _config.yml: the config file for the site

## editing the site
### add a research post
* create a markdown file in _research/
* add content to the markdown file. The markdown file will have two sections: front matter and post content. The front matter is everything between the `---` lines and it specifies variables to use in the rendering templates. The content is everything that follows the last `---` line and this is the actual text of the post. So the full markdown file should look something like this:
		
		---
		layout: post
		title:  Your Post Title
		date:   2020-06-11 11:42:58 -0700
		categories: research
		description: A short description of the post that will show up on the homepage in the research list
		img_path: /assets/image_for_post.jpeg
		img_text: Your image description text
		---
		This is the actual text that will go into the post. 
* save the post's image in assets/ with the same name you specified for the `img_path` variable in the markdown file
* add the filename to "collections.research.order" in _config.yml. This list dictates the order in which research posts will show up on the homepage, so add the filename wherever you want it in the list

### add a news post
* create a markdown file in _news/ with its content following this example (you will notice there is no option to add a description or image for news posts):
		
		---
		layout: post
		title:  Your Post Title
		date:   2020-06-11 11:42:58 -0700
		categories: news
		---
		This is the actual text that will go into the post. 
* add the filename to "collections.news.order" in _config.yml. This list dictates the order in which research posts will show up on the homepage, so add the filename wherever you want it in the list

### edit the homepage style of the "about me" section
The "about me" section is styled differently than the research and news post lists. The styling for the "about me" section happens at the top of _includes/menu_item.html, in the `<div class="aboutme-container">` object. The content for this section is specified in _data/menu.yml in the first entry, with `title: about me`. The title of this section MUST be "about me". Here is how the content is styled:
* The first element in the _data/menu.yml "about me" entry list is the site title, rendered as `<h1>`
* The next element(s) in the _data/menu.yml "about me" entry list should be short descriptions, and will be rendered as `<p>` blocks
* The rest of the elements in the _data/menu.yml "about me" entry list should include a title and a url, and these elements are rendered side-by-side as a list of links, where the entire `title` value is a hyperlink that points to `url`.

### edit the homepage style of the "research" section
The "research" section is styled differently than the news post list. The styling for the "research" section is in _includes/research_post_list.html and assets/css/main.scss. The content for each post is taken from the front matter in its markdown file (in _research/). For each research post on the homepage, we display 3 things:
* an image, specified in the post's markdown file's front matter in the `img_path` and `img_text` fields
* the post tile (as a link to the post itself), specified in the post's markdown file's front matter in the `title` field
* a short description of the post, specified in the post's markdown file's front matter in the `description` field
