# Customization Guide

Complete step-by-step guide for editing quizzes.

## Overview

The quiz template uses a simple JSON structure to define scenarios, options, and feedback. Edit the JSON, refresh your browser - done!

No JavaScript needed. Just edit text files.

## File Structure

Your quiz has 2 files in the same folder:
- **`index.html`** - The quiz application (don't edit unless advanced)
- **`quiz-data.json`** - Your scenario data (EDIT THIS!)

## 5-Minute Setup

### Step 1: Copy Template Files (1 min)
```bash
cp templates/scenario-quiz-template.html index.html
cp templates/quiz-data.template.json quiz-data.json
```

### Step 2: Open quiz-data.json in Text Editor (30 sec)
- Windows: Notepad or Notepad++
- Mac: TextEdit or VS Code
- Linux: nano, vim, or VS Code

### Step 3: Edit Title & Description (1 min)
```json
{
  "title": "Your Quiz Title",
  "description": "One sentence on what learners will learn",
  ...
}
```

### Step 4: Edit Scenarios (2 min)
Replace the `scenarios` array with YOUR content:
```json
"scenarios": [
  {
    "id": 1,
    "scenario": "Your scenario title",
    "customerSays": "The situation",
    "question": "How do you respond?",
    "options": [
      {
        "text": "Option text",
        "score": 3,
        "feedback": "Coaching feedback"
      }
    ]
  }
]
```

### Step 5: Test (30 sec)
1. Open `index.html` in browser
2. Take your quiz
3. Refresh browser after edits to see changes

## Detailed Editing Guide

### Editing the Title & Description

```json
{
  "title": "Your Quiz Title Here",
  "description": "One sentence describing what learners will learn or practice"
}
```

**Examples:**

✓ **Good titles:**
- "Sales Objection Handler"
- "Workplace Compliance Training"
- "Product Knowledge Assessment"

✗ **Bad titles:**
- "Quiz" (too generic)
- "Training Module" (unclear what it's about)

✓ **Good descriptions:**
- "Practice handling real-world sales objections"
- "Learn to recognize and respond to harassment correctly"
- "Test your ability to match customer problems to features"

✗ **Bad descriptions:**
- "This is a quiz" (doesn't say what's in it)
- "Answer questions" (too vague)

---

### Editing Scenarios

Each scenario is one interactive situation:

```json
{
  "id": 1,
  "scenario": "Your Scenario Title",
  "customerSays": "The situation or objection",
  "question": "What's your response?",
  "options": [...]
}
```

**Fields:**
- `id`: Unique number (1, 2, 3, 4...). Must be unique per scenario.
- `scenario`: Title that appears as a heading
- `customerSays`: The situation or objection (make it realistic!)
- `question`: What you're asking them to do (usually "How do you respond?")
- `options`: Array of possible answers

**Example:**
```json
{
  "id": 1,
  "scenario": "Price Objection",
  "customerSays": "Your competitor costs 40% less. Why should I pay more?",
  "question": "How do you respond?",
  "options": [...]
}
```

---

### Editing Response Options

Each option is one possible response:

```json
{
  "text": "The response option",
  "score": 3,
  "feedback": "Coaching feedback for this response"
}
```

**Fields:**
- `text`: What the learner will click
- `score`: Points for this answer (0, 1, 2, or 3)
- `feedback`: What you tell them about their choice

**Scoring Guide:**
- `score: 3` - Elite response (best practice)
- `score: 2` - Good response (acceptable, could improve)
- `score: 1` - Weak response (misses key element)
- `score: 0` - Poor response (counterproductive or wrong)

**Feedback Examples:**

✓ **Good feedback (specific & coaching):**
```
"✓ Excellent! You pivoted from price to value AND provided specific proof (SLA). This addresses their real concern while building trust."
```

✓ **Also good (directional):**
```
"⚠️ You acknowledged their concern, but should have provided proof first. Next time, say: 'That's valid. Here's what customers experience...'"
```

✗ **Bad feedback (too generic):**
```
"Wrong answer."
```

✗ **Bad feedback (not helpful):**
```
"That's not good."
```

**Feedback Formula:**
1. Start with emoji: ✓ (good) or ⚠️ (needs work)
2. Explain what was good/bad
3. Provide "next time" coaching
4. Keep under 2 sentences

**Example:**
```json
{
  "text": "Your price includes premium support and faster implementation.",
  "score": 3,
  "feedback": "✓ Perfect! You pivoted from price to value AND gave specific proof. Customers can justify this to their finance team."
}
```

---

### Adding New Scenarios

Copy an existing scenario and modify:

1. **Open quiz-data.json**
2. **Find the last scenario** (look for the highest `id`)
3. **Copy that scenario block**
4. **Paste after it**
5. **Increment the `id`** (if last was 5, new is 6)
6. **Change the content** to your new scenario
7. **Save**
8. **Refresh browser** to test

**Template for new scenario:**
```json
{
  "id": 6,
  "scenario": "Your New Title",
  "customerSays": "Your situation",
  "question": "How do you respond?",
  "options": [
    {
      "text": "Strong response",
      "score": 3,
      "feedback": "Why this is excellent..."
    },
    {
      "text": "Weak response",
      "score": 0,
      "feedback": "Why this is problematic..."
    }
  ]
}
```

---

### Changing Mastery Levels

The mastery levels appear at the end of the quiz based on score:

```json
"masteryLevels": [
  {
    "threshold": 85,
    "label": "Elite 🏆",
    "description": "You consistently handle objections with confidence."
  },
  {
    "threshold": 70,
    "label": "Skilled 💼",
    "description": "You handle most scenarios well."
  },
  {
    "threshold": 50,
    "label": "Developing 📈",
    "description": "You're building confidence."
  },
  {
    "threshold": 0,
    "label": "Keep Practicing 🎯",
    "description": "Every response is a learning opportunity."
  }
]
```

**To customize:**
1. Change the `label` to your desired name
2. Change the `description` to match your message
3. Adjust `threshold` values if desired (keep in descending order: 85, 70, 50, 0)

**Example:**
```json
{
  "threshold": 85,
  "label": "Product Expert 🌟",
  "description": "You deeply understand our products and can match customer needs to solutions perfectly."
}
```

---

## Common Customizations

### For Sales Training
Focus on:
- Real objections your team faces
- Competitive intelligence
- Value-based selling responses
- Proof points (cases, data, testimonials)

Example:
```json
{
  "scenario": "Competitor Comparison",
  "customerSays": "[COMPETITOR NAME] has feature X that we need.",
  "options": [
    {
      "text": "We have feature X as well - here's how ours is better because...",
      "score": 3,
      "feedback": "Perfect! You corrected misconception and showed your advantage."
    }
  ]
}
```

### For Compliance Training
Focus on:
- Clear right/wrong answers
- Policy references
- Proper procedures
- Report escalation

Example:
```json
{
  "scenario": "Policy Violation Report",
  "customerSays": "You witness employee misconduct.",
  "options": [
    {
      "text": "Report to HR immediately per company policy.",
      "score": 3,
      "feedback": "✓ Correct. Section 5.2 of handbook requires prompt reporting."
    },
    {
      "text": "Talk to the person first.",
      "score": 0,
      "feedback": "❌ Wrong. Always report to HR first. They're trained to investigate."
    }
  ]
}
```

### For Product Training
Focus on:
- Use cases
- Feature matching
- Customer problems
- Solution positioning

Example:
```json
{
  "scenario": "Customer Need Match",
  "customerSays": "We need real-time inventory across 50 stores.",
  "options": [
    {
      "text": "Our Inventory Dashboard with real-time sync is perfect for this.",
      "score": 3,
      "feedback": "Excellent! You matched their need to the right feature."
    }
  ]
}
```

### For Manager Training
Focus on:
- Communication skills
- Emotional intelligence
- Coaching approach
- Difficult conversations

Example:
```json
{
  "scenario": "Difficult Conversation",
  "customerSays": "Employee says your feedback felt harsh.",
  "options": [
    {
      "text": "Listen, validate their feeling, explain your intent.",
      "score": 3,
      "feedback": "Perfect! You showed empathy while clarifying. This rebuilds trust."
    }
  ]
}
```

---

## Before Publishing

### ✅ Edit Checklist

- [ ] Title is clear and specific
- [ ] Description explains what learners will learn
- [ ] All scenarios are realistic
- [ ] All options have clear text (not too long)
- [ ] All scoring makes sense (best answers = 3)
- [ ] All feedback is helpful and coaching-focused
- [ ] Mastery levels make sense for your audience
- [ ] No typos or spelling errors
- [ ] JSON is valid (check [jsonlint.com](https://www.jsonlint.com))

### ✅ Testing Checklist

- [ ] Open `index.html` in browser
- [ ] Take the quiz start to finish
- [ ] Check that all scenarios load
- [ ] Check that scores calculate correctly (should be out of 18 for 6 scenarios)
- [ ] Check that feedback displays properly
- [ ] Check mastery level matches score
- [ ] Test on mobile browser (phone/tablet)
- [ ] Click "Retake Quiz" - make sure it resets

---

## Validating JSON

If your quiz doesn't load, you have a JSON syntax error.

**Check with jsonlint.com:**
1. Copy your `quiz-data.json`
2. Go to [jsonlint.com](https://www.jsonlint.com)
3. Paste it
4. Click **Validate**
5. It shows you exactly what's wrong

**Common JSON Errors:**

❌ **Missing comma between fields:**
```json
{
  "title": "Quiz"
  "description": "Missing comma above"
}
```
✓ **Fix:** Add comma after "Quiz"

❌ **Trailing comma (last item):**
```json
{
  "options": [
    { "text": "Option 1" },
    { "text": "Option 2" },  ← Remove this comma
  ]
}
```
✓ **Fix:** Remove comma after last item in array

❌ **Mismatched quotes:**
```json
{
  "title": 'Quiz with single quotes'
}
```
✓ **Fix:** Use double quotes: `"Quiz with double quotes"`

❌ **Unmatched braces:**
```json
{
  "scenarios": [
    { "id": 1 }
  ]
}  ← Need closing brace here
```
✓ **Fix:** Count opening and closing braces

---

## Troubleshooting Edits

### "I made changes but they don't appear"

**Solution:**
1. Make sure you saved the `quiz-data.json` file
2. Hard refresh browser: Ctrl+Shift+R (Windows) or Cmd+Shift+R (Mac)
3. Close and reopen the file in your editor

### "I get a JSON error"

**Solution:**
1. Go to [jsonlint.com](https://www.jsonlint.com)
2. Paste your quiz-data.json
3. Fix the error shown
4. Save again

### "Some characters appear broken"

**Solution:**
1. Make sure your text editor is set to UTF-8 encoding
2. File → Save As → Select UTF-8 encoding
3. Save and try again

### "I deleted something and now it won't work"

**Solution:**
1. Undo (Ctrl+Z or Cmd+Z) in your text editor
2. Or restore from the template: copy quiz-data.template.json again
3. Then carefully re-edit

---

## Best Practices

### 1. Keep Scenarios Realistic
Don't use generic examples. Use REAL situations your team faces.

### 2. Write Specific Feedback
Generic feedback ("Wrong answer") doesn't help learners improve. Be specific:
- What they did wrong
- Why it matters
- What to do next time

### 3. Balance Difficulty
- Too easy: Learners get bored
- Too hard: Learners get frustrated
- Target: 70% average, with range of 0-100%

### 4. Keep It Short
- 4-6 scenarios is ideal
- 10+ scenarios = people skip it
- Long quizzes = lower completion rates

### 5. Review Regularly
- Check scores over time
- Adjust if everyone gets 95% (too easy)
- Adjust if everyone fails (too hard)
- Update content based on feedback

---

## Next Steps

1. **Start simple** - Create 4 good scenarios before adding more
2. **Test with users** - Have 3-5 people take your quiz
3. **Iterate** - Adjust based on feedback
4. **Measure impact** - Track scores and improvement
5. **Expand** - Add more quizzes as you perfect your process

---

**See Also:**
- [JSON_SCHEMA.md](JSON_SCHEMA.md) - Complete field reference
- [RISE_INTEGRATION.md](RISE_INTEGRATION.md) - Deploy to Rise 360
- [TROUBLESHOOTING.md](TROUBLESHOOTING.md) - Common issues
- [ADVANCED_FEATURES.md](ADVANCED_FEATURES.md) - Optional enhancements
