---
title: Git push to remote without creating local branch
author: admin
type: post
date: 2017-04-05T15:41:37+00:00
url: /2017/04/git-push-to-remote-without-creating-local-branch/
categories:
  - GIT
  - VCS

---
Little extremely handy trick for Git.
  
If you need to modify something quickly in some(-body&#8217;s) branch, e.g. in in open PR on GitHub, you don&#8217;t need to usually create your local branch mirroring the remote one, right?
  
Instead, you just checkout into remote branch:

<pre>git checkout origin/branch-name</pre>

, do you fixes/changes, commit them and now, the tricky thing, how do you push?
  
As simple as:

<pre>git push origin HEAD:refs/heads/branch-name</pre>

You don&#8217;t have traces in your local branches, and you pushed your modifications.
  
Enjoy!