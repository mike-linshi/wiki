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

When we write a feature story, we do so in the following format:

```ruby Cuke Story
Feature: Story
  As a User
  I need to be able to see the login page
  So that I can log in```

Each feature is described using three words: As, I, and So. The feature story describes the general feature in terms of who the user is (`As`), what the user should expect to see (`I`), and what the expected result is once the user finishes interacting with the login page(`So`).

The next step is to implement a `Scenario`. Each scenario is a defined user environment that specifies what the user is trying to do at that point, and what the user should expect to see once the user's actions have been implemented. Each scenario is effectively testing a small component of the overall feature to ensure the feature performs as expected.

```ruby Scenario
Scenario: Invalid User
  Given I am not logged in
  And I am an invalid User
  When I try to log in
  Then I should be given a Login Failure message```

There are three key words that are used to define a scenario: `Given`,`When`, and `Then`. A `Given` statement states what is known about the user at that point in time. A `When` statement specifies a user interaction that takes place. Finally, a `Then` statement specifies the result that should occur once the user action takes place.

## Rails Migrations
When you are implementing a permanent action, such as creating a table, use the `change` method. A `change` method is pretty major.

When implementing a minor change, such as adding or removing a column from an existing table, use the `up`/`down` methods. `Up` and `Down` methods are minor in terms of scale.
