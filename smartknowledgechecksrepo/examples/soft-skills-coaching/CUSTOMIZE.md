# Customize for Your Management Culture

## Quick Customizations

### Update Scenarios with Your Situations
Replace generic scenarios with ones YOUR managers actually face:

**Generic:**
```json
"customerSays": "An employee says your feedback felt harsh."
```

**Customized:**
```json
"customerSays": "An employee on your team says they felt criticized in the 1-on-1 meeting yesterday."
```

### Align Coaching Feedback with Your Values
Make feedback reflect YOUR company's management philosophy:

```json
"feedback": "✓ Perfect! You led with [YOUR COMPANY'S VALUE], which aligns with how we build trust with our team."
```

## Editing Scenarios

### Step 1: Identify Common Manager Situations
What difficult conversations do YOUR managers struggle with?
- Giving feedback
- Managing conflict
- Handling underperformance
- Difficult departures
- Delegation
- Other

### Step 2: Create Realistic Scenarios
Use ACTUAL situations you've observed:

```json
{
  "id": 1,
  "scenario": "Your Situation Title",
  "customerSays": "What actually happens in your organization",
  "question": "How should a good manager respond?",
  "options": [
    {
      "text": "The response aligned with YOUR company values",
      "score": 3,
      "feedback": "✓ Correct! This approach [specific benefit]. This is how we build trust with our teams."
    },
    {
      "text": "A response that misses the mark",
      "score": 0,
      "feedback": "❌ This approach [why it fails]. Instead, [your preferred approach]. Remember: [principle that matters]."
    }
  ]
}
```

### Step 3: Reflect Your Company Culture
Make sure answers align with what you VALUE:

**Cultures that VALUE empathy & listening:**
```json
{
  "text": "Have a private conversation first to understand what's happening",
  "score": 3
}
```

**Cultures that VALUE direct accountability:**
```json
{
  "text": "Address it immediately with clear expectations about consequences",
  "score": 3
}
```

**Cultures that VALUE coaching & development:**
```json
{
  "text": "See it as a learning opportunity and work with them to improve",
  "score": 3
}
```

## Example Customizations

### For Startup Culture (Flat, Direct)
```json
{
  "id": 1,
  "scenario": "Missed Deadline",
  "customerSays": "A team member missed a critical deadline without warning.",
  "question": "How do you respond?",
  "options": [
    {
      "text": "In our flat org, you handle it immediately: 'This deadline matters. What happened and how do we prevent this?' Direct but respectful.",
      "score": 3,
      "feedback": "Perfect! Direct communication is how we operate. You got to the point, took accountability seriously, and focused on solutions."
    }
  ]
}
```

### For Enterprise Culture (Process, Accountability)
```json
{
  "id": 1,
  "scenario": "Policy Violation",
  "customerSays": "An employee violated a documented policy.",
  "question": "What's your first step?",
  "options": [
    {
      "text": "Document the violation, inform HR, follow the progressive discipline process, and include the employee in the conversation.",
      "score": 3,
      "feedback": "Correct! We follow our documented process to protect both the employee and the company. HR partnership ensures fairness."
    }
  ]
}
```

### For Engineering Culture (Logic & Data)
```json
{
  "id": 1,
  "scenario": "Technical Decision Disagreement",
  "customerSays": "You disagree with an engineer's technical approach. You think it's inefficient.",
  "question": "How do you handle it?",
  "options": [
    {
      "text": "Ask them to explain their reasoning first. Maybe they see something you don't. If you disagree, present your reasoning with data.",
      "score": 3,
      "feedback": "Perfect! In our culture, we respect technical expertise and data-driven decisions. You might learn something. Always inquire before you instruct."
    }
  ]
}
```

### For Sales Culture (Results, Resilience)
```json
{
  "id": 1,
  "scenario": "Missed Quota",
  "customerSays": "A rep missed quota for the second month in a row.",
  "question": "Your approach?",
  "options": [
    {
      "text": "Understand what happened - is it effort, skills, or market? Then create a 30-day plan with specific actions and daily check-ins.",
      "score": 3,
      "feedback": "Smart! In sales, we're empathetic but results-focused. Understand the root cause, then act. You show you care AND you drive accountability."
    }
  ]
}
```

## Testing with Your Leadership Team

Before deploying to all managers:

1. **Have 5-10 managers take the quiz**
2. **Ask them:**
   - "Are these realistic situations you face?"
   - "Are the 'correct' answers what you would do?"
   - "Do the answers reflect our company values?"
3. **Adjust based on feedback**

## Deploy Thoughtfully

1. **Partner with HR or your leadership team**
2. **Frame it as:** "This helps us build consistent management practices"
3. **Follow up with:**
   - Group discussion of tough scenarios
   - Tie to your management training program
   - Consider pairing high-scoring managers with those who scored lower

## Advanced: Build a Management Playbook

Use quiz results to create a management playbook:

**Step 1:** Review quiz results
**Step 2:** Identify scenarios where team has different answers
**Step 3:** Discuss: "What would a great manager do here?"
**Step 4:** Document as your company's "right way" to handle that situation
**Step 5:** Use the playbook to train new managers

This turns quiz data into organizational learning!

## Measuring Impact

Track these indicators:
- Manager quiz scores
- Employee engagement scores (after managers take quiz)
- Voluntary turnover (good managers reduce it)
- Internal promotion rate (good managers develop talent)
- Performance review feedback (consistency improves)

---

**Need help?** See [README.md](README.md) or [../../docs/TROUBLESHOOTING.md](../../docs/TROUBLESHOOTING.md)
