# Influencer Data Scraper for OPS Team

This Apify actor automates the collection of influencer/creator data from **Instagram**, **TikTok**, and **YouTube** profiles. It formats the data according to your OPS team's brief requirements.

## Features

- ✅ Scrapes multiple platforms: Instagram, TikTok, YouTube
- ✅ Extracts key metrics: followers, average views, engagement rate
- ✅ Auto-populates date and team information
- ✅ Outputs data in your exact spreadsheet format
- ✅ Batch processing of multiple creators
- ✅ Export to CSV/Excel compatible format

## What Data is Extracted

For each creator profile, the actor extracts:

| Column | Description | Source |
|--------|-------------|--------|
| **Internal Comment** | Your note about the creator | Manual input |
| **Date** | Entry date (DD-MM-YYYY) | Auto-generated |
| **Executive** | OPS member name | Manual input |
| **Team** | Warriors/Falcons/Phoenix/Eagles | Manual input |
| **Creator Name** | Profile/channel name | Auto-scraped |
| **Category** | Niche (Tech/AI/Fashion/etc.) | Manual input |
| **Platform** | Instagram/TikTok/YouTube | Auto-detected |
| **Platform Link** | Full profile URL | Input |
| **Followers** | Total follower count | Auto-scraped |
| **Region** | Creator's country | Auto-scraped (when available) |
| **Cost** | Quoted price | Leave blank for manual entry |
| **Avg Views** | Average views from recent posts | Auto-calculated |
| **ER** | Engagement rate (%) | Auto-calculated |
| **Client Comment** | Client feedback | Leave blank |
| **TCE Comment** | Internal approval | Leave blank |

## Input Configuration

### Required Fields

- **Platform Links**: Array of creator profile URLs
  ```
  https://www.instagram.com/shraddha.dsgn/
  https://www.tiktok.com/@username
  https://www.youtube.com/@channelname
  ```

### Optional Fields

- **Executive**: Name of OPS team member (e.g., "Joyce")
- **Team**: Select from Warriors, Falcons, Phoenix, or Eagles
- **Category**: Creator niche (e.g., "Tech", "Fashion", "AI")
- **Internal Comment**: Notes about the creator (e.g., "Quick responder, open to negotiation")

## Usage Example

### Input JSON:
```json
{
  "platformLinks": [
    "https://www.instagram.com/shraddha.dsgn/",
    "https://www.tiktok.com/@techcreator",
    "https://www.youtube.com/@techannel"
  ],
  "executive": "Joyce",
  "team": "Warriors",
  "category": "Tech",
  "internalComment": "Quick responder, open to negotiation"
}
```

### Output (Dataset):
```json
[
  {
    "Internal Comment": "Quick responder, open to negotiation",
    "Date": "18-11-2025",
    "Executive": "Joyce",
    "Team": "Warriors",
    "Creator Name": "Shraddha DSGN",
    "Category": "Tech",
    "Platform": "Instagram",
    "Platform Link": "https://www.instagram.com/shraddha.dsgn/",
    "Followers": 250000,
    "Region": "India",
    "Cost": "",
    "Avg Views": 120000,
    "ER": "4.5",
    "Client Comment": "",
    "TCE Comment": ""
  }
]
```

## How to Use on Apify

### Step 1: Deploy the Actor

1. Go to [Apify Console](https://console.apify.com/)
2. Click **Actors** → **Create new**
3. Choose **Import from GitHub** or upload files manually
4. Upload these files:
   - `src/main.js`
   - `package.json`
   - `.actor/actor.json`
   - `.actor/input_schema.json`
   - `Dockerfile`

### Step 2: Configure Input

1. Open your actor in the Apify Console
2. Go to the **Input** tab
3. Add creator profile URLs (one per line or as JSON array)
4. Fill in Executive, Team, Category fields
5. Add any internal comments

### Step 3: Run the Actor

1. Click **Start** button
2. Wait for the scraping to complete (usually 1-3 minutes per profile)
3. View results in the **Dataset** tab

### Step 4: Export Data

1. Go to **Dataset** tab
2. Click **Export** button
3. Choose format: **CSV**, **Excel**, or **JSON**
4. Download and import into your spreadsheet

## Exporting to Google Sheets

You can directly export to Google Sheets:

1. After actor run completes, go to **Dataset**
2. Click **Export** → **Google Sheets**
3. Authorize Apify to access your Google account
4. Select or create a spreadsheet
5. Data will be appended to your sheet automatically

## Scheduling Regular Runs

To automate weekly/daily scraping:

1. Go to **Schedules** in Apify Console
2. Click **Create new schedule**
3. Set frequency (e.g., "Every Monday at 9 AM")
4. Select this actor
5. Configure input (can use different URLs each time)

## Platform-Specific Notes

### Instagram
- Extracts followers, recent post views
- Calculates ER based on average views/followers
- May require login for some profiles (can be configured)

### TikTok
- Extracts followers, video views
- Uses last 12 videos for average calculation
- Works best with public profiles

### YouTube
- Extracts subscribers, recent video views
- Uses last 12 videos for average calculation
- Handles both channels and handles (@username)

## Limitations & Notes

1. **Cost field**: Must be filled manually after scraping (quotes from creators)
2. **Region**: May not always be available; some platforms don't display it
3. **Rate limits**: Social platforms may block excessive requests; use reasonable delays
4. **Private profiles**: Cannot scrape private/locked accounts
5. **Engagement Rate**: Simplified calculation (Avg Views / Followers × 100)

## Troubleshooting

### "No data extracted"
- Check if the profile URL is correct and publicly accessible
- Ensure the profile isn't private/restricted
- Platform may have changed HTML structure (contact support)

### "Actor failed"
- Check input format (URLs should be complete with https://)
- Verify network connectivity
- Some profiles may require login (premium feature)

### "Missing followers/views"
- Platform may have removed public stats
- Profile may be new with limited data
- Wait a few seconds and retry

## Cost Optimization

- **Compute units**: ~0.01-0.03 per profile (depending on platform)
- Batch multiple creators in one run to save on startup time
- Use scheduling to run during off-peak hours for lower costs

## Support

For issues or feature requests:
- Check Apify actor logs for detailed error messages
- Contact your Apify account manager
- Submit issues via Apify Console feedback

## Version History

- **v1.0.0**: Initial release with Instagram, TikTok, YouTube support

---

**Created for OPS Team Brief Format**  
Last Updated: November 2025
