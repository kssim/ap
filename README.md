# AP
"AP" is [Jekyll](https://jekyllrb.com/) theme for career. This theme is free and open-source.  
Based on Chester How tale-theme(https://github.com/chesterhow/tale) with a few new features:  
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
├── _includes                   # theme includes
├── _layouts                   # theme layouts (see below for details)
├── _posts                     # Project & Portfolio posts
├── _sass                      # Sass partials 
├── portfolio                  # Main page for "portfolio"
├── assets
|  ├── css                     # font-awesome and main css
|  ├── fonts                       # Font-Awesome
|  ├── favicon.ico                 # Favicon
|  └── img                         # Images used for "about" page
├── _config.yml                # sample configuration
└── index.md                   # Resume to show on "about" page
```

## License
[The MIT License (MIT)](https://raw.githubusercontent.com/kssim/ap/master/LICENSE)
