# Where was this branched from?

Have you ever wanted to have quick visibility to show where a specific branch was branched from? Maybe you're a git pro and you know some awesome command that spits out what you want? Maybe you just like looking at the logs and tracing it back? If you are one of those cool people, ignore this, just close this open tab and never come back.

Still here? Cool! So why would you want to quickly have textual visibility showing when a commit was made from and what the new branch? I can think of a few reasons why I want this. My main reason is because I hate having to pull up the log or history or looking up a command to figure out how to get what I want. Instead I just want to have an empty commit message that is created when a branch is created.

## What does it actually do?
Great question! This is a post-checkout hook for git that upon checking out a new branch named branch b from branch (git checkout -b branchb), it will write a commit message on the new branch saying: "Branching from brancha to branchb". That is it.

## Installation

### Create the hook
Create a file in your repositories .git/hooks directory named post-checkout

### Add the post-checkout code
In your new file, grab the contents from the source above in the post-checkout file

### Pro Tip
If you want to be cool and have this hook added to every new repository you create, run this:

```shell
git config --global init.templatedir '~/my/git-templates/git'
```

There are newer ways to do that command, but it works for most version of git...I think

In that new directory, add a hooks directory and add your post-checkout hook there. The I think you can add that new hook to old repos by running git init in the existing repo, but don't quote me on that, quote a search engine response.