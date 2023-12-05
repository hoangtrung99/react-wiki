<!-- You can view the Markdown formatting at https://github.com/hoangtrung99/wiki/blob/master/coding-rules-and-guidelines.md
 -->

# Coding rules and guidelines

## Purpose of Having Coding Standards

- A coding standard gives a uniform appearance to the codes written by different engineers.
- It improves readability, and maintainability of the code and it reduces complexity also.
- It helps in code reuse and helps to detect error easily.
- It promotes sound programming practices and increases efficiency of the programmers.

### Table of contents

1. [Naming Conventions](#naming-conventions)
2. [Formatting and Linting](#formatting-and-linting)
3. [Comments and Documentation](#comments-and-documentation)
4. [Modularity and Reusability](#modularity-and-reusability)
5. [Error Handling](#error-handling)
6. [Code Readability](#code-readability)
7. [Coding Style](#codeing-style)
8. [Commit linting](#commit-lint)

### Naming Conventions

- Use English language when naming your variables and functions.
- Use meaningful names for variables and functions.
- Use camelCase when naming variables and functions.
- Use PascalCase when naming classes and type or interface in Typescript.
- Use UPPER_CASE when naming constants.
- Use snake_case when naming files and folders and property of object.
- Use kebab-case when naming route.
- Use prefix `is` or `has` or `should` when naming boolean variable.
- Use prefix `get` when naming function return value.
- Use prefix `set` when naming function set value.
- Use prefix `handle` when naming function handle event.
- Not to use a single character variable or function names such as a, b, c, etc. Use a relevant name according to your variable and function operations.
- Not to use reserved keywords as variable names.
- **S-I-D**
  - Short. A name must not take long to type and, therefore, remember;
  - Intuitive. A name must read naturally, as close to the common speech as possible;
  - Descriptive. A name must reflect what it does/possesses in the most efficient way.
- **Avoid contractions**. Do not use contractions. They contribute to nothing but decreased readability of the code. Finding a short, descriptive name may be hard, but contraction is not an excuse for not doing so.
- Avoid context duplication

**Please see more : [Naming cheatsheet](https://github.com/kettanaito/naming-cheatsheet)**

See the below code snippet:

```js
/* Bad */
const page_count = 5;
const shouldUpdate = true;

/* Good */
const pageCount = 5;
const shouldUpdate = true;
---------------------------------------
/* Bad */
const onItmClk = () => {}

/* Good */
const onItemClick = () => {}
---------------------------------------
/* Bad */
const a = 5 // "a" could mean anything
const isPaginatable = a > 10 // "Paginatable" sounds extremely unnatural
const shouldPaginatize = a > 10 // Made up verbs are so much fun!

/* Good */
const postCount = 5
const hasPagination = postCount > 10
const shouldPaginate = postCount > 10 // alternatively
```

### Formatting and Linting

Formatting the code will improve the readability and organization of the code. Using consistent tabs or spaces in code increases the readability of code.

Formatting the code includes formatting the line breaks, code snippets, and other things. Use some code formatting tools for that.

Currently, projects from modern frameworks all use tools for formatting and linting. If not available, we can consider using the following tools for the project.

- For Typescript and Javascript: [ESLint](https://eslint.org/), [Prettier](https://prettier.io/)
- For PHP, Laravel: [Laravel Pint](https://laravel.com/docs/10.x/pint), [PHP CS Fixer](https://github.com/PHP-CS-Fixer/PHP-CS-Fixer)

### Comments and Documentation

Commenting on your code is another way of making the code readable. This can be from your perspective or other developers'. You can explain the uses of function, TODO, FIXME, bug explanation, Algorithm steps, and others.

- Code without comments is not optimized enough.
- Code with too many comments is a sign of bad code.
- Comments should explain why instead of what, it can explain why if it's a bit complicated.
- Write your comments as such others can easily understand. It should be able to explain the purpose, functionality, or intent of the code.
- Put comments as such it provides context. You should If you're referring to something specific, provide enough context for others to understand your comment. You should write a comment before the code. In-line comments should be used for small comments.
- Follow a consistent commenting style as per the programming language. There are various ways of commenting but choose one and stick with that for readability purposes.
- Be concise with your comments. Long and overly explained comments can become difficult to read.
  Don’t write comments for each line. As it will overshadow the important comments and also make the code full of comments.
- Self-explanatory steps and usually things should be exempt from commenting.

Tools such as [Better Comments](https://marketplace.visualstudio.com/items?itemName=aaron-bond.better-comments) can help you in writing finer comments. [Mintlify](https://mintlify.com/) can help you in generating comments and documentation for your project.
[TODO Tree](https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree) Helps you manage TODO, FIXME... labels in projects.

### Modularity and Reusability

The meaning of modularity is to break down the long program into smaller modules or pieces of code snippets. Convert your code into separate functions or classes for a particular operation. That will make your code clean and efficient.

Reusability means using the same code repeatedly or multiple times. This can save you a lot of time and effort. For example, write a function for addition once, and use it in a calculator application, doing mathematical operations, logic operations, and other locations in your code, etc.

A mandatory piece of code must not be repeated more than twice. If it is repeated more than twice, then it should be converted into a function or class.

### Error Handling

- The message displayed to the user when encountering an error must be a clear message.
- Any error messages from the server must be processed so that the user can understand.
- Any error cases should be recorded in logs or notified to the development team if possible (can use webhook through slack, use sentry, ...)
- Make sure that your code is always able to handle errors. For instance, while requesting an API. Your code should cover both scenarios that is success and failure. As per the response, create a log for developers and notify the user about the unsuccessful request. This is one such way of making your code error-proof.
- The API side must agree on an error return format for the client side to easily handle.

### Code Readability

Write the code which is easy to read and understand. Use comments, format the code, and remove unnecessary things like extra tabs or spaces, extra lines, etc to make your code more readable and understandable for other developers in the team.

Using functions or classes as much as possible, reusing your code, and making complex logic simple can enhance the code's readability.

### Coding Style

- Code should be easily understandable. The complex code makes maintenance and debugging difficult and expensive.
- Each variable should be given a descriptive and meaningful name indicating the reason behind using it. This is not possible if an identifier is used for multiple purposes and thus it can lead to confusion to the reader. Moreover, it leads to more difficulty during future enhancements.
- Length of functions should not be very large. It should be broken down into smaller functions. This makes the code more readable and understandable.
- Use the following coding style:
  - [Javascript - Airbnb](https://github.com/airbnb/javascript)
  - [react-philosophies](https://github.com/mithi/react-philosophies)
  - [Clean code javascript](https://github.com/ryanmcdermott/clean-code-javascript#table-of-contents)
  - [PHP - PSR-12](https://www.php-fig.org/psr/psr-12/)

### Commit lint

- Use rules of [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0-beta.2/#specification)
- Version format: `MAJOR.MINOR.PATCH` [SemVer](https://semver.org/)
