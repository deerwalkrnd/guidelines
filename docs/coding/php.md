---
id: php
title: PHP
description: A guidelines for php.
slug: /coding/php
sidebar-position: 3
last_update:
  date: 2024-12-30
  author: Yashaswi Karkee
---

# PSR-12 Guidelines for PHP

PSR-12 builds upon PSR-1 and PSR-2, setting comprehensive coding standards for PHP. Following these guidelines ensures clean, readable, and maintainable code. Here’s a guide to implementing PSR-12 in PHP projects:

## 1. Basic Coding Standards:

### 1.1 PHP Tags
   * Always use `<?php` for PHP code.
   * Avoid short tags like `<?` as they can cause conflicts (e.g., issues with `<?xml` if not specified properly). Consistently using `<?php` prevents such problems.

### 1.2 Character Encoding
   * Use UTF-8 without a BOM for all PHP files.

### 1.3 Line Endings
   * Use Unix-style line endings (LF).

### 1.4 Line Length
   * Limit lines to 120 characters. If a line exceeds this length, consider breaking it into multiple lines.

### 1.5 Indentation
   * Use 4 spaces per indentation level. Tabs should be avoided.

### 1.6 Keywords
   * All keywords (e.g., `if`, `else`, `function`) must be in lowercase.

## 2. Namespace and Use Statements:

### 2.1 Namespaces
   * Declare namespaces immediately after the `<?php` tag:

   ```php
   <?php
   namespace App\Http\Controllers;
   ```

### 2.2 Use Statements
   * Place `use` statements after the namespace declaration.
   * Group related `use` statements together.
   * Use one `use` statement per class or function:

   ```php
    use Illuminate\Http\Request;
    use App\Models\User;
   ```

## 3. Classes, Properties, and Methods:

### 3.1 Class Declaration
   * Class names should follow PascalCase:

   ```php
    class UserController extends Controller
    {
    }
   ```

### 3.2 Properties
   * Always declare the visibility (`public`, `protected`, `private`) of properties:

   ```php
    private $name;
    protected $email;
    public $isActive;
   ```

### 3.3 Methods
   * Method names should follow camelCase.
   * Declare visibility (public, protected, private) for all methods.
   * Adhere to the Single Responsibility Principle: each method should perform only one specific task.

   ```php
    public function getUser()
    {
        return $this->user;
    }
   ```

### 3.4 Brace Style
   * Opening braces `{` should go on the next line for classes, methods, and functions:

   ```php
    public function getUser()
    {
        return $this->user;
    }
   ```

### 3.5 Abstract, Final, and Static
   * Follow this order for method modifiers: `abstract`, `final`, visibility (`public`/`protected`/`private`), `static`.

## 4. Control Structures:

### 4.1 Spacing
   * Add a single space after control structure keywords.
   * No space after the opening parenthesis or before the closing parenthesis:

   ```php
    if ($user->isActive) {
        return true;
    }
   ```

### 4.2 Braces
   * Always use braces `{}` even for single-line statements.

### 4.3 Switch Statements
   * Indent case statements with one level and the code within them with two levels:

   ```php
    switch ($status) {
        case 'active':
            return 'Active';
        default:
            return 'Inactive';
    }
   ```

## 5. Formatting Rules:

### 5.1 Blank Lines
   * Add a blank line between class methods and after the namespace declaration.

### 5.2 Trailing Commas
   * Use trailing commas in multi-line arrays:

   ```php
    return [
        'name' => $name,
        'email' => $email,
    ];
   ```

### 5.3 Visibility
   * Always explicitly declare visibility for class constants and methods.

### 5.4 Type Declarations
   * Use type hints and return types for methods:

   ```php
    public function getUser(int $id): User
    {
        return User::find($id);
    }
   ```

## 7. Comments:

### 7.1 Inline Comments
   * Use `//` for single-line comments, placed above the line of code if lengthy.

### 7.2 DocBlocks
   * Use DocBlocks for class definitions, properties, and methods:

   ```php
    /**
     * Get the user by ID.
     *
     * @param int $id
     * @return User
     */
    public function getUser(int $id): User
    {
        return User::find($id);
    }
   ```

## 8. Composer and Autoloading:

### 8.1 PSR-4 Autoloading
   * Follow PSR-4 autoloading standards for all classes.

### 8.2 Dependencies
   * Install and manage dependencies using Composer.
