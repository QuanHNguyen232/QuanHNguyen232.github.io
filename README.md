A Github Pages template for academic websites. This was forked (then detached) by [Stuart Geiger](https://github.com/staeiou) from the [Minimal Mistakes Jekyll Theme](https://mmistakes.github.io/minimal-mistakes/), which is © 2016 Michael Rose and released under the MIT License. See LICENSE.md.

I think I've got things running smoothly and fixed some major bugs, but feel free to file issues or make pull requests if you want to improve the generic template / theme.

### Note: if you are using this repo and now get a notification about a security vulnerability, delete the Gemfile.lock file. 

# Instructions

1. Register a GitHub account if you don't have one and confirm your e-mail (required!)
1. Fork [this repository](https://github.com/academicpages/academicpages.github.io) by clicking the "fork" button in the top right. 
1. Go to the repository's settings (rightmost item in the tabs that start with "Code", should be below "Unwatch"). Rename the repository "[your GitHub username].github.io", which will also be your website's URL.
1. Set site-wide configuration and create content & metadata (see below -- also see [this set of diffs](http://archive.is/3TPas) showing what files were changed to set up [an example site](https://getorg-testacct.github.io) for a user with the username "getorg-testacct")
1. Upload any files (like PDFs, .zip files, etc.) to the files/ directory. They will appear at https://[your GitHub username].github.io/files/example.pdf.  
1. Check status by going to the repository settings, in the "GitHub pages" section
1. (Optional) Use the Jupyter notebooks or python scripts in the `markdown_generator` folder to generate markdown files for publications and talks from a TSV file.

See more info at https://academicpages.github.io/

## To run locally (not on GitHub Pages, to serve on your own computer)

1. Clone the repository and made updates as detailed above
1. Make sure you have ruby-dev, bundler, and nodejs installed: `sudo apt install ruby-dev ruby-bundler nodejs`
1. Run `bundle clean` to clean up the directory (no need to run `--force`)
1. Run `bundle install` to install ruby dependencies. If you get errors, delete Gemfile.lock and try again.
1. Run `bundle exec jekyll liveserve` to generate the HTML and serve it from `localhost:4000` the local server will automatically rebuild and refresh the pages on change.

# Changelog -- bugfixes and enhancements

There is one logistical issue with a ready-to-fork template theme like academic pages that makes it a little tricky to get bug fixes and updates to the core theme. If you fork this repository, customize it, then pull again, you'll probably get merge conflicts. If you want to save your various .yml configuration files and markdown files, you can delete the repository and fork it again. Or you can manually patch. 

To support this, all changes to the underlying code appear as a closed issue with the tag 'code change' -- get the list [here](https://github.com/academicpages/academicpages.github.io/issues?q=is%3Aclosed%20is%3Aissue%20label%3A%22code%20change%22%20). Each issue thread includes a comment linking to the single commit or a diff across multiple commits, so those with forked repositories can easily identify what they need to patch.

# Further Instructions
* Sample: [Building an Academic Website](https://jayrobwilliams.com/posts/2020/06/academic-website/) on jayrobwilliams.com
* To add new navigation link, add folder `_name`, add page `name.md`, then under `_pages`, add corresponding file
* [Official instruction](academicpages.github.io)

<details>
<summary>teaching code base example</summary>

```python
27 results - 12 files

_config.yml:
178:   teaching:
212:   # _teaching
215:       type: teaching

_data\navigation.yml:
9:   - title: "Teaching"
10:     url: /teaching/    

_includes\archive-single.html:
41:         {% if post.collection == 'teaching' %}

_layouts\single.html:
37:         {% if page.collection == 'teaching' %}

_pages\cv.md:
51: Teaching
53:   <ul>{% for post in site.teaching %}

_pages\markdown.md:
19:   * _teaching/

_pages\teaching.html:
3: title: "Teaching"
4: permalink: /teaching/
10: {% for post in site.teaching reversed %}

_sass\vendor\font-awesome\_icons.scss:
193: .#{$fa-css-prefix}-chalkboard-teacher:before { content: fa-content($fa-var-chalkboard-teacher); }

_sass\vendor\font-awesome\_variables.scss:
207: $fa-var-chalkboard-teacher: \f51c;

_teaching\2014-spring-teaching-1.md:
2: title: "Teaching experience 1"
3: collection: teaching
5: permalink: /teaching/2014-spring-teaching-1
11: This is a description of a teaching experience. You can use markdown like any other post.

_teaching\2015-spring-teaching-2.md:
2: title: "Teaching experience 2"
3: collection: teaching
5: permalink: /teaching/2015-spring-teaching-1
11: This is a description of a teaching experience. You can use markdown like any other post.

assets\fonts\fa-solid-900.svg:
414:     <glyph glyph-name="chalkboard-teacher"
```
</details>