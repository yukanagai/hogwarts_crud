# Hogwarts CRUD Git Branch Exercise

## Greetings!

Obviously we all love the Harry Potter series, so a group of enterprising WDI students has opted to create a CRUD app to track the students of Hogwarts School of Witchcraft and Wizardy.

This exercise is a practice in merging files from other Git branches. We have a full fledged Rails app built across all branches. Your job is to merge them back together.

## Learning Objectives

- Practice pulling git branches from remote repositories
- Practice being a full fledged "merge master" with git branch commands

## Completion

Completion for this HW is part 9. There's no code here that's broken, just code you have to merge, and the occasional merge conflict that you will have to resolve. At the end of all of this you will have a working CRUD app for Hogwarts students.

## Setup - DONT RUN ANY RAILS CONFIG COMMANDS

FIRST: Fork this repository into your own Github account.

Then clone it to your machine, OUTSIDE of your `pluto` repo. This app is to be tracked separately from your work. Then view all of the branches on the origin remote. **DONT RUN ANY RAILS CONFIG COMMANDS YET(db:create, migrate, etc..).**

```bash
git clone your_fork_ssh.git
git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/andres_assets
  remotes/origin/chris_controllers
  remotes/origin/jaskars_gems
  remotes/origin/master
  remotes/origin/meijis_migrations
  remotes/origin/mohammed_models
  remotes/origin/riddels_routes
  remotes/origin/stephs_seeds
  remotes/origin/victorias_views
  remotes/origin/yeungs_yml
```

### __IMPORTANT__

For each part of the hw, we'll be creating a branch on our end to catch the changes made in the origin remote repo. DO NOT PULL THE BRANCH DIRECTLY INTO MASTER i.e `git pull origin jaskars_gems`. It merges the branches automatically, which is really really really bad form that will make senior devs want to shank you cold blooded. Instead, follow the directions for part 1 for each subsequent step.

# Part 1 - Jaskar's Gems

Jaskar has added the `pry-rails` gem to the Gemfile in his branch `jaskars_gems`.

Let's create a branch of the same name on our local repository so we can catch his changes.

`git checkout -b jaskars_gems`

If you `git branch -a`, you'll see `jaskars_gems` is now green, and local to our machine. We can now inspect its changes.

Go back to master branch: `git checkout master`

Check the diff in code: `git diff jaskars_gems`

This lets you quickly check the altered code in the target branch when compared to the branch you're currently in (master).

Seeing that this is just a single line in the Gemfile, merge Jaskar's wise gem choice into master.

`git merge jaskars_gems`

Provided everything went well, you can add, commit, and push to origin.

# Part 2 - Meiji's Migrations

Meiji went through the trouble of writing several migration files to create the House & Student tables.
Repeat the process in Part 1 for Meiji's wonderful database migrations.

# Part 3 - Steph's Seeds.rb

Steph wrote a cool Ruby script that hit a Harry Potter wiki and scraped all of the character names, houses, and image urls. This has been used to build your `seeds.rb` in Steph's branch. Create your own local version of `stephs_seeds` and merge it into master.

## Hark a MERGE conflict

You might have noticed that you get a merge conflict message after merging `stephs_seeds` into `master`. Read the message and go to the file in question. Git is really good about this and has preserved both versions of the code. One section is code from HEAD in the master branch, the other is the code from Steph's branch. If Steph's code make sense over the HEAD branch, simply erase all of the lines with arrow/equals markings.

```
<<<<<<< HEAD
# code in master
=======
# stephs code - keep this
>>>>>>> stephs_seeds
```

Add/Commit/Push the triumphant code.

# Part 4 - Yeung's YML

Oh no, we forgot to set the database to Postgresql!!

Not to worry, Calvin Yeung has branched the code and pushed up a revised `database.yml` file that fixes this.

Merge his changes in `yeungs_yml` into `master` by following the same steps as previous.

# Part 5 - Chris' Controllers

While you were getting confused with the database files, Chris was calmly vaping away and wrote the controllers for our app! Merge the code from `chris_controllers` into master while we debate which VG/PG ratio generates the sickest clouds.

# Part 6 - Mohammed's Models

Mohammed in the meantime wrote the ActiveRecord Models needed to make this app work, and promptly went back to planning his badass wedding in Cairo. Merge is code from `mohammed_models`

# Part 7 - Victoria's Views

Victoria decided we needed some basic views for our site, and has whipped them up in `victorias_views`

# Part 8 - Riddel's Routes

Harrison Riddeled up some routes for our site, using some nice rails helpers. Merge the code in from `riddels_routes`.

# Part 9 - Andres' Assets

Finally, we need some styling in our app, which Andres has graciously provided in `andres_assets`. Merge the code in and we're good to go!

# Bonus

# Part 10 - Rack it All Up

Now that we're all set up, lets try running our app!

```
bundle install
rake db:create
rake db:migrate
rake db:seed

rails s
```

Doesn't all work? Sort through the errors in your code! Perhaps one of your merges was done incorrectly, or it's just plain old Ruby errors. If it continues to break google/stack overflow it!

# Part 11 - Heroku it up!

Some of you are perhaps rusty with Heroku, get this app online to show your buddies!

# Part 12 - Fun

Add yourselves to the app. Put yourself in a house of your choosing.
