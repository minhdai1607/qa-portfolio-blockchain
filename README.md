# Mocana API Testing

## Introduction

This project with main purpose is to use playwright of typescript to do automated testing.  
It's an E2E and API automation testing framework for Mocana.

## Project structure

```bash
mocana-e2e-test/                  # Root project directory.
|── config/                       # All configuration for running.
│    ├── api/                     # Api configuration directory.
│    │    └── config.ts           # Api configuration contains test runs, reports, base URL.
│    └── web/                     # Configuration e2e directory.
│         └── config.ts           # E2e configuration contains test run, report, base URL, browser.
|── core_lib/                     # Libs directory.
│    └── utilities.ts             # Libs utilities include function for general use.
|── models/                       # Models directory.
│    ├── api/                     # Api models directory.
│    └── web/                     # e2e models directory.
├── data/                         # Data directory.
│    ├── api/                     # Data api directory include request data, schema data.
│    │    ├── request/            # Request data.
│    │    └── schema/             # Used to validate the api's response schema.
│    └── web/                     # Data e2e directory include request data.
├── api/                          # Api object model directory.
│    └── HelpersApi.ts            # Serves as base API containing commonly used functions.
├── pom/                          # Page object model directory.
│    └── web/                     # E2E object model directory and locator.
│         └── BasePage.ts         # Contains functions that help interacting with page such as click, fill, get text,...
|── tests/                        # Test root directory.
│    ├── api/                     # Test api root directory.
│    └── web/                     # Test e2e root directory.
├── .env                          # env: setup environment.
├── .gitignore                    # Files or folders to ignore in a project.
├── package.json                  # Descriptive and functional metadata such as a name, version, and dependencies.
├── README.md                     # README: text file that introduces and explains a project.
└── tsconfig.json                 # The root of a TypeScript project.
```

## Setup environment

1. Install the required library environment: Nodejs: v20.x, npm: 10.x

- Download and install nodejs from link download: https://nodejs.org/en/download  
  ![Screenshot 2023-10-31 at 09 38 45](https://github.com/mocaverse/automation-test/assets/147599444/3a68a2d3-e2c1-45be-8d77-a7cbc77db2f8)

- Install npm:

```bash
  npm install npm@latest -g
```

2. Install library of NPM packages:

```bash
  npm install
```

3. Install browser include chromium, firefox, webkit, ...

```bash
  npx playwright install
```

For example  
![unnamed](https://github.com/mocaverse/automation-test/assets/147599444/495a6b59-7dce-4104-b13d-f88aa3635a5a)

4. Create an .env file in the project to set up the environment

- File .env content

```bash
# Environment of application: STAGING or PRODUCTION. For now just support STAGING, in the future will support PRODUCTION
# For example:
#   ENV=STAGING
ENV=STAGING

# The path(s) to the test file(s) to run. This can be a single file or a glob pattern.
# This variable can hold single value or multiple values separated by comma.
# For example:
#   TEST_FILES_API=tests/api/*.ts                                        //Run all tests with API
#   TEST_FILES_API=tests/api/auth/login.spec.ts                          //Run file with API
#   TEST_FILES_API=tests/api/auth/login.spec.ts,tests/api/heathz.spec.ts //Run multiple test file with API
#   TEST_FILES_WEB=tests/web/*.ts                                        //Run all tests with E2E
#   TEST_FILES_WEB=tests/web/home.spec.ts                                //Run file with E2E
#   TEST_FILES_WEB=tests/web/home.spec.ts,tests/web/home.spec.ts         //Run multiple test file with E2E
TEST_FILES_API=tests/api/*.ts


# The browsers run on the website. Website browser: chromium, firefox, webkit, ...
# This variable can hold single value or multiple values separated by comma.
# For example:
#    BROWSER=chromium                          // Run a browser
#    BROWSER=chromium,firefox,webkit           // Run multiple browsers
BROWSER=chromium

# Run tests in headed browsers
HEADLESS=true

# Base URl E2E
# For example:
#   APP_URL=https://staging.mocaverse.xyz
APP_URL=https://staging.mocaverse.xyz

# Endpoint type of API
# Endpoint type: core, points-api, ...
# For example:
#   ENDPOINT_TYPE=moca-id-api                  //core
#   ENDPOINT_TYPE=points-api                   //points-api
ENDPOINT_TYPE=moca-id-api

# ZEPHYR AUTH TOKEN
ZEPHYR_AUTH_TOKEN=...
```

## Run the test script

To run test with API test:

- Run test file

```bash
  npm run api
```

- Run by priority

```bash
  npm run api.priority.high      //Run on high priority
  npm run api.priority.medium    //Run on medium priority
  npm run api.priority.low       //Run on low priority
```

- Run file test and view test report:

```bash
  npm run api.report
```

To run test with E2E test:

- Run test file

```bash
  npm run web
```

- Run test file and view test report:

```bash
  npm run web.report
```

- Run by ui:

```bash
  npm run web.ui
```

For example  
![Screenshot 2023-10-31 at 09 25 05](https://github.com/mocaverse/automation-test/assets/147599444/c017d702-07f7-46c1-89ba-8b557b376921)

- Run with the debug:

```bash
  npm run web.debug
```

- Run by priority

```bash
  npm run web.priority.high      //Run on high priority
  npm run web.priority.medium    //Run on medium priority
  npm run web.priority.low       //Run on low priority
```

- Run by title

```bash
  npx playwright test --config=config/web/config.ts -g "$TITLE"
  # For example:
  #   npx playwright test --config=config/web/config.ts -g "Verify has title of Mocana"
```

## Report

To view test report:

- View test report:

```bash
  npm run report
```

For example  
![Screenshot 2023-10-31 at 09 36 55](https://github.com/mocaverse/automation-test/assets/147599444/6e6548aa-da59-4e16-b7b5-dbf7c9558b3e)

- View test report with allure report:

```bash
  npm run report.allure
```

For example  
![Screenshot 2023-11-01 at 13 32 03](https://github.com/mocaverse/automation-test/assets/147599444/719fa161-a771-4f8a-9308-f13ddc2aad7b)
