# CS294 RISE Class Github Pages Website

To contribute to this class fork this repo and send pull requests with any changes to the content.

This website is written using Jekyll Bootstrap with some modifications to improve support for github pages. 

# Building Locally

Make sure you have a version of ruby that is 2.2 or higher. If not on a mac run:

```bash
brew install ruby
```

You will also need bundle:

```bash
gem install bundle
```

then to setup the Jekyll build environment run:

```bash
cd path/to/cs294-rise-fa16
bundle install
```

Finally to serve the project locally:

```bash
bundle exec jekyll serve --baseurl ''
```
