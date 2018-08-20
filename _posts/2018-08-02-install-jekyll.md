---
layout: post
title: How to easily run a Jekyll blog on github
subtitle: Show how to setup a blog on github pages
tags: [Jekyll,Blog,Github]
---

Github pages helps you host your blog on Github, automatically update your blog by pushing changes to a repository on your Github account.

This guide can help you get up and running pretty quickly.

# Setup your repository that'll host your blog source

Navigate to [Github](http://github.com), Login and click **New Repository**

![New Github repo button](/img/2018-08-02-install-jekyll/new_repo_button.png)

On the New repository page, change the name to be your Github username **{github_name}/{github_name}.github.io**.

This is my repository example

![New Github repo page]({{ site.url }}/img/2018-08-02-install-jekyll/new_repo_page.png)

Leave the rest of the options and click **Create Repository**

Next go the **Settings** option for the repository

under the **GitHub Pages** heading click **Change Theme** option

![Change Theme]({{ site.url }}/img/2018-08-02-install-jekyll/change_theme.png)

Try some of the themes and then click **Select Theme**

![Theme Chooser]({{ site.url }}/img/2018-08-02-install-jekyll/theme_selection.png)

Add a comment and then commit the changes

![Commit Changes]({{ site.url }}/img/2018-08-02-install-jekyll/commit_changes.png)

Test by going to **http://{github_name}.github.io**
