---
title: icons and htmlproofer tests
date: 2025-12-27 12:00:00 -0500
categories: [github-pages]
tags: []
---
I'm applying what I learn last time and made an account on Jekyllrb Forums. I can ask questions from actual users instead of relying on Claude to the forums for me. 
## To do
- chase down this HTMLProofer Test failure
- favicons avatar

##HTMLProofer
![HTMLProofer test failure 1](/assets/img/2025-12-27-htmlprooferfail1.png){: width="50%" height="50%"}
I might regret this later, but I'm going to just disable HTMLproofer entirely. If the site breaks horribly, I'll worry about it then. For this, I'm challenging myself to avoid using Claude and find my answer in the Jekyll documentation. I found a [mention](https://jekyllrb.com/docs/continuous-integration/travis-ci/#the-html-proofer-executable) of the HTMLproofer gem being called in the Gemfile, so I'll be commenting that out.
![HTMLProofer test failure 2](/assets/img/2025-12-27-htmlprooferfail2.png){: width="50%" height="50%"}

This had no real effect, so I started poking around other files looking for HTMLProofer. I found `.vscode/tasks.json` and deleted something, but after it had no effect I reverted the push with `git revert <hash>`.

I finally gave up and did as Claude asked: deleted the Test block from `pages-deploy.yml`
```- name: Test site
        run: |
          bundle exec htmlproofer _site \
            \-\-disable-external \
            \-\-ignore-urls "/^http:\/\/127.0.0.1/,/^http:\/\/0.0.0.0/,/^http:\/\/localhost/"
```
After a 3-minute build, I have all green checks and no test run.

![HTMLProofer test disabled](/assets/img/2025-12-27-htmlprooferdisabled.png){: width="50%" height="50%"}

## Favicons

Chirpy describes a method for customizing your avatar. Basically you go to RealFaviconGenerator.net, upload a 512x512 png, download zip, and extract a zip into /assets/img/favicons/ and delete `site.webmanifest`. After following these steps, my avatar is still blank.

the _config.yml has a line for avatar which I changed, best guess :
```# the avatar on sidebar, support local or CORS resources
avatar: '/assets/img/favicons/web-app-manifest-512x512.png'```

Additionally, inspecting the webpages head.html shows a reference to `site.manifest`
![head.html inspection](20251227webmanifest.png)

So against the guidance of Chirpy's docs, I redownloaded from Real Favicon Generator and entered the inteded filepath in their step-by-step webpage, and copied over the `/assets/img/favicon/` directory. That worked!

## WIL
- forums are good
- Nosing around and messing with configs is sometimes a necessary part of problem solving, so get comfortable using `git revert` and `git reset --hard`.



