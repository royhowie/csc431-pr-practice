# How to submit a pull request

Pre-requisites:
  * Have [git installed][install-git] on your computer
  * Have a [github account][github-join]

Steps:
  1. Fork the this [pull-request practice][csc431-pr-practice] on github by
    clicking  on that link and clicking "Fork" at the top right of the page.
  2. Clone the repo to your computer.
    1. Open terminal. Navigate to the directory you want a copy of the
      repository in.
    2. `git clone git@github.com:YOUR_GITHUB_USERNAME/csc431-pr-practice.git`
    3. Do not forget to substitute your github username into the above command.
  3. `cd csc431-pr-practice`
  4. We need to tell git where the main repo and where your repo live.
    - Fortunately, git already knows where your copy lives on github, as you
      just cloned the fork. Your copy is called `origin`.
    - The main copy will be called `upstream`; this is a common name choice,
      meant to refer to how the main copy lives upstream of yours (metaphor?).
    - `git remote add upstream git@github.com:royhowie/csc431-pr-practice.git`
    - Note how the `upstream` repo reference points to my account, `royhowie`.
  5. Now we need to do some work. This is how you set up what you want to
    contribute to the `upstream` repo.
    1. First, make sure we're up to date.
    2. `git checkout master`. This tells git that you want to temporarily work
      on the  `master` branch (temporarily).
    3. Grab any new changes made upstream: `git pull upstream master`
    4. Push those changes downstream to `origin`: `git push origin master`
    5. Make a new branch. Branch names are pretty important. They should
      describe a common set of topics on which you're about to work.
    6. We'll call our new branch `learn-pr/YOUR_NAME` (your actual name please)
    7. To do this, run `git checkout -b learn-pr/YOUR_NAME`. `-b` stands for
      "new branch."
  6. Now you do your actual work.
    1. Create a file `your_name.txt` (actual name). Put something random in it.
    2. Run `git status`. You should see a list of "untracked files." One of them
      should be `your_name.txt`
    3. We want to add this file to our current commit.
    4. To do so, run `git add your_name.txt`
    5. Run `git status` again. You should see a new list: "changes to be
      committed."
    6. Make the commit: `git commit -m 'Practicing pull requests'`
    7. Push this commit to your repo: `git push -u origin learn-pr/YOUR_NAME`
  7. Navigate to github to your fork of the repo. There should be a green
    button at the top of the repo page: "compare and pull request." Click it.
  8. Create the pull request. I will get a notification.
  9. You're done. You've submitted a pull request.
  10. For our csc431 project, you'll start at step 5 after you've done steps 1-4
    for the first time. (We'll get into branch naming later.)

[csc431-pr-practice]: https://github.com/royhowie/csc431-pr-practice
[github-join]: https://github.com/join
[install-git]: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git
