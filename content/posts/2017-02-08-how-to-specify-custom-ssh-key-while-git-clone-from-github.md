---
author: rodush
categories:
  - Security
  - HowTo
tags:
  - Debian
  - GIT
  - MacOS
  - VCS
  - SSH
date: '2017-02-08T05:33:57+00:00'
hiddenInHomeList: "true"
title: How to specify custom ssh key while git clone from github
url: /2017/02/how-to-specify-custom-ssh-key-while-git-clone-from-github/
---
If you need to provide some custom ssh key while cloning your repository from github (or pulling, whatsoever), run this command:

```sh
ssh-agent $(eval `ssh-agent -s`; ssh-add ~/.ssh/{your-custom-keyfile}; git clone git@github.com:{username}/{repo-name}.git .)
```

Please note, you should replace `{strings}` with plain string values!
