<h1>
  <span class="headline">Budget Tracker Application Project</span>
  <span class="subhead">Project Requirements and Guidance</span>
</h1>

## Overview

**Objective**:

Develop a comprehensive budget tracking application to help a small business manage its finances across multiple accounts, categories, and time periods.

This project will deepen your Python skills and provide extensive practice with file handling, data analysis, and user interaction.

**Scope and Complexity**:

This is a terminal-based application, meaning users will interact with it entirely through the terminal. The project will involve creating a more sophisticated system that tracks finances in greater detail, provides analytical insights, and offers a flexible interface for different types of users. The project is estimated to take around **15 hours** to complete.

Users will navigate through the application using text-based menus and commands, making it essential to focus on creating a clear and user-friendly terminal interface.

**_You will work individually on this project_**.

> ❗️ As a reminder, General Assembly has a zero-plagiarism policy. **_Your project's code must be substantially yours_**. Do not copy code from similar projects or other sources. However, using code from the internet to accomplish generic tasks is okay - for example, a line of code that replaces a character at a specific position in a string.

A printable version of the project requirements can be found [here](./assets/project-requirements.pdf).

## Technical requirements

### Minimum requirements

> ✅ Any items marked incomplete in this section will result in the project receiving a failing grade.

Your Application must have the following functionality:

1. **Add a New Entry**: Users can add a new budget item (income or expense).
2. **Display Account Balance**: Calculate and display the net balance for selected accounts or categories.
3. **View All Entries**: Show all previous budget entries.
4. **Search Entries**: Search for specific entries by title, date, or category.
5. **Generate Reports**: Create financial reports based on custom parameters (ex: date range, category, account).
6. **Manage Accounts and Categories**: Add, edit, or delete accounts and categories.
7. **Exit**: Safely exit the application.

## Detailed Technical Requirements

### 1. Main Menu

When the application starts, it should display a menu with the following options. The user should be able to choose an option by typing the corresponding `number` or `command` and pressing <kbd>Enter</kbd>:

1. **Add a New Entry**: Users can add a new budget item (income or expense).
2. **Display Account Balance**: Calculate and display the net balance for selected accounts or categories.
3. **View All Entries**: Show all previous budget entries.
4. **Search Entries**: Search for specific entries by title, date, or category.
5. **Generate Reports**: Create financial reports based on custom parameters (ex: date range, category, account).
6. **Manage Accounts and Categories**: Add, edit, or delete accounts and categories.
7. **Exit**: Safely exit the application.

**Helpful Hints**:

- Use a loop to display the menu repeatedly until the user chooses to exit.
- Validate the user’s input to ensure they enter a valid option.
- Use functions to handle each menu option, making your code more modular and easier to maintain.

### 2. Add a New Entry

When the user chooses to add a new budget entry, the application should prompt them for the following details:

1. **Title**: A short description of the budget item (ex: "Office Supplies").
2. **Type**: Whether the item is an **Income** or an **Expense**. Ask the user to enter "I" for Income or "E" for Expense.
3. **Amount**: The monetary value of the item. Ensure that the input is a valid `number` (ex: no letters or special characters).
4. **Date**: The date of the transaction in `"MM-DD-YYYY"` format. Validate the date to ensure it's in the correct format.
5. **Category**: The category under which this entry falls (ex: "Office Supplies," "Salary"). Hint: Provide a list of existing categories for the user to choose from.
6. **Account**: The account to which this entry belongs (ex: "Business Account," "Personal Account"). Provide a list of existing accounts for the user to choose from.

Example:

```plaintext
  Title: Office Supplies
  Type: Expense
  Amount: 150
  Date: 12-01-2023
  Category: Office Supplies
  Account: Business Account
```

After gathering all the information, the application should:

- Append the new entry to the appropriate `.csv` file.
- Confirm to the user that the entry was successfully added.

**Helpful Hints**:

- Consider creating a function to validate user input (ex: checking if the amount is a valid number).
- Use Python’s `csv` module to open the `.csv` file in append mode and write the new entry as a new row.

### 3. Display Account Balance

When the user chooses to display the account balance, the application should:

- Ask the user if they want to view the balance for a specific account or for all accounts combined.
- If the user chooses a specific account, prompt them to select an account from the list of available accounts.
- Calculate the total income and total expenses by reading the relevant `.csv` file(s).
- Subtract the total expenses from the total income to display the net balance.

Example:

```plaintext
  Net Balance for Business Account: $450
```

**Helpful Hints**:

- Use a loop to read through the `.csv` file line by line and sum the amounts based on whether they are income or expense.
- If the user is viewing the balance for a specific account, filter the entries by account name before calculating the totals.

### 4. View All Entries

