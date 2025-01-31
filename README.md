# IdeaCenter Automation Tests

This repository contains automated UI tests for the IdeaCenter web application, implemented using C#, NUnit, and Selenium WebDriver.

## Project Structure
The repository consists of two separate test implementations:
1. **No POM Approach** - Directly interacts with web elements inside the test methods.
2. **POM (Page Object Model) Approach** - Uses structured page classes for better maintainability.

### 1. No POM Approach
This implementation directly interacts with UI elements within the test methods. It is located in the `IdeaCenterNoPom` namespace.

#### Features:
- Uses `OpenQA.Selenium` for UI automation.
- Tests include:
  - Creating an idea with invalid data.
  - Creating an idea with random data.
  - Viewing the last created idea.
  - Editing the last created idea's title and description.
  - Deleting the last created idea.
- Login is handled in the `OneTimeSetup` method.
- The test order is managed using `[Order(n)]` attributes.

### 2. POM (Page Object Model) Approach
This implementation follows the Page Object Model for better maintainability and reusability. It consists of two main folders:

#### **Pages Folder:**
Contains page classes that encapsulate interactions with web elements.
- **BasePage.cs** - Common methods used across different pages.
- **CreateIdeaPage.cs** - Methods for interacting with the idea creation form.
- **IdeasEditPage.cs** - Methods for editing an idea.
- **IdeasReadPage.cs** - Methods for reading an idea's details.
- **LoginPage.cs** - Handles login functionality.
- **MyIdeasPage.cs** - Interactions with the user's ideas list.

#### **Tests Folder:**
Contains test classes utilizing the page objects.
- **BaseTest.cs** - Handles setup and teardown configurations.
- **IdeaCenterTests.cs** - Contains the test methods for various idea operations.

## Prerequisites
- .NET SDK (Latest version recommended)
- Chrome browser installed
- Chrome WebDriver matching the Chrome version
- NUnit and Selenium dependencies installed

## Installation & Setup
1. Clone this repository:
   ```sh
   git clone https://github.com/yourusername/IdeaCenterAutomation.git
   cd IdeaCenterAutomation
   ```
2. Restore dependencies:
   ```sh
   dotnet restore
   ```
3. Run tests:
   ```sh
   dotnet test
   ```

## Test Execution
- Tests can be executed using `dotnet test` or through the NUnit Test Explorer in Visual Studio.
- Browser actions are handled using Selenium WebDriver with ChromeDriver.
- Implicit and explicit waits are used to handle page interactions efficiently.

## Future Enhancements
- Extend test coverage for additional user scenarios.
- Implement parallel test execution for improved efficiency.
- Add reporting and logging for better test result insights.
