# About

Personal blog of Roman Dushko.

# Tech Stack

Uses [Hugo](https://gohugo.io/) blog engine with [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme.
Hosted at [GitHub Pages](https://docs.github.com/en/pages).

## Prerequisites

- golang v1.22+
- hugo v0.168+
- git (2.43+, but any latest, really)

# Contribution

In order to contribute content, you first need to clone repository to your local machine, including submodules (where "themes" are installed):

```sh
git clone --recursive git@github.com:rodush/blog.git .
```

## Creating content

To create a new article / post, use hugo's native command:

```sh
hugo new content ./content/<path>
```

## Updating content

1. Make changes to the needed [content](./content/) file(s).
2. Add modifiled files with `git add .` (make sure only relevant files are added),
and commit them - `git commit`.

## Preview blog locally

It is possible to run hugo on local machine to preview the post.
Start the local hugo server:

```sh
hugo server
```

navigate to [https://localhost:1313](https://localhost:1313) to see how it looks.

# Publishing

While in the `master` branch, commit all the needed modifications and push to remote.\
The updated wesite will be published via GitHub Actions (workflows) automatically.

Once workflow successfully finished, navigate to the [Blog](https://www.rodush.com) to check the changes have been published successfully.
