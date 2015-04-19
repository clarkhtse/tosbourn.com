---
layout: post
title: Git command to show files changed in a commit
categories:
- Development Help
tags:
- Git
---
Recently I wanted to pull a list of changed files from an older commit from the command line.

Turns out (like most things in Git) this is very easy to do.
    git show --name-only {commit}

You can replace {commit} with the SHA1 you want to retrieve, or things like
`HEAD` or `HEAD^^`

I made this post into a YouTube video

<iframe width="640" height="480" src="https://www.youtube.com/embed/gDZW-gT3YQk"
frameborder="0" allowfullscreen></iframe>
