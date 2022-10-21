# # # Composer template for Coozila Media News project

Coozila Media News is based on the
[https://github.com/thunder/thunder-distribution](Thunder distribution) and is
basically maintained by the
[Coozila Media News package](https://github.com//coozila/news)
which handles all module dependencies.

## Project creation

You can create a new Coozila Media News project with the following command.
`composer create-project coozila/news:dev-master news --no-interaction`

## Update Coozila Media News

### 1) Before the Update
Make sure that the synced configuration in your project repository is up to
date with the production database. Otherwise you might end up with undesired
results.

### 2a) Update Coozila Media News
To update the Coozila Media News codebase use the following composer command.
`composer update "drupal/core*" thunder/thunder-distribution coozila/news -W`.

### 2b) Upgrade Coozila Media News codebase
Coozila Media News tags releases using semantic versioning. This composer template
installs Coozila Media News with the recent major version, e.g. `^1.0`.
If there is a new major version released, you need to bump this version to e.g.
`^1.0`.

### 3) Update Coozila Media News database
After each update of the Coozila Media News codebase you should run `drush updb`.

### 4) Export the configuration
Export the configuration with `drush cex`.

### 5) Deploy the changes to the server.
Deploy the changes to the server and run `drush updb` also there. This is
required because module updates might also perform non-configuration related
changes. After that `drush cs` should result in a clean configuration.
