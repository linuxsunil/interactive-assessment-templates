# Smart Knowledge Check Template - GitHub Repository Structure

## Directory Layout

```
smart-knowledge-checks/
│
├── README.md                           # Main documentation
├── QUICKSTART.md                       # 5-min setup guide
├── LICENSE                             # MIT License
├── .gitignore
│
├── templates/
│   ├── scenario-based-quiz.html        # Main template (customizable)
│   ├── config.template.json            # Template config file
│   └── styles.css                      # Optional custom styles
│
├── examples/
│   ├── sales-objection-handler/
│   │   ├── index.html                  # Full example
│   │   ├── quiz-data.json              # Scenario data
│   │   └── README.md                   # How this example works
│   │
│   ├── compliance-training/
│   │   ├── index.html
│   │   ├── quiz-data.json
│   │   └── README.md
│   │
│   ├── product-knowledge/
│   │   ├── index.html
│   │   ├── quiz-data.json
│   │   └── README.md
│   │
│   └── soft-skills-coaching/
│       ├── index.html
│       ├── quiz-data.json
│       └── README.md
│
├── docs/
│   ├── CUSTOMIZATION_GUIDE.md          # Step-by-step editing
│   ├── JSON_SCHEMA.md                  # Data structure guide
│   ├── RISE_INTEGRATION.md             # How to use in Rise 360
│   ├── ADVANCED_FEATURES.md            # Branching, scoring, etc.
│   └── TROUBLESHOOTING.md              # Common issues
│
└── tools/
    ├── config-generator.html           # Interactive tool to build config
    └── validator.js                    # Validate quiz data
```

---

## File Contents

### 1. README.md

```markdown
# Smart Knowledge Checks: Interactive Quiz Templates for Rise 360

Build scenario-based, branching quizzes with weighted scoring and coaching feedback.

## What You Get

- **6 Scenario-Based Quizzes**: Sales, compliance, product knowledge, soft skills
- **Smart Scoring**: Weighted answers (0-3 points), adaptive difficulty
- **Coaching Feedback**: Specific, actionable feedback per response
- **Zero Code Required**: Just edit the JSON, get instant quizzes
- **Rise 360 Ready**: Drop HTML into Rise code blocks, works immediately
- **Mobile Friendly**: Responsive design, works on all devices

## Quick Start (5 Minutes)

1. Pick an example (Sales, Compliance, Product)
2. Open the HTML file in a browser - it works!
3. Edit `quiz-data.json` with your scenarios
4. Paste updated HTML into Rise 360
5. Done!

## Examples Included

### Sales Objection Handler
- 6 real-world sales scenarios
- Price, features, trust, timing objections
- Branching responses and recovery plays
- Mastery levels: Elite Closer → Keep Practicing

### Compliance Training
- Harassment recognition scenarios
- Decision-based branching
- Compliance-focused feedback
- ADDIE-validated structure

### Product Knowledge
- Feature discovery scenarios
- Customer segment matching
- Use case application
- Adaptive difficulty

### Soft Skills Coaching
- Manager feedback scenarios
- Decision-making exercises
- Behavioral responses
- Mastery-based scoring

## For Learning Developers

### Edit in 3 Steps

1. **Copy the template**
   ```bash
   git clone https://github.com/YourOrg/smart-knowledge-checks.git
   cd smart-knowledge-checks/examples/sales-objection-handler
   ```

2. **Edit quiz-data.json with your scenarios**
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
         "options": [...]
       }
     ]
   }
   ```

3. **Use config-generator.html to build JSON visually** (no coding!)
   - Fill in form fields
   - See JSON auto-generate
   - Copy-paste into your file

### Deploy to Rise 360

- Take the HTML file
- Rise → Add Content Block → Web Object → Custom HTML
- Paste entire file
- Save and preview
- Learners take quiz inside Rise!

## Documentation

- [CUSTOMIZATION_GUIDE.md](docs/CUSTOMIZATION_GUIDE.md) - Full editing guide
- [JSON_SCHEMA.md](docs/JSON_SCHEMA.md) - Data structure reference
- [RISE_INTEGRATION.md](docs/RISE_INTEGRATION.md) - Rise 360 setup
- [ADVANCED_FEATURES.md](docs/ADVANCED_FEATURES.md) - Branching, adaptive difficulty

## Features

✅ **Weighted Scoring** - Answers worth 0-3 points  
✅ **Smart Feedback** - Specific, coaching-focused responses  
✅ **Branching Scenarios** - Different paths based on answers  
✅ **Mastery Levels** - Elite/Skilled/Developing/Keep Practicing  
✅ **Response History** - See all answers + feedback at end  
✅ **Mobile Responsive** - Works on phones, tablets, desktops  
✅ **No Backend Required** - Pure HTML/CSS/JavaScript  
✅ **ADDIE Aligned** - Designed by instructional designers  

## Requirements

- Modern browser (Chrome, Safari, Firefox, Edge)
- Text editor to edit JSON
- Rise 360 account (or any LMS with code block support)