When the user chooses to view all entries, the application should:

- Ask if they want to view entries for a specific account, category, or date range, or if they want to view all entries.
- Read the relevant `.csv` file(s) and filter the entries based on the user’s selection.
- Display each entry in a clear and readable format, including the title, type, amount, date, category, and account.

Example:

```plaintext
  1. [12-01-2023] Office Supplies: -$150 (Expense) - Category: Office Supplies - Account: Business Account
  2. [12-02-2023] Client Payment: +$600 (Income) - Category: Revenue - Account: Business Account
```

**Helpful Hints**:

- Use Python’s `csv` module to read the file and filter the data based on the user’s criteria.
- Consider displaying entries in a table format using string formatting to ensure everything aligns properly.

### 5. Search Entries

The search functionality should allow the user to search for specific entries by:

- **Title**: Display all entries with titles that match the search term.
- **Date**: Display all entries from a specific date.
- **Category**: Display all entries within a certain category.
- **Account**: Display all entries within a specific account.

Example:

```plaintext
  Search Results for "Office Supplies":
  1. [12-01-2023] Office Supplies: -$150 (Expense) - Category: Office Supplies - Account: Business Account
```

The search results should be displayed in the same format as the "View All Entries" option.

**Helpful Hints**:

- Use `if` statements to check each entry against the search criteria.
- Consider allowing partial matches (ex: searching for "Office" should match "Office Supplies").

### 6. Generate Reports

The reporting feature should allow the user to generate and view detailed financial reports. The user can specify parameters for the report, such as:

- **Date Range**: Generate a report for a specific month, quarter, or year.
- **Category**: Generate a report for a specific category, showing total income and expenses.
- **Account**: Generate a report for a specific account, showing the overall performance.

Each report should include:

- Total income, total expenses, and net balance.

Example:

```plaintext
  Report for Business Account (December 2023):
  Total Income: $2000
  Total Expenses: $1500
  Net Balance: $500
```

**Helpful Hints**:

- Use the same logic as the "Display Account Balance" feature but include additional filtering based on the user’s inputs.

### 7. Manage Accounts and Categories

This feature allows the user to manage the accounts and categories used in their budget tracker. They should be able to:

- **Add a New Account or Category**: Prompt the user for a name and add it to the appropriate list.
- **Edit an Existing Account or Category**: Allow the user to rename an account or category.
- **Delete an Account or Category**: Remove an account or category from the list. Ensure that any entries associated with the deleted account or category are handled appropriately (ex: reassign them or warn the user).

Example:

```plaintext
  Added New Account: Personal Account
  Added New Category: Travel Expenses
```

**Helpful Hints**:

- Implement error handling to ensure that accounts and categories are not accidentally deleted.

## Code convention and UI/UX requirements

> ✅ More than three items marked incomplete in this section will result in the project receiving a failing grade.

- The code must be well-organized and modular, with functions handling specific tasks.
- The code should follow Python best practices and be well-documented with comments where necessary.
- The terminal interface must be user-friendly and intuitive, with clear prompts and instructions.
- The application must validate user input to ensure that it is correct and within expected parameters.
- Error messages should be clear and informative, guiding users to correct their input.

## README requirements

> ✅ More than two items marked incomplete in this section will result in the project receiving a failing grade.

- The app's name.
- A brief description of your app and its functionality.
- A _Getting started_ section. This section should include instructions on how to interact with your app.
- A _Technologies used_ section. This section should list the principal technologies used by your application, for example, Python and any major frameworks or libraries.
- If necessary, an _Attributions_ section. This section should include links to any external resources (such as libraries or assets) you used to develop your application that require attribution. You can exclude this section if it does not apply to your application.

## Evaluation

Your instructional team will evaluate your project after the project's due date. Your instructors will use the above guidelines to determine whether or not your project meets all of the minimum requirements.

If there is a specific section of code that you would like an instructor to provide additional feedback on, please ask!

## Guidance

### Getting started

Here are some quick tips to get your project started:

- Discuss your app idea with an instructor to get feedback before you dive too deep into planning.
- **_Keep it simple._** Minimum Viable Product (MVP) functionality that works well is better than extra functionality added to an app with bugs
- Prioritize and implement functionality step-by-step, one at a time. Develop features in a way that allows you to test as you go - try your best to follow the flow of data through your app.
- Regularly review the project requirements to ensure you're on track to pass the project. A printable version of the project requirements can be found [here](./assets/project-requirements.pdf).
- Add comments to your code where it makes sense to do so. Most code is self-documenting, and you shouldn't add comments explaining the obvious. Ideally, comments should explain the **_why_** of code where it's necessary.

### Project assistance

Your instructor team will provide guidelines for reaching out for help during the project.
