# Automated Functional Tests for Trust Wallet App

### Summary
This repository contains automated functional tests for the TrustWallet Android app, developed using Appium and Java with TestNG and Maven.

### Tech Stack
- **Java 11** — core programming language
- **Appium** — mobile test automation framework
- **TestNG** — test runner and assertions
- **Maven 3.8.5** — dependency management and build tool

### Project Structure
```
src/
├── apps/android/          # Android APK under test
├── main/java/
│   ├── pages/             # Page Object classes (BasePage, CreateNewWalletPage)
│   └── utils/             # Driver setup utilities (DriverUtils)
└── test/java/tests/       # Test classes (BaseTest, CreateNewWalletTests)
```

### Test Cases
| Test Class | Test | Description |
|---|---|---|
| `CreateNewWalletTests` | `createNewWalletUsingBackupSkipOption` | Verifies user can create a new wallet by skipping the backup option, validates passcode mismatch error, sets up passcode, and confirms wallet creation |

---

## Setup

### Prerequisites
- **[Java 11](https://openjdk.java.net/projects/jdk/11/)**
  ```
  brew install openjdk@11
  ```
- **[Maven 3.8.5](https://maven.apache.org/download.cgi)**
  ```
  brew install maven
  ```
- **Node.js**
  ```
  brew install node
  ```
- **Appium**
  ```
  npm install -g appium
  ```
- **IDE** — [IntelliJ IDEA](https://www.jetbrains.com/help/idea/installation-guide.html#standalone) (Community edition is sufficient)

### Android / iOS Setup
- [Common setup](https://automationhacks.io/slides/2021/appium-conf/hello-appium-writing-your-first-tests/04-common-libraries/)
- [Android setup](https://automationhacks.io/slides/2021/appium-conf/hello-appium-writing-your-first-tests/05-setup-for-android/)
- [iOS setup](https://automationhacks.io/slides/2021/appium-conf/hello-appium-writing-your-first-tests/09-setup-for-ios/)

### Device Configuration
Start an Android emulator matching these capabilities:

```java
capabilities.setCapability("platformName", "android");
capabilities.setCapability("platformVersion", "14");
capabilities.setCapability("deviceName", "Pixel 8");
```

---

## Running Tests

Run a specific test class:
```
mvn clean test -Dtests=CreateNewWalletTests
```

Run the full suite:
```
mvn clean test
```

---

## Reports

After a test run, reports are generated under `target/surefire-reports/` (excluded from version control).

- **Per-class report:** `target/surefire-reports/<ClassName>/`
- **Full suite report:** `target/surefire-reports/emailable-report.html`
