
# Refactoring Code with GitHub Copilot

## Overview

This exercise focuses on crafting effective prompts to generate high-quality code. Your goal is to refine the way you communicate with GitHub Copilot to produce clean, structured, and maintainable code. By iterating on your prompts, you'll learn how to guide GitHub Copilot to assist you in generating the desired results.

## Learning Objectives

By the end of this exercise, you should be able to:
1. **Craft Effective Prompts**: Formulate clear and concise prompts that guide the AI to generate high-quality, functional code.
2. **Iterate and Improve Prompts**: Refine your prompts through iteration to optimize the generated code’s structure and readability.
3. **Identify Prompt Impact**: Understand how different prompt variations impact the AI’s code output, including readability, maintainability, and adherence to coding best practices.
4. **Incorporate Best Practices**: Use prompts to encourage the AI to apply design patterns, naming conventions, and clean code principles.
5. **Troubleshoot Prompt-Generated Code**: Diagnose and correct issues in generated code by adjusting the prompt rather than manually editing the code.

## Prerequisites

This exercise uses the [Calculator app](https://github.com/bxtp4p/copilot-app-calculator) repository. Clone the repository and follow the instructions in the README to get started.

```bash
git clone https://github.com/bxtp4p/copilot-app-calculator.git
cd copilot-app-calculator
```
## Setup

Follow the setup instructions in the [Calculator app](https://github.com/bxtp4p/copilot-app-calculator) repository.

## Problem Statement

The `Calculator` class contains several [design issues]([url](https://refactoring.guru/refactoring/smells)) that make it difficult to read, maintain, and extend. These include:

- **God Object (Too Many Responsibilities)**:  
  The `Calculator` class is overloaded with unrelated tasks, such as basic arithmetic operations, file input/output, and circle area calculations, violating the Single Responsibility Principle (SRP).

- **Class Overload**:  
  The class has an excessive number of methods, even though individual methods are not lengthy. These methods should be distributed across separate classes or modules.

- **Duplicate Code**:  
  Repeated logic is used in multiple methods to update `self.result` and manage `self.history`, leading to redundancy.

- **Inconsistent Error Handling**:  
  The `divide` method handles division by zero with a print statement, unlike the return-based error handling used elsewhere in the class.

- **Inappropriate Access to Data**:  
  The `save_to_file` and `load_from_file` methods directly access and manipulate the `history` attribute, violating principles of encapsulation.

- **Responsibility Misalignment**:  
  The `save_to_file` and `load_from_file` methods are responsible for file operations, which should be delegated to a dedicated file handler class instead.

- **Primitive Obsession**:  
  The calculation history is stored as a simple list of strings, where a more meaningful data structure, such as a custom class or object, would better represent the history.

- **Long Parameter Lists**:  
  Methods like `add`, `subtract`, and `multiply` take multiple parameters, making them harder to read and increasing the likelihood of errors.

- **Hidden Dependency**:  
  The use of `math.pi` directly instead of defining a constant within the class or module introduces a hidden dependency, making the code less maintainable and testable.

## Task

Utilize effective AI prompt engineering to address the identified code smells in the `Calculator` class. Follow these steps:

1. **Select Code Smells**:
   - Review the list of code smells provided in the Problem Statement.
   - Choose one or more code smells you wish to address in the refactoring process.

2. **Craft Prompts**:
   - Write clear and specific prompts that instruct the AI to refactor the `Calculator` class to eliminate the selected code smells.
   - Ensure your prompts guide the AI to improve the code’s structure, readability, and maintainability without altering its core functionality.

3. **Generate Refactored Code**:
   - Use the crafted prompts with the AI tool to generate the refactored version of the `Calculator` class.
   - Review the generated code to ensure it effectively addresses the chosen code smells.

4. **Iterate and Refine**:
   - If the initial output does not fully resolve the code smells, refine your prompts for better results.
   - Repeat the generation process until the refactored code meets the desired quality standards.

5. **Document Changes**:
   - Provide a summary of the prompts you used and explain how each prompt contributed to resolving specific code smells.
   - Highlight the improvements made in the refactored `Calculator` class.

## Expected Outcome

Refactor the `Calculator` class to resolve one or more of the identified code smells. The refactored code should demonstrate improved readability, maintainability, and testability without altering its core functionality.

In addition:
- **Documentation**: Provide clear, concise documentation that explains the structure and purpose of the refactored code.
- **Unit Tests**: Implement comprehensive tests to validate the functionality of the refactored class, ensuring that future modifications can be made confidently.

The final result should be a cleaner, well-documented, and fully tested codebase that aligns with coding best practices.

## Tips

### Prompting Tips
- **Be Specific**: Clearly state which code smells you’re targeting in your prompts to guide the AI effectively.
- **Iterate and Refine**: Don’t expect perfect results on the first try—refine your prompts based on the AI’s output to improve the generated code.
- **Prioritize Clarity**: Ensure your prompts are clear and concise to reduce ambiguity in the code generation process.
- **Preserve Functionality**: While refactoring, ensure that the core functionality of the `Calculator` class remains intact.

### GitHub Copilot Best Practices
- **Manage Expectations**: GitHub Copilot won’t always produce flawless code. Use its suggestions as a starting point, and don’t hesitate to modify the code as necessary to meet your needs.
- **Ask for Help**: If you’re unsure about a concept or get stuck, ask GitHub Copilot Chat for assistance. It can act as an expert guide. For example, if you need clarification on a term like "Primitive Obsession," ask, *"What is Primitive Obsession?"* and it will provide a helpful explanation.
- **Use Copilot Chat Commands**: If you’re unsure how to use GitHub Copilot Chat, use the `/help` command to view a list of available commands for guidance.

### Example Solution
- An example of a refactored solution is available in the [`copilot-exercise-refactoring-completed`](https://github.com/bxtp4p/copilot-app-calculator/tree/copilot-exercise-refactoring-completed) branch of the [Calculator](https://github.com/bxtp4p/copilot-app-calculator) repository. Keep in mind, this is just one possible approach. Feel free to experiment with different refactoring strategies.
- If you're stuck, you can also refer to the [completed](https://github.com/bxtp4p/copilot-exercise-refactoring/tree/completed) branch, which includes the prompts used to generate the solution. You’ll find these prompts in the `/completed` directory.

---

This version is more concise and organized, making it easier to follow while still covering the essential tips.
