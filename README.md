
## Scope and Purpose of this Hugo-theme
This Hugo-theme is **bare-bones minimalistic on purpose**! 

Minimalistic does not mean as minimalistic or stripped of as possible, but being reduced to whatever Hugo delivers out of the box (no 3rd-party components or dependencies) but will be required by MOST HugoThemes that might be based on this.

As this intended BareBones-Theme comes **without css or design-fluff** (e.g. bootstrap) and therefore comes in white and black ugliness, it is great for 

a) **learning the fundamental core theme components** and how HUGO builds upon them in general,  without being distacted and finally being lost in the overwhelming feature-fluff of the themes that normally are offered for download.   

b) having a **minimalistig testbed** for testing our own stuff without interfering with non-required complexity or 3rd-Party dependencies. BareBones is Hugo plus our HugoNoTheme-Theme! Period. 

c) The NoThemes-Theme is a great **starting point for your own**, more sophisticated themes.

## Why building from scratch?

Neither the **official HUGO Theme-Providers nor HUGO itself seem to offer a bare-bones theme** that suits our purpose (most probably not to make Hugo looking bad, when such minimalims is accidently choosen for the wrong purpose). 

The theme that came closest to our expectations is the [XMin Theme](https://github.com/yihui/hugo-xmin) you may preview in the [Hugo ThemesShop](https://themes.gohugo.io/themes/hugo-xmin/) - but we had to strip it down even further.

Further we (internally) needed a Render-Hooks to deal with `[my link](../myLink.md#section01)` formatted Hyerlinks in our `*.md` source/content files. For us this is bare-bones requirements as well as we need and want hyperlinks in our sources that work on GitHub and our Markdown editors (currently using [Markddown Monster](https://markdownmonster.west-wind.com/) as well. 

So, for getting really down to bare-bones, we had to build it from scratch.

Last but not least, it is always a good idea to know and fully control the base of all your futere undertakings. 

### Minimal Theme related Files
```plaintext
├── config.toml
└── themes
    └── NoTheme
        └── layouts
            ├── _default     // mind the "_" underscore!
            │   ├── list.html
            │   ├── single.html
            │   └── _markup  // mind the "_" underscore!
            │       └── render-link.html              │
            │
            └── partials
                ├── footer.html
                └── header.html
```

**in more detail** this files have the following purpose

* **Root**-folder:
    * `config.toml`: must contain a reference to the Theme and the Menu for the NavBar
    
* `\themes\NoTheme\layouts\_default`-folder:
    * `site.html`: template for rendering single content-pages
    * `list.html`: template for rendering summary/index-pages

* `\themes\NoTheme\layouts\partials`-folder
    * `footer.html`: template for rendering content-pages with Copyright notes.
    * `header.html`: template for rendering summary/index-pages with a navigation bar

* `\themes\NoTheme\layouts\_default\_markup`-folder
    * `render-link.html`: the code that maps `[my link](../mylink.md#section01)` formatted hyperlinks to its `*.html` counterpart

Together, all these files make our HugoNoTheme. 

They are many less than what would be generated with the standard `hugo new theme myTheme` command.

<div style="margin-top: 20px; padding: 15px 15px 5px 15px; color:black; font-size:small; background-color:PowderBlue"><b>Design Decision</b>: we could have done it without `footer.html` and `header.html` as well by moving their content to the top (header) and end (footer) of the `list.html` and `single.html` templates. 

However, following the DRY-principle,  we have found this additional "complexity" acceptable fo the advantage to keep headers (with its navigation-Bar) and footers consistent for site and index pages (which otherwise they might not).</div>

<hr>
<b>SideNote</b>: Why the `hugo new theme` command will not do the trick:
<div style="font-size:small">
Hugo provides, out of the box,  a <code>hugo new theme myThemeName</code> command, that will generate a much more complex, nested folder-structure of empty files.  

This. for HUGO Theme designers, is the normal way to do it,  and is explained over and over again in manuals, books and communities. This approach is normally great for experienced designers who are building production-ready themes. 

But this complexity is ways beyond our "minimalistic" attempt and confusing for beginners. 

<div style="margin-top: 20px; padding: 15px 15px 5px 15px; color:black; background-color:pink; font-size:small">In case you still want to generate our NoTheme-files with the <code>hugo new theme myThemeName</code> command: Be aware that you <b>MUST delete unused/empty theme-relates files</b> as they might overwrite our own stuff and will confuse users when seeing those files but having no meaning nor impact. 
</div>

<hr>