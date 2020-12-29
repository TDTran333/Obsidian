---
tags: R, blog
---
Link: [Website](https://alison.rbind.io/post/2020-12-27-blogdown-checks/), [Starting](https://alison.rbind.io/post/2017-06-12-up-and-running-with-blogdown/), [Troubleshoot](https://alison.rbind.io/post/2019-03-04-hugo-troubleshooting/)
Related: [[Blogdown Book]]

# Unbreak your Blogdown Site
Problem: there are lots of (predictable) ways that blogdown users can stumble into pain. We have added some printed messages like errors and warnings to help teach users, but the problem with those is that users still experience pain first. They may get frustrated and give up early, or start to tune out these “helpful” messages.

Proposed solution: take a more proactive stance to guide users toward success first by offering some targeted functions to help them sidestep predictable pain points, while at the same time helping users understand all the moving pieces.

### “checking” functions for blogdown

| Check Functions   | Details                                |
| ----------------- | -------------------------------------- |
| check_config()    | Check your site’s configuration        |
| check_gitignore() | Check your .gitignore file             |
| check_hugo()      | Check your Hugo versions               |
| check_content()   | Check your Hugo content                |
| check_netlify()   | Check your Netlify setup               |
| check_site()      | Wraps all five up in a single function |

##### Check your site’s configuration
Your Hugo site’s main configuration file is located in the project root of your website, called `config.toml` or `config.yaml`. This file is your most direct line of communication with Hugo itself, and settings in this file are usually the first I check when trying to help users troubleshoot their build.

##### Check your `.gitignore` file
If you are using blogdown, you’ll likely need a version control system like Git. Files named in a `.gitignore` file will always be ignored whenever you add and commit files to your remote repository, but having the wrong files listed here can easily sink you a few hours. This function screens for items you should remove, and for items you can safely add. It also checks if you are using Netlify, which we assume based on the presence of a `netlify.toml` file in your project.

##### Check your Hugo versions
Hugo versions are by far one of the biggest pain point. Some themes aren't compatible with some Hugo version.

Note that the new blogdown Hugo versioning system now relies on a `.Rprofile` file that you probably want to keep in the project root. These files are a bit annoying, because anytime you need to edit them, you’ll want to restart your R session for changes to take effect. If you don’t have a project-level `.Rprofile` file, try the newly added `blogdown::config_Rprofile()` function to create one (see `?config_Rprofile` for help).

##### Check your Hugo content
Your Hugo site’s content predictably lives inside the `content/` folder of your project. But there are lots of unpredictable things Hugo can do (or not do) with your content. For example, I think [every blogdown user](https://alison.rbind.io/post/2019-03-04-hugo-troubleshooting/#dates) at some point has stumbled into the `draft: TRUE` minefield, or the future dated content abyss. As well, many users accidentally end up with duplicate rendered output files (Hugo will prefer the `.html` if present).

Note that this also checks that all R Markdown files have some kind of knitted rendered output present. This is 🆕, and we believe is a better default. Think: save-on-knit. You now only need to knit R Markdown files (the previous behavior was knit-on-save, which sometimes led to an error-filled render vortex if your code did not run).

##### Check your Netlify setup
Check Hugo version on Netlify vs. the local version.
You want these to match, so that you can be reasonably sure that what you see on your public site will not be a surprise



