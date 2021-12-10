# Upgrade Drupal 8.9.19 to 9.x.x

  * Temporarily add write access to protected files and directories:
    
    ```bash
    $ chmod 777 web/sites/default
    $ chmod 666 web/sites/default/*settings.php
    $ chmod 666 web/sites/default/*services.yml  
    ```

  * Next, you'll need to pull in both the Drupal 9 version of core-recommended and dev-dependencies packages as dependencies. We use --no-update to avoid a chicken-and-egg problem with mutual dependencies:

    ```bash
    fin composer require 'drupal/core-recommended:^9' 'drupal/core-composer-scaffold:^9' 'drupal/core-project-message:^9' --update-with-dependencies --no-update
    ```

    * If need do this:
    
      ```bash
      fin composer remove drupal-composer/drupal-scaffold
      ```

  * Now, actually perform the update to the code itself:
  
  ```bash
  composer update
  ```
