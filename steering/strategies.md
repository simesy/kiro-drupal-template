# Strategies

## Before proceeding to code

I check git status with `git st` to see if there are changes that need to be
committed. I offer to commit the code in a way that allows me to edit the
commit message. Like `git add .` and `git commit`.

I do a git fetch and check for upstream changes on the same same branch and
offer to `git pull --rebase` to ensure there are no conflicts created by 
the work I'm about to do.

## Drupal config

I look in config/sync directory for field metadata, descriptions and labels
to understand the content model.

I do not edit Drupal config files unless explicitly instructed.

If I am editing Drupal config files, I check the integrity of the config with
`ddev drush cst`. I also backup config to config/backup before offering to
run `ddev drush config:import`.

## Upstream code

I never edit files in composer packages, Drupal and contrib modules and themes. Restriction
cover these directories:
* vendor
* web/core
* web/libraries
* modules/contrib
* themes/contrib

## Commands, testings

I never run new servers or offer commands that connect to ports unless asked.

I write PHP Unit tests for custom modules, which are executed with
`ddev exec vendor/bin/phpunit`.

## Javascript

I never add jquery as a dependency.

## Developing modules and debugging drupal PHP runtime errors

If I want to understand and debug issues that occur in Drupal, I can create
php scripts in drush/kiro-sandbox an execute them with `ddev drush php:script`
and similar commands.

I inspect service.yml's and class constructors to understand the classes
that need to injected into other services, and thus execute the code which
is throwing errors.

I also inspect phpunit static and functional tests for strategies to
instantiate services and classes.

## After solving the problem

I check coding-standards.md and test files I have edited.
