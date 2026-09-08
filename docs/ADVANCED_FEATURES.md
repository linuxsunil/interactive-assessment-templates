# Advanced Features

Optional advanced features for complex quizzes.

## Branching (Different Paths Based on Answers)

Make scenarios connect based on learner responses.

### What It Does
- If learner selects a strong answer, show harder/different scenario next
- If learner selects weak answer, show remediation or recovery scenario
- Creates personalized learning paths

### How to Use

In your `quiz-data.json`, add `branch` to options:

```json
{
  "id": 1,
  "scenario": "Price Objection",
  "customerSays": "Your competitor costs less.",
  "options": [
    {
      "text": "Strong response",
      "score": 3,
      "feedback": "Great!",
      "branch": 5
    },
    {
      "text": "Weak response",
      "score": 0,
      "feedback": "Let's work on this...",
      "branch": 3
    }
  ]
}
```

The `branch` value is the scenario `id` to jump to next.

### Example: Sales Training
- Scenario 1: Price objection (good answer → branch to 5)
- Scenario 3: Recovery play (for weak answers to scenario 1)
- Scenario 5: Feature gap (for strong answers to scenario 1)

### Best Practices
- Without `branch`, quiz proceeds sequentially
- Use `branch` sparingly for complex paths
- Test different paths to ensure they all make sense
- Don't create loops (scenario A branches to B, B branches back to A)

---

## Time-Based Scoring (Optional Enhancement)

Want faster answers = more points? This requires code modification.

### How It Works
Track how fast learners answer. Bonus points for quick correct answers.

### Implementation
In `index.html`, find `selectOption` function and modify:

```javascript
function selectOption(index, totalOptions) {
  const q = quizData[currentQuestion];
  const selectedOption = q.options[index];
  
  // Track response time
  const responseTime = Date.now() - questionStartTime;
  
  // Bonus points for speed (optional)
  let finalScore = selectedOption.score;
  if (selectedOption.score >= 2 && responseTime < 15000) { // 15 seconds
    finalScore = Math.min(3, finalScore + 0.5); // Bonus max 0.5 points
  }
  
  score += finalScore;
  // ... rest of function
}
```

### Trade-offs
- ✅ Encourages quick thinking
- ❌ Penalizes thoughtful consideration
- ❌ More complex to implement and explain
- **Recommendation:** Use sparingly, only if training emphasizes speed

---

## Adaptive Difficulty (Optional Enhancement)

Make questions get harder based on performance.

### How It Works
Track streak of correct answers. Show harder scenarios when learner is doing well.

### Implementation
In `index.html`, modify before `renderQuestion`:

```javascript
// Track streak
let correctStreak = 0;

function selectOption(index, totalOptions) {
  const q = quizData[currentQuestion];
  const selectedOption = q.options[index];
  
  // Update streak
  if (selectedOption.score >= 2) {
    correctStreak++;
  } else {
    correctStreak = 0;
  }
  
  // Adjust next scenario based on streak
  if (correctStreak >= 2) {
    // Skip easier scenarios, show harder ones
  } else if (correctStreak === 0 && selectedOption.score === 0) {
    // Show remediation scenarios
  }
  // ... rest of function
}
```

### Trade-offs
- ✅ Personalizes experience
- ✅ Keeps strong learners challenged
- ❌ Complex to implement
- ❌ Requires careful scenario design
- **Recommendation:** Use only if you have 10+ scenarios

---

## Randomized Scenario Order (Optional Enhancement)

Shuffle scenarios so each learner gets different order (prevents cheating).

### Implementation
In `index.html`, after loading quizData, add:

```javascript
// Shuffle scenarios randomly
function shuffleArray(array) {
  for (let i = array.length - 1; i > 0; i--) {
    const j = Math.floor(Math.random() * (i + 1));
    [array[i], array[j]] = [array[j], array[i]];
  }
  return array;
}

async function loadQuizData() {
  // ... existing code ...
  quizData = shuffleArray(data.scenarios);
  // ... rest of function ...
}
```

