#Set Up Your Profile
</br>
####These are instructions for adding a Developer or Developer Apprentice to the Flatiron Labs website.
</br>
## Set Up Environment
#####The Website runs on Node so you will need to have Node installed on your computer.
</br>
Clone Repo:

```console
  git clone git@github.com:flatiron-labs/www_roots.git
```
Install Node:
```console
brew install node
```
Go into ww_roots Directory:

```console
  cd www_roots
```
Install dependencies:

```console
npm install
```
Create a Feature branch and Switch to that Branch
```console
git checkout -b John
```
Launch Server

```console
node app.js
```

## Create Your Profile
#####You'll need to have an image of yourself and one of your spirit animal to make a profile.
</br>
Add your two images to `public/images` folder

Once images have been added go to the `_team.jade` partial in the `views` folder

Once there copy a `.team_member` div and paste it before the very last div

```
    .team_member
      img.circle_headshot(src='images/adam.png')
       .member_text
         p.bio_headline
           a.headline_link(href="") Adam Jonas
           span - Developer Lead
            p.bio_text I enjoy tacos, dogs, and red sour patch kids.
            .icons
              a(href='https://github.com/adamjonas', target='_blank'): i.fa.fa                   -github-alt
              a(href='http://www.linkedin.com/in/ajonas/', target='_blank'): i.fa               .fa-linkedin
              a(href='https://twitter.com/adamcjonas'): i.fa.fa-twitter
```
  Edit div with your information

```
    .team_member
      img.circle_headshot(src='images/John.png')
        .member_text
          p.bio_headline
            a.headline_link(href="") John Doe
              span - Developer Lead
               p.bio_text This is where you would put your bio
               .icons
                 a(href='https://github.com/johndoe', target='_blank'): i.fa.fa                    -github-alt
                 a(href='http://www.linkedin.com/in/jdoe/', target='_blank'): i.fa                   .fa-linkedin
                 a(href='https://twitter.com/johndoe'): i.fa.fa-twitter
```
</br>
##Pushing Changes
##### You can add and commit your changes normally
</br>
But you'll need submit a pull request to the `develop` branch by running `git pull --rebase develop` and wait for your request to be accepted.

Congrats! You're done.



