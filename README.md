# Google Sheets Setup Guide

## 1. Enable Google Sheets API
- Go to the [Google Cloud Console](https://console.cloud.google.com/).
- Create a new project or select an existing one.
- Navigate to **APIs & Services > Library**.
- Search for "Google Sheets API" and click **Enable**.

## 2. Create Service Account
- Navigate to **APIs & Services > Credentials**.
- Click **Create Credentials > Service Account**.
- Give it a name and click **Create and Continue**.
- (Optional) Grant it roles, then click **Done**.
- Click on the newly created service account.
- Navigate to the **Keys** tab.
- Click **Add Key > Create New Key**.
- Select **JSON** and click **Create**. A file will download.

## 3. Setup Replit Secrets
- Open the file you just downloaded.
- Copy the **entire JSON content**.
- In Replit, go to the **Secrets** tool (padlock icon).
- Add a new secret with the key `GOOGLE_CREDENTIALS` and paste the full JSON as the value.
- Add another secret with the key `SHEET_ID` and paste your Google Sheet's ID (found in the URL: `https://docs.google.com/spreadsheets/d/SPREADSHEET_ID/edit`).

## 4. Share Google Sheet
- Open your Google Sheet.
- Click **Share**.
- Paste the service account email (found in your `GOOGLE_CREDENTIALS` JSON as `client_email`).
- Grant it **Editor** access and click **Send**.

## 5. Usage
- The app will now be able to sync data with the specified Google Sheet.
- Use the `/test-sheet` route to verify the connection.