### Considerations
- ✅ Prevents copying answers
- ⚠️ Harder to direct learners to specific scenarios
- ⚠️ Review by topic becomes harder

---

## Question Pools (Optional Enhancement)

Show random subset of questions instead of all scenarios.

### How It Works
If you have 20 scenarios but only want each learner to see 10 (random 10).

### Implementation
In `index.html`:

```javascript
async function loadQuizData() {
  const data = await fetch('quiz-data.json').then(r => r.json());
  
  // Show random 10 scenarios
  const numToShow = 10;
  const shuffled = shuffleArray(data.scenarios);
  quizData = shuffled.slice(0, numToShow);
  
  // ... rest of function ...
}
```

### Benefits
- More practice scenarios without longer quizzes
- Different experience for each learner
- Easier to prevent cheating

---

## Custom Styling Per Scenario (Advanced)

Apply different styling/colors to different scenarios.

### Implementation
In each scenario, add `style` field:

```json
{
  "id": 1,
  "scenario": "Title",
  "customerSays": "...",
  "style": {
    "borderColor": "#ff0000",
    "backgroundColor": "#ffe6e6"
  },
  "options": [...]
}
```

Then in `renderQuestion()`, apply the style:

```javascript
const style = q.style ? `style="border-left-color: ${q.style.borderColor}; background-color: ${q.style.backgroundColor};"` : '';
html += `<div class="scenario" ${style}>`;
```

### Use Cases
- Color code by difficulty (green=easy, red=hard)
- Color code by topic
- Visual variety to reduce fatigue

---

## Conditional Questions (Advanced)

Show different questions based on learner answers.

### Implementation
More complex - requires custom JavaScript modifications to branch logic.

Generally same as "branching" above, but with dynamic question selection.

---

## Certification/Compliance Passing

If you need learners to pass (score ≥ 80%), require retakes:

```html
<!-- In results, add -->
<button onclick="if(percentage < 80) { location.reload(); } else { /* mark complete */ }">
  Next
</button>
```

This forces retakes until passing.

---

## Collecting Additional Data

Want to collect learner name, department, etc. before the quiz?

Add a form before the quiz starts:

```html
<div id="formSection">
  <form onsubmit="startQuiz(event)">
    <label>Name: <input type="text" id="learnerName" required></label>
    <label>Department: <input type="text" id="learnerDept" required></label>
    <button type="submit">Start Quiz</button>
  </form>
</div>

<script>
function startQuiz(event) {
  event.preventDefault();
  const name = document.getElementById('learnerName').value;
  const dept = document.getElementById('learnerDept').value;
  // Store in session or send to server
  document.getElementById('formSection').style.display = 'none';
  loadQuizData();
}
</script>
```

---

## Exporting Results (Advanced)

Want to send quiz results to external system?

At the end of `showResults()`, add:

```javascript
// Send results to your server
fetch('https://your-server.com/api/quiz-results', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({
    learnerName: sessionData.name,
    score: score,
    maxScore: maxScore,
    responses: responses,
    timestamp: new Date()
  })
});
```

This requires a backend API to receive the data.

---

## When NOT to Use Advanced Features

- If your quiz is for basic learning (not needed)
- If your team doesn't have developers (too complex)
- If you're just getting started (start simple, add later)
- If you need to maintain it yourself (stick to basics)

---

## Recommended Starting Point

Begin with:
1. Basic 4-6 scenarios
2. Simple 3-4 option answers
3. Weighted scoring (0-3)
4. Clear feedback
5. Mastery levels

Once you have that working well, THEN add advanced features if needed.

---

## Getting Help with Advanced Features

These features require JavaScript knowledge:
- Talk to your development team
- Or contact the template maintainers
- Or consider hiring a developer for customization

---

**See Also:**
- [CUSTOMIZATION_GUIDE.md](CUSTOMIZATION_GUIDE.md) - Basic customization
- [JSON_SCHEMA.md](JSON_SCHEMA.md) - Data structure
