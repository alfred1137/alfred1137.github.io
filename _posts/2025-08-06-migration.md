---
title: "Blog Migration - From GitHub Wiki to this"
date: 2025-08-06 08:30:00 +0800
categories: [Site Update, General]
tags: [Journal, AI]
description: "A look into my recent blog migration, the reasons behind it, the challenges I faced, and the new features I'm excited about."
---

Hello visitors!

For the past week or so, I have been working on setting this blog up and migrating some existing content over. I can finally say that the blog is up and running!

This post will walk you through why I made the switch, the migration process, the hurdles I overcame, and what this means for the future of my content.

## ~~Story of my life~~ Why do I even bother?

I consider myself barely *code-literate*. The most "coding" I have ever done was in University, during my Ecological Data Science class. My lecturer [Dr Tim Bonebreak](https://x.com/bonebraking) taught the class how to use **R**. I knew Python and such existed; and I knew they are very efficient in processing information. I just didn't think that my corporate career will require extensive understanding or use of these tools.

Fast forward to when *ChatGPT* happened. Many thought we would be displaced out of our job because *AI can do what you do if not better*. I saw the great potential of it being my platform to get access to the computing power of programming language without me having to write a line of code!

After a few years of hopping between ChatGPT, Gemini, and Claude, I decided to put my ability to use AI to my advantage to a test. I looked up a nice Jekyll template [Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy) for GitHub Page; started a repo with the template the [author](https://github.com/cotes2020) has kindly built; cloned the repo and get to work in Visual Studio Code.

## Didn't you say *Migration*?

Yes, I did. I weren't exactly starting from scratch, I was documenting my gameplay of [career mode](/posts/LOFC-CM-CH00/) in EA FC 2025 in a [GitHub Wiki](https://github.com/alfred1137/LOFC-CM-202503/wiki). That means I had some basic experience working with Git and GitHub.

The GitHub Wiki was simple and allowed for quick content creation. All I have to do is write the story in a Markdown file, commit and sync it, and *VOILÀ*: the page is on the worldwide web! As the project evolved, however, I encountered problems:

-   **Limited Customization:** The styling and layout options on the Wiki were restrictive. I wanted a look that I could control.
-   **Lack of Structure:** Features like categories, tags, and a proper archive were missing, making it difficult for readers to discover and navigate posts.
-   **Manual Processes:** Many aspects, like creating a table of contents or ensuring a consistent look, were manual and time-consuming.
-   **Integration of coding agent:** Rules, workflows, and documentations that are created for the coding agent (in my case - [Cline](https://cline.bot/)) are mostly in `.MD` format. By GitHub Wiki's default, they **all** show-up on the navigation bar, which I dislike

## The Migration

The migration was a multi-step process that involved careful planning and execution, using my **Leyton Orient Career Mode (LOFC-CM)** series as the pilot project.

### 1. Choosing the Right Tools & Workflow

I chose **Jekyll**, a powerful static site generator, for its simplicity and strong integration with **GitHub Pages**. The [**Chirpy theme**](https://github.com/cotes2020/jekyll-theme-chirpy) was selected for its clean design, rich feature set (including dark mode, search, and a beautiful TOC), and excellent documentation.

My entire deployment process is automated through **GitHub Actions**. Any commit to the main branch triggers a workflow that builds the site and deploys it, making publishing seamless.

### 2. Configuring the basics

The first major task was to configure the basics of the blog. This involved diving into the `_config.yml` file, which acts as the central hub for the site's settings. I updated key variables such as:

-   **`url`**: Setting the website's address.
-   **`avatar`**: Uploading my personal avatar.
-   **`timezone`**: Ensuring post dates and times reflects my time in UTC+8.
-   **`lang`**: Defining the site's primary language.

Beyond the main configuration, I also customized the social media links in `_data/contact.yml` and made some minor tweaks to the site's styling by adding custom CSS to `assets/css/jekyll-theme-chirpy.scss`.

These were all very easy with the aid of Cline.

### 3. Taming the Assets

I then moved all my existing Markdown files from the Wiki to the new project structure. I did this chapter by chapter, which involved:

-   Setting up the `_posts` directory.
-   Renaming files to the required `YYYY-MM-DD-TITLE.md` format.
-   Adding standardized YAML front matter to each post for titles, dates, categories, and tags to ensure consistency across the series.

All images and other media assets were consolidated into post-specific folders within the `assets/img/` directory (e.g., `assets/img/LOFC-CM-CH01/`). This required updating all image links within the posts to point to their new, centralized location, ensuring a more organized and maintainable structure.

Again, *fairly easy* when assisted with Cline. It has chosen to complete a lot of these with shell scripts, which are basic enough that I know exactly what each one is going to do to my computer.

## Challenges and Learnings

The above was the easy part. The real challenge comes as soon as I started working on implementing the specific syntax or variables that Jekyll expect on the LOFC-CM series.

### So much that I didn't know

-   **External Links Handling:** I naively thought I could just put - *for example* - `www.leytonorient.com` as link like how I would normally do in a browser. I commit, sync, GitHub action run, and then I get a big ❌ for failure to validate. I didn't know external links must start with `https://`
-   **Internal Links Handling:** Do I put `/` before the relative path to an asset? Is it `/asset/img/` or `asset/img/` or `/asset/img`...? Turns out, it was circumstantial.
-   **Too Many Request:** I needed to audit the old posts to check for compliance to the formatting required for the new blog environment. That sounded easy enough. How about I develop a Cline workflow with detailed instruction about what to check and how to change? Ok, done - Let's run it. `Cline wants to read this file`, `Cline wants to edit this file`, `The model used search patterns that don't match anything in the file. Retrying...`. and then I get a huge block of warning text telling me I have reached my Gemini quota. Guess I will have to get a sip of tea and then hit retry.

To those of you who understand computer better, the above might be very trivial. For me, however, each of them was a bit of an *Eureka* moment.

With the aid of Cline, none of these problems was showstopper. I ran into error; I passed the error to Cline; I received advice on what may have gone wrong - and then I worked on resolving it. The entire experience was very pleasant. I certainly have learnt a lot!

## Thank you for reading

Honestly, I fully expect *nobody* to read this. I still thought it was a good idea to journal what I was spending my time on. My **Leyton Orient series** started for the exact same reason. If you have some time spare, do [go over](/posts/LOFC-CM-CH00/) and give it a read!
