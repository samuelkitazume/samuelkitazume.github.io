---
layout: post
title:  "What is good code?"
date:   2024-09-27 20:00:00 -0400
categories: code frontend
---

# Good code is not simple to define
Recently this has been in my head for just too too long. Am I the only one that feels like there are no consensus on this topic?
"Maintainable code is a readable code". Ok, define readable. Readable is subjective. My code is readable for me, yours isn't. Does that mean you code is bad? Not really.

Here's my breakdown of what makes a code readable

### Naming Conventions should be very descriptive

- *Meaningful Names*: Variables, functions, classes, and components should have names that clearly convey their purpose. Avoid vague or generic names like `data`, `temp`, or `handleClick`. Instead, use names that describe what the entity represents or does, such as `userProfile`, `fetchUserData`, or `onSubmitForm`.
- *Consistent Naming Patterns*: Stick to a naming convention throughout the codebase, such as camelCase for variables and functions (`userProfile`, `fetchUserData`), PascalCase for components and classes (`UserProfile`, `UserService`), and SCREAMING_SNAKE_CASE for constants (`MAX_RETRIES`).
- *Avoid Abbreviations and Acronyms*: While abbreviations might be shorter, they often make the code less clear. Use complete words unless the abbreviation is widely understood within the team (e.g., `API` or `ID`).

### Code Structure and Formatting

- *Consistent Indentation and Spacing*: Use consistent indentation (e.g., 2 or 4 spaces). Personally I prefer 2 spaces (never tabs!) and spacing to visually separate different blocks of code. Most modern editors can auto-format code according to the project's style guide. Leverage prettier and lint for this please!
- *Logical Grouping*: Group related code together. For example, place related functions, constants, and component states close to each other. This makes it easier to understand the flow and relationships within the code.
- *Limit Line Length*: This may seem weird for some but keep lines of code short, typically around 80–100 characters. This makes code easier to read without horizontal scrolling and encourages breaking down complex statements into simpler ones.

### EFFECTIVE Comments and Documentation
I used to think comments are a sign of poorly-made code. I was wrong, but here are some tips to do this effectively.

- *Explain Why, Not What*: Use comments to explain the purpose of the code or why a particular approach was taken, rather than what the code is doing (which should be evident from the code itself). For example:
```
// Retry three times because the API is flaky during peak hours.
```
- *Document Edge Cases and Complex Logic*: If a function handles specific edge cases or has complex logic that might not be immediately clear, document these cases with comments. This helps other developers understand the code's behavior in unusual scenarios. JSDocs can be extra helpful for these scenarios.
- *Avoid Redundant Comments*: Comments should add value! Avoid comments that simply restate what the code does. Example:
```
// Increment the counter above counter++;.
```

### Simplified and Modular Code
- *Small Functions and Components*: Keep functions and components small and focused on a [*single responsibility*](https://www.designgurus.io/answers/detail/solid-design-principles). This makes the code easier to understand, test, and reuse. If a function or component is getting too large, consider breaking it into smaller pieces.
- *Avoid Deep Nesting*: Deeply nested code, such as loops or conditionals, can be hard to follow. Refactor nested structures by extracting logic into separate functions or components. For example, instead of multiple nested if statements, use early returns or guard clauses to simplify the flow. Some [VSCode plugins](https://marketplace.visualstudio.com/items?itemName=kisstkondoros.vscode-codemetrics) can help out with this as well
- *Use Standard Patterns and Best Practices*: I almost wanted to avoid this but I guess it is worth mentioning. Follow established patterns and best practices for the language and framework you are using. For instance, use map instead of forEach when transforming arrays, and follow React's hook usage rules for consistent state management. Patterns and Best Practices are also kinda subjective so... take this with a grain of salt.

### Use of Consistent and Clear Syntax
- *Avoid Magic Numbers and Strings*: Instead of using raw numbers or strings in the code, define them as constants with meaningful names. Example:
```
const MAX_RETRY_COUNT = 3;
// or
const STATUS_SUCCESS = 'success';
```
This makes the code more readable and easier to update.
- *Leverage Language Features for Clarity*: Use language features that improve clarity, such as destructuring in JavaScript, spread/rest operators, and optional chaining. This is almost the same as the patterns and best practices bullet point. For example, instead of accessing deep object properties with multiple `.` operators, use destructuring. Example:
```
const { user: { name } } = response.data;.
```
- *Consistent Error Handling*: Implement a consistent error-handling strategy across the codebase. Use clear, descriptive error messages and, where applicable, custom error classes. This helps in quickly understanding and debugging issues.

---

### Final thoughts

Anyways, I hope these quick tips can help you understand better what you should consider when coding but the most important thing you should keep in mind:
good code is not written all at once. There are deadlines, there are constraints and so many decisions involved when coding a new feature, starting a new project and even refactoring legacy code. What you need to understand is, whenever you are touching your codebase, it may not be a good time to improve everything, but *it's always a good time to improve something* :)

Sam

