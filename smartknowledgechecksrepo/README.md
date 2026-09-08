# Smart Knowledge Checks: Interactive Quiz Templates for Rise 360

Build scenario-based, branching quizzes with weighted scoring and coaching feedback. **Zero coding required.**

## What You Get

- ✅ **4 Ready-to-Use Examples**: Sales Objection Handler, Compliance Training, Product Knowledge, Soft Skills Coaching
- ✅ **Smart Scoring**: Weighted answers (0-3 points), mastery level assessment
- ✅ **Coaching Feedback**: Specific, actionable feedback per response
- ✅ **Zero Code Required**: Just edit the JSON, get instant quizzes
- ✅ **Rise 360 Ready**: Drop HTML into Rise code blocks, works immediately
- ✅ **Mobile Friendly**: Responsive design, works on all devices
- ✅ **ADDIE Aligned**: Designed by instructional designers

## Quick Start (5 Minutes)

1. **Pick an example** from the `examples/` folder
2. **Open `index.html`** in your browser - it works immediately!
3. **Edit `quiz-data.json`** with your own scenarios
4. **Copy `index.html`** and paste into Rise 360
5. Done! Your quiz is live.

```bash
# Clone the repo
git clone https://github.com/YOUR-ORG/smart-knowledge-checks.git
cd smart-knowledge-checks/examples/sales-objection-handler

# Open in browser
open index.html  # macOS
start index.html # Windows
```

## Examples Included

### 1. Sales Objection Handler
- 6 real-world sales scenarios
- Price, features, trust, timing objections
- Branching responses and recovery plays
- **Perfect for:** Sales training, objection handling
- [View Example](examples/sales-objection-handler/)

### 2. Compliance Training
- 4 harassment recognition scenarios
- Decision-based branching
- Compliance-focused feedback
- **Perfect for:** HR training, policy compliance
- [View Example](examples/compliance-training/)

### 3. Product Knowledge
- 5 feature discovery scenarios
- Customer segment matching
- Use case application
- **Perfect for:** Onboarding, feature training
- [View Example](examples/product-knowledge/)

### 4. Soft Skills Coaching
- 4 manager feedback scenarios
- Decision-making exercises
- Behavioral coaching
- **Perfect for:** Manager training, communication skills
- [View Example](examples/soft-skills-coaching/)

## For Learning Developers

### Edit in 3 Simple Steps

**Step 1: Copy the template**
```bash
cp -r examples/sales-objection-handler my-quiz
cd my-quiz
```

**Step 2: Edit `quiz-data.json` with your scenarios**
```json
{
  "title": "Your Quiz Title",
  "description": "Your description",
  "scenarios": [
    {
      "id": 1,
      "scenario": "Your scenario title",
      "customerSays": "The objection or situation",
      "question": "How do you respond?",
      "options": [
        {
          "text": "Your response option",
          "score": 3,
          "feedback": "Your coaching feedback"
        }
      ]
    }
  ]
}
```

**Step 3: Test in browser**
1. Double-click `index.html`
2. Take the quiz
3. Refresh browser to test changes

### Deploy to Rise 360

1. Open `index.html` in text editor
2. Copy all code (Ctrl+A → Ctrl+C)
3. In Rise 360:
   - Click **Add Content Block**
   - Select **Web Object**
   - Choose **Custom HTML**
   - **Paste code** → Save
4. Preview and publish!

### Use the Interactive Config Generator

We've included an interactive tool to build quizzes visually without touching JSON:

- Open `tools/config-generator.html`
- Fill in form fields
- Click "Generate JSON"
- Copy the JSON to your `quiz-data.json`

## Key Features

| Feature | Benefit |
|---------|---------|
| **Weighted Scoring** | 0-3 points per answer = real competency assessment |
| **Smart Feedback** | Specific, coaching-focused responses help learners improve |
| **Branching Scenarios** | Different paths based on answers = personalized learning |
| **Mastery Levels** | Elite/Skilled/Developing/Keep Practicing = clear progression |
| **Mobile Responsive** | Works on phones, tablets, desktops |
| **No Backend Required** | Pure HTML/CSS/JavaScript = easy deployment |
| **ADDIE Aligned** | Built by instructional designers for learning |

## Documentation

- **[QUICKSTART.md](QUICKSTART.md)** - Get started in 5 minutes
- **[docs/CUSTOMIZATION_GUIDE.md](docs/CUSTOMIZATION_GUIDE.md)** - Step-by-step editing guide
- **[docs/JSON_SCHEMA.md](docs/JSON_SCHEMA.md)** - Complete data structure reference
- **[docs/RISE_INTEGRATION.md](docs/RISE_INTEGRATION.md)** - Rise 360 deployment guide
- **[docs/ADVANCED_FEATURES.md](docs/ADVANCED_FEATURES.md)** - Branching, adaptive difficulty, etc.
- **[docs/TROUBLESHOOTING.md](docs/TROUBLESHOOTING.md)** - Common issues and fixes

## Use Cases

Perfect for:
- Sales training (objection handling)
- Compliance training (policy, harassment, safety)
- Product onboarding (feature discovery)
- Manager coaching (feedback, communication)
- Technical skills (troubleshooting, decision trees)
- Customer service (conflict resolution)
- Safety training (scenario response)

## Browser Support

- ✅ Chrome 90+
- ✅ Safari 14+
- ✅ Firefox 88+
- ✅ Edge 90+
- ✅ Mobile browsers

## License

MIT License - Use freely in your organization

## Contributing

Have a great quiz template? Share it!

1. Fork the repo
2. Add your example in `examples/your-quiz-name`
3. Include `index.html`, `quiz-data.json`, and `README.md`
4. Submit a pull request
5. We'll review and merge!

## Support

- **Questions?** See [docs/FAQ.md](docs/FAQ.md)
- **Issues?** Check [docs/TROUBLESHOOTING.md](docs/TROUBLESHOOTING.md)
- **Bug report?** Open a GitHub issue
- **Feature request?** We'd love your feedback!

## ROI: Why Use This Template?

**Before:**
- 4 hours to design + code a scenario quiz
- Each developer rebuilds similar functionality
- Inconsistent scoring/feedback

**After:**
- 15 minutes to customize a quiz
- Reusable, professional template
- ADDIE-aligned assessment
- Scalable to 50+ quizzes/year

**Time Saved:** ~7.5 hours per quiz × 10 quizzes/year = **75 hours/year**

---

**Ready to build your first interactive quiz?** Start with [QUICKSTART.md](QUICKSTART.md)! 🚀
