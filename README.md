# Flatiron Labs Wiki

## Pull Request Process
The Pull Request Process implies the use of `Pivotal Tracker` and `Git/Github`.

For each feature card that is listed on pivotal tracker and has been started, there should be a corresponding branch in the project repository.

When a card has been completed, then a Pull Request should be submitted. The Pull Request should correspond only to one card on Pivotal Tracker, and should be separate from any others that exist.

Once the code in the Pull Request has been properly reviewed by the code tester, and has also recieved a thumbs up from at least 2 co-developers, then that branch should be merged into the develop branch.

Once a branch has been merged, reach out to the QA point person to ensure a timely response.

##Repository Branching Structure
There are two primary branches that are utilized within a Flatiron Labs repo: `master` and `develop`. The rest of the branches, if there are any, should be considered feature branches.

Once a feature branch has been reviewed by Scott (testing), TJ (QA), and has been given two thumbs ups by 2 other Flatiron Labs developers, then it should be merged into the `develop` branch. Once the feature is considered stable and is well-integrated within the `develop` branch, then it should be merged into `master`.

## BDD Testing Process
### RSpec Unit Testing
We implement unit tests via RSpec. Unit tests are used to test singular components in a codebase, such as a controller. There are several principles to follow when implementing unit tests.

Follow the single responsibility principle (SRP). As advocated by Sandi Metz, make sure that each test has a singular responsibility - simple is key in terms of readability and implementation. In conjunction with this principle, avoid 'before(:all)' statements whenever possible.

Follow the AAA pattern: Arrange, Act, and Assert. It's best to set up each test by arranging the data needed, then act upon that data by manipulating it to the test's specifications, and finally assert that the manipulated data should result in some specific result.

### Feature Testing via Cucumber
We implement feature tests using Cucumber. Feature tests are also known as integration tests. Integration tests are meant to test aggregated modules to ensure that users are interacting with features as expected.

Feature tests are written out via plain text stories, and once the feature steps are generated, we make the tests pass using succinct, clear Ruby code.

Each feature is described using three general statements: As a <role>, I need to do <something>, and So that I may see <expected outcome>. Each feature story describes the general feature in terms of who the user is (`As`), what the user should expect to see (`I`), and what the expected result is once the user finishes interacting with the login page(`So`). For example, when we write a feature story, we do so in the following format:

```ruby Cuke Story
Feature: Story
  As a User
  I need to be able to see the login page
  So that I can log in```

The next step is to implement a `Scenario`. Each scenario is a defined user environment that specifies what the user is trying to do at that point, and what the user should expect to see once the user's actions have been implemented. Each scenario is effectively testing a small component of the overall feature to ensure the feature performs as expected.

There are three key statements that are used to define a scenario: `Given`,`When`, and `Then`. These also follow the AAA pattern mentioned in paragraph 3 of this section. A `Given` statement is where we arrange the data necessary to recreate the scenario. A `When` statement specifies a user interaction that allows us to act upon the arranged data. Finally, a `Then` statement asserts a result or outcome that should occur once the user action takes place.

```ruby Scenario
Scenario: Invalid User
  Given I am not logged in
  And I am an invalid User
  When I try to log in
  Then I should be given a Login Failure message```

## Rails Migrations
When you are implementing a permanent action, such as creating a table, use the `change` method. A `change` method is pretty major.

When implementing a minor change, such as adding or removing a column from an existing table, use the `up`/`down` methods. `Up` and `Down` methods are minor in terms of scale.

## Application Launch Checklist

Once an application is near or has reached completion, then we proceed into the following launch checklist. This checklist ensures that there are vital components in place for a production environment. 

- Is there a favicon?
- Are there proper meta-tags in place (think FB & Twitter)
- Bonus points, what happens if I drop the root domain into a FB share box?
Have you included a Google Analytics code?
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

##Style Guide
- 2 space code indentation (for readability)
- 1 line buffer between code blocks
- Append 'js' tag to HTML/CSS classes & ids for context
- Pivotal Card ID in branch and commit message
  - POSS EXAMPLE BRANCH: 123456789_new_feature
  - POSS EXAMPLE COMMIT: [123456789] started new feature
