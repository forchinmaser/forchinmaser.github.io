---
title: "Gemfile Dependencies"
date: 2025-12-27 10:01:00 -0500
categories: [github-pages]
---

## Fail Forward

Last night Claude walked me through the setup of a git page. Everything seemed fine, the actions workflows all showed green checks, but the website gave a 404 error. Looking through the Annotations and run details, I noticed two warnings about and some yellow text:

<img src="/_posts/images/20251226Annotation-Warnings.png" alt="Annotations Failed to save" width=50% height=50%>
<img src="/_posts/images/20251226-Jekyll-yellow.png" alt="Deprecation You appear to have pagination turned on, but you haven't included the jekyll-paginate gem" width=50% height=50%> 

I was pretty tired and just guessed by throwing plugins: [jekyll-paginate] into _config.yaml. This broke the Jekyll build even worse.

<img src="/_posts/images/20251226-Jekyll-red.png" alt="Dependency Error Yikes! It looks like you don't have jekyll-paginate or one of its dependencies installed. In order to use Jekyll as currently configured, you'll need to install this gem. If you've run Jekyll with bundle exec, ensure that you have included the jekyll-paginate gem in your Gemfile as well. The full error message from Ruby is 'cannot load such file -- jekyll-paginate'" width=50% height=50%>

Instead of reverting it, I'm going to move forward with corrections and properly add the paginate plugin. I want to get comfy just fixing errors instead of nervously undoing until it "works" again. Claude showed the correct syntax for Gemfile and _config.yml which resolved the deprecation issue. 
	![correct syntax for Gemfile and _config.yml](/_posts/images/20251226Paginate-Syntax.png)
But I'm still getting a 404 error. Claude says I need an index.md now, and I'm realizing that using AI is not a replacement for RTFM.

The github-pages route doesn't seem to be documented that well, or at least not in the step-by-step tutorial manner that I need at my skill level. I discovered that Jekyll is often run locally and a little filesystem is set up for your webpage. You then just push this full webpage to git like normal. I guess this github action with Jeykll does this somewhere in the cloud, so all I do it upload .md files. I think if I had skimmed through their documentation first, I would have allowed Claude to direct me better.

This was a really productive process because it also gave me an opportunity to customize ~/.zshrc () and get quicker in git and the terminal in general. I never really got the hang of nano/vim so opening TextMate with `mate` has helped. Still haven't figures out why the `ctrl-x-e` command won't work.

The first blog post went live and I immediately realized I wanted a little more design and a categories/tags side column to file away future posts. Minima doesn't have this and I'm not about to start learning html/css right now. Claude recommended I use Chirpy or similar. 

This required renaming my local repo `...-backup` and deleting the github repo entirely. It feels like a a step backwards, and I was nervous doing so, but I'm trying to shake off the tendency to just keep things precariously balanced and instead just jump in with confidence that I can rebuild it. Every time will get faster and this repeat experience is just part of the process. Plus the Front Matter format is diffeernet so unless I want to write a script to convert 20-50 posts, now is the best time.


<img src="/_posts/images/2025-12-27-build-failures.png" alt="List of build failures fuck fuck fuck" width="50%" height="50%">

I can't do this right now, I'm just chasing my tail. Will knock out tomorrow morning.

....


Ok it's tomorrow. I just remembered that last time I had to configure and commit a jeykll.yml to the repo. Double checking with Claude: "nope not necessary"...

Double checking with Jekyll and Chirpy docs "CONFIGURE JEKYLL.YML"...
<img src="/_posts/images/2025-12-27-create-jekyllyml.png" alt="Create jekyll.yml" width=50% height=50%>
Yep, that solved the problem. Chirpy is live and looks great. There is still some issue with a local change I made to pages-deploy.yml, but apparently I don't have permission to push that change remotely. Looking through git docs now, but otherwise this was a successs. On to configuring Mikrotik!

# WIL

- Read documentation first. If you don't get it, at least skim before asking for help from a human or LLM. This will outline a general area to parse the advice you're given.
- |Termimal short cuts|keystroke|
  |-------------------|---------|
	|Delete text **before** cursor|`ctrl-u`|
	|Delete text **after** cursor|`ctrl-k`|
	|Click to place cursor|`ctrl-lmb`|  
- Markdown should be required in public school in place of cursive.
- AI is a best just a reference tool, not a troubleshooting tool.




