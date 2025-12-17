AEROVEX DASHBOARD - DEPLOYMENT GUIDE
=====================================

IMPORTANT: NEW SETUP FOR AI CHAT FEATURE
-----------------------------------------
The dashboard now includes an AI assistant that requires a backend.
You can no longer use Netlify Drop — you need to deploy via GitHub.

DEPLOYMENT STEPS:

1. CREATE A GITHUB REPO
   - Go to github.com and create a new repository
   - Upload all files from this folder (keep the folder structure!)

2. CONNECT TO NETLIFY
   - Go to netlify.com and sign in
   - Click "Add new site" → "Import an existing project"
   - Connect your GitHub account and select the repo

3. ADD YOUR API KEY
   - In Netlify, go to Site settings → Environment variables
   - Add a new variable:
     Key: ANTHROPIC_API_KEY
     Value: your-api-key-here
   - Get your API key from console.anthropic.com

4. DEPLOY
   - Netlify will auto-deploy when you push to GitHub
   - Your AI chat will now work!

UPDATING DATA:
- Edit the CSV files in GitHub and commit
- Netlify will auto-redeploy

FILE STRUCTURE:
---------------
aerovex-dashboard/
├── index.html                    (main dashboard)
├── logo.png                      (your logo)
├── All_Business_Data_for_Dashboard.csv
├── Ad_Campaign_Data.csv
├── netlify.toml                  (Netlify config)
└── netlify/
    └── functions/
        └── chat.js               (AI backend)

CSV FILE FORMATS:
-----------------
All_Business_Data_for_Dashboard.csv:
Month,Days,Google Spend,Google Revenue,Meta Spend,Meta Revenue,Website Sales,Lucas Sales,Affiliate Sales,Total Business Sales,Website Traffic

Ad_Campaign_Data.csv:
Platform,Campaign Name,Cost,Revenue,Clicks,Start Date,End Date

TROUBLESHOOTING:
----------------
- Chat not working? Check that ANTHROPIC_API_KEY is set in Netlify
- Data not updating? Make sure you committed and pushed to GitHub
- Function errors? Check Netlify Functions logs in the dashboard
