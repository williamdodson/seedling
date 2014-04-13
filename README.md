# Seedling

**Seedling** helps you create Jekyll-based prototypes for your projects. It comes with a set of basic wireframe-style `CSS` rules written in Sass for easy customization. Basic media queries are baked in so you can start designing for mobile devices right away. This is how every new web project starts at [William Dodson Design](http://williamdodson.co/).

## Requirements

Seedling requires the following Ruby Gems to be installed on your system:

* Jekyll
* Sass
* Bourbon
* Neat

Just run `gem install` from a terminal window for each of the required gems listed above. This will get your environment set up so you can build your prototype.

## Instructions

If you've used both Jekyll and Sass before then you can pretty much dive right in and start working. The only difference is that Seedling compiles the HTML to the `_wireframe` folder instead of `_site`. If you're new to Jekyll, Sass, Bourbon, and Neat please take a few moments to review their documentation before planting your first **Seedling** project:

* [Jekyll](http://jekyllrb.com/)
* [Sass](http://sass-lang.com/)
* [Bourbon](http://bourbon.io/)
* [Neat](http://neat.bourbon.io/)

### Step 1: Clone Seedling

```
$ git clone https://github.com/obxdesignworks/seedling.git your-project-name
```

### Step 2: Edit the `_config.yml` Settings

The Jekyll configuration file contains some preferences that you will need to customize for your project. Here is the default configuration included with **Seedling**:

```
name: Seedling Prototype
markdown: redcarpet
destination: _wireframe
encoding: UTF-8
exclude: ['sass', 'README.md']
```

Specifically you will want to change the value for `name: Seedling Prototype` to match your project's name.

### Step 3: Build the Initial Project

```
$ cd your-project-name
$ jekyll build
```

This will build the initial site for you in the `_wireframe` folder. If you prefer to use a different output folder you can change the destination directive in `_config.yml` before running the build command for the first time: 

```
destination: your-folder-name
```

### Step 4: Create Your Pages

Now you can simply start adding pages to the project as needed. There are several ways in which you can rebuild the site so that you can see your changes in the prototype. By default, the `jekyll build` command runs once, recreates the destination folder, and stops processing. If you prefer to have Jekyll automatically rebuild the site as you make changes simply add the regeneration flag to the build command: `jekyll build -w` or `jekyll build --watch`. 

## Notes

### Why I Created Seedling

One day I was watching a video from Happy Cog designer, [Patrick Marsceill](http://happycog.com/marsceill), on [HTML Prototyping](http://mijingo.com/products/screencasts/html-prototyping) and I realized that Patrick's workflow was very similar to my own. The biggest difference was that he uses [CodeKit's `.kit` language](https://incident57.com/codekit/kit.php) for prototyping and I use Jekyll. It's a great workflow, but most of the prototypes that I build require a bit more functionality than `.kit` files can offer me. Jekyll uses [Liquid](http://liquidmarkup.org/) as a template language which provides more robust constructs; for loops, flow control, etc. Jekyll also provides the ability to use `.yml` data sets which can save some time. For example, I can use Jekyll's [data files functionality](http://jekyllrb.com/docs/datafiles/) to loop over sets of data instead of copy-pasting the same HTML code over and over again.

In the end, it comes down to personal preference. I simply prefer my own Jekyll-based setup for the following reasons:

1. I can switch from wireframe to a functional prototype pretty quickly; simply edit the existing Sass files already in place and start building the final design.
2. Upon client approval of the wireframes I can change the output folder to `_prototype` and preserve them for future reference.
3. It uses [Git](http://git-scm.com/) to manage revision; just delete the existing `.git` folder for the **Seedling** repository and run `git init` to start versioning in your own new repository.
4. Loop constructs and flow control statements in my Jekyll pages can be easily converted to another programming language like PHP or Ruby:

```
# Liquid
{% for v in var %}
	...do something
{% endfor %}

# PHP
<?php foreach(var as v) : ?>
	...do something
<?php endfor; ?>

# Ruby ERB
<% for @v in @var %>
	...do something
<% end %>

```