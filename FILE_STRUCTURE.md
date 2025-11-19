# Actor File Structure

```
influencer-data-scraper/
│
├── .actor/
│   ├── actor.json              # Actor configuration & metadata
│   └── input_schema.json       # Input form schema (UI in Apify Console)
│
├── src/
│   └── main.js                 # Main scraping logic
│
├── package.json                # NPM dependencies
├── Dockerfile                  # Container configuration
├── README.md                   # Full documentation
├── DEPLOYMENT.md              # Deployment guide
└── input.json                 # Sample input for testing

```

## File Descriptions

### `.actor/actor.json`
- Defines actor name, title, description
- Configures input/output storage
- Sets display properties for results

### `.actor/input_schema.json`
- Creates the input form in Apify Console
- Defines fields: platformLinks, executive, team, etc.
- Sets validation rules and examples

### `src/main.js`
- **Main scraping engine**
- Contains scrapers for Instagram, TikTok, YouTube
- Extracts: followers, views, engagement rate
- Formats output to match your spreadsheet

### `package.json`
- Lists required NPM packages
- Apify SDK, Crawlee, Puppeteer
- Defines start script

### `Dockerfile`
- Specifies Node.js + Puppeteer environment
- Based on official Apify image
- Installs dependencies and copies code

### `README.md`
- Complete user documentation
- Features, usage examples, troubleshooting
- Export and scheduling instructions

### `DEPLOYMENT.md`
- Step-by-step deployment guide
- Multiple deployment options
- Google Sheets integration

### `input.json`
- Sample input for local testing
- Shows correct JSON format
- Can be used as template

---

## How Data Flows

```
1. User Input (URLs + metadata)
        ↓
2. Apify Actor Initialization
        ↓
3. Puppeteer Browser Launch
        ↓
4. For each URL:
   - Detect platform (IG/TikTok/YouTube)
   - Navigate to profile
   - Extract data (followers, views, etc.)
   - Calculate engagement rate
   - Add metadata (date, team, executive)
        ↓
5. Combine all results
        ↓
6. Save to Apify Dataset
        ↓
7. Export to CSV/Sheets/JSON
```

---

## Customization Points

### Add New Platform
Edit `src/main.js` → Add new scraper function:
```javascript
async function scrapeLinkedIn(page, url, log) {
  // Your scraping logic here
}
```

### Change Output Format
Edit `src/main.js` → Modify result object:
```javascript
const result = {
  'Custom Field': 'value',
  // ... rest of fields
};
```

### Add More Input Fields
Edit `.actor/input_schema.json` → Add property:
```json
"newField": {
  "title": "New Field",
  "type": "string",
  "editor": "textfield"
}
```

### Adjust Timeouts
Edit `src/main.js` → Change timeout values:
```javascript
navigationTimeoutSecs: 60,  // Increase if needed
```

---

## Next Steps

1. ✅ Files created and ready
2. 📤 Upload to Apify Console
3. 🔨 Build the actor
4. ▶️ Run test with sample URLs
5. 📊 Export to your spreadsheet
6. ⏰ Set up weekly schedule
7. 🎯 Start collecting creator data!

---

**All files are ready for deployment!**
