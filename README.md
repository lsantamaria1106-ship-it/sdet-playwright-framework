# SDET Playwright Framework

This repository contains an **end-to-end test automation framework** built with **Playwright + TypeScript**.  
The goal is to demonstrate best practices for UI test automation, including reusable code structure, reporting, and CI/CD integration.

---

## ⚡ Features
- Page Object Model (POM) design
- Example login test case
- Custom reporter integration
- Ready for GitHub Actions CI/CD pipeline

---

## 📂 Project Structure
The project structure is as follows:

sdet-playwright-framework/
 ┣ tests/
 ┃ ┗ login.test.js
 ┣ package.json
 ┣ README.md

---

## 🚀 Getting Started

1. **Clone the repository**  
   `git clone https://github.com/yourusername/sdet-playwright-framework.git`  
   `cd sdet-playwright-framework`

2. **Initialize the project and install dependencies**  
   `npm init -y`  
   `npm install @playwright/test --save-dev`

3. **Run tests**  
   `npx playwright test`

---

## 🧪 Example Test (login.test.js)

```javascript
const { test, expect } = require('@playwright/test');

test('Login page should load', async ({ page }) => {
  await page.goto('https://www.saucedemo.com/');
  await expect(page.locator('#user-name')).toBeVisible();
  await expect(page.locator('#password')).toBeVisible();
  await expect(page.locator('#login-button')).toBeVisible();
});

test('User can log in with valid credentials', async ({ page }) => {
  await page.goto('https://www.saucedemo.com/');
  await page.fill('#user-name', 'standard_user');
  await page.fill('#password', 'secret_sauce');
  await page.click('#login-button');
  await expect(page.locator('.inventory_list')).toBeVisible();
});
