## PULL REQUESTS

### Intro
Don't submit a pull request until you know what's inside of it and that it is clean/pristine (DONE).

A PR is an invitation for others to go into your PR and get an insight into your project.

### Each Pull Request has an ID and description
Each pull request that gets submitted should have a corresponding Pivotal card ID attached in the description.

### Difference between Master and Feature branch
Master represents the pristine, unfettered source of code. A feature branch should represent the pristine, unfettered source of code for that feature. Therefore, a sub-feature branch should be the best version of what you can implement.

On big projects, typically you submit a pull request into a feature branch, particularly when you are working on a large feature. We call this a sub-feature.

### Comments
When we have a pull request open, the goal is to have as few/little comments as possible. When there are a LOT of comments made on a pull request, something is going on. This is an indicator that your pull request is not ready to be merged into the feature/master branch.

### Code Ownership
Ownership of code. This code is a reflection of all of us who have worked on the project, because it speaks to the quality of the project and its underlying code. This is why we need to be critical during review of other PRs.

### Importance of File Changes
If there are a lot of files changed, that means that there is a lot of breadth. If there are a lot of new LOCs, then that generally means that there is a lot of depth. However, if there is only a small incremental change in LOCs and a lot of files changed, then there's a lot of breadth, but not a lot of depth. We want to aim for more depth when working on a feature. Aim for proportionality -- for a level 2 card, there should be a correspondingly low level of commits; for a level 5 card, there should be a correspondingly high level of commits.

AJ typically reviews a PR by going through the 'Files Changed' tab. This helps to get an understanding of what was done, and its corresponding scope.

### Outdated Diff Tab
If you see 'outdated diff', that probably means that an issue that was commented on was corrected. Assumption that one would make upon seeing that is that this issue is no longer an issue, and move on to the next issue.

### Opening a PR Early
If you're not quite comfortable with what you're doing, it's okay to put it out as an early PR in order to get feedback.

### Launching to Server
  - Open a PR
  - Before giving a thumbs up
  - Before launching to staging
  - Before launching to production

### Gitx
  - Master is green
  - Remote branch is light blue
  - When 'Merge Pull Request' button is green, it's good to go
  - When 'Merge Pull Request' button is grey, you have issues (probably need to rebase master on top of your feature branch, or your feature branch on top of your sub-feature branch)
  - Easy to use the 'amend' feature

### Being a Good Driver
  - Anticipation of what other people are going to do
  - Communication is the foundation of understanding a feature/project
  - Direction is important; ties into communication

### Takeaways
  - Have a mental checklist in place to review code before opening PR
  - Take ownership of your code, as well as your co-worker's code
  - Understand the differences between master/feature branch protocols
