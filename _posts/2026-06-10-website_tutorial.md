---
title: 'Creating an Academic Personal Website'
date: 2026-06-10
permalink: /posts/2026/06/website_tutorial/
excerpt: Curious about how I created my personal website? It's not as difficult as it may seem. Also, it's completely free to create and host!
toc: true
toc_sticky: true
tags:
  - tutorials
---

# Creating an Academic Portfolio Website
This website was created using GitHub Pages, which you can read more about [in their documentation](https://docs.github.com/en/pages). I based my website off this [existing GitHub Pages template.](https://academicpages.github.io/) If you want to use a different template, you can find additional templates [here,](https://github.com/topics/portfolio-website) or you can do your own research.

 Using a pre-existing template is why you don't need a background in web development to create your own academic portfolio! 

 For this tutorial, I am assuming that you have a basic understanding of GitHub (clone, commit, pull, push) and Markdown in order to create the the webpages on your website
 
If you don't, I recommend checking out [this GitHub tutorial](https://docs.github.com/en/get-started/start-your-journey/hello-world) and this [basic Markdown syntax.](https://www.markdownguide.org/basic-syntax/) 

 On to the website tutorial!

## Required Materials
1. GitHub Account
    * If you don't have a GitHub account, you can make one [here](https://docs.github.com/en/get-started/start-your-journey/creating-an-account-on-github).
2. A few hours!

## Step 1: Fork the Academic Pages Template
In GitHub, a **repository** is a collection of files for a specific software project that can be updated and tracked as changes are made over time. **Forking** a repository means that you are creating a copy of an existing repository that another creator has made.

For my personal website, I am using this [template](https://academicpages.github.io/) by Academic Pages for my website.

To fork the repository, first navigate to the [source code for the template](https://github.com/academicpages/academicpages.github.io). Next, click on the Fork button.

![Button to Fork a repository](/images/fork.png)

This will bring you to a new page where you can name your new forked repository. Make sure you name your repository **\<your_github_username\>.github.io** as this will be the URL for your website.

You should now have a new repository for your website!

## Step 2: Set up the Sidebar
In order to set up the sidebar, which is present on all pages of the website, you will need to modify files in your repository. 

To do this, I would recommend cloning the repository from GitHub onto your computer so you can make local changes and push those changes to GitHub. **Cloning** is where you create a copy of a repository locally on your computer. You can then modify files locally and push (or upload) those files to GitHub. See [here](https://www.w3schools.com/git/git_clone.asp) if you want to learn more about cloning on GitHub.

If you don't know how to clone a repository, you can modify files directly on the GitHub website for your repository. To do this, click a file you want to edit, click on the Pencil icon, modify the file as desired, and then clicking the green Commit button in order to push (or upload) those changes to the master branch.

![Edit icon](/images/edit.png)

In order to setup the sidebar for the website, you will need to edit the `_config.yml` file in the root directory of your repository.

### Modify Basic Site Settings
If you open the `_config.yml` file in your repository, under basic site settings, you should see these options from the Academic Pages template:

![Basic Site Settings](/images/basic_site_settings.png)

Make sure you update the title, name, description, url, and repository for your website. 

Repository is the path to the repository from your GitHub account, which should be **\<your_github_username>/<your_github_username>.github.io**

### Modify Author Information
In order to change the profile picture, first you need to upload a headshot of yourself into the `images/` folder for the repository. You can do this on the GitHub website by clicking on the `images/` folder and clicking Add File in the top right corner, or by locally adding a file and pushing it to GitHub. 

Replace `profile.png` with the name of your image file.

![Biographic Information](/images/biographic_info.png)

Also, make sure you modify name, bio, location and employer. If you don't want a certain category shown on the sidebar, you can comment it out by putting a \# in front of the corresponding line (as shown in the image for pronouns and URI)

If you keep scrolling down the `_config.yml` file, you can add your usernames for different academic websites, software development websites, and social media. All of these will appear on the sidebar after you add them. 

## Step 3: Deploy Your Website
Next, you will need publish your website online using GitHub Pages. Starting from your repository page, click on the settings tab.

![Settings Tab](/images/settings.png)

From the sidebar, click on the Pages tab.

![Pages Tab](/images/pages.png)

Under **Build and Deployment**, choose "Deploy from a Branch" as your Source, and the master branch as your Branch. Click to Save.

It may take a few minutes, but now when you visit **\<your_ github_username\>.github.io**, the website should be live!

At this point, the sidebar should be filled out to your liking, and the sidebar should stay the same when you click between different pages on the website.

## Step 4: Edit Your Home Page
In order to edit your website's home page, you will need to edit the `about.md` file, which is in the `_pages/` folder. (The `.md` file extension means Markdown). 

You can change the title of the website's home page by modifying the `title` at the top. All of the content on the home page is written using Markdown, so you can add headers, plain text, images, links, to your liking!

You can look at the raw code for the home page of my website [here](https://github.com/hannahhafner/hannahhafner.github.io/blob/master/_pages/about.md?plain=1). 

## Step 5: Add or Remove Pages from the Navigation Menu
You might have noticed that the navigation menu by default contains the following webpages: Publications, Talks, Teaching, Portfolio, Blog Posts, CV, Guide. You may not want all of these pages on your website, or you might want to add new pages. 

### Removing Pages from the Navigation Menu

To remove pages from the navigation menu, you can delete or comment out pages from the `navigation.yml` file, which lives in the `_data/` folder. Note that if you comment out or delete a page from the navigation menu, **this will not fully remove the page from your website**, it only removes the webpage from the navigation menu. 

You can see this if you click on the sitemap in the footer of the website — all of the website pages are listed, regardless if they are in the Navigation menu. You can remove the Sitemap [here](https://github.com/academicpages/academicpages.github.io/wiki/Customizing-the-layout-of-your-site#removing-the-sitemap)

![Site map](/images/footer.png)

### Adding New Pages to the Navigation Menu

To add a new page to the navigation menu, first you'll need to create a new Markdown (`.md`) file in the `pages/` folder. 

At the top of your Markdown file, add a YAML header like this one:

```yml
---
permalink: /my-new-page/
title: "This is my new page"
author_profile: true
redirect_from: 
  - "/mnp/"
  - "/mnp.html"
---
```
Note the permalink — this is how you direct the navigation menu to specific pages on the website. 

If you return to the `navigation.yml`, file, you can now add your new page, where the url is the permalink you just created.

```yml
- title: "My New Page"
  url: /my-new-page/
```

You can now modify the page as desired, and after pushing your changes to GitHub, you should see the new page in the menu bar. 

## Step 6: Add Your CV

Instead of using the default CV page formatted with Markdown, I wanted to add a CV pdf that I already had on hand to my website. 

To do this, I first uploaded my CV into the `files/` directory. Then, I deleted the original Markdown content from the `cv.md` page, and added a redirect to the YAML header. 

```yml
---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
redirect_to: /files/myCV.pdf
---
```

This ensures that when a user clicks on the CV tab, they will be taken to your CV file instead of a Markdown CV. 

## Read More
Now that the foundation of your website is set up, I highly recommend checking out the [Academic Pages wiki](https://github.com/academicpages/academicpages.github.io/wiki) for more information. 
* Here, you can read more about how the content sections of the template are organized, update the Academic pages theme, and even add Google Analytics to your site (track website engagement).
