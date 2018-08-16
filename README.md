# docs

This is a project to produce content to our documentation site over at https://informasjonsforvaltning.github.io/

We use [Hugo](https://gohugo.io/) and the [docDock theme](http://docdock.netlify.com/) to build our site.
## Requirements
You need to have git and hugo installed.
## Produce content
To produce content to the site, you need to do the following steps. Only people with the correct privileges will actually be able to publish new content.
```
git clone https://github.com/Informasjonsforvaltning/docs.git
cd docs
hugo server - D # This will start hugo in draft livereload mode
atom . # Open the content folder in your favourite editor
```
At http://localhost:1313 you will see your site as you update and save content.
## Publish
To publish your new content to our site, you need to do the following steps. Only people with the correct privileges will actually be able to publish new content.
```
<Press Ctrl+C to kill the hugo server>
./deploy.sh
```
This script will generate, commit and publish the new content (the public folder) to our site.
