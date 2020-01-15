# Setup a Jekyll site using Jekyll 4 and Bootstrap 4

# Preiminaries...
## 1. Bootstrap
Go to <https://getbootstrap.com/> and download the newest version (at the time of writing v4.3.1 )
Press Button marked "Download" on next page press "Download source".
Unzip to `/home/harald/buildspace/bootstrap/bootstrap-4.3.1`.

## 2.Ruby version
Get the newest Ruby version (at the time of writing v2.6.5 ):

        $ rvm install 2.6.5
        $ rvm --default use 2.6.5

# create new project in Rubymine
1. Close all projects 
2. In splash screen create new project
3. in new project screen select: 
      select "Empty Project"
      Location: `/home/harald/RubymineProjects/lb-klingt`
      Tick: "Use Gemset..."

Now we have a project with: ".ruby-gemset" and ".ruby-version"

# Populate Project with initial files.

copy the following files and adapt them to your needs:

- `.gitignore`
- `.rubocop.yml`
- `_config.yml`
- `Gemfile`
- `index.html`

1. run Git.
2. run `$ bundle install`
3. close and reopen RubyMine. Verify that now `jekyll 4` and `jekyll-sass-converter` are listed.
4. run `$ which jekyll` verify that the response isd something like
  `/home/harald/.rvm/gems/ruby-2.6.5@lb-klingt/bin/jekyll`
5. run `$ jekyll --version` expect  `jekyll 4.0.0`

# Build and test for the first time

run `$ jekyll serve`

## Step 2, copy paste the "carousel" example
1. replace the index.html 
2. create a directory `assets`. From `<bootstrap-root>/site/docs/4.XXX/assets`:
    - copy `/js/vendor/`
    - copy the `brand` and the `img` directory.
3. From `<bootstrap-root>/dist/js`:
    - copy `bootstrap.min.js` and map 
    - copy `bootstrap.min.js`
4. From `<bootstrap-root>/site/docs/4.1/examples/carousel`
    - copy `carousel.css` into `assets/styles`
    - copy `index.html`
    - copy `_layouts/examples.html`
5. copy the favicon from `<bootstrap-root>/site/favicon.ico` into the root.
6. copy some of the _layout (default and examples)
6. copy some of the _includes (/icons analytics.html etc)
8. Rename `_layouts.examples` to `landingpage`


Run `jekyll serve`


# Bootstrapize the site

lets study the following tutorial and see wht we can make of it...
<https://www.tutorialrepublic.com/twitter-bootstrap-tutorial/bootstrap-get-started.php>

### Use JavaScrip from CDN (Content Delivery Network)
edit  `_include.footer`. Replace the content with:
```html
    <!-- JS files: jQuery first, then Popper.js, then Bootstrap JS -->
    <script src="https://code.jquery.com/jquery-3.3.1.slim.min.js" integrity="sha384-q8i/X+965DzO0rT7abK41JStQIAqVgRVzpbzo5smXKp4YfRvH+8abtTE1Pi6jizo" crossorigin="anonymous"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.14.7/umd/popper.min.js" integrity="sha384-UO2eT0CpHqdSJQ6hJty5KVphtPhzWj9WO1clHTMGa3JDZwrnQq4sF86dIHNDz0W1" crossorigin="anonymous"></script>
    <script src="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/js/bootstrap.min.js" integrity="sha384-JjSmVgyd0p3pXB1rRibZUAYoIIy6OrQ6VrjIEaFf/nJGzIxFDsf4x0xIM+B07jRM" crossorigin="anonymous"></script>
```
### Make css building dynamic...
1. move `assets/styles/carousel.css` to `_sass/landingpage.scss`
1. create the file  `assets/styles/main.scss`
2. remove all css files in `assets/styles/`
3. copy `<bootstrap-root>/bootstrap-4.3.1/scss` to `_sass/bootstrap`
5. ...

see also <https://www.tutorialrepublic.com/twitter-bootstrap-tutorial/bootstrap-grid-system.php>

### Theming Bootstrap
see <https://getbootstrap.com/docs/4.0/getting-started/theming/>


### Customizing the navigation bar
see <https://www.tutorialrepublic.com/twitter-bootstrap-tutorial/bootstrap-navbar.php> 
### .......

Lets use the default files from jekyll.

Create a directory `_layouts` and add the files `default.html` etc.

# Using Sass to build CSS



# Adding Bootstrap
## Different alternatives.
Twitter maintains a [Bootstrap Ruby Gem.](https://github.com/twbs/bootstrap-rubygem) so it seems tempting to use it.
But this will pull 65 gems into your installation which is quite an overkill. (So I run `$bundle clean --force` after 
having installed).
Finally I decided to copy the original development files into my project.









