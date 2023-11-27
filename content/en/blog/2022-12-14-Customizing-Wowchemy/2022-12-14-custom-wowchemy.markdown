---
title: "Miscellaneous Tips for Customizing your Wowchemy Academic Site"
author: ["admin"]
date: '2022-12-14'
lastmod: '2022-12-15'
slug: custom-wowchemy
categories: []
tags: []
summary: "Notes from far too long spent googling around for tips on customizing this Wowchemy site"
subtitle: "Notes from far too long spent googling around for tips on customizing this Wowchemy site"
smartDashes: true
toc: true
commentable: true
codefolding_show: show
---

<style type="text/css">

pre {
  max-height: 350px;
  overflow-y: auto;
}

pre[class] {
  max-height: 350px;
}
::-webkit-scrollbar {
  -webkit-appearance: none;
  width: 7px;
  scrollbar-color: red yellow;
}

::-webkit-scrollbar-thumb {
  border-radius: 4px;
  background-color: rgba(0, 0, 0, .5);
  box-shadow: 0 0 1px rgba(255, 255, 255, .5);
  scrollbar-color: red yellow;
}

.scrollable-element {
  
}

</style>

It's undeniably great that blogdown/Hugo Academic (now [Wowchemy](https://wowchemy.com/docs/)) made creating a professional website so accessible, but there is a notable downside: it became really hard to make your site stand out. 

To try and leave a slightly more lasting mark, I spent more hours than I'd like to admit googling around, finding little tweaks that would differentiate my website from the standard template. I'm generally happy with the result, and I figured if I could cut down on others' frustration by sharing what I did, that's the least I could do. I have no web design experience and struggled throughout with HTML/CSS/Go, as well as with the general structure of the website. In other words, if I can do it, so can you! 