## Browser Support

- ✅ Chrome 90+
- ✅ Safari 14+
- ✅ Firefox 88+
- ✅ Edge 90+
- ✅ Mobile browsers

## License

MIT License - Use freely in your organization

## Support

- Issues? Check [TROUBLESHOOTING.md](docs/TROUBLESHOOTING.md)
- Questions? Open a GitHub issue
- Want to contribute? Submit a PR!

## Contributing

Have a great quiz template? Share it!
1. Fork the repo
2. Add your example in `examples/your-quiz-name`
3. Include README.md and quiz-data.json
4. Submit PR
5. We'll review and merge!

## Credits

Built by [Your Org] Learning & Development team
Inspired by ADDIE framework and adult learning principles
```

---

### 2. QUICKSTART.md

```markdown
# Quick Start: 5 Minutes to Your First Quiz

## Step 1: Pick an Example (1 min)

Choose your starting point:
- **Sales Objection Handler** - For sales training
- **Compliance Training** - For HR/compliance
- **Product Knowledge** - For onboarding
- **Soft Skills** - For manager training

## Step 2: Open in Browser (1 min)

```bash
# Download or clone repo
git clone https://github.com/YourOrg/smart-knowledge-checks.git
cd smart-knowledge-checks/examples/sales-objection-handler

# Open in browser (double-click on index.html)
open index.html
```

Or just download the HTML and open it!

## Step 3: Edit Your Content (2 min)

Open `quiz-data.json` in any text editor:

```json
{
  "title": "Your Course Title Here",
  "description": "Brief description",
  "scenarios": [
    {
      "id": 1,
      "scenario": "Scenario Title",
      "customerSays": "What they say / The situation",
      "question": "How do you respond?",
      "options": [
        {
          "text": "Option A - Your response",
          "score": 3,
          "feedback": "Great! You did X because..."
        },
        {
          "text": "Option B - Alternative",
          "score": 1,
          "feedback": "Good attempt, but..."
        }
      ]
    },
    // ... more scenarios
  ]
}
```

## Step 4: Test It (30 sec)

Refresh your browser - changes appear instantly!

## Step 5: Deploy to Rise 360 (1 min)

1. Open `index.html` in text editor
2. Copy all code
3. In Rise:
   - Click **"Add Content Block"**
   - Select **"Web Object"**
   - Choose **"Custom HTML"**
   - **Paste code** → Save
4. Done! Preview to test.

## That's It! 🎉

Your interactive quiz is now live in Rise 360.

---

## Next Steps

- **Customize further**: See [CUSTOMIZATION_GUIDE.md](../docs/CUSTOMIZATION_GUIDE.md)
- **Use config builder**: Open `tools/config-generator.html` - build JSON visually
- **Add branching**: See [ADVANCED_FEATURES.md](../docs/ADVANCED_FEATURES.md)
- **Deploy to your LMS**: Same process for Canvas, Blackboard, Moodle, etc.

## Need Help?

- **Error when opening?** Check [TROUBLESHOOTING.md](../docs/TROUBLESHOOTING.md)
- **Want to do something advanced?** See [ADVANCED_FEATURES.md](../docs/ADVANCED_FEATURES.md)
- **Questions about structure?** See [JSON_SCHEMA.md](../docs/JSON_SCHEMA.md)
```

---

### 3. CUSTOMIZATION_GUIDE.md

```markdown
# Customization Guide: Edit for Your Courses

## Overview

The quiz template uses a simple JSON structure to define scenarios. Edit the JSON, refresh browser - done!

## JSON File Structure

```json
{
  "title": "Quiz Title",
  "description": "What learners will learn",
  "estimated_completion_minutes": 10,
  "scenarios": [
    {
      "id": 1,
      "scenario": "Scenario Title",
      "customerSays": "What the customer/situation presents",
      "question": "What's your response?",
      "options": [
        {
          "text": "Your response option",
          "score": 3,
          "feedback": "Coaching feedback for this response",
          "branch": 2  // (optional) Next scenario ID
        }
      ]
    }
  ]
}
```

## Editing Steps

### Step 1: Change the Title & Description

```json
{
  "title": "Your New Quiz Title",
  "description": "One sentence on what learners will learn"
}
```

### Step 2: Edit or Add Scenarios

Each scenario is one interactive situation:

```json
{
  "id": 1,
  "scenario": "Scenario Title (appears as heading)",
  "customerSays": "The situation or objection they'll face",
  "question": "What's your response?",
  "options": [ ... ]
}
```

**Example:**
```json
{
  "id": 1,
  "scenario": "Price Objection",
  "customerSays": "Your competitor costs 40% less. Why should I pay more?",
  "question": "How do you respond?",
  "options": [
    {
      "text": "Our solution includes X, Y, Z that competitors don't offer.",
      "score": 3,
      "feedback": "Perfect! You pivoted from price to value and provided specific differentiators."
    }
  ]
}
```

### Step 3: Edit Response Options

Each option is one possible response:

