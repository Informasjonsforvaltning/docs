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
To add the content to `<organization name>.github.io`, you need to add a submodule:
```
rm -rf public
git submodule add -b master git@github.com:<organization name>/<organization name>.github.io.git public
git add .
git push -u origin master
```
To regenerate the content and push the submodule to `<organization name>.github.io.git`:
```
hugo
cd public
git add .
git commit -m "Generate site"
git push origin master
```
To automate the last part, use the [./deploy.sh](./deploy.sh) script. You should find your site at `http://<organization name>.github.io`.


## Credits

- http://docdock.netlify.com/
- https://gohugo.io/hosting-and-deployment/hosting-on-github/#github-user-or-organization-pages
- https://github.com/whipperstacker/blog/blob/master/content/post/deploying-a-hugo-site-to-github-pages.md
