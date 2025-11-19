# Quick Deployment Guide

## Option 1: Deploy via Apify Console (Recommended)

### Step-by-Step:

1. **Create Account**
   - Go to https://apify.com
   - Sign up for free account (includes free tier)

2. **Create New Actor**
   - Click **Actors** → **Create new**
   - Select **Empty actor**

3. **Upload Files**
   - Upload all files from this folder:
     - `src/main.js`
     - `package.json`
     - `Dockerfile`
     - `.actor/actor.json`
     - `.actor/input_schema.json`
     - `README.md`

4. **Build the Actor**
   - Click **Build** button
   - Wait for build to complete (~2-3 minutes)

5. **Test Run**
   - Go to **Input** tab
   - Add sample URLs:
     ```
     https://www.instagram.com/shraddha.dsgn/
     ```
   - Fill in Executive: "Joyce"
   - Select Team: "Warriors"
   - Category: "Tech"
   - Click **Start**

6. **View Results**
   - Go to **Dataset** tab after run completes
   - Export to CSV or Google Sheets

---

## Option 2: Deploy via Apify CLI

### Prerequisites:
```bash
npm install -g apify-cli
apify login
```

### Deploy:
```bash
# Navigate to actor directory
cd /path/to/influencer-data-scraper

# Deploy to Apify
apify push

# Run the actor
apify call
```

---

## Option 3: Run Locally (Testing)

### Prerequisites:
```bash
npm install
```

### Set Environment:
```bash
export APIFY_LOCAL_STORAGE_DIR=./apify_storage
export APIFY_TOKEN=your_token_here
```

### Create Input:
Create `apify_storage/key_value_stores/default/INPUT.json`:
```json
{
  "platformLinks": ["https://www.instagram.com/shraddha.dsgn/"],
  "executive": "Joyce",
  "team": "Warriors",
  "category": "Tech"
}
```

### Run:
```bash
npm start
```

### View Results:
Check `apify_storage/datasets/default/` folder

---

## Connecting to Google Sheets

### Method 1: Apify Integration (Easiest)
1. Run your actor
2. Go to **Dataset** → **Export** → **Google Sheets**
3. Authorize Apify
4. Select/create spreadsheet
5. Done! Data automatically synced

### Method 2: Google Sheets Add-on
1. Install "Apify for Google Sheets" add-on
2. Configure actor ID and API token
3. Use `=APIFY()` formula to fetch data
4. Set up auto-refresh

### Method 3: Zapier/Make Integration
1. Create Zap/Scenario
2. Trigger: "Apify Actor Run Finished"
3. Action: "Add Row to Google Sheets"
4. Map fields accordingly

---

## Batch Processing Tips

### Process Multiple Creators:
```json
{
  "platformLinks": [
    "https://www.instagram.com/creator1/",
    "https://www.instagram.com/creator2/",
    "https://www.tiktok.com/@creator3",
    "https://www.youtube.com/@creator4"
  ],
  "executive": "Joyce",
  "team": "Warriors",
  "category": "Tech"
}
```

### Run Weekly Automatically:
1. Go to **Schedules** in Apify Console
2. Click **Create new**
3. Set: "Every Monday at 9:00 AM"
4. Select this actor
5. Configure input (or use webhook to get dynamic URLs)

---

## Cost Estimates (Apify Pricing)

- **Free Tier**: $5 worth of usage/month
- **Per Profile**: ~$0.01-0.03 (varies by platform)
- **Example**: 100 profiles/week = ~$2-3/week

### Optimization:
- Batch creators in single run (saves startup time)
- Use scheduling during off-peak hours
- Cache results when possible

---

## Troubleshooting

### Build Failed
- Check `package.json` syntax
- Ensure all files are uploaded
- Verify Dockerfile is correct

### Actor Timeout
- Increase timeout in actor settings (Settings → Advanced)
- Reduce batch size (fewer URLs per run)

### No Data Extracted
- Verify URLs are publicly accessible
- Check if profile is private
- Platform may have changed structure (need update)

### Rate Limited
- Add delays between requests
- Use proxies (Apify provides free residential proxies)
- Spread runs across multiple days

---

## Need Help?

- **Apify Documentation**: https://docs.apify.com
- **Community Discord**: https://discord.com/invite/jyEM2PRvMU
- **Support**: support@apify.com
- **Actor Issues**: Check logs in Apify Console

---

**Ready to go! 🚀**

Start by uploading files to Apify Console or running locally for testing.
