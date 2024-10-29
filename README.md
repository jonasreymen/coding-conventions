Here's the **README** with the **Usage** section removed:

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
    "phpstan": "./vendor/bin/phpstan analyse --configuration phpstan.dist.neon",
    "phpstan-baseline": "@phpstan --generate-baseline",
    "phpcs": "./vendor/bin/phpcs --standard=PSR12 src/",
    "phpcbf": "./vendor/bin/phpcbf --standard=PSR12 src/"
}
```

### Explanation of Commands:
- **phpstan**: Runs PHPStan with a specified configuration file, `phpstan.dist.neon`.
- **phpstan-baseline**: Generates a baseline file to suppress known issues for future analysis runs.
- **phpcs**: Runs PHP CodeSniffer to check for adherence to the PSR-12 standard.
- **phpcbf**: Runs PHP Code Beautifier and Fixer (PHPCBF) to automatically correct coding standard violations.

With these commands in place, you can use Composer scripts to run them conveniently:

```bash
composer phpcs         # Checks code against PSR-12 standards
composer phpcbf        # Fixes PSR-12 coding standard violations
composer phpstan       # Runs static analysis with PHPStan
composer phpstan-baseline  # Generates a baseline file for PHPStan
```

---

## Author

- **jonasreymen**  
  [jonasreymen@outlook.com](mailto:jonasreymen@outlook.com)

---

## Acknowledgments

This package was inspired by industry best practices and aims to support developers in maintaining clean, readable, and efficient PHP code. Special thanks to the open-source PHP community and contributors to **PHPStan** and **PHP CodeSniffer**.

--- 