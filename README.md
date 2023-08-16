# Installing DDEV
https://github.com/ddev/ddev
# Clone and locally install the Drupal site
- From the command line, navigate to the local directory where you want to clone
the project into then enter the command:

`git clone https://github.com/Xibalba9/drezal.git`
- The next step is to utilize DDEV to get the site up-and-running on your local machine. From the command line, run the following command:

`ddev config`

Prompts:
- `Project name: drazel`
- `Docroot location: web`
- `Application type: drupal10`


- From the command line, run the following command to create and run the containers for this project:

`ddev start`
- If this example utilized the standard method of not committing Composer dependencies to the Git repository, at this point the `composer install` command would need to be run. This could be done either by a version of Composer installed on the host operating system (Mac OS X, Windows 10 Pro, Linux) or by connecting to the DDEV web container using the `ddev ssh` command and using the version of Composer installed there.
- To set up the `settings.local.php` file, from the project root run:

`cp web/sites/example.settings.local.php web/sites/default/settings.local.php`
- Import the database provided with this project (in the repository's drazel/db_backup/ directory). This can be accomplished with the following command:

`ddev import-db --src=db_backup/aug-16-2023.sql.gz`
- Now that we have the complete codebase on our local environment with DDEV up-and-running, the database imported and connected to the codebase, the final step is to import our content files. The DDEV Demo repository includes a archive of the necessary content files, and they can be easily imported into the site with the import-files command:

`ddev import-files --src=files_backup/drazel_files.zip`
- `ddev launch`
