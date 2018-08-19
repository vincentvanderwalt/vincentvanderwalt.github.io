---
layout: post
title: See How To Edit A Jekyll Blog Locally
subtitle: How to edit your blog locally
tags: [Jekyll,Blog,Github]
---

Hosting your blog on github is easy. But how do you add posts ?

This guide can help you add posts locally and push them to your blog.

# Prerequisites

You have to have Git installed locally as well as some editor to edit to the Markdown files.

You can find ***git*** [Here](https://git-scm.com/)

Personally I use Visual Studio Code which is free and comes with a nice Markdown previewer out the box.

***Visual studio code*** can be downloaded from [Here](https://code.visualstudio.com/)

If you'd like a good linter (analyzer) to check for errors in your code install [MarkdownLint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)

To run your site locally, you need ***Ruby*** with ***Jekyll*** and ***Bundler*** installed.

You can find Ruby (ensure **MSYS2-Devkit** is also installed ) [Here](https://rubyinstaller.org/downloads/)

You install Jekyll and Bundler by running the following Gem Command

```bash

Gem install Jekyll Bundler

```

## Clone your github repository locally

Navigate to [Github](http://github.com), Login and click on the **Search box**

![github repository search box](../img/2018-08-10-local-edit/github_searchbox.png)

Type in your repository hosting your blog **{github_name}/{github_name}.github.io**.

This is my repository example

![github repository search box with repo name](../img/2018-08-10-local-edit/github_search_with_repo.png)

Now click on the actual repository to open it

Next, click on the **Clone or download** button

![github clone option](../img/2018-08-10-local-edit/github_clone_button.png)

Click on the **Copy** option to copy the url of the repository

![github clone url](../img/2018-08-10-local-edit/github_clone_option.png)

On your local drive create a folder to copy your site into

![local blog parent folder](../img/2018-08-10-local-edit/local_blog_parent_folder.png)

Open Command Prompt and type

```bash
git clone {Your_Repository_URL}

```

Here's mine

![git clone example](../img/2018-08-10-local-edit/git_clone_example.png)

You should now see a folder with your github blog name

![local folder structure](../img/2018-08-10-local-edit/local_folder_structure.png)

## Adding a new post

Notice the **_posts** folder.

This is where your blog posts will live.

Images used in the blog posts should be placed in the **img** folder.

I tend to put blog post associated images in it's own folder for structure.

![local img structure](../img/2018-08-10-local-edit/local_img_structure.png)

To add a new post, open the **_posts** folder and add a new markup file with the following format **yyyy-mm-dd-{post_title}.md**

Open the file and add the following to the top of the file

```Markdown

---
layout: post
title: {Title_of_your_post}
subtitle: {Subtitle_here}
tags: [Any appropriate tags]
---

```

Now add the rest of your post using Markdown

## Test your changes locally

To test your changes locally, do the following.

Firstly you need to add a **Gemfile** to the root folder of your blog.

Open the file in your favourite editor and add the following

```Gemfile

source 'https://rubygems.org'

gem "github-pages", '163', group: :jekyll_plugins

```

Save the file then open a commandline in the root of your blog folder

Run the following command

```bash

Bundle install

```

Then

```bash

Bundle exec Jekyll serve

```

You're blog will be available locally at http://localhost:4000

Running ***Bundle exec Jekyll serve*** enables live tracking of changes to posts.

Change any of your posts, save the file and the site at local host will have the changes after refreshing the page.

## Deploy your site to github

Once you're ready to deploy your site, open the command line at the root of your blog folder.

Run the following command to add your new files

```bash

git add *

```

Now run this to commit your changes locally

```bash

git commit -m "{your_commit_comment_here}

```

Now push your changes to github

```bash

git push

```

You're changes should now be available online

Congratulations !!!