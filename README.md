
# GitHub Copilot Prompt Engineering Exercise: Refactoring

This exercise focuses on refactoring. Refactor the applicationto improve its structure, readability, and maintainability.

## Instructions

This exercise uses the [Calculator app](https://github.com/bxtp4p/copilot-app-calculator) repository. Clone the repository and follow the instructions in the README to get started.

```bash
git clone https://github.com/bxtp4p/copilot-app-calculator.git
cd copilot-app-calculator
```

## Problem

The code in the `Calculator` class has a number of [code smells](https://refactoring.guru/refactoring/smells) that make it difficult to read and maintain:

- **Large Class/Too Many Responsibilities (God Object):**

  - The `Calculator` class handles many unrelated responsibilities: basic arithmetic, file I/O, and circle area calculation. It violates the Single Responsibility Principle (SRP).

- **Long Method:**

  - While individual methods are not very long, the class itself has too many methods, which can be split into different classes or modules.

- **Duplicated Code:**

  - Similar logic is repeated across methods for updating `self.result` and appending to `self.history`.

- **Inconsistent Error Handling:**

  - The `divide` method uses a print statement to handle division by zero, which is inconsistent with the return-based approach used elsewhere.

- **Inappropriate Intimacy:**

  - The `save_to_file` and `load_from_file` methods directly manipulate the history attribute, which should be encapsulated.

- **Feature Envy:**

  - The methods `save_to_file` and `load_from_file` demonstrate feature envy by directly handling file operations instead of delegating to a separate file handler class.

- **Primitive Obsession:**

  - The history is stored as a list of strings. A more appropriate data structure, such as a custom class or objects, could be used to represent calculation history more clearly.

- **Long Parameter List:**

  - Some methods take multiple parameters (`add`, `subtract`, `multiply`, etc.), making them harder to read and maintain.

- **Global Variable (Hidden Dependency):**

  - The use of `math.pi` directly instead of a constant defined in the class or module makes the code harder to test and maintain.

## Task

Each of the code smells identified provides an opportunity for refactoring. Choose one or more code smells to address and refactor the Calculator class accordingly.

## Expected Outcome

Refactor the Calculator class to address one or more of the identified code smells. The refactored code should be easier to read, maintain, and test.

Additionally, generate documentation and tests for the refactored code to ensure that it is well-documented and that future changes can be made with confidence.

## Tips

- Don't expect GitHub Copilot to produce perfect results, all of the time. It's a tool to help you write code, but it's up to you to decide what to do with its suggestions. Feel free to modify the code as you see fit.

- If you don't understand how to do something, or if you get stuck, don't hesitate to ask GitHub Copilot Chat for help. Think of it as a seasoned expert in the thing you're trying to do who can help guide you in the right direction. Don't be afraid to ask it questions! For example, if you don't know what Primitive Obsession is, you could ask, "What is Primitive Obsession?" and it will give you a brief explanation.

- If you don't remember how to do something with GitHub Copilot Chat, use the `/help` command to see a list of available commands.

- An example result of this exercise can be found in the [`copilot-exercise-refactoring-completed`](https://github.com/bxtp4p/copilot-app-calculator/tree/copilot-exercise-refactoring-completed) branch of the [Calculator](https://github.com/bxtp4p/copilot-app-calculator) repo. Note that this is just one possible solution, and there are many other ways to refactor the code. Feel free to experiment and try different approaches. If you're still stuck, you can refer to the [completed]() branch in this repo for the prompts used to generate the results. Prompts will be located in the `/completed` directory.
