## PULL REQUESTS

### Intro
Don't submit a pull request until you know what's inside of it and that it is clean/pristine (DONE) or otherwise communicated to the team that it is a work in progress.

A PR is an invitation for others to go into your PR and get an insight into your project.

### Each Pull Request has an ID and description
Each pull request that gets submitted should have a corresponding github issue attached in the description.

### Comments
When we have a pull request open, the goal is to share knowledge and encourage code review. When there are a LOT of comments made on a pull request, something is going on. It may mean that your PR is too big or you left a bunch of errors in the code or that it's an opportunity to discuss some higher level issues based on the feature you are building -- we want to avoid the first two, but should be encouraging the third.

### Code Ownership
Ownership of code. This code is a reflection of all of us who have worked on the project, because it speaks to the quality of the project and its underlying code. This is why we all need to review code with a critical eye during review of other PRs.

### Importance of File Changes
If there are a lot of files changed, that means that there is a lot of breadth. If there are a lot of new LOCs, then that generally means that there is a lot of depth. However, if there is only a small incremental change in LOCs and a lot of files changed, then there's a lot of breadth, but not a lot of depth. We want to aim for more depth when working on a feature. Aim for proportionality. The amount of code you submit should correspond to the complexity of the feature.

@adamjonas typically reviews a PR by going through the 'Files Changed' tab. This helps to get an understanding of what was done, and its corresponding scope, but you should do whatever works best for you.

### Outdated Diff Tab
If you see 'outdated diff', that probably means that an issue that was commented on was corrected. Assumption that one would make upon seeing that is that this issue is no longer an issue, and move on to the next issue.

### Opening a PR Early
If you're not quite comfortable with what you're doing, it's okay to put it out as an early PR in order to get feedback. Just be sure to communicate that somehow to your teammates with a comment or an appropriate github issue label.

### Launching to Server
  - Open a PR
  - Solicit feedback by asking for a PR with tags or on the slack channel
  - Be available to respond to comments and questions
  - Make revisions
  - Get a thumbs up from 2 people and at least one senior dev
  
  - Test on Staging
  - Before launching to production

### Being a Good Driver
  - Anticipation of what other people are going to do
  - Communication is the foundation of understanding a feature/project
  - Direction is important; ties into communication

### Takeaways
  - Have a mental checklist in place to review code before opening PR
  - Take ownership of your code, as well as your co-worker's code
  - Understand the differences between the state of master and your feature branch so you aren't surprised by bugs
