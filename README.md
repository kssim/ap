# AP  [![Build Status](https://travis-ci.org/kssim/ap.svg?branch=master)](https://travis-ci.org/kssim/ap.svg?branch=master)
"AP" is [Jekyll](https://jekyllrb.com/) theme for career. This theme is free and open-source.  
Based on Chester How's tale-theme(https://github.com/chesterhow/tale) with a few new features:  
* SNS Link
* Google Analytics
* Responsive design
* Upgrading awesome fonts and modifying some layouts.
* Use "About" as main.
  * It can be written in simple resume form.
* Change "Post" to "Project Portfolio"
  * You can manage your project experience just like running a blog.


# Preview
[![AP Screenshot](https://github.com/kssim/ap/blob/master/screenshot.png?raw=true)](https://kssim.github.io/ap/)


# Usage
1. Fork and clone the AP repo:
    * git clone https://github.com/kssim/ap.git
2. Install Jekyll:
    * gem install jekyll
3. Install the theme's dependencies
    * bundle install
4. Customize the theme
    * update _config.yml
5. Run the Jekyll server
    * jekyll serve


## Structure
* Here are the main files of the template
```bash
ap
├── _includes                  # theme includes
├── _layouts                   # theme layouts (see below for details)
├── _posts                     # Project & Portfolio posts
├── _sass                      # Sass partials 
├── portfolio                  # Main page for "portfolio"
├── assets
|  ├── css                     # font-awesome and main css
|  ├── fonts                   # Font-Awesome
|  ├── favicon.ico             # Favicon
|  └── img                     # Images used for "about" page
├── _config.yml                # sample configuration
└── index.md                   # Resume to show on "about" page
```

## Configure AP
Open _config.yml in a text editor to change most of the blog's settings.


### Site Configuration
Configure Jekyll as your own blog or with a subpath in in _config.yml:  
```yml
title: [Website Title]
baseurl: [Website Subpath]
url: [Github Page Url]
google_analytics: [Google Analytics Tracking ID]
```
Please configure this before using the theme.  
And to enable Google Analytics, add your [Traking ID](https://support.google.com/analytics/answer/1008080?visit_id=1-636579797402349951-2693679291&rd=1)



### About You
Meta variables hold basic information about your profile and resume.  
Change these variables in _config.yml:  
```yml
author:
  name: [Your Name]
  desc: [Short introduction]
  email: [Your E-Mail Address]
  selfie: [Your Avatar]
```
Please configure this before using the theme.



### SNS Information
Your SNS information to display at the bottom of the page.  
All values except "email" are text values.  
```yml
social:
  email: true
  behance:
  bitbucket:
  dribbble:
  facebook:
  flickr:
  github: 
  google_plus:
  instagram:
  keybase:
  linkedin:
  pinterest:
  reddit:
  soundcloud:
  stack_exchange:
  steam:
  tumblr:
  gitlab:
  twitter: 
  vimeo:
  wordpress:
  youtube:
  default_txt: "Follow On"
```


## Portfolio Schema
```markdown
---
layout: post
title:  [Project title to show in portfolio list]
info: [A brief introduction to show in portfolio list]
tech: [The technologies used in the project to show in portfolio list]
type: [Property of the project to be displayed in front of the project's info(toy or company name)]
---
```

## Other formats
It uses the markdown syntax by default, and there is no format other than the one mentioned above.  
You can use it as you like.  


## License
[The MIT License (MIT)](https://raw.githubusercontent.com/kssim/ap/master/LICENSE)
