Saito(pronunciation of 'site' in Japanese) Boilerplate is static website boilerplate for designers and everyone.

![](https://github.com/hakuoku/hugo-saito-boilerplate/blob/master/images/screenshot.png)

## Features
- Flexibility for building any type of website.(personal, portfolio, documentation...)
- Social links（Twitter, Facebook, Instagram, Google+, GitHub, GitLab, Pinterest, Tumblr, Vimeo, YouTube, Linkedin）
- Twitter & Facebook card
- Disqus
- Google Analytics
- Font Awesome

## Installation
In your Hugo project directory, run

```
git clone https://github.com/hakuoku/saito-boilerplate.git themes/saito-boilerplate
```

and add your config.toml

```toml
theme = "saito-boilerplate"
```

## Configuration
Add the following lines to your config.toml according to your need.

```toml
baseurl = "http://www.example.com"
languageCode = "en-us"
DefaultContentLanguage = "en-us" # change to your language
title = "Your Site Title"
theme = "saito-boilerplate"

hasCJKLanguage = false # if your site has CJK language, set true
canonifyurls = true
paginate = 3 # default number of pages per page in pagination
publishDir = "docs" # if you use GitHub to deploy
disqusShortname = "yourdisqusshortname"
googleAnalytics = "UA-123-45" # to enable Disqus and Google Analytics

[params]
    description = "Conan Doyle's personal website"
    keywords = "mystery, history, medicine"
    images = [""] # your site-wide thumbnail image used in Twitter card and opengraph

[author]
    name = "Sir Arthur Conan Doyle"

[social] # to enable social links, add your account names
    twitter = "BakerStJournal"
    facebook = ""
    facebook_admin = "" # enables facebook opengraph
    linkedin = ""
    instagram = ""
    googleplus = ""
    github = ""
    gitlab = ""
    pinterest = ""
    tumblr = ""
    vimeo = ""
    youtube = ""

# if you want markdown WYSIWYG line break
[blackfriday]
    extensions = ["hardLineBreak"]

# main menu
[[menu.main]]
    name = "About"
    url = "/about/"
    weight = 1
[[menu.main]]
    name = "Works"
    url = "/works-index/"
    weight = 2
[[menu.main]]
    name = "Blog"
    url = "/blog/"
    weight = 3

# add footer contents here
[[params.footer]]
    name = "221B, Baker Street"
    url = false
[[params.footer]]
    name = "Mail"
    url = "mailto:"
```

## Usage
### Content Management
To create contents which you want show in home page, make files in `/content/home` directory.

```
hugo new home/home-contents.md
```

To create contents which you want show up in chronological order(like blog), make files in `/content/blog` directory.

```
hugo new blog/mypost01.md
```

To create contents which you *don't* want show up chronologically, make files in `/content/works`(or any other name as you like) directory.

```
hugo new works/mywork01.md
```

And create `works-index.md`(fix name according to the name you picked in previous step) page in `content` root directory, then manually add links of your non-chronological contents to the page.

### Add CSS
Saito Boilerplate's CSS should be placed on `/static/css/style.css`. If you use Sass or other preprosessor, please make sure styles are compiled into that file.

Or you can add custom stylesheets and CDN links as many as you want. Copy `css.html` from `/themes/saito_boilerplate/layouts/partials` into `/layouts/partials` directory and add links to your stylesheets.

```html
<link rel="stylesheet" href="{{ "css/mystyle.css" | absURL }}">
```

For custom js files, follow the same steps above.

### Favicons
Name your favicons `favicon-16x16.png`, `favicon-32x32.png` and `apple-touch-icon.png`(180 × 180) and place them `/static/img` directory.

### Twitter card and opengraph
To enable Twitter card and Facebook og, add Twitter account name and Facebook App ID in [social] section in `config.toml`.

And then set `images` value in site and individual post's params.

```toml
images = ["/img/thumbnail01.png"]
```

## License
Saito Boilerplate is licensed under the MIT license.

## Special Thanks
This project is deeply inspired by [CSS Zen Garden](http://csszengarden.com/). Pay a visit to experience the beauty of CSS design.
