
---

# Coding Conventions

**Coding Conventions** is a PHP package created to elevate code quality, maintainability, and consistency within individual or team projects. Designed specifically for PHP developers, this package enforces standardized coding practices and provides tools to analyze, refactor, and enhance code based on industry best practices. With a focus on readability, reusability, and optimized performance, **Coding Conventions** integrates seamlessly into PHP development workflows, making it easier for developers to write cleaner, more maintainable code.

---

## Features

- **Enforces Coding Standards:** Uses PHPCS to ensure adherence to PHP coding standards.
- **Static Analysis:** Integrates with PHPStan, including strict rules, to catch potential issues early.
- **Customizable:** Allows configuration adjustments to match project-specific coding standards.

---

## Getting Started

### Prerequisites

Ensure you have the following:
- PHP >= 8.3
- Composer

### Installation

1. **Require the Package:**

   ```bash
   composer require --dev jonas-reymen/coding-conventions
   ```

---

## Configuration

To streamline usage, you can add the following commands to the `scripts` section of your `composer.json`:

```json
"scripts": {
    "phpstan": "./vendor/bin/phpstan analyse --configuration phpstan.neon",
    "phpstan-baseline": "@phpstan --generate-baseline",
    "phpcs": "./vendor/bin/phpcs --standard=phpcs.xml",
    "phpcbf": "./vendor/bin/phpcbf --standard=phpcs.xml"
}
```

### Using the Default PHPStan and PHPCS Configurations

#### PHPStan

To leverage the default configuration provided by **Coding Conventions**, include its `phpstan.dist.neon` file in your project:

1. Create a `phpstan.neon` file in your project’s root directory if it doesn’t exist.
2. Add the following line to include the configuration from **Coding Conventions**:

   ```yaml
   includes:
       - vendor/jonas-reymen/coding-conventions/phpstan.dist.neon
   ```

This inclusion lets you use the default PHPStan settings from **Coding Conventions** and easily extend or override them in your project’s `phpstan.neon`.

#### PHPCS

To use the provided `phpcs.dist.xml` configuration:

1. **Create a `phpcs.xml` file** in the root of your project.
2. **Include `phpcs.dist.xml`** from the package.

   Example `phpcs.xml`:

   ```xml
   <?xml version="1.0"?>
   <ruleset name="CustomPHPCSConfiguration">
       <!-- Include the default rules from phpcs.dist.xml in your package -->
       <rule ref="vendor/jonas-reymen/coding-conventions/phpcs.dist.xml"/>
   </ruleset>
   ```

   This configuration will apply the default rules from `phpcs.dist.xml` in your project.

### Explanation of Commands:
- **phpstan**: Runs PHPStan with the configuration file, `phpstan.neon`.
- **phpstan-baseline**: Generates a baseline file to suppress known issues for future analysis runs.
- **phpcs**: Runs PHP CodeSniffer to check for adherence to PSR-12 standard and custom rules in `phpcs.xml`.
- **phpcbf**: Runs PHP Code Beautifier and Fixer (PHPCBF) to automatically correct coding standard violations.

With these commands in place, you can use Composer scripts to run them conveniently:

```bash
composer phpcs         # Checks code against PSR-12 standards and custom rules
composer phpcbf        # Fixes coding standard violations
composer phpstan       # Runs static analysis with PHPStan
composer phpstan-baseline  # Generates a baseline file for PHPStan
```

---

## Author

- **jonasreymen**  
  [jonasreymen@outlook.com](mailto:jonasreymen@outlook.com)

---

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## Acknowledgments

This package was inspired by industry best practices and aims to support developers in maintaining clean, readable, and efficient PHP code. Special thanks to the open-source PHP community and contributors to **PHPStan** and **PHP CodeSniffer**.

---