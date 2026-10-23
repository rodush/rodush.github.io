---
author: rodush
categories:
 - howto
tags:
  - GIT
  - VCS
date: '2017-04-05T15:41:37+00:00'
title: Git push to remote without creating local branch
url: /2017/04/git-push-to-remote-without-creating-local-branch/
---
Little extremely handy trick for Git.
  
If you need to modify something quickly in some(-body&#8217;s) branch, e.g. in in open PR on GitHub, you don&#8217;t need to usually create your local branch mirroring the remote one, right?
  
Instead, you just checkout into remote branch:

```sh
git checkout origin/branch-name
```

, do you fixes/changes, commit them and now, the tricky thing, how do you push?
  
As simple as:

```sh
git push origin HEAD:refs/heads/branch-name
```

You don't have traces in your local branches, and you pushed your modifications.
  
Enjoy!
