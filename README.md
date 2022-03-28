# KHGhost Theme

KHGhost is a modified fork of [TryGhost/Starter](https://github.com/TryGhost/Starter) and is used on my own website [KHDev](https://khdev.ch). Feel free to use this theme as is on your own blog or fork it and modify it to your specific needs.

&nbsp;

# Features

How does this differ to the TryGhost/Starter template?

-   Simple Card layout
-   Works on Desktop and Mobile
-   Dark Mode
-   Removed JQuery dependencies for the Mobile hamburger menu
-   Also removed the JQuery code for infinitescrolling, fitvideo and galleries (no clue what they were for exactly)
-   Syntax Highlighting with Prism.js

# Todo

I am happy with the way the theme looks so far but there are a few improvements I want to implement.

**Better way to handle front page post count:**  
Right now I just have all posts displayed on the front page. This will become very large and messy once I actually have more than 10 posts. I am thinking of implementing a load more button after X posts that loads the rest. Or make the front page just display a few posts (3 to 5) with some other website related stuff and move posts to another section entirely.

**Featured Posts:**  
This might cross with the Todo above. Basically just display the latest 3 featured posts on the front page at the top.

**Tag page:**  
I want to create a specific Tag page in a small card grid layout consisting of an image, the name of the tag and the ammount of posts the tag contains.

**Lightbox integration:**  
This should be a pretty simple integration via [Fluidbox](https://forum.ghost.org/t/fluidbox-integration-for-image-click-lightboxes/7451) but I might look for smaller implementations.

**Cleaning up unused styles and organizing the code better:**  
I am not a webdeveloper so I just mashed together different things until the endresult was to my liking. I want to clean this up a bit so its more useful to other people.

**Use Ghosts custom settings more:**  
Currently a lot is hardcoded but I want to be able to change certain things like Casper in the Ghost Admin interface. This shouldnt be too difficult, instead of multiple color variables I just need to use Color Mod to change the variables.

https://ghost.org/docs/themes/custom-settings/

# First time using a Ghost theme?

Ghost uses a simple templating language called [Handlebars](http://handlebarsjs.com/) for its themes.

We've documented our default theme pretty heavily so that it should be fairly easy to work out what's going on just by reading the code and the comments. Once you feel comfortable with how everything works, we also have full [theme API documentation](https://themes.ghost.org) which explains every possible Handlebars helper and template.

**The main files are:**

-   `default.hbs` - The main template file
-   `index.hbs` - Used for the home page
-   `post.hbs` - Used for individual posts
-   `page.hbs` - Used for individual pages
-   `tag.hbs` - Used for tag archives
-   `author.hbs` - Used for author archives

One neat trick is that you can also create custom one-off templates just by adding the slug of a page to a template file. For example:

-   `page-about.hbs` - Custom template for the `/about/` page
-   `tag-news.hbs` - Custom template for `/tag/news/` archive
-   `author-ali.hbs` - Custom template for `/author/ali/` archive

&nbsp;

# Development

Styles are compiled using Gulp/PostCSS to polyfill future CSS spec. You'll need [Node](https://nodejs.org/), [Yarn](https://yarnpkg.com/) and [Gulp](https://gulpjs.com) installed globally. After that, from the theme's root directory:

```bash
# Install
yarn

# Run build & watch for changes
yarn dev
```

Now you can edit `/assets/css/` files, which will be compiled to `/assets/built/` automatically.

The `zip` Gulp task packages the theme files into `dist/<theme-name>.zip`, which you can then upload to your site.

```bash
yarn zip
```

&nbsp;

# PostCSS Features Used

-   Autoprefixer - Don't worry about writing browser prefixes of any kind, it's all done automatically with support for the latest 2 major versions of every browser.
-   [Color Mod](https://github.com/jonathantneal/postcss-color-mod-function)

&nbsp;

# Copyright & License

Copyright (c) 2013-2022 Ghost Foundation - Released under the [MIT license](LICENSE).
