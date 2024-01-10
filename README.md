# Abyss Coding Standard

## Installation

1. Install via composer
    ```bash
    composer require --dev abyss/coding-standard
    ```
2. Create the `phpcs.xml` file in root path of you repository
    ```xml
    <?xml version="1.0"?>
    <ruleset xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
             xsi:noNamespaceSchemaLocation="vendor/phpcsstandards/php_codesniffer/phpcs.xsd">
    
        <arg name="basepath" value="."/>
        <arg name="cache" value=".phpcs-cache"/>
        <arg name="colors"/>
        <arg name="extensions" value="php"/>
        <arg name="parallel" value="80"/>
    
        <!-- Show progress -->
        <arg value="sp"/>
    
        <!-- Paths to check -->
        <file>src</file>
        <file>test</file>
    
        <!-- Include all rules from the Abyss Coding Standard -->
        <rule ref="AbyssCodingStandard"/>
    </ruleset>
    ```
   
3. Add composer scripts into your `composer.json`:
    ```json lines
    "scripts": {
      "lint-check": "phpcs",
      "lint-fix": "phpcbf"
    }
    ```

## Usage

- To run checks only:

  ```bash
  composer lint-check
  ```

- To automatically fix many CS issues:

  ```bash
  composer lint-fix
  ```

## License

The coding-standard is open-sourced software licensed under the [MIT](LICENSE.md)
