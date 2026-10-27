# botmail-playwright-otp-verification

A Playwright test template demonstrating OTP (One-Time Password) verification flow with Botmail.

## Prerequisites

- Botmail workspace with subscription
- Supabase project for authentication
- Browser installed for Playwright

## Setup

1. Install dependencies:
   ```bash
   pnpm add -D @playwright/test
   ```

2. Configure environment variables in `.env`:
   ```env
   BOTMAIL_API_URL=http://localhost:3456
   SUPABASE_URL=your_supabase_url
   SUPABASE_ANON_KEY=your_supabase_anon_key
   ```

3. Run the tests:
   ```bash
   pnpm test
   ```

## OTP Verification Flow

The test demonstrates:
1. User signs in via Supabase OAuth
2. OTP is sent to user's email
3. User enters OTP code
4. Verification completes and user is authenticated

## Example Test

```ts
import { test, expect } from '@playwright/test';

test('user can verify OTP and sign in', async ({ page }) => {
  // Navigate to login page
  await page.goto('/login');

  // Sign in with Google
  await page.click('button[aria-label="Sign in with Google"]');
  await page.waitForURL('/dashboard');

  // Verify dashboard is accessible
  await expect(page).toHaveTitle(/Botmail/);
});
```