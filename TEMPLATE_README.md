# Interactive Scenario Quiz - Template README

## For Learning Developers: How to Use This Template

This template allows you to create professional, interactive scenario-based quizzes with **zero coding required**. Just edit the JSON file with your scenarios.

---

## Files You Have

### 1. `scenario-quiz-template.html`
The main quiz application. Works standalone - just open in a browser!

**Features:**
- ✅ Beautiful, responsive design
- ✅ Weighted scoring (0-3 points per question)
- ✅ Coaching feedback
- ✅ Mastery level assessment
- ✅ Works on desktop, tablet, mobile

### 2. `quiz-data.template.json`
Your scenario data file. Edit this with your content.

**What to edit:**
- Quiz title and description
- Scenarios (situations/objections)
- Response options (what learners can choose)
- Feedback (coaching for each response)
- Scoring (points per option)

---

## 5-Minute Setup

### Step 1: Create Your Files (1 min)
1. Copy `scenario-quiz-template.html` → Rename to `index.html`
2. Copy `quiz-data.template.json` → Rename to `quiz-data.json`
3. Keep both files in the same folder

### Step 2: Edit quiz-data.json (3 min)
Open in any text editor (Notepad, VS Code, etc.):

```json
{
  "title": "YOUR QUIZ TITLE",
  "description": "YOUR DESCRIPTION",
  "scenarios": [
    {
      "id": 1,
      "scenario": "Your Scenario Title",
      "customerSays": "The situation or objection",
      "question": "How do you respond?",
      "options": [
        {
          "text": "Your response option",
          "score": 3,
          "feedback": "Your feedback here"
        }
      ]
    }
  ]
}
```

### Step 3: Test It (1 min)
1. Double-click `index.html` → Opens in browser
2. Take the quiz
3. Refresh browser to test changes

### Step 4: Deploy to Rise 360 (1 min)
1. Open `index.html` in text editor
2. Copy all code
3. Rise 360:
   - Add Content Block → Web Object → Custom HTML
   - Paste code
   - Save
4. Done! Your quiz is live.

---

## Common Customizations

### Change the Quiz Title
**In `quiz-data.json`:**
```json
"title": "Sales Objection Handler"
```

### Add a Scenario
**In `quiz-data.json`, add to `scenarios` array:**
```json
{
  "id": 3,
  "scenario": "Price Objection",
  "customerSays": "Your solution costs 40% more than competitor X.",
  "question": "How do you respond?",
  "options": [
    {
      "text": "Our price includes premium support and faster implementation.",
      "score": 3,
      "feedback": "Perfect! You pivoted from price to value."
    },
    {
      "text": "You get what you pay for.",
      "score": 0,
      "feedback": "Avoid this - it's dismissive and doesn't address their concern."
    }
  ]
}
```

### Change Feedback
```json
"feedback": "Great job! You showed empathy first, then provided proof. This builds trust."
```

### Adjust Scoring
- **`score: 3`** - Elite response (best practice)
- **`score: 2`** - Good response (helpful, but could improve)
- **`score: 1`** - Weak response (misses key element)
- **`score: 0`** - Poor response (counterproductive)

**Example:**
```json
{
  "text": "Let me get back to you with data.",
  "score": 1,
  "feedback": "Good intent, but provide immediate value first. Then follow up with data."
}
```

---

## Tips for Writing Great Feedback

**Good Feedback (Specific & Coaching):**
```
"✓ Excellent! You pivoted from price to value AND provided specific proof (uptime SLA). 
This addresses their real concern (justifying to finance) while building trust."
```

**Bad Feedback (Generic & Not Helpful):**
```
"Wrong answer."
```

**Formula for Great Feedback:**
1. Start with emoji (✓ or ⚠️)
2. Explain what was good/bad
3. Provide the "next time" guidance

**Example:**
```
"⚠️ You acknowledged their concern, but you should have provided proof first. 
Next time, say: 'That's a valid concern. Here's what our customers experience...' [proof]. 
Then ask for the next meeting."
```

---

## Popular Quiz Types

### Sales Training
```json
{
  "scenario": "Price Objection",
  "customerSays": "Your competitor costs less. Why should I pay more?",
  "options": [
    {
      "text": "Our solution includes X, Y, Z they don't offer.",
      "score": 3,
      "feedback": "Perfect! You pivoted from price to value with specific differentiators."
    }
  ]
}
```

### Compliance Training
```json
{
  "scenario": "Harassment Recognition",
  "customerSays": "A coworker made a joke about someone's appearance.",
  "options": [
    {
      "text": "It's not harassment, just a joke.",
      "score": 0,
      "feedback": "Incorrect. Impact matters more than intent. If someone is offended, it's harassment."
    }
  ]
}
```

### Product Onboarding
```json
{
  "scenario": "Feature Discovery",
  "customerSays": "We need to track inventory across 50 stores in real-time.",
  "options": [
    {
      "text": "Use the Inventory Dashboard with sync enabled.",
      "score": 3,
      "feedback": "Correct! This is the perfect use case for real-time inventory sync."
    }
  ]
}
```

### Manager Coaching
```json
{
  "scenario": "Difficult Conversation",
  "customerSays": "An employee says your feedback felt harsh.",
  "options": [
    {
      "text": "Listen, validate their feeling, explain your intent.",
      "score": 3,
      "feedback": "Excellent! You showed empathy while clarifying your good intent. This rebuilds trust."
    }
  ]
}
```

---

## Validation & Testing

### Before Publishing:

✅ **Edit checklist:**
- [ ] Quiz title is clear and specific
- [ ] Description explains what learners will learn
- [ ] All scenarios are realistic and specific
- [ ] All options have clear text
- [ ] All scoring makes sense (best answers = 3 points)
- [ ] All feedback is helpful and coaching-focused
- [ ] JSON file is valid (no syntax errors)

