# Customize for Your Sales Team

## Quick Changes

### Your Company Name
In `quiz-data.json`, find:
```json
"customerSays": "Your competitor costs 40% less."
```

Change to:
```json
"customerSays": "[COMPETITOR NAME] costs 40% less than [YOUR COMPANY]."
```

### Your Product Features
Find response options with:
```json
"text": "Our solution includes premium support, faster implementation..."
```

Edit with YOUR features:
```json
"text": "Our solution includes [YOUR FEATURE 1], [YOUR FEATURE 2], [YOUR FEATURE 3]..."
```

### Your Customer Types
Find:
```json
"customerSays": "We need real-time inventory across 50 stores."
```

Edit for YOUR customers:
```json
"customerSays": "We need [THEIR SPECIFIC NEED] for [THEIR INDUSTRY]."
```

### Your Pricing Structure
Find:
```json
"customerSays": "Your competitor costs 40% less."
```

Change to reflect your pricing:
```json
"customerSays": "[COMPETITOR] offers the same thing for [THEIR PRICE]."
```

## Editing Steps

### Step 1: Open quiz-data.json
Use any text editor (Notepad, VS Code, etc.)

### Step 2: Change the Title & Description
```json
{
  "title": "Your Company Sales Training",
  "description": "Practice handling objections your team actually faces"
}
```

### Step 3: Edit Each Scenario

Find a scenario you want to customize:
```json
{
  "id": 1,
  "scenario": "Price Objection",
  "customerSays": "...",
  "question": "How do you respond?",
  "options": [...]
}
```

Edit:
- `scenario`: Your objection title
- `customerSays`: The actual objection (make it realistic!)
- `question`: What you want them to answer (usually stays the same)
- `options`: Response choices and coaching

### Step 4: Edit Response Options
```json
{
  "text": "Your response option",
  "score": 3,
  "feedback": "Why this is an excellent response"
}
```

**Scoring Guide:**
- `score: 3` - Elite response (best practice)
- `score: 2` - Good response (acceptable, needs refinement)
- `score: 1` - Weak response (misses key element)
- `score: 0` - Poor response (counterproductive)

**Feedback Guide:**
- Start with emoji: ✓ (good) or ⚠️ (weak)
- Explain what was good/bad
- Provide coaching: "Next time, try..."

### Step 5: Save & Test
1. Save `quiz-data.json`
2. Refresh browser (Ctrl+R or Cmd+R)
3. Take quiz
4. Check scoring

## Adding New Scenarios

Copy an existing scenario block and modify:

```json
{
  "id": 7,
  "scenario": "Your New Objection Title",
  "customerSays": "What the customer says or the situation",
  "question": "How do you respond?",
  "options": [
    {
      "text": "Strong response",
      "score": 3,
      "feedback": "Why this response is excellent..."
    },
    {
      "text": "Weak response",
      "score": 0,
      "feedback": "Why this response misses the mark..."
    }
  ]
}
```

**Important:** Remember to:
- Increment the `id` (1, 2, 3, 4, 5, 6, 7...)
- Keep the JSON format valid (no missing commas!)
- Validate at [jsonlint.com](https://www.jsonlint.com)

## Example Customizations

### For SaaS Company
```json
{
  "id": 1,
  "scenario": "Feature Parity Question",
  "customerSays": "Does your API support the same webhooks as Salesforce?",
  "question": "How do you respond?",
  "options": [
    {
      "text": "Not currently, but we have our GraphQL API that's actually more flexible. Want me to show you?",
      "score": 3,
      "feedback": "Perfect! You acknowledged the gap, positioned your alternative as superior, and moved forward with a next step."
    }
  ]
}
```

### For Professional Services
```json
{
  "id": 2,
  "scenario": "Budget Constraint",
  "customerSays": "Your proposal is beyond our budget this year.",
  "question": "How do you respond?",
  "options": [
    {
      "text": "I understand. What if we phase this - Phase 1 with the core modules now, Phase 2 next year when budgets refresh?",
      "score": 3,
      "feedback": "Excellent! You solved for their constraint without lowering price. Phasing shows you're flexible and customer-focused."
    }
  ]
}
```

### For Enterprise Software
```json
{
  "id": 3,
  "scenario": "Security Concerns",
  "customerSays": "Your solution isn't SOC 2 Type II certified like our current vendor.",
  "question": "How do you respond?",
  "options": [
    {
      "text": "We're completing SOC 2 Type II certification next month. I'll have the report for you before your decision. Meanwhile, here's our security whitepaper.",
      "score": 3,
      "feedback": "Brilliant! You showed timeline clarity, credibility (whitepaper), and urgency. This handles their concern without giving up the deal."
    }
  ]
}
```

## Testing Your Changes

Before deploying to Rise 360:

✅ **Edit checklist:**
- [ ] Title and description are clear
- [ ] All scenarios are realistic
- [ ] All options have clear text
- [ ] Scoring makes sense (best answers = 3)
- [ ] All feedback is helpful and specific
- [ ] JSON file is valid (check [jsonlint.com](https://www.jsonlint.com))

✅ **Testing checklist:**
- [ ] Open `index.html` in browser
- [ ] Take the quiz all the way through
- [ ] Check that scores calculate correctly
- [ ] Verify feedback displays properly
- [ ] Test on mobile browser

## Deploy Updated Version

1. Copy updated `index.html` code
2. Update in Rise 360
3. Republish course
4. Share with your team!

---

**Need help?** See [README.md](README.md) or [../../docs/TROUBLESHOOTING.md](../../docs/TROUBLESHOOTING.md)
