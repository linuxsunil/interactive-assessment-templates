# Customize for Your Organization

## Key Changes

### Update Policy References
Find scenarios and replace with YOUR organization's policies:

In `quiz-data.json`, find:
```json
"feedback": "Our policy is clear: if a comment is offensive..."
```

Change to:
```json
"feedback": "[YOUR COMPANY] policy is clear: if a comment is offensive..."
```

### Customize Scenarios
Replace generic situations with scenarios YOUR team actually faces:

**Generic:**
```json
"customerSays": "A coworker made a joke about someone's appearance."
```

**Customized:**
```json
"customerSays": "[Specific incident type your team has experienced]"
```

### Update Mastery Descriptions
Make them match your company culture:

```json
{
  "threshold": 85,
  "label": "Compliance Champion 🏆",
  "description": "[Your company's description of excellent compliance knowledge]"
}
```

## Editing Scenarios

### Step 1: Identify Your Key Scenarios
What compliance situations does YOUR team face most often?
- Harassment/discrimination
- Data privacy/confidentiality
- Safety procedures
- Policy violations
- Other

### Step 2: Edit quiz-data.json
Update each scenario:
```json
{
  "id": 1,
  "scenario": "Your Scenario Title",
  "customerSays": "What actually happens in your workplace",
  "question": "How should employees respond?",
  "options": [
    {
      "text": "Correct response based on YOUR policy",
      "score": 3,
      "feedback": "Why this is correct per YOUR policy"
    },
    {
      "text": "Incorrect response",
      "score": 0,
      "feedback": "Why this violates YOUR policy"
    }
  ]
}
```

### Step 3: Ensure Strict Scoring for Compliance
Compliance scenarios typically use:
- `score: 3` - Correct per policy
- `score: 0` - Violates policy

(Use `score: 1-2` only for scenarios with gray areas)

### Step 4: Make Feedback Policy-Specific
Good compliance feedback:
```json
"feedback": "✓ Correct! Per [Section 3.2] of our handbook, you must report immediately. This protects everyone."
```

## Example Customizations

### For Healthcare Organization
```json
{
  "id": 1,
  "scenario": "HIPAA Privacy Violation",
  "customerSays": "A coworker asks you about a patient's diagnosis in the hallway.",
  "question": "What do you do?",
  "options": [
    {
      "text": "Don't answer. HIPAA protects patient privacy in all settings, including casual conversations.",
      "score": 3,
      "feedback": "✓ Correct! HIPAA violations happen in hallways too. Never discuss patient info outside secure settings."
    }
  ]
}
```

### For Financial Services
```json
{
  "id": 2,
  "scenario": "Client Information Protection",
  "customerSays": "A client's account information is visible on your desk when a visitor walks by.",
  "question": "What should happen?",
  "options": [
    {
      "text": "You should have secured the document immediately. Per Regulation Y, client info must be protected.",
      "score": 3,
      "feedback": "✓ Correct! Always secure client documents. This is required by regulators AND our policy."
    }
  ]
}
```

### For Manufacturing
```json
{
  "id": 3,
  "scenario": "Safety Procedure Violation",
  "customerSays": "Your coworker skips a safety step because 'it takes too long.'",
  "question": "What do you do?",
  "options": [
    {
      "text": "Report it to your supervisor immediately. Safety steps exist to prevent injuries.",
      "score": 3,
      "feedback": "✓ Correct! Every step matters. Report violations so we can prevent accidents."
    }
  ]
}
```

## Testing Your Changes

Before deploying:

✅ **Policy accuracy:**
- [ ] All scenarios reflect YOUR actual workplace
- [ ] All answers match YOUR written policies
- [ ] Feedback cites YOUR policy documents
- [ ] Mastery levels match YOUR culture

✅ **Quality check:**
- [ ] All correct answers are clearly correct
- [ ] All wrong answers are clearly wrong
- [ ] No ambiguous scenarios
- [ ] JSON is valid (check [jsonlint.com](https://www.jsonlint.com))

## Important: Legal Review

**Before deploying to your organization:**

1. Have your HR/Legal team review the quiz
2. Ensure all scenarios match your policies
3. Ensure all feedback aligns with your handbook
4. Consider having HR sign off on accuracy

This protects your organization and ensures accuracy.

## Deploy Updated Version

1. Get HR/Legal approval
2. Copy updated `index.html`
3. Deploy to Rise 360
4. Share with your team with clear guidance
5. Track completion and discuss low scores with employees

---

**Need help?** See [README.md](README.md) or [../../docs/TROUBLESHOOTING.md](../../docs/TROUBLESHOOTING.md)
