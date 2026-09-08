# JSON Schema Reference

Complete documentation of the quiz data structure.

## Full Structure

```json
{
  "title": "Quiz Title",
  "description": "Brief description of the quiz",
  "estimated_completion_minutes": 10,
  "scenarios": [
    {
      "id": 1,
      "scenario": "Scenario Title",
      "customerSays": "The situation or objection",
      "question": "What's your response?",
      "options": [
        {
          "text": "Response option text",
          "score": 3,
          "feedback": "Coaching feedback for this response",
          "branch": 2
        }
      ]
    }
  ],
  "masteryLevels": [
    {
      "threshold": 85,
      "label": "Elite 🏆",
      "description": "Mastery level description"
    }
  ]
}
```

## Field Reference

### Root Level

| Field | Type | Required | Description | Example |
|-------|------|----------|-------------|---------|
| `title` | string | Yes | Quiz title displayed at top | "Sales Objection Handler" |
| `description` | string | Yes | One sentence on learning outcome | "Practice handling sales objections" |
| `estimated_completion_minutes` | number | No | How long quiz takes | 10 |
| `scenarios` | array | Yes | Array of scenario objects | [ { ... } ] |
| `masteryLevels` | array | No | Array of mastery level definitions | [ { ... } ] |

### Scenario Object

| Field | Type | Required | Description | Example |
|-------|------|----------|-------------|---------|
| `id` | number | Yes | Unique scenario ID (1, 2, 3...) | 1 |
| `scenario` | string | Yes | Scenario title/heading | "Price Objection" |
| `customerSays` | string | Yes | The situation/objection statement | "Your competitor costs 40% less." |
| `question` | string | Yes | Question prompt for learner | "How do you respond?" |
| `options` | array | Yes | Array of response options | [ { ... } ] |

### Option Object

| Field | Type | Required | Description | Example |
|-------|------|----------|-------------|---------|
| `text` | string | Yes | Response option text | "Our solution includes X, Y, Z" |
| `score` | 0-3 | Yes | Points for this answer | 3 |
| `feedback` | string | Yes | Coaching message | "Excellent! You pivoted to value..." |
| `branch` | number | No | Next scenario ID to show (branching) | 5 |

### Mastery Level Object

| Field | Type | Required | Description | Example |
|-------|------|----------|-------------|---------|
| `threshold` | number | Yes | Percentage threshold (0-100) | 85 |
| `label` | string | Yes | Mastery level label with emoji | "Elite 🏆" |
| `description` | string | Yes | What this level means | "You consistently..." |

## Scoring Guide

Use this scoring framework:

- **`score: 3`** - Elite response (best practice, fully correct)
- **`score: 2`** - Good response (helpful, acceptable, but could improve)
- **`score: 1`** - Weak response (misses a key element or partially wrong)
- **`score: 0`** - Poor response (counterproductive, clearly wrong, or harmful)

**Total possible score** = number of scenarios × 3

Example: 6 scenarios = 18 points possible

## Mastery Level Guide

Standard mastery levels:

```json
"masteryLevels": [
  {
    "threshold": 85,
    "label": "Elite 🏆",
    "description": "You consistently choose strong responses..."
  },
  {
    "threshold": 70,
    "label": "Skilled 💼",
    "description": "You handle most scenarios well..."
  },
  {
    "threshold": 50,
    "label": "Developing 📈",
    "description": "You're building confidence..."
  },
  {
    "threshold": 0,
    "label": "Keep Practicing 🎯",
    "description": "Every response is a learning opportunity..."
  }
]
```

**Important:** Thresholds should be in descending order (highest first).

## Complete Example

```json
{
  "title": "Sales Objection Handler",
  "description": "Practice handling real-world sales objections with confidence",
  "estimated_completion_minutes": 12,
  "scenarios": [
    {
      "id": 1,
      "scenario": "Price Objection",
      "customerSays": "Your competitor costs 40% less. Why should I pay more?",
      "question": "How do you respond?",
      "options": [
        {
          "text": "Our solution includes premium support, faster implementation, and 99.99% uptime.",
          "score": 3,
          "feedback": "✓ Excellent! You pivoted from price to value with specific proof points."
        },
        {
          "text": "You get what you pay for.",
          "score": 2,
          "feedback": "Good! You contrasted value, but could name specific features we have that competitors don't."
        },
        {
          "text": "Let me get back to you with pricing data.",
          "score": 1,
          "feedback": "⚠️ You've given them time to shop. Address value FIRST, then price."
        },
        {
          "text": "If you think we're expensive, you don't understand our value.",
          "score": 0,
          "feedback": "❌ Dismissive. Instead listen: 'Cost matters. Let me show you the ROI...'"
        }
      ]
    },
    {
      "id": 2,
      "scenario": "Feature Gap",
      "customerSays": "Your solution doesn't have real-time reporting.",
      "question": "What's your move?",
      "options": [
        {
          "text": "Actually, we do - it's in our Analytics Dashboard. Plus we include automated alerts.",
          "score": 3,
          "feedback": "Perfect! You corrected the misconception AND added value."
        }
      ]
    }
  ],
  "masteryLevels": [
    {
      "threshold": 85,
      "label": "Elite Closer 🏆",
      "description": "You consistently handle objections with confidence and close deals."
    },
    {
      "threshold": 70,
      "label": "Skilled Negotiator 💼",
      "description": "You handle most objections well. Focus on scenarios where you scored lower."
    },
    {
      "threshold": 50,
      "label": "Developing 📈",
      "description": "You're building confidence. Review your lower scores carefully."
    },
    {
      "threshold": 0,
      "label": "Keep Practicing 🎯",
      "description": "Every objection is a learning opportunity. Study feedback and retake."
    }
  ]
}
```

## Optional: Branching

For advanced quizzes with branching (different paths based on answers):

```json
{
  "text": "Strong response",
  "score": 3,
  "feedback": "Great job!",
  "branch": 5
}
```

This tells the quiz to jump to scenario `id: 5` after this response. Without a `branch` field, it moves to the next scenario in order.

## Validation

**Valid JSON:**
- All strings in double quotes
- All objects have commas between fields
- Arrays properly closed with brackets
- No trailing commas

**Check your JSON:**
Use [jsonlint.com](https://www.jsonlint.com) to validate before deploying.

Common errors:
```json
❌ Missing comma:
{
  "title": "Quiz"
  "description": "Missing comma"
}

✓ Correct:
{
  "title": "Quiz",
  "description": "Now it has comma"
}
```

---

## See Also

- [CUSTOMIZATION_GUIDE.md](CUSTOMIZATION_GUIDE.md) - How to edit quizzes
- [RISE_INTEGRATION.md](RISE_INTEGRATION.md) - Deploying to Rise 360
- [TROUBLESHOOTING.md](TROUBLESHOOTING.md) - Common issues and fixes
