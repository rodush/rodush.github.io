---
title: "Personal Blog With Hugo and Github Pages"
date: 2026-10-24T18:32:29+02:00
categories:
  - howto
  - blog
tags:
  - hugo
  - github
  - pages
  - blog
draft: true
---

In this post I would like to share how to setup personal blog pretty much for free,
using [Github Pages](https://pages.github.com) for hosting and personal site engine like [Hugo](https://gohugo.io).

You may only need to pay costs of the custom domain name, if you want URL to be something different than `<username>.github.io` (default domain of your website hosted on Github Pages).

You might wonder, how this post is different from many other resources available on Internet, including video's like [this](https://www.youtube.com/watch?v=LIFvgrRxdt4) or [this](https://www.youtube.com/watch?v=_QSr2_pxIJs)  on YouTube.\
In many cases, it will repeat what's been mentioned already, but also it uses simpler setup with just one repository.

We will be using modern technique of publishing the website by means of Github Actions (Workflows), like in the 2nd video link I mentioned above, so every time you push changes to your `main` branch, updates are automatically published.

# What you need?

1. Github Account. Go and create one by signing up at [https://github.com/signup](https://github.com/signup) if you don't have it yet.
1. Once signed up, create repository called `<your-github-username>.github.io`. Yes, it needs to be called exactly like that!
1. \* _Custom domain name (it's optional, but looks much nicer than the default Github Page's domain name)_\
Find whatever works best for you in your region, I am not advising anything particular.
1. Computer with, preferrably, unix-based operating system. For the sake of this post I am using Linux Mint with the default `bash` terminal.

## Setup computer for work

On your computer you will need to have Go programming language installed. It is used to convert `.md` files of your blog posts into HTML, as well as processing other supplementary files - images, CSS, JS, and few others). Follow instructions [here](https://go.dev/doc/install).

You need to have [hugo](https://gohugo.io/installation/) installed. Default installation instructions will advise you to use your system package manger, like `homebrew` for MacOS, or `apt` for Ubuntu family. What I noticed is that it does not install the latest version of `hugo` out of its default repositories. So my advice would be to grab the freshest and latest version from the hugo's [Releases](https://github.com/gohugoio/hugo/releases) page directly.

## Setup Github repository

If you have your personal _Free_ Gihub account, you will have to make your resitory "public" in order to use Github Pages.

Scroll down to the very bottom of the [Settings](https://github.com/<your-github-username>/<your-github-username.github.io/settings) page, where under the **"Danger zone"** you will see the `[Change visibility]` button. Click it and follow the on-screen instructions. Make sure repository is (made) public.
![Make Repository Public](/images/settings-make-repo-public.png).

While in the `Settings`, click the [Pages](https://github.com/<your-github-username>/<your-github-username.github.io/settings/pages) link in the left navigation panel:
![Github Pages settings page](/images/settings-pages.png)

Find the **"Build and deployment"** section, and as **Source** select _Github Actoins_, like on the screenshot above.

Under **"Custom domain"** section specify your custom domain name. Once clicked `Save` button it will initiate the DNS Check. You need to connect the dots by teaching your domain name provider to talk to Github Actions. It is all described in the GH's pages' documentation - [Configuring an apex domain](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/managing-a-custom-domain-for-your-github-pages-site#configuring-an-apex-domain).

Essentially, in your control panel of the domain registrant you should configure records to look like this:
![DNS configuration for Github Pages](/images/cname+a-records-github-dns.png).

# Creating your blog

For your Hugo-based blog (or site), you need to pick some [theme](https://themes.gohugo.io/). Quite simplistic but very popular one is a [PaperMod](https://themes.gohugo.io/themes/hugo-papermod/). The great news is that **all** hugo themes **have to be made free**, following the MIT license. Not like for [Astro](https://astro.build/themes/). But of course, paid themes are much more polished and :cool:-looking! Even though even for Astro you may find some [free themes](https://astro.build/themes/1/?search=&price%5B%5D=free) as well.

Cool stuff about Hugo's themes and the website, that they are mostly super lightweight and blazing fast, scoring :100:! or close to 100, at the [Page Speed Insights](https://pagespeed.web.dev/) website:
![PageSpeed Insights for www.rodush.com](/images/pagespeed-rodush-com.png)

You will be working on your web site / blog by creating content in Markdown on your local machine (or directly from Github, really). So, you need to clone your repository:

```sh
git clone git@github.com:<your-github-username>/<your-github-username>.git 
```

I will not be repeating how to create Hugo site or content, you can find all the relevant information in the Hugo's and PaperMod's documentation, i.e. [here](https://gohugo.io/getting-started/quick-start/).

I will show you how to add theme as a git submodule though, and how to check that it actually is registered correctly.

```sh
git submodule add git@github.com:adityatelange/hugo-PaperMod.git themes/PaperMod
```

where `themes` is the directory which will hold your theme's cloned files.

Next time, when you are cloning your repository on another clean machine, you will need to clone the content including the submodules:

```sh
git clone --recursive git clone git@github.com:<your-github-username>/<your-github-username>.git
```

and then you will be able to pull content of the submodule with:

```sh
git submodule sync
```

you should see something like:

```sh
Synchronizing submodule url for 'themes/PaperMod'
```

and in your `.gitmodules` file you should see an entry:

```
[submodule "themes/charaka"]
  path = themes/charaka
  url = https://github.com/natarajmb/charaka-hugo-theme.git
```

Make sure you've committed both.
