# Unified Feed — Microsoft Outlook

A single-page app that consolidates email and calendar from multiple Microsoft/Outlook accounts into one unified feed. Uses the Microsoft Graph API with Device Code Flow — no popups, works from any machine.

## Deploy to GitHub Pages (free, 3 steps)

### Step 1 — Create a GitHub repository

1. Go to [github.com/new](https://github.com/new)
2. Name it `unified-feed` (or anything you like)
3. Set it to **Public**
4. Click **Create repository**

### Step 2 — Upload the file

1. On your new repo page, click **Add file → Upload files**
2. Drag and drop `index.html` into the upload area
3. Click **Commit changes**

### Step 3 — Enable GitHub Pages

1. Go to **Settings → Pages**
2. Under **Source**, select **Deploy from a branch**
3. Choose **main** branch and **/ (root)** folder
4. Click **Save**

Your app will be live at:
```
https://YOUR-USERNAME.github.io/unified-feed
```
(takes ~60 seconds to go live after saving)

## Azure App Registration — one-time setup

1. Go to [portal.azure.com](https://portal.azure.com) → **Azure Active Directory → App registrations → New registration**
2. Name it anything (e.g. `Unified Feed`)
3. Leave Redirect URI blank (not needed for device code flow)
4. Click **Register**
5. Copy the **Application (client) ID**
6. Go to **API permissions → Add permission → Microsoft Graph → Delegated** and add:
   - `User.Read`
   - `Mail.Read`
   - `Calendars.Read`
7. Go to **Authentication → Advanced settings** → set **Allow public client flows** to **Yes** → Save

## Usage

1. Open your GitHub Pages URL in any browser
2. Paste your Azure App Client ID
3. Click **Get sign-in code**
4. Open any browser, go to `microsoft.com/devicelogin`, enter the code
5. Sign in — your inbox and calendar load automatically
6. Click **+ Add Microsoft account** to add more accounts

Your Client ID is saved in localStorage so you only need to paste it once per browser.
