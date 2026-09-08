# Quick Start: 5 Minutes to Your First Quiz

## Step 1: Pick an Example (1 min)

Choose your starting point based on your use case:

- **Sales Objection Handler** - For sales training
- **Compliance Training** - For HR/compliance
- **Product Knowledge** - For onboarding
- **Soft Skills Coaching** - For manager training

## Step 2: Open in Browser (1 min)

```bash
# Download or clone repo
git clone https://github.com/YOUR-ORG/smart-knowledge-checks.git
cd smart-knowledge-checks/examples/sales-objection-handler

# Open in browser
# On macOS:
open index.html

# On Windows:
start index.html

# Or just double-click index.html
```

## Step 3: Edit Your Content (2 min)

Open `quiz-data.json` in any text editor (Notepad, VS Code, etc.):

```json
{
  "title": "Your Quiz Title Here",
  "description": "Brief description of what learners will learn",
  "scenarios": [
    {
      "id": 1,
      "scenario": "Scenario Title",
      "customerSays": "What the customer/situation presents",
      "question": "How do you respond?",
      "options": [
        {
          "text": "Your response option",
          "score": 3,
          "feedback": "Great! You did X which shows Y. This approach..."
        },
        {
          "text": "Alternative response",
          "score": 1,
          "feedback": "Good attempt, but you could strengthen this by..."
        }
      ]
    }
  ]
}
```

**Key fields to customize:**
- `title`: Your quiz name
- `scenarios`: Array of situations learners will face
- `customerSays`: The objection, situation, or scenario
- `options`: Response choices (keep 3-4 options per scenario)
- `score`: Points (3 = best, 2 = good, 1 = weak, 0 = poor)
- `feedback`: Coaching message for each response

## Step 4: Test It (30 sec)

1. **Refresh your browser** (Ctrl+R or Cmd+R)
2. **Take the quiz** - try different answers
3. **Check scoring** - does it feel right?
4. **Make changes** - edit JSON again, refresh to see updates

## Step 5: Deploy to Rise 360 (1 min)

### Method A: Copy/Paste HTML (Simplest)

1. Open `index.html` in text editor
2. Select all code (Ctrl+A or Cmd+A)
3. Copy (Ctrl+C or Cmd+C)
4. In Rise 360:
   - Click **Add Content Block**
   - Select **Web Object**
   - Choose **Custom HTML**
   - **Paste code** → Save
5. Preview and publish!

### Method B: Use the Config Generator (No Coding)

1. Open `tools/config-generator.html`
2. Fill in the form fields
3. Click **"Generate JSON"**
4. Copy the JSON and paste into your `quiz-data.json`

## That's It! 🎉

Your interactive quiz is now live and ready for learners.

---

## Next Steps

### Want to customize more?
See [docs/CUSTOMIZATION_GUIDE.md](../docs/CUSTOMIZATION_GUIDE.md) for:
- Adding more scenarios
- Changing colors and styling
- Using branching (different paths based on answers)
- Setting mastery levels

### Having issues?
See [docs/TROUBLESHOOTING.md](../docs/TROUBLESHOOTING.md) for:
- Quiz won't load
- JSON syntax errors
- Scoring problems
- Mobile display issues

### Need the full technical reference?
See [docs/JSON_SCHEMA.md](../docs/JSON_SCHEMA.md) for complete field documentation

---

## Common Questions

**Q: Do I need to know JavaScript?**
A: No! Just edit the JSON file. The HTML does all the heavy lifting.

**Q: Can I use this in my LMS (Canvas, Blackboard, Moodle)?**
A: Yes! Any LMS that supports code blocks works. Same copy/paste process.

**Q: Can I change the colors?**
A: Yes! In the HTML file, find the `<style>` section and look for `#667eea` (blue) and `#764ba2` (purple). Change to your brand colors.

**Q: How many scenarios should I include?**
A: 4-6 is ideal. Keeps quiz under 10 minutes.

**Q: Can I make it harder/easier?**
A: Yes! Add more/fewer scenarios, use different question types, adjust scoring weights.

---

**Ready to go?** Pick an example from the `examples/` folder and start editing! 🚀
