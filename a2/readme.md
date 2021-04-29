

The Linux source codes that I've modified are in `283` branch.

https://github.com/Sean-Wu-TW/linux/tree/cmpe283-v5.10-rc1



















# How to fork your own repository on GitHub

 April 12, 2017

Forking someone’s repository on GitHub is very easy. You just click the **Fork** button on their repository page, and you will get your own personal copy of their repository in your GitHub account, simply clone it and you’re good to go.

However when you try to fork one of your **own** repositories then you will quickly discover this **doesn’t** work.

Clicking the Fork button on your own repository does nothing! (…other than a page refresh). For some reason, GitHub do not support creating forks from your own repository. However you can achieve something similar using **upstream remotes** in Git.

The steps are as follows:

## 1. Create a new repository for your fork

On GitHub, create your new (empty) repository https://github.com/new, using the default settings. This will be your forked repository.

## 2. Clone your fork

Make a local copy of your new forked repository using **git clone**.

```shell
$ git clone https://github.com/<username>/<forked-repo>.git
```

## 3. Add your original repository as an Upstream Remote

Add your original repository as an upstream remote in your forked repository. Doing this will allow you to pull in changes from your original repository to your forked repository.

```shell
$ cd <forked-repo>
$ git remote add upstream https://github.com/<username>/<original-repo>.git
```

## 4. Update your fork

Update your fork with all the changes from your original repository using **git pull**.

```shell
$ git pull upstream master
```

## 5. Push

When you are done, simply **push** your new fork back into GitHub.

```shell
$ git push origin master
```







