# Automation

- Make sure sure nodejs already installed in the system by enter following node version command in command prompt
```sh
		>>node -v	
```
    When its show version number, then nodejs already installed in the system, otherwise follow the steps
- Download nodejs application from following url and install
```sh
		https://nodejs.org/download/release/v16.15.1/node-v16.15.1-x64.msi
```
    No need to change any options while install, just click "next" button in all window and finally "finish".
- Now open new command prompt and enter following command to check installed node version
```sh
		>>node -v
```
	  Its output like "v16.15.1"
- Navigate to working directory [Example : E:\AutomationTesting\test-case-automation]
- Run following command and enter details of project (or just press "enter" key to set default/empty value)

```sh
	>>npm init playwright@latest
```
- To update Playwright to the latest version run the following command:
```sh
	>>npm install -D @playwright/test@latest
```
- You can always check which version of Playwright you have by running the following command:
```sh
	>>npx playwright --version
```
- After install, open "E:\AutomationTesting\test-case-automation\package.json" and update the line as follows
```sh
	"test": "npx playwright test"
```
- Run the install command and select the following to get started:
   - Choose between TypeScript or JavaScript (default is TypeScript)
   - Name of your Tests folder (default is tests or e2e if you already have a tests folder in your project)
   - Add a GitHub Actions workflow to easily run tests on CI
   - Install Playwright browsers (default is true)

- Playwright will download the browsers needed as well as create the following files.
```sh
		   playwright.config.ts
	package.json
	package-lock.json
	tests/
  	example.spec.ts
	tests-examples/
  	demo-todo-app.spec.ts
``` 
- Run following command to create playwright folders
```sh
	>>npm run test  
```
- After your test completes, an HTML Reporter will be generated.
- Run following command to Show HTML Reporter.
```sh
	>>npx playwright show-report 
```
- Running the Example Test in UI Mode
- Run following command to your tests with UI Mode for a better developer experience with time travel debugging, watch mode and more.
```sh
	>>npx playwright test --ui 
```
- Write the test case fallowed the files path : "tests/example.spec.ts"
```sh
import { test, expect } from '@playwright/test';

test('has title', async ({ page }) => {
  await page.goto('https://playwright.dev/');

  // Expect a title "to contain" a substring.
  await expect(page).toHaveTitle(/Playwright/);
});

test('get started link', async ({ page }) => {
  await page.goto('https://playwright.dev/');

  // Click the get started link.
  await page.getByRole('link', { name: 'Get started' }).click();

  // Expects page to have a heading with the name of Installation.
  await expect(page.getByRole('heading', { name: 'Installation' })).toBeVisible();
});
```
  
