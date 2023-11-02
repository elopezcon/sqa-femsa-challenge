# **SQA FEMSA Challenge**
## **Table of Contents**
- [Introduction](#introduction)
- [Goals](#goals)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [Frontend Project](#frontend-project)
  - [Frontend Automation Tasks](#fronted-automation-tasks)
- [Backend Project](#backend-project)
  - [Backend Automation Tasks](#backend-automation-tasks)
- [Mobile Project](#mobile-project)
  - [Mobile Automation Tasks](#mobile-automation-tasks)
- [References](#references)
- [FAQ](#faq)

## **Introduction**
This repository is meant to be used as a checklist for the candidates for FEMSA project in order to gain knowledge and have a standard structure across all the projects.

## **Goals**
- Implement a design pattern and structured folders for frontend automation.
  - Page Object Model.
- Use different levels of documentation.
  - Comments inside code.
- Use best practices for element selectors.
  - Avoid absolute selectors.
  - Unique selectors.
  - Use different selectors supported.
- Coding best practices.
  - Code Abstraction.
  - Naming conventions for method, classes and tests.
  - Avoid hardcoded data.
  - Avoid magic numbers.
  - Descriptive name for test scripts.
  - Avoid explicit waits. (if possible).
  - Hooks.
- Best practiced for Assertions.
  - Single assertion per test.
  - Avoid assertions on the page objects.
- Proper Data management
  - Usage of data providers
  - Usage of .env/config files (when possible) for sensible data.
- Implement Backend Automation.
- Implement Mobile Automation.

## **Tech Stack**
Tools:
- [VSCode](https://code.visualstudio.com/)
- [Homebrew](https://brew.sh/)
- [Node](https://nodejs.org/en/)
- [Appium Doctor](https://www.npmjs.com/package/appium-doctor) (Mobile Only)
- [Appium](https://appium.io/) (Mobile Only)
    - [Appium Server](https://github.com/appium/appium-desktop/releases)
    - [Appium Inspector](https://github.com/appium/appium-inspector/releases)
- [Xcode](https://developer.apple.com/xcode/) (Mobile Only)
- [Android Studio](https://developer.android.com/studio) (Mobile Only)

Frameworks:

- [Cypress](https://www.cypress.io/)
- [CodeceptJS](https://codecept.io/basics/#architecture)


## **Getting Started**
* As a starter point it is recommended to install [Homebrew](https://brew.sh/) to help you with the tool installation process.
* Also, we require to download and install [node](https://nodejs.org/en/download/).

    To see if Node is installed, type in `node -v` Terminal.

    To see if NPM is installed, type in `npm -v` Terminal.

*  You need to create a env file the .zshrc file (in case there is no .zshrc file refer to [FAQ](#faq) section.):

    ```bash
    open -e ~/.zshrc
    ```

## **Frontend Project**
1. Initialize a new npm project and install all required dependencies for Cypress, use the [references](#references) section.
2. Navigate to [Todoist](https://todoist.com/) and create an account, get familiar with the site since we are using it for the whole challenge.
3. Implement your code using Page Object Model structure for [Cypress](https://www.cypress.io/blog/2019/01/03/stop-using-page-objects-and-start-using-app-actions).

### Fronted Automation Tasks:
- Successful login.
  - Define a test case that performs a successful login, using credentials stored preferably in a .env file
- Unsuccessful login. 
  - Define multiple negative scenarios for login.
- Create a new task. 
  - Create a new task and validate it was created correctly.
- Create 10 new tasks. 
  - Create 10 new tasks and validate they were created correctly.

> Note: If you have any doubt or questions remember you to ask your Mentor or ask on the QA community in the [#qa-cypress](https://join.slack.com/share/enQtNjEzMzc3MjM5NTQxMy00MWY3YjEyYjhlOTQwMmM0ODFmNWZlMzdkYzg3ZTRjN2IzM2FmYzE1NjU3MDM0YWJjYTMyYjQ5NDY2Nzc0OGNm) channel in Slack.

## **Backend project**
1. Initialize a new npm project and install all required dependencies for Cypress, use the [references](#references) section.
2. Navigate to [Todoist API](https://developer.todoist.com/rest/v2).
3. Implement your code using the structure for [Cypress](https://learn.cypress.io/advanced-cypress-concepts/integration-and-api-tests).

### Backend Automation Tasks:
1. Get your authorization token and save it as an environment variable.
2. Create a new folder inside your collection for projects and another one for tasks. 
3. Create the following endpoints and its corresponding Tests: status codes, content, json schema,response time, etc.    
  a) Projects:
    * Get all projects
    * Create a new project
    * Get a project
    * Update a project
    * Delete a project

    b) Tasks:  
   * Get active tasks  
   * Create a new task  
   * Get an active task  
   * Update a task    
   * Delete a task
4. Create Negative scenarios for each endpoint.

  > Note: If you have any doubt or questions remember you to ask your Mentor or ask on the QA community in the [#qa-cypress](https://join.slack.com/share/enQtNjEzMzc3MjM5NTQxMy00MWY3YjEyYjhlOTQwMmM0ODFmNWZlMzdkYzg3ZTRjN2IzM2FmYzE1NjU3MDM0YWJjYTMyYjQ5NDY2Nzc0OGNm) channel in Slack.

## Mobile Set Up 

> Note: This set up is only required if a Mobile Automation challenge is going to be implemented, if only Web or API are presented please skip this section.

* Install [appium-doctor](https://www.npmjs.com/package/appium-doctor) to check the required preconditions for appium to run successfully.
```bash
npm install -g appium-doctor
```
> Once installed executed `appium-doctor --ios` for iOS and `appium-doctor --android` to check the status of your mobile set up and find the missing tools required.


## iOS Setup
1. Download and install [XCode](https://developer.apple.com/xcode/) from Mac AppStore or Web.
2. Install required simulators:
    Launch Xcode and select **Xcode > Preferences > Components** to install the simulators that you might want to test against.

## Android Setup

1. Download and install [JAVA](https://www.oracle.com/java/technologies/downloads/) JDK.
2. Set up the JAVA_HOME path:

   *  You need to add a JAVA_HOME to the PATH variable inside the .zshrc file (in case there is no .zshrc file refer to [FAQ](#faq) section.):

    ```bash
    open -e ~/.zshrc
    ```

    * In a text editor, add the variable:
    
    ```
    export JAVA_HOME=$(/usr/libexec/java_home)
    export PATH=$JAVA_HOME/bin:$PATH
    ```

    * Save and close the file.

    * Apply the changes:

    ```bash
    source ~/.zshrc
    ```

    * Verify that you have Java installed on your local machine:

    ```bash
    java -version
    ```
3. Install the Android SDK and Platform Tools

    * Go to [Android Studio Download Link](https://developer.android.com/studio?pkg=studio) to download the latest version.
    * Launch the Android Studio DMG file and follow the Setup Wizard instructions through the rest of the setup, which includes downloading Android SDK components that are required for the development.

2. Add the ANDROID_HOME path to your PATH variable inside the .zshrc file:

```bash
open -e ~/.zshrc
```

3. In a text editor, add the following variables:

```bash
export ANDROID_HOME=/Users/<your.user>/Library/Android/sdk

export PATH=$PATH:$ANDROID_HOME/tools

export PATH=$PATH:$ANDROID_HOME/tools/bin

export PATH=$PATH:$ANDROID_HOME/platform-tools
```

4. Save and close the file.

5. Apply the changes:

```bash
source ~/.zshrc
```
> Note: Configure your terminal to increase your productivity. You can use the following post as a [suggestion](https://ivanaugustobd.medium.com/your-terminal-can-be-much-much-more-productive-5256424658e8).

## **Mobile project**
1. Perform a [Mobile Set up](#mobile-set-up) for Android or iOS (Only one is necessary).
2. Initialize a new npm project and install all required dependencies for [CodeceptJS](https://codecept.io/basics/#architecture).
3. Download the test app .apk for Android and .zip for iOS simulator from [My Demo App](https://github.com/saucelabs/my-demo-app-rn/releases) repository.
4. Implement your code using the structure for [CodeceptJS](https://codecept.io/pageobjects/#dependency-injection).

### Mobile Automation Tasks:
- Successful login.
  - Define a test case that performs a successful login, using credentials stored preferably in a .env file
- Unsuccessful login. 
  - Define multiple negative scenarios for login.
- Log out. 
  - Successfully log out.
- Cart. 
  - Add 1 item to the shopping cart anv validate it was added.

  > Note: If you have any doubt or questions remember you to ask your Mentor or ask on the QA community in the [#qa-mobile-experts](https://join.slack.com/share/enQtNjEzNjk4Nzg0NTA3NS1iZTFmOWE5NWZhZTgyODAxYmY1OWI1NGI0NjdkNTNkMDliZmM3MmZhNmI3Y2NhMWU5YmM3YzE4OGIzODZiODlh) channel in Slack.


## **References**

### Frameworks
Frontend Web and API Javascript based frameworks:
* [Cypress](https://www.cypress.io/)

Frontend Mobile Javascript based frameworks:
* [CodeceptJS](https://codecept.io/basics/#architecture)

### Selectors 
If there are no _element ID_, _acesibility ID_ or the  xpath of the element is too long; we recomend to use [Android UiSelector](https://developer.android.com/reference/android/support/test/uiautomator/UiSelector) and [iOS Predicates](http://appium.io/docs/en/writing-running-appium/ios/ios-predicate/). 

Read the following documentation for more detailed information about mobile [locators](https://kobiton.com/book/chapter-4-appium-locator-finding-strategies).

- Android

Different examples for mobile locators in Android.

```javascript
Accesibility_ID: '~menu item log in',
Ui_Selector: 'android=new UiSelector().description("menu item log in")'
Xpath: '//android.view.ViewGroup[@content-desc="menu item log in"]'
```

- iOS

Different examples for mobile locators in iOS.

```javascript
Accessibility_ID: '~menu item log in',
Class_Chain: '-ios class chain:**/XCUIElementTypeOther[`label == "Log In"`]',
Predicate_String: '-ios predicate string: type == "XCUIElementTypeOther" && label == "Log In"',
Xpath: '//XCUIElementTypeOther[@name="menu item log in"]'
```

## **FAQ**
Q1) How do I create a .zshrc file?

A1) Follow the instructions described in this [post](https://superuser.com/questions/886132/where-is-the-zshrc-file-on-mac).