The full codebase for my website is available on [Github](https://github.com/nballou/nickballousite).

**Crucial note**: These alterations frequently did not work out of the box for me when using others' code, and they similarly may not for you. Due to 1) differences in Wowchemy versions and other idiosyncratic parts of your setup, and 2) poor documentation from me after having gone through a lot of trial and error, these tips are more about pointing you in the right direction with sources rather than directly solving your problems. 

# Setting up your site

These tips assume that you already have a working, deployed version of a Wowchemy site. This is too large a topic to dive into here, but some of the resources I found helpful when first doing this include: 

- [Dan Quintana's blog post on creating your website](https://www.dsquintana.blog/create-an-academic-website-free-easy-2020/)
- [Andreas Handel's post on creating a website in under an hour](https://www.andreashandel.com/posts/2020-01-02-blogdown-website-1/index.html)
- [Wowchemy's own tutorial/guide](https://wowchemy.com/docs/getting-started/hugo-github-quickstart/) (duh)

# Basics of Wowchemy/Hugo Customization

Customizations to your Wowchemy site typically take one of 4 forms:

1. Changing a predefined parameter in the `config/_default` files (mainly `params.yaml` and `config.yaml`)
2. Altering a theme in `data/themes` - for exmaple, I created a file `data/themes/my_theme.toml` where I set all of the colors for both light and dark mode across the website. I can highly recommend [Coolers](https://coolors.co/1c2945-f3b26d-ffffff-e97149) for trying out different color palettes until you find one you're happy with.
3. Adding/changing a *partial*---essentially a bit of code that defines a certain design feature on your website. For example, partials might define where your profile picture appears, the number of columns used to display the content of a given page, the presence of a background image, and much more. Using partials was by far the hardest part of Wowchemy for me to wrap my head around. 
    + By default, partials are defined in your theme, and can be found under `themes/github.com/wowchemy/wowchemy-hugo-themes/modules/wowchemy/v5/layouts/partials` (I know, it really feels like they could've simplified that folder structure a bit). You should never alter these files in the theme itself. Instead, you should make a *copy* of partials, and put them in a new folder at the root of your directory: `layouts/partials`. The partials in your root directory will override the "default" ones in the theme, allowing you to change the design without risking breaking anything---you can always just delete the custom partial.
4. Changing the styling with custom SCSS code (which is just CSS code, but fancier). You can add a file called `custom.scss` inside `assets/scss` folder (again, you may need to create this folder first). Within this file, you use CSS code to specify certain elements/classes of elements, and can change their visual properties. This might include the formatting of your headings, various colors or padding, animations (see below), and much more.

If you master these four strategies for customizing your website, you'll have the main tools in your toolkit for making your website stand out from the crowd. As above, it's beyond the scope of this post to teach you how to do each of these things thoroughly, but here are some resources that helped me:

- The basics of predefined parameters: [Dan Quintana's blog post on creating your website](https://www.dsquintana.blog/create-an-academic-website-free-easy-2020/)
- Getting to grips with `custom.scss`: [Connor Rothschild's blog post](https://www.connorrothschild.com/post/animate-hugo-academic)
- Understanding how partials work: noisyoscillator's [post on customizing Hugo websites](https://hackmd.io/@noisyoscillator/hugo-academic-customizations#i18n); Yorkyard's [getting started with Hugo partials](https://www.yockyard.com/post/getting-started-with-hugo-partials/)
- [Setting up a Blogdown site from scratch](https://www.mark-druffel.com/2022/building-blogdown-site), with lots of custom tweaks, by Mark Druffel

# Changes on my site

## About widget

The about widget is the first thing your visitors are going to see, and therefore was the aspect I spent the most time customizing. Each of the changes I made is detailed below. 

## (Re)move interests/education for a cleaner homepage

This alteration was inspired by [Matteo Courthoud's site](https://matteocourthoud.github.io), and he also wrote his own helpful tutorial on how to achieve similar results. To do so, I copied the `about.html` partial from the theme (found at `themes/github.com/wowchemy/wowchemy-hugo-themes/modules/wowchemy/v5/layouts/partials/widgets/about.html`) and put it into the folder for customized partials (`layouts/partials`, in this case inside a `layouts/partials/widgets` subfolder mirroring where it was found in the theme).

Don't be alarmed if you open up this file and are immediately overcome by a sense to burn the whole thing to the ground, that's how I felt too. But the necessary change is actually quite small. In the theme partial, all you need to do is remove the code that inputs the interest/education section. In my case, this was located on lines 92--122, and looked like this:


```html

<div class="row">

      {{ with $person.interests }}
      <div class="col-md-5">
        <div class="section-subheading">{{ i18n "interests" | markdownify }}</div>
        <ul class="ul-interests mb-0">
          {{ range . }}
          <li>{{ . | markdownify | emojify }}</li>
          {{ end }}
        </ul>
      </div>
      {{ end }}

      {{ with $person.education }}
      <div class="col-md-7">
        <div class="section-subheading">{{ i18n "education" | markdownify }}</div>
        <ul class="ul-edu fa-ul mb-0">
          {{ range .courses }}
          <li>
            <i class="fa-li fas fa-graduation-cap"></i>
            <div class="description">
              <p class="course">{{ .course }}{{ with .year }}, {{ . }}{{ end }}</p>
              <p class="institution">{{ .institution }}</p>
            </div>
          </li>
          {{ end }}
        </ul>
      </div>
      {{ end }}

    </div>
```

Get rid of this, and only your bio description will appear in the about widget, and should automatically vertically center as well (though I did end up doing some manual positioning by adding a few `</br>` tags to the beginning of my bio, which is located in `content/authors/admin/_index.md`).

If you still want that interest/education section shown somewhere, don't worry---you can activate the CV widget instead, which shows the same information in a separate section of your homepage.

## Add background image to bottom of about widget

Another easy one: in the same `about.html` partial you made, simply add the following lines before the first html lines (after the Go shortcode lines):


```html
<div>
  <a class="background-img" href="#img1"><img id="img1" src="img/footer.png" /></a>
</div>
```

The `src` you specify in your image will of course need to point to an image file. Image files like this live in the `static` folder, which should already exist inside your root folder. My background image is therefore found at `static/img/footer.png`, but the `static` is omitted inside the html code when you reference it. 

I made my background image simply using Powerpoint, with the help of my girlfriend's eye for design.

## Add animations to about widget 

This alteration was inspired by [Connor Rothschild's post](https://www.connorrothschild.com/post/animate-hugo-academic), which describes how to use relatively simple CSS code to animate elements of one's page. 

The blog post describes how to do basic animations, using two broad steps:

1. Identify the class of the element you'd like to animate, which you can do by either:
  a. Co-opting the classes already used by Wowchemy (you can use the inspect element feature of your browser, for example, to look at these)
  b. Adding or amending the classes in the underlying html code by altering the partial where those classes are assigned. 
2. Use CSS code to target those classes/elements and add animations

Animations are remarkably simple. I won't rehash Connor's entire post, but the simplest animation could be as small as: 


```css
@keyframes slide-from-right {
  0% {
    transform: translateX(150%);
  }
  100% {
    transform: translateX(0%);
  }
}
```


<style type="text/css">
@keyframes slide-from-right {
  0% {
    transform: translateX(150%);
  }
  100% {
    transform: translateX(0%);
  }
}
</style>

This defines an animation where the position of the element(s) is 150% of it's normal X position at the beginning (0% completion), and it's normal X position at the end of the animation (100% completion). 

You then simply apply this newly-defined animation to the html element of interest. For example, to apply this animation with a duration of 1s to your name and affiliation under your profile picture, you would do: 


```css
.portrait-title {
  animation: slide-from-right 1s forwards;
}
```


<style type="text/css">
.portrait-title {
  animation: slide-from-right 1s forwards;
}
</style>

To get the specific animations I use on my about widget, I borrowed code from the [old version of his website](https://github.com/connorrothschild/v2), and lightly amended it to get the elements to slide in from opposite sides. The relevant bits, which live in `assets/scss/custom.scss` (again, you'll need to create this folder/file if you don't have it already; see Connor's blog post for more details), are the following:


```css
/* Animate text coming from right */ 
.main-content {
  animation: slide-from-right 1.5s cubic-bezier(0.4, 0, 0.13, 1) forwards;
  animation-delay: 0ms;
}

/* Animate CV button coming from right */ 
.btn-download {
  opacity: 0;
  animation: fade-in 2s forwards;
  animation-delay: 1.4s;
}

#profile {
  
  .avatar-square {
  -webkit-clip-path: polygon(25% 5%, 75% 5%, 100% 50%, 75% 95%, 25% 95%, 0% 50%);
  clip-path: polygon(25% 5%, 75% 5%, 100% 50%, 75% 95%, 25% 95%, 0% 50%);
  opacity: 0;
  position: relative;
  right: -300px;
  -webkit-animation: slide-left 2s cubic-bezier(0.87, 0, 0.13, 1) forwards;
  animation: slide-left 2s forwards cubic-bezier(0.87, 0, 0.13, 1) forwards;
  }

  .portrait-title {
    opacity: 0;
    position: relative;
    left: -1000px;
    -webkit-animation: slide-right 2s cubic-bezier(0.87, 0, 0.13, 1) forwards;
    animation: slide-right 2s cubic-bezier(0.87, 0, 0.13, 1) forwards;
    
  }
  
  @-webkit-keyframes slide-right {
      100% { left: 0; opacity: 1}
  }
  
  @keyframes slide-right {
      100% { left: 0; opacity: 1; }
  }
  
  @-webkit-keyframes slide-left {
      100% { right: 0; opacity: 1; }
  }
  
  @keyframes slide-left {
      100% { right: 0; opacity: 1; }
  }
}
```

I'm particularly pleased with the staggered fade-in of the contact icons. All that was required to achieve that was to add a fade-in animation to each of those icons, and fuss with the timing a little bit (note how each icon is animated .1 seconds later than the previous one): 


```css
.network-icon {
    
    margin-top: 15px;
    padding: 5px;
    
    .fa-envelope {
      opacity: 0;
      -webkit-animation: grow 2s ease forwards;
              animation: grow 2s ease forwards;
      -webkit-animation-delay: 1.3s;
              animation-delay: 1.3s;
    }
    
    .fa-mastodon {
      opacity: 0;
      -webkit-animation: grow 2s ease forwards;
              animation: grow 2s ease forwards;
      -webkit-animation-delay: 1.4s;
              animation-delay: 1.4s;
    }
    
    .fa-linkedin {
      opacity: 0;
      -webkit-animation: grow 2s ease forwards;
              animation: grow 2s ease forwards;
      -webkit-animation-delay: 1.5s;
              animation-delay: 1.5s;
    }
    
    .fa-playstation {
      opacity: 0;
      -webkit-animation: grow 2s ease forwards;
              animation: grow 2s ease forwards;
      -webkit-animation-delay: 1.6s;
              animation-delay: 1.6s;
    }
    
    @-webkit-keyframes grow {
        100% { opacity: 1; }
    }
    
    @keyframes grow {
        100% { opacity: 1; }
    } 
  }
```

## Change shape of profile picture 

First, make sure `/config/_default/config.yaml` has avatar shape set to `square`, rather than circle. From there, you can use the CSS `clip-path` property to reshape your image. I wanted an R-inspired hexagon (albeit rotated incorrectly), so I added the following to my `custom.scss`:


```css
/* This block may have other things in it, if for example you also decided to animate your avatar */
.avatar-square {
  -webkit-clip-path: polygon(25% 5%, 75% 5%, 100% 50%, 75% 95%, 25% 95%, 0% 50%);
  clip-path: polygon(25% 5%, 75% 5%, 100% 50%, 75% 95%, 25% 95%, 0% 50%);
}
```

There are of course much more complicated masking options if you want a more complicated shape, but this worked well for my purposes.

Source: [https://codepen.io/imohkay/pen/ZGbmoQ](https://codepen.io/imohkay/pen/ZGbmoQ)

# Other changes

## Add table of contents to blog posts

This is a [built-in feature](https://wowchemy.com/docs/content/writing-markdown-latex/#table-of-contents) of Wowchemy, and enabled by default for book-style posts. However, I couldn't get it working on my blog posts for a frustratingly long time. I'm still not 100% sure how it all works, but in the meantime, I sorted it by:

1. Adding `toc: true` to the front matter of my blog posts
2. Writing blogposts in Rmarkdown, and adding `options(blogdown.method = 'markdown')` to the `.Rprofile` file for the website, which should be in your base directory (or else you can create one. Earlier, I'd had this set to `blogdown.method = html`, which appears to have been the main problem.

From there, nicely floating table of contents began appearing for my blog posts on the right. Initially, the text formatting was justified, which I thought looked funny with so few words, so I added the following to `custom.scss`:


```css
.docs-toc {
  text-align: left;
}
```

Finally, I wasn't happy with the line spacing of headings that were long enough to wrap, so I reduced that using: 


```css
#TableOfContents li a {
  line-height: 20px
}
```


<style type="text/css">
#TableOfContents li a {
  line-height: 20px
}
</style>


## Using Gisqus for commenting

Look, I'm not kidding myself that my blog posts get a ton of traffic, but in the post-Twitter era, I like the idea that people at least have the *option* to leave a comment on the post itself. I'm not a huge fan of Disqus, both due to its UI and its tendency to harvest and sell your data, and I don't want to pay if I don't have to, so I settled on using Gisqus. 

This was relatively easy to setup thanks to [this blog post by Yury Zhauniarovich](https://zhauniarovich.com/post/2021/2021-06-giscus/). However, I ran into one hitch with the partial not loading. Ultimately, I needed to dig into the commit history to find [this post](https://github.com/wowchemy/wowchemy-hugo-themes/pull/2830) with the updated partial code. For my version of Wowchemy, the `giscus.html` file inside layouts/partials/comments` should therefore be: 


```html
{{ if site.Params.features.comment.giscus }}
<script src="https://giscus.app/client.js"
        data-repo="{{site.Params.features.comment.giscus.repo}}"
        data-repo-id="{{site.Params.features.comment.giscus.repo_id}}"
        data-category="{{site.Params.features.comment.giscus.category}}"
        data-category-id="{{site.Params.features.comment.giscus.category_id}}"
        data-mapping="{{site.Params.features.comment.giscus.mapping}}"
        data-reactions-enabled="{{site.Params.features.comment.giscus.reactions_enabled}}"
        data-theme="{{site.Params.features.comment.giscus.theme}}"
        crossorigin="anonymous"
        async>
</script>
<noscript>Please enable JavaScript to view the comments powered by giscus.</noscript>
{{ end }}
```

## Scrollable code blocks

When sharing long blocks of code (like I've occasionally needed to do in this post), you can follow the [Rmarkdown cookbook instructions here](https://bookdown.org/yihui/rmarkdown-cookbook/html-scroll.html) to place a maximum height on the blocks and make them scrollable. In short, this involved adding this to the beginning of a given .Rmd file:


```css
pre {
  max-height: 300px;
  overflow-y: auto;
}

pre[class] {
  max-height: 300px;
}
```

If you'd like the scroll bar to always be visible---something I find useful, given macOS's tendency to hide it automatically and occasional ambiguity about whether there's more to see---further add the following, which I found on [this StackOverflow post](https://stackoverflow.com/questions/7492062/css-overflow-scroll-always-show-vertical-scroll-bar):


```css
::-webkit-scrollbar {
  -webkit-appearance: none;
  width: 7px;
}

::-webkit-scrollbar-thumb {
  border-radius: 4px;
  background-color: rgba(0, 0, 0, .5);
  box-shadow: 0 0 1px rgba(255, 255, 255, .5);
}
```


<style type="text/css">
::-webkit-scrollbar {
  -webkit-appearance: none;
  width: 7px;
}

::-webkit-scrollbar-thumb {
  border-radius: 4px;
  background-color: rgba(0, 0, 0, .5);
  box-shadow: 0 0 1px rgba(255, 255, 255, .5);
}
</style>

## Tweak article heading formatting

I played around with using colors to demark different headings, particularly `<h1>` which I thought could stand out a little more. In the end I decided an underline was nicer, which I added with the following in `custom.scss`, sourced from [this StackOverflow post](https://stackoverflow.com/questions/16073323/horizontal-rule-line-beneath-each-h1-heading-in-css). For people who are equally unversed in CSS as me, note that the `.article-style h1` syntax at the top means that only `h1` tags that are inside an element with `class="article-style` will be affected; this allows us to exclude the article title which are otherwise just normal `h1` headings.


```css
.article-style h1:after {
  content:' ';
  display:block;
  border:.1rem solid #d0d0d0;
  border-radius:4px;
  -webkit-border-radius:4px;
  -moz-border-radius:4px;
  box-shadow:inset 0 1px 1px rgba(0, 0, 0, .05);
  -webkit-box-shadow:inset 0 1px 1px rgba(0, 0, 0, .05);
  -moz-box-shadow:inset 0 1px 1px rgba(0, 0, 0, .05);
}
```


<style type="text/css">
.article-style h1:after {
  content:' ';
  display:block;
  border:.1rem solid #d0d0d0;
  border-radius:4px;
  -webkit-border-radius:4px;
  -moz-border-radius:4px;
  box-shadow:inset 0 1px 1px rgba(0, 0, 0, .05);
  -webkit-box-shadow:inset 0 1px 1px rgba(0, 0, 0, .05);
  -moz-box-shadow:inset 0 1px 1px rgba(0, 0, 0, .05);
}
</style>

## Code folding (collapsible code chunks)

This one was a doozy. I was able to find three people who had blogged about this, from oldest to most recent:

- [Sébastien Rochette](https://statnmap.com/2017-11-13-enable-code-folding-in-bookdown-and-blogdown/)
- [James Pustejovsky](https://www.jepusto.com/code-folding-update/)
- [Mark Druffel](https://www.mark-druffel.com/2022/building-blogdown-site/#code-folding)

I followed Mark Druffel's post most closely (although all three were helpful)---unfortunately, however, his too did not work straight out of the box. To get his tutorial to work, I needed to make a few minor tweaks:

1. In `codefolding.js`, available from [James Pustejovsky here](https://github.com/jepusto/jepusto.com/blob/main/static/js/codefolding.js) and referenced in Mark's post, I changed L19 from `var rCodeBlocks = $('pre.sourceCode, pre.r, pre.python, pre.bash, pre.sql, pre.cpp, pre.stan, pre.js');` to `var rCodeBlocks = $('pre.chroma');`---Wowchemy appears to have restructured code blocks to all share a high-level class regardless of language, derived from the Syntax highlighter Chroma
2. I added the primary lines of code (see chunk below) to the top of `layouts/partials/page_footer.html`, a partial that we know will be loaded on all pages
    + Make sure that the jQuery version number matches the one that you download, and make sure the downloaded jQuery file in your `static/js` folder is not the two-liner they give you when you select it on the [jQuery website](https://releases.jquery.com), but the raw text from the url that two-liner points you to
3. I decided to keep the config options, but lost about an hour to a really dumb mistake - in `params.yaml`, make sure to set `coldfolding_show` to either `show` or `hide` *without quotes* - all kinds of weird behavior occurs if you include quotes
  
The relevant code inserted at the top of the `page_footer.html` partial is:


```html
{{ if not .Site.Params.disable_codefolding }}
<script src="{{ "js/jquery-3.6.2.min.js" | relURL }}"></script>
<script src="{{ "js/transition.js" | relURL }}"></script>
<script src="{{ "js/collapse.js" | relURL }}"></script>
<script src="{{ "js/dropdown.js" | relURL }}"></script>
<script src="https://cdn.jsdelivr.net/npm/popper.js@1.16.0/dist/umd/popper.min.js"></script>
{{ end }}

<script src="{{ "js/codefolding.js" | relURL }}"></script>
<link rel="stylesheet" href="{{ "css/codefolding.css" | relURL }}" />
<script>
$(document).ready(function () {
  window.initializeCodeFolding("show" === {{ if isset .Params "codefolding_show" }}{{ .Params.codefolding_show }}{{ else }}{{ default ("hide") .Site.Params.codefolding_show }}{{ end }});
});
</script>
```

## Switch up your syntax highlighter

Wowchemy's [guide to changing your syntax highlighter](https://wowchemy.com/docs/getting-started/customization/#code-syntax-highlighting) is perfectly good, but I ran into one minor problem so I thought I'd mention it. I wasn't able to find the raw CSS files for each Chroma style anywhere, so you need to run a terminal command in Hugo to grab them. However, if you're like me and use blogdown, it's worth noting that these commands should be executed using `blogdown::hugo_cmd()`, rather than in the terminal itself. For example, to download the Dracula style, I ran `blogdown::hugo_cmd("gen chromastyles --style=dracula > assets/css/libs/chroma/dracula.css")`.

Make sure you then update `params.yaml` to use your new highlighter like so:


```yaml
features:
  syntax_highlighter:
    theme_light: igor
    theme_dark: dracula
    enable: true
```

The most complete list of Chroma options I could find is available [here](https://swapoff.org/chroma/playground/).

## Custom email address

After almost 15 years with my beloved gmail, I decided it would be nice to have a custom email address associated with my domain:  [nick@nickballou.com](mailto:nick@nickballou.com). I use Google domains for registering my website, which costs about £10/year. They want an additional £5/month, however, to set up a Google workspace and get a Google-backed email account associated with your domain, which was too rich for my blood. 

Instead, I decided to use [Zoho](https://www.zoho.com/en-uk/), which for £11/year I found to be worthwhile. The Zoho step-by-step guide when you sign upis pretty good---just note that if you're using Netlify for DNS hosting, which I was, you'll need to add the custom records on Netlify, not on your domain registrar. [This support post](https://answers.netlify.com/t/support-guide-how-can-i-receive-emails-on-my-domain/178) was helpful in sorting it all out. 

# Conclusion

Those are the little tweaks I made to spice up my website, and I hope I can help someone else spend less time banging their head against the wall than I did in order to get there. Again, all code for my website is available on [Github](https://github.com/nballou/nickballousite), so feel free to poke around/copy/etc.

What other alterations have you made to your Hugo/Wowchemy site? Feel free to let me know in the comments---after all, we wouldn't want the effort of setting those up to go to waste!
