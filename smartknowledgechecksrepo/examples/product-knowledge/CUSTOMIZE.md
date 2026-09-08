# Customize for Your Product Line

## Quick Start

Replace these in `quiz-data.json`:
- Product/feature names with YOUR products
- Customer scenarios with YOUR real use cases
- Correct answers with YOUR product capabilities

## Editing Scenarios

### Step 1: Identify Your Key Products
What are your top 5 products or features?
- Product A (use case)
- Product B (use case)
- Product C (use case)
- etc.

### Step 2: Create Realistic Scenarios
Use ACTUAL customer situations:

**Example:**
```json
{
  "id": 1,
  "scenario": "Your Product Use Case",
  "customerSays": "Describe an actual customer problem your team has solved",
  "question": "Which product solves this?",
  "options": [
    {
      "text": "Your Product Name - brief explanation of how it solves the problem",
      "score": 3,
      "feedback": "✓ Correct! [Your Product] solves this because [specific benefit]."
    },
    {
      "text": "Wrong product or wrong approach",
      "score": 0,
      "feedback": "❌ That's not the right fit. The answer is [Your Product] because [why]."
    }
  ]
}
```

### Step 3: Make Feedback Business-Focused
Good product knowledge feedback:
```json
"feedback": "✓ Perfect! You matched the customer need (multi-channel selling) to our solution (Omnichannel Platform). This is an upsell opportunity - they don't know we have it."
```

### Step 4: Test with Your Sales Team
Before deploying:
1. Have 5-10 reps take the quiz
2. See which scenarios are confusing
3. Revise based on their feedback
4. Deploy with manager introduction

## Example Customizations

### For Software Company
```json
{
  "id": 1,
  "scenario": "Enterprise Security Needs",
  "customerSays": "We need SSO, SAML, and data encryption for our 500-person company.",
  "question": "Which plan do they need?",
  "options": [
    {
      "text": "Enterprise Plan - includes SSO, SAML, advanced encryption, and dedicated support",
      "score": 3,
      "feedback": "Perfect! This is exactly what Enterprise customers need. This is an upsell from Standard Plan."
    }
  ]
}
```

### For SaaS Product
```json
{
  "id": 2,
  "scenario": "High-Volume API Calls",
  "customerSays": "Our app makes 100k API calls per day. We're hitting rate limits on our current plan.",
  "question": "What do you recommend?",
  "options": [
    {
      "text": "Upgrade to our Scale plan - unlimited API calls, dedicated infrastructure, $5k/month",
      "score": 3,
      "feedback": "Correct! This is a natural upsell. They've outgrown Standard. Scale plan solves the rate limiting problem."
    }
  ]
}
```

### For Service Company
```json
{
  "id": 3,
  "scenario": "Implementation Support",
  "customerSays": "We're a startup with no tech expertise. We need help implementing the solution.",
  "question": "What service do they need?",
  "options": [
    {
      "text": "Our Implementation Services package - includes setup, training, and 30-day support",
      "score": 3,
      "feedback": "Exactly! Startups usually need Implementation Services. Without it, they struggle. This is a critical upsell."
    }
  ]
}
```

## Advanced: Create Product Matrices

Help your team understand which product for which customer:

```json
{
  "id": 1,
  "scenario": "Small Business (1-50 people)",
  "customerSays": "We need basic functionality, low cost, easy to use",
  "question": "Which product tier?",
  "options": [
    {
      "text": "Starter Plan - $99/month, core features, perfect entry point",
      "score": 3,
      "feedback": "✓ Correct! Starter is designed for small teams. Higher plans are overkill for their size."
    }
  ]
}
```

## Testing Your Changes

Before deploying:

✅ **Accuracy check:**
- [ ] All scenarios reflect REAL customer situations
- [ ] All correct answers match YOUR actual product capabilities
- [ ] Feedback explains the business reasoning
- [ ] Mastery levels make sense for YOUR sales team
- [ ] JSON is valid (check [jsonlint.com](https://www.jsonlint.com))

✅ **Sales team check:**
- [ ] Have 3-5 salespeople take the quiz
- [ ] Ask: "Are these realistic customer situations?"
- [ ] Ask: "Are the answers what you'd recommend?"
- [ ] Adjust based on their feedback

## Deploy Updated Version

1. Have sales leadership review
2. Copy updated `index.html`
3. Deploy to Rise 360
4. Email your team with context:
   - "This tests your product knowledge"
   - "Target score: 85%"
   - "Talk to [Product Manager] if you have questions"
5. Track scores and review low scores with reps

## Measuring Impact

Track these metrics:
- Average quiz score by team
- Score improvements over time
- Correlation with sales performance
- Product upsell rates (do product-trained reps sell more upgrades?)

---

**Need help?** See [README.md](README.md) or [../../docs/TROUBLESHOOTING.md](../../docs/TROUBLESHOOTING.md)
