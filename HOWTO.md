# How we did it

Here is a short description of what we did to set up our site to our [organization page](https://help.github.com/articles/user-organization-and-project-pages/#user-and-organization-pages-sites)

## On Github:
1. Create a `<docs repository>` to hold content and source files.
2. Create a `<organization name>.github.io` repository that will contain the fully rendered version of the Hugo website.

## Requirements
You need to have [Git](https://git-scm.com/) and [Hugo](https://gohugo.io/) installed on your pc.

## In a capable terminal:
```
mkdir <docs repository> && cd <docs repository>
hugo new site .
git init
git submodule add https://github.com/vjeantet/hugo-theme-docdock.git themes/docdock
git submodule init
git submodule update
cp themes/docdock/exampleSite/config.toml .
```
Edit the config.toml file as needed. Specifically the following should read:
```
theme = "docdock"
# themesdir = "../.."
```

## Automatic deploy of static content to our site with Travis
Essentially what we did was to set up travis to generate static content with hugo and push the new content to our site. This is made possible by the .travis.yml script. Note that you will have to generate a secret key for Travis at github and add it you the travis-configuration. For a good step-by-step description, check this [blog](https://www.martinkaptein.com/blog/hugo-with-travis-ci-on-gh-pages/).

## Credits

- http://docdock.netlify.com/
- https://gohugo.io/hosting-and-deployment/hosting-on-github/#github-user-or-organization-pages
- https://github.com/whipperstacker/blog/blob/master/content/post/deploying-a-hugo-site-to-github-pages.md
- https://www.martinkaptein.com/blog/hugo-with-travis-ci-on-gh-pages/
