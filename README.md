# An attempt to revert the group module patch 

https://www.drupal.org/node/2797793
Provides a patch that was installed on a site I support. 

We need to roll this back before we can upgrade the project to group 1.6.x or 2.x

## How to set up
`ddev start && ddev composer install`

Set up the site

`ddev drush site:install --account-name=admin --account-pass=admin -y`

Then install the group module and gnode module

`ddev drush en gnode -y`

`ddev drush uli`

Add a group type and enable at least one content type

Add a group and attach a content type to it. 

Comment out all the hooks in the module my_updater.install

run `ddev drush en my_updater`
