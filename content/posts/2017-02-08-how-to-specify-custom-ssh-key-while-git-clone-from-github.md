---
title: How to specify custom ssh key while git clone from github
author: admin
type: post
date: 2017-02-08T05:33:57+00:00
url: /2017/02/how-to-specify-custom-ssh-key-while-git-clone-from-github/
categories:
  - Debian
  - GIT
  - MacOS
  - Security
  - VCS

---
If you need to provide some custom ssh key while cloning your repository from github (or pulling, whatsoever), run this command:

``<br />
ssh-agent $(eval `ssh-agent -s`; ssh-add ~/.ssh/{your-custom-keyfile}; git clone git@github.com:{username}/{repo-name}.git .)<br />
`` 

Please note, you should replace \`{strings}\` with plain string values!