```json
{
  "text": "The response the learner can choose",
  "score": 3,
  "feedback": "Specific feedback on why this response is good/bad"
}
```

**Scoring Guide:**
- `score: 3` - Elite response (best practice)
- `score: 2` - Good response (acceptable, needs refinement)
- `score: 1` - Weak response (misses key element)
- `score: 0` - Poor response (counterproductive)

**Feedback Guide:**
- Start with emoji: ✓ (good) or ⚠️ (weak)
- Explain what was good or wrong
- Give coaching: "Next time, try..."
- Keep under 2 sentences

**Example:**
```json
{
  "text": "Let me check with my manager and get back to you.",
  "score": 0,
  "feedback": "⚠️ You've given them an excuse to say no. Always provide value BEFORE asking for a callback. Try: 'Let me show you the ROI first, then we can discuss timeline.'"
}
```

### Step 4: Add Branching (Optional)

Make scenarios connect based on responses:

```json
{
  "text": "Your great response",
  "score": 3,
  "feedback": "Great job!",
  "branch": 5  // Next scenario ID to show
}
```

**Example:**
- Scenario 1: "Price objection"
- If they answer well (score 3) → branch to Scenario 5: "Feature gap"
- If they answer poorly (score 0) → branch to Scenario 3: "Recovery play"

---

## Common Customizations

### Change the Quiz Title
```json
"title": "Your New Title"
```

### Add More Scenarios
Copy a scenario block and change:
- `id`: increment (1, 2, 3...)
- `scenario`: new title
- `customerSays`: new situation
- `options`: new responses

### Make Feedback More Specific
Good feedback:
```json
"feedback": "✓ You addressed their concern AND provided proof (case study). This builds trust."
```

Bad feedback:
```json
"feedback": "Wrong answer"
```

### Adjust Difficulty
- **Easier**: More scenarios, simpler options
- **Harder**: Fewer scenarios, nuanced options, higher scores needed

---

## Testing Your Changes

1. **Save quiz-data.json**
2. **Refresh browser** (Ctrl+R or Cmd+R)
3. **Go through quiz** - test your changes
4. **Check scoring** - does it match your intent?

---

## File Format Rules

⚠️ **Important**: Keep valid JSON format!

```json
✓ CORRECT:
{
  "scenarios": [
    {
      "id": 1,
      "text": "Your text here"
    }
  ]
}

✗ WRONG (missing comma):
{
  "scenarios": [
    {
      "id": 1
      "text": "Your text here"
    }
  ]
}
```

**Validate your JSON**: Use [jsonlint.com](https://www.jsonlint.com)

---

## Examples: Different Quiz Types

### Compliance Training
```json
{
  "scenario": "Harassment Recognition",
  "customerSays": "A coworker made a joke about someone's appearance",
  "options": [
    {
      "text": "It's just a joke, not harassment",
      "score": 0,
      "feedback": "Incorrect. Intent isn't what matters - impact does. If it offends or creates discomfort, it's harassment."
    }
  ]
}
```

### Sales Training
```json
{
  "scenario": "Objection Handling",
  "customerSays": "Your price is 40% more than competitor X",
  "options": [
    {
      "text": "We offer premium support, faster implementation, and 99.99% uptime",
      "score": 3,
      "feedback": "Perfect! You pivoted from price to value and provided specific differentiators."
    }
  ]
}
```

### Product Onboarding
```json
{
  "scenario": "Customer Use Case",
  "customerSays": "We need to track real-time inventory across 50 stores",
  "options": [
    {
      "text": "Use the Inventory Dashboard with sync enabled",
      "score": 3,
      "feedback": "Correct! This is the exact use case for our real-time inventory feature."
    }
  ]
}
```

### Manager Coaching
```json
{
  "scenario": "Difficult Conversation",
  "customerSays": "An employee says your feedback was harsh",
  "options": [
    {
      "text": "Listen to their concern, validate their feeling, explain your intent",
      "score": 3,
      "feedback": "Excellent! You showed empathy while clarifying intent. This rebuilds trust."
    }
  ]
}
```

---

## Advanced Options

See [ADVANCED_FEATURES.md](ADVANCED_FEATURES.md) for:
- Adaptive difficulty
- Branching logic
- Time-based scoring
- Conditional questions
- Remediation paths

---

## Support

- **JSON validation error?** Check [TROUBLESHOOTING.md](TROUBLESHOOTING.md)
- **Want branching?** See [ADVANCED_FEATURES.md](ADVANCED_FEATURES.md)
- **Need custom styling?** See [styles guide](#)
```

---

This gives your team everything they need! Should I now create:

1. ✅ **The actual GitHub repo structure files** (config template, validator, etc.)
2. ✅ **The 3 complete example quizzes** (Compliance, Product, Soft Skills)
3. ✅ **The remaining docs** (JSON_SCHEMA, RISE_INTEGRATION, etc.)
4. ✅ **A config generator tool** (interactive form to build JSON)

Want me to build all of those, or start with getting this set up in a real GitHub repo structure?