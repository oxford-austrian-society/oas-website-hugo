# Technical Documentation

This website is built based on the following tools:

- **[Hugo](http://gohugo.io)**, a static site generator written in golang. It generates a fully-functional website using markdown-files in the content section and suitable html-templates.
- **[Github pages](https://pages.github.com)**, Github's framework for hosting static sites
- **[Wercker](http://wercker.com)**, a Docker-based continuous integration tool that handles the build and commit workflow.
- **[Prose.io](http://prose.io#about)**, an online-editing tool for Github-repositories that acts like a content management system.

## Repository-structure

All the project-files are stored in the **[oas-website-hugo-repository](https://github.com/oxford-austrian-society/oas-website-hugo)**.

```
.
├── config.toml
├── content
├── docs
├── _prose.yml
├── public
├── static
├── themes
└── wercker.yml

```

### Content

The **[content-folder](https://github.com/oxford-austrian-society/oas-website-hugo/tree/master/content)** contains the markdown files, which will constitute the content of the page. General content such as the **About** and **Calendar** are stored in this folder. The subfolder **[blog](https://github.com/oxford-austrian-society/oas-website-hugo/tree/master/content/blog)** contains timestamped posts, such as updates, news, announcements and reports on passed events.

### Static

Static files are stored in the **[static-folder](https://github.com/oxford-austrian-society/oas-website-hugo/tree/master/static)**. These include image uploads, custom-css and custom javascript.

### Themes

The **[themes-folder](https://github.com/oxford-austrian-society/oas-website-hugo/tree/master/themes)** contains a copy of the code for the **[hugo-future-imperfect-theme](https://github.com/jpescador/hugo-future-imperfect)**. In order to prevent problems in the build step, we use a copy rather than a clone of the original repository, as a git-repository inside a git-repository will be treated as a submodule. Submodules are linked-up git-repositories. An additional clone step is thus required to retrieve the code that is needed for building the website.

### Public

This is the folder hugo will build the static site to. In order to host the site under `oxford-austrian-society.github.io`, github needs the static site to be on the master-branch of a repository with just that name. Hence, this folder is setup as a submodule, linking to the the **[oxford-austrian-society.github.io-repo](https://github.com/oxford-austrian-society/oxford-austrian-society.github.io)**. In the build step, the static site is generated and updates are automatically pushed to the repo. Thus, there is no need to interact directly with this repository.

## Workflow

For guidelines on the general useage of hugo, please consult their excellent documentation: http://gohugo.io/overview/usage/ and http://gohugo.io/overview/installing/.

### Generate new post via command line

```
hugo new blog/my-post-name
```
This will generate a new markdownfile `/content/blog/my-post-name.md`. The markdown-file will contain the following header:

```
+++
author = ""
date = "YYYY-MM-DD"
categories = []
description = ""
linktitle = ""
featured = ""
featuredpath = ""
featuredalt = ""
type = "post"
+++
```

The precise contents of the header are specified under `[/themes/imperfect/archetypes/blog.md](https://github.com/oxford-austrian-society/oas-website-hugo/blob/master/themes/imperfect/archetypes/blog.md)`. The presence of these metadata is crucial for the theme to work correctly.
