### PSR-12 Guidelines for Laravel Projects

PSR-12 extends and improves upon PSR-1 and PSR-2, setting coding style standards for PHP. Adhering to these standards ensures clean, readable, and maintainable code. Here's a basic guide to follow PSR-12 in all Laravel projects:

---

#### **1. Basic Coding Standards**

1. **PHP Tags**
   - Always use `<?php` for PHP code.
   - Avoid using short tags like `<?`.

2. **Character Encoding**
   - Use UTF-8 without a BOM for all PHP files.

3. **Line Endings**
   - Use Unix-style line endings (`LF`).

4. **Line Length**
   - Limit lines to 120 characters. If longer, consider breaking the code into multiple lines.

5. **Indentation**
   - Use **4 spaces** per indentation level. Avoid tabs.

---

#### **2. Namespace and Use Statements**

1. **Namespaces**
   - Declare namespaces on the first line after the `<?php` tag:
     ```php
     <?php

     namespace App\Http\Controllers;
     ```

2. **Use Statements**
   - Place all `use` statements after the namespace declaration.
   - Group related use statements together.
   - Use one `use` statement per class or function:
     ```php
     use Illuminate\Http\Request;
     use App\Models\User;
     ```

---

#### **3. Classes, Properties, and Methods**

1. **Class Declaration**
   - Begin with the `class` keyword followed by the class name in PascalCase:
     ```php
     class UserController extends Controller
     {
     }
     ```

2. **Properties**
   - Declare visibility for all properties: `public`, `protected`, or `private`.
     ```php
     private $name;
     protected $email;
     public $isActive;
     ```

3. **Methods**
   - Method names should be in camelCase.
   - Always declare visibility for methods.

4. **Brace Style**
   - Opening braces `{` go on the next line for classes, methods, and functions:
     ```php
     public function getUser()
     {
         return $this->user;
     }
     ```

5. **Abstract, Final, and Static**
   - Follow this order for method modifiers: `abstract`, `final`, `public/protected/private`, `static`.

---

#### **4. Control Structures**

1. **Keywords**
   - Use lowercase for control structure keywords like `if`, `else`, `for`, `while`, etc.

2. **Spacing**
   - Add a single space after control structure keywords and open the parenthesis in same line.
   - No space after the opening parenthesis or before the closing parenthesis:
     ```php
     if ($user->isActive) {
         return true;
     }
     ```

3. **Braces**
   - Always use braces `{}` even for single-line statements.

4. **Switch Statements**
   - Indent `case` statements with one level and the code within them with two levels:
     ```php
     switch ($status) {
         case 'active':
             return 'Active';
         default:
             return 'Inactive';
     }
     ```

---

#### **5. Formatting Rules**

1. **Blank Lines**
   - Add a blank line between class methods and after the `namespace` declaration.

2. **Trailing Commas**
   - Use trailing commas in multi-line arrays:
     ```php
     return [
         'name' => $name,
         'email' => $email,
     ];
     ```

3. **Visibility**
   - Declare visibility explicitly for class constants and methods.

4. **Type Declarations**
   - Use type hints and return types for methods:
     ```php
     public function getUser(int $id): User
     {
         return User::find($id);
     }
     ```

---

#### **6. Laravel Specific Practices**

1. **Controllers**
   - Use resource controllers for CRUD operations to follow RESTful conventions.

2. **Models**
   - Define relationships, casts, and scopes in models with clear spacing between sections.
   - Accessing database should be done in methods of a model.

3. **Routes**
   - Group routes logically, and use middleware for shared functionality.

4. **Blade Templates**
   - Indent nested sections for readability, and avoid inline PHP.

---

#### **7. Comments**

1. **Inline Comments**
   - Use `//` for single-line comments, placed above the line of code if lengthy.

2. **DocBlocks**
   - Use DocBlocks for class definitions, properties, and methods:
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

---

#### **8. Composer and Autoloading**

1. **PSR-4 Autoloading**
   - Follow PSR-4 autoloading standards for all classes.

2. **Dependencies**
   - Install and manage dependencies using Composer.

---


By following these PSR-12 guidelines, you can write Laravel code that is clean, consistent, and easier to maintain. Also, you can refer to **'Laravel Modules Package'** for writing efficient modular code. Happy coding! 🎉
