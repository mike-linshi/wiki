# Flatiron Labs Wiki

## Pull Request Process
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

## BDD Testing Process
### RSpec Unit Testing
We implement unit tests via RSpec. Unit tests are used to test singular components in a codebase, such as a controller. There are several principles to follow when implementing unit tests.

Follow the single responsibility principle (SRP). As advocated by Sandi Metz, make sure that each test has a singular responsibility - simple is key in terms of readability and implementation. In conjunction with this principle, avoid 'before(:all)' statements whenever possible.

Follow the AAA pattern: Arrange, Act, and Assert. It's best to set up each test by arranging the data needed, then act upon that data by manipulating it to the test's specifications, and finally assert that the manipulated data should result in some specific result.

### Feature Testing via Cucumber
We implement feature tests using Cucumber. Feature tests are also known as integration tests. Integration tests are meant to test aggregated modules to ensure that users are interacting with features as expected.

Feature tests are written out via plain text stories, and once the feature steps are generated, we make the tests pass using succinct, clear Ruby code.

Each feature is described using three general statements: `As a <role>`, `I need to do <something>`, and `So that I may see <expected outcome>`. Each feature story describes the general feature in terms of who the user is (`As`), what the user should expect to see (`I`), and what the expected result is once the user finishes interacting with the login page(`So`). For example, when we write a feature story, we do so in the following format:

```ruby Cuke Story
Feature: Story
  As a User
  I need to be able to see the login page
  So that I can log in
```

The next step is to implement a `Scenario`. Each scenario is a defined user environment that specifies what the user is trying to do at that point, and what the user should expect to see once the user's actions have been implemented. Each scenario is effectively testing a small component of the overall feature to ensure the feature performs as expected.

There are three key statements that are used to define a scenario: `Given`,`When`, and `Then`. These also follow the AAA pattern mentioned in paragraph 3 of this section. A `Given` statement is where we arrange the data necessary to recreate the scenario. A `When` statement specifies a user interaction that allows us to act upon the arranged data. Finally, a `Then` statement asserts a result or outcome that should occur once the user action takes place.

```ruby Scenario
Scenario: Invalid User
  Given I am not logged in
  And I am an invalid User
  When I try to log in
  Then I should be given a Login Failure message
```

## Rails Migrations
When you are implementing a permanent action, such as creating a table, use the `change` method. A `change` method is pretty major.

When implementing a minor change, such as adding or removing a column from an existing table, use the `up`/`down` methods. `Up` and `Down` methods are minor in terms of scale.

## Application Launch Checklist

Once an application is near or has reached completion, then we proceed into the following launch checklist. This checklist ensures that there are vital components in place for a production environment.

- Is there a favicon?
- Are there proper meta-tags in place (think FB & Twitter)
- Bonus points, what happens if I drop the root domain into a FB share box?
- Have you included a Google Analytics code?
- Who needs access to this?
- Are there proper error pages?
- Have you included an exception tracker like Airbrake or Sentry?
- Have you upgraded the database to a Production Tier database?
- Is there a Pingdom monitor running?
- If your project is hosted on Heroku, is it running on Unicorn?
- If your project is hosted on Heroku, have you run the Heroku Production check?
- Do all your images have alt attributes?
- Do you have any console.logs still in your JS?
- Are there any debug or testing routes still accessible?
- Has all staging demo data been removed?
- Have DB column limits been set reasonably?
- Have you properly indexed your database?
- If your project is hosted on Heroku, have you enabled PGBackups add-on?
- Have you installed Cloudflare and set up caching rules?
- Have you properly run your application through Blitz.io?

## Style Guide
- 2 space code indentation (for readability)
- 1 line buffer between code blocks
- Append 'js' tag to HTML/CSS classes & ids for context
- Pivotal Card ID in branch and commit message
  - POSS EXAMPLE BRANCH: 123456789_new_feature
  - POSS EXAMPLE COMMIT: [123456789_new_feature] started new feature

## Book Club at Flatiron labs

### Pertinent Information
- Event Time: 12-1PM, Thursdays
- Location: Flatiron School, 11 Broadway (#260)

### To Do Before Book Club Meeting
- Read the assigned chapters!
- Take notes
- Bring in 3 thoughts/points of discussion to share with the group

### During Book Club Meeting
- Actively partake in the discussion
- Bring up key takeaways that resonated with you
- Bring up questions that you had during the reading, or ask for more clarification on a subject
- Discuss code examples

### Books Covered
- Principles of Object-Oriented Design (Sandi Metz)
- The Pragmatic Programmer (Dave Thomas, Andy Hunt)
