# 📋 Quick Reference Card - Influencer Scraper

**For OPS Team Members**

---

## 🎯 What You Need

| Item | Value |
|------|-------|
| **Actor URL** | https://console.apify.com/actors/[YOUR_ACTOR_ID] |
| **Login** | [Your Apify email] |
| **Team** | Warriors / Falcons / Phoenix / Eagles |

---

## ⚡ How to Run (3 Steps)

### 1️⃣ Prepare URLs
Copy creator profile links:
```
https://www.instagram.com/username/
https://www.tiktok.com/@username
https://www.youtube.com/@channelname
```

### 2️⃣ Fill Input Form
- **Platform Links:** Paste URLs (one per line)
- **Executive:** Your name (e.g., Joyce)
- **Team:** Select from dropdown
- **Category:** Tech / Fashion / AI / etc.
- **Internal Comment:** Notes about creator

### 3️⃣ Run & Export
1. Click **Start**
2. Wait 1-2 minutes
3. Go to **Dataset** tab
4. Click **Export → Google Sheets**

---

## 📊 What Gets Scraped

✅ Creator name  
✅ Followers count  
✅ Average views  
✅ Engagement rate (%)  
✅ Platform (auto-detected)  
✅ Region (when available)  

❌ Cost (fill manually)  
❌ Client comments (fill manually)  
❌ TCE comments (fill manually)  

---

## 🔢 Supported Platforms

| Platform | URL Format | Example |
|----------|-----------|---------|
| Instagram | instagram.com/username | instagram.com/shraddha.dsgn |
| TikTok | tiktok.com/@username | tiktok.com/@techcreator |
| YouTube | youtube.com/@channel | youtube.com/@TechBurner |

---

## ⏱️ Timing

| Action | Time |
|--------|------|
| 1 profile | 30-60 seconds |
| 10 profiles | 5-10 minutes |
| 50 profiles | 20-30 minutes |

---

## 💡 Pro Tips

### Batch Processing
Run multiple creators at once:
```
https://www.instagram.com/creator1/
https://www.instagram.com/creator2/
https://www.instagram.com/creator3/
...
```

### Reuse Settings
Your last input is saved automatically!

### Export Directly
Skip CSV → Use "Google Sheets" export

### Weekly Schedule
Ask admin to set up automatic Monday runs

---

## 🐛 Common Issues

### "No data extracted"
→ Check if profile is public  
→ Verify URL is complete with https://

### "Actor failed"
→ Reduce number of URLs  
→ Try again in a few minutes

### "Missing followers"
→ Platform changed layout  
→ Report to admin for update

---

## 📞 Who to Contact

| Issue | Contact |
|-------|---------|
| Technical problems | Tech team / Admin |
| Actor not working | Check logs first, then admin |
| Need new feature | Submit request to team lead |
| Training needed | Ask colleague or check SETUP_GUIDE.md |

---

## 🎓 Quick Training (For New Members)

1. **Watch:** Admin does 1 demo run
2. **Try:** Do 1 test run with sample URL
3. **Practice:** Run with 5 real creators
4. **Master:** Add to weekly workflow

**Time to proficiency:** 10-15 minutes

---

## 📈 Metrics to Track

After each run, check:
- ✅ Number of creators processed
- ✅ Success rate (how many extracted)
- ✅ Time taken
- ✅ Cost (in Apify console)

**Goal:** 95%+ success rate

---

## ⚙️ Default Settings (Don't Change)

These are pre-configured:
- Timeout: 60 seconds
- Max retries: 3
- Browser: Headless Chrome
- Proxies: Automatic

---

## 🔄 Weekly Workflow

**Every Monday:**
1. Receive brief from core team
2. Extract creator URLs from brief
3. Run actor with URLs
4. Export to Google Sheets
5. Fill in Cost + Comments manually
6. Submit completed brief

**Time saved:** ~3 hours per week

---

## 📋 Checklist Before Submitting

- [ ] All URLs processed successfully
- [ ] Creator names correct
- [ ] Followers/views look reasonable
- [ ] Cost filled in (from quotes)
- [ ] Category correct
- [ ] Team name correct
- [ ] Executive name (yours) added
- [ ] Internal comments added

---

## 🎯 Quality Checks

### Quick Validation:
1. Followers > 10K? (usually)
2. Engagement rate 1-10%? (typical range)
3. Avg views makes sense? (not 0 or weird number)
4. Creator name matches profile?

If something looks off → Double-check manually

---

## 💾 Backup Your Work

Apify keeps results for 30 days.

**Best practice:**
- Export to Google Sheets immediately
- Download CSV backup weekly
- Save in team drive

---

## 🚀 Next Level Skills

Once comfortable:
1. Learn to schedule runs
2. Create custom categories
3. Build team dashboards
4. Analyze trends over time

---

## 📞 Emergency Contacts

| Situation | Action |
|-----------|--------|
| Actor completely broken | Email tech@company.com |
| Urgent deadline | Use manual process + report issue |
| Apify account issue | Login to apify.com/support |

---

## 🎉 Success Stories

"Went from 4 hours to 30 minutes per brief!" - Sarah, Warriors

"No more calculation errors!" - Mike, Falcons

"Can now research 3x more creators" - Ana, Phoenix

---

**Keep this card handy! 📌**

Print or bookmark for quick reference during your workflow.

---

**Last Updated:** November 2025  
**Version:** 1.0  
**For:** OPS Team (Warriors, Falcons, Phoenix, Eagles)
