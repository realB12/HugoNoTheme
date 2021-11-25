
## Scope and Purpose of this Hugo-theme
This Hugo-theme is **bare-bones minimalistic on purpose**! 

Minimalistic does not mean as minimalistic or stripped of as possible, but being reduced to whatever Hugo delivers out of the box (no 3rd-party components or dependencies) but will be required by MOST HugoThemes that might be based on this.

As this intended BareBones-Theme comes **without css or design-fluff** (e.g. bootstrap) and therefore comes in white and black ugliness, it is great for 

a) **learning the fundamental core theme components** and how HUGO builds upon them in general,  without being distacted and finally being lost in the overwhelming feature-fluff of the themes that normally are offered for download.   

b) having a **minimalistig testbed** for testing our own stuff without interfering with non-required complexity or 3rd-Party dependencies. BareBones is Hugo plus our HugoNoTheme-Theme! Period. 

c) The NoThemes-Theme is a great **starting point for your own**, more sophisticated themes.

## Why building from scratch

Neither the **official HUGO Theme-Providers nor HUGO itself seem to offer a bare-bones theme** that suits our purpose (most probably not to make Hugo looking bad, when such minimalims is accidently choosen for the wrong purpose). 

The theme that came closest to our expectations is the [XMin Theme](https://github.com/yihui/hugo-xmin) you may preview in the [Hugo ThemesShop](https://themes.gohugo.io/themes/hugo-xmin/) - but we had to strip it down even further.

Further we (internally) needed a Render-Hooks to deal with `[my link](../myLink.md#section01)` formatted Hyerlinks in our `*.md` source/content files. For us this is bare-bones requirements as well as we need and want hyperlinks in our sources that work on GitHub and our Markdown editors (currently using [Markddown Monster](https://markdownmonster.west-wind.com/) as well. 

So, for getting really down to bare-bones, we had to build it from scratch.

Last but not least, it is always a good idea to know and fully control the base of all your futere undertakings. 