✅ **Test checklist:**
- [ ] Open `index.html` in browser - works without errors
- [ ] Take the quiz all the way through
- [ ] Check that scores calculate correctly
- [ ] Verify feedback displays properly
- [ ] Test on mobile browser (iPhone/Android)

### Check JSON Syntax

If quiz doesn't load, your JSON has an error. Validate at:
**[jsonlint.com](https://www.jsonlint.com)**

Common errors:
```json
❌ Missing comma:
{
  "title": "Quiz"
  "description": "Missing comma above"
}

✓ Correct:
{
  "title": "Quiz",
  "description": "Comma added"
}
```

---

## Deploying to Rise 360

### Step 1: Prepare Files
1. Have your `index.html` file ready
2. Make sure `quiz-data.json` is in same folder

### Step 2: Copy HTML Code
1. Open `index.html` in text editor
2. Select all (Ctrl+A or Cmd+A)
3. Copy (Ctrl+C or Cmd+C)

### Step 3: Add to Rise
1. Create new lesson in Rise 360
2. Click "Add Content Block"
3. Select "Web Object"
4. Choose "Custom HTML"
5. Paste your code
6. Click Save

### Step 4: Test in Rise
1. Preview the lesson
2. Take the quiz
3. Verify scoring and feedback work
4. Publish when ready

### Step 5: Deploy to Learners
1. Publish lesson
2. Add to course
3. Assign to learners
4. Done!

---

## Troubleshooting

### "Quiz won't load or shows blank page"
**Solution:** Check JSON syntax at jsonlint.com. Common: missing comma, unmatched quotes.

### "Feedback not showing after answer"
**Solution:** Make sure each option has `feedback` field with text.

### "Scoring seems wrong"
**Solution:** Verify `score` values (0-3). Total quiz = sum of all question max scores (3 each).

### "Quiz looks bad on mobile"
**Solution:** Works on all modern browsers (Chrome, Safari, Firefox, Edge). Check device compatibility.

### "How do I change colors?"
**Solution:** In `index.html`, find the `<style>` section and change color codes:
```css
/* Change primary color from purple to blue */
#667eea → #0066ff
#764ba2 → #0052cc
```

---

## Advanced Features (Optional)

### Add Branching (Different Paths)
Want different scenarios based on responses?

In `options`, add `branch`:
```json
{
  "text": "Strong response",
  "score": 3,
  "feedback": "Great!",
  "branch": 5  // Jump to scenario ID 5
}
```

To implement: Modify JavaScript to check `branch` field and jump to that scenario.

### Add Time-Based Scoring
Want faster answers = more points?

Modify scoring formula in JavaScript:
```javascript
// If answered in <15 seconds = bonus
const timeBonus = responseTime < 15 ? 1.5 : 1.0;
finalScore = baseScore * timeBonus;
```

### Add Adaptive Difficulty
Want questions to get harder?

Track streak:
```javascript
if (correctStreak >= 2) {
  difficulty = "hard"; // Show harder scenarios
} else {
  difficulty = "easy"; // Show easier scenarios
}
```

---

## Real-World Examples

### Example 1: Sales Team Objection Handler
- 6 scenarios: Price, features, trust, timing, competition, recovery
- 4 options per scenario
- Weighted scoring emphasizing value-based selling
- Mastery levels: "Elite Closer" to "Keep Practicing"

### Example 2: Compliance Training
- 4 scenarios: Recognition, reporting, investigation, prevention
- Clear right/wrong answers
- Strict scoring (3 or 0, no middle ground)
- Emphasis on policy and procedure

### Example 3: Product Onboarding
- 5 scenarios: Feature discovery, customer use cases, problem-solving
- Mix of 3-4 options
- Branching paths (great answer → harder question)
- Mastery = can apply features to customer problems

### Example 4: Manager Coaching
- 4 scenarios: Feedback, conflict, motivation, delegation
- Nuanced answers (2-3 good responses per scenario)
- Emphasis on empathy and communication
- Reflection-based feedback

---

## Frequently Asked Questions

**Q: Can I use this for compliance training?**
A: Absolutely! Create strict scenarios with clear right/wrong answers.

**Q: How many scenarios should I include?**
A: 4-6 is ideal. Keeps quiz under 10 minutes.

**Q: Can I randomize the order?**
A: Not in this version, but it's easy to add. Ask your developer.

**Q: Can I export scores to a gradebook?**
A: Not by default, but Rise can track completion. For detailed tracking, ask your developer.

**Q: Can I embed this in my LMS?**
A: Yes! Works in any LMS that supports code blocks (Rise, Canvas, Blackboard, Moodle, etc.)

**Q: Who do I contact if something breaks?**
A: Check TROUBLESHOOTING.md or contact your development team.

---

## Next Steps

1. ✅ Copy `scenario-quiz-template.html` → `index.html`
2. ✅ Copy `quiz-data.template.json` → `quiz-data.json`
3. ✅ Edit `quiz-data.json` with your scenarios
4. ✅ Test by opening `index.html` in browser
5. ✅ Deploy to Rise 360
6. ✅ Share with learners!

**That's it! Your interactive quiz is ready.** 🎉

---

## Support

- **Documentation:** See docs/ folder
- **Examples:** See examples/ folder  
- **Issues:** Contact your learning team

---

## Version History

- **v1.0** (Current) - Initial template release
  - Scenario-based quizzes
  - Weighted scoring (0-3)
  - Coaching feedback
  - Mastery level assessment
  - Mobile responsive

---

**Happy quiz building!** 🚀
