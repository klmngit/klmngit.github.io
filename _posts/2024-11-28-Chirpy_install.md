---
title: GitHub Pages - the fast way !
date: 2024-11-28
categories: [WWW,GitHub]
tags: [blog,jekyll, chirpy,github,ci/cd]
---

# GitHub setup
1. Sign in to GitHub and navigate to the [starter](https://github.com/cotes2020/jekyll-theme-chirpy/fork), top left - press the green drop down button "Use this template" and ~~select "Create a new repository"~~ create new fork (I will try to add some comment and explanationm later). 
2. In the "Repository" field - enter your GitHub name and add "github.io" as the domain. For me it was "klmngit.github.com". 

> Please remember about the domain - otherwise the website will work locally, but won't be validated by the GitHub Actions HTML-proofer. Keep it as the public. 
{: .prompt-warning }

# Docker 
## 
1. Install [Docker Desktop](https://www.docker.com/products/docker-desktop/)
2. Install [Visual Studiio Code](https://code.visualstudio.com/)
3. Install [Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension for VSCode.
4. Clone your new repo into Docker container volume: in VSCode press F1 and run "Dev Containers: Clone Repository in Container Volume" command.

# Jekyll server
If Docker container is cloned correctly - run in this container VSCode terminal and start Jekyll serwer with:
```terminal
bundle exec jekyll s
```
New instance should be generated and webserver should be listening @ http://localhost:4000 - open your browser and check it !
Here you can see an example Terminal output from my server:
```terminal
vscode ➜ /workspaces/klmngit.github.io (main) $ bundle exec jekyll s
logger was loaded from the standard library, but will no longer be part of the default gems starting from Ruby 3.5.0.
You can add logger to your Gemfile or gemspec to silence this warning.
csv was loaded from the standard library, but will no longer be part of the default gems starting from Ruby 3.4.0.
You can add csv to your Gemfile or gemspec to silence this warning.
/usr/local/rvm/gems/default/gems/safe_yaml-1.0.5/lib/safe_yaml/load.rb:22: warning: base64 was loaded from the standard library, but will no longer be part of the default gems starting from Ruby 3.4.0.
You can add base64 to your Gemfile or gemspec to silence this warning.
Configuration file: /workspaces/klmngit.github.io/_config.yml
            Source: /workspaces/klmngit.github.io
       Destination: /workspaces/klmngit.github.io/_site
 Incremental build: disabled. Enable with --incremental
      Generating... 
                    done in 0.256 seconds.
 Auto-regeneration: enabled for '/workspaces/klmngit.github.io'
    Server address: http://127.0.0.1:4000/
  Server running... press ctrl-c to stop.
  ```

# Adjusting config
Edit _config.yml and make any necessary changes.

# Deploy using GitHub Actions
Open GitHub repository, go to "Settings", opne "Pages" and select "GitHub Actions" in "Source" dropdown menu. Make changes to the local repo and push it to GitHub. This will trigger "GitHub Actions" and run build and deploy workflow. 
