# Frequently Asked Questions

## General Questions

### Q: Do I need to know JavaScript or coding?
**A:** No! Just edit the JSON file with your scenarios. The HTML does all the heavy lifting.

### Q: Can I use this with LMS besides Rise 360?
**A:** Yes! Any LMS that supports code blocks works: Canvas, Blackboard, Moodle, Articulate Online, etc. Same copy/paste process.

### Q: How many scenarios should I include?
**A:** 4-6 is ideal. Keeps quiz under 10 minutes. Too many scenarios = quiz fatigue and lower completion.

### Q: Can I make it longer than 10 minutes?
**A:** Yes, just add more scenarios. But consider:
- Attention span declines after 10-15 minutes
- Longer quizzes have lower completion rates
- Better to break into multiple shorter quizzes

### Q: Can I make it shorter?
**A:** Yes! 2-3 scenarios works fine for quick knowledge checks. Minimum is 1 scenario (though that's just a question, not really a quiz).

---

## Technical Questions

### Q: Can I change the colors?
**A:** Yes! In the HTML, find the `<style>` section and look for `#667eea` (purple) and `#764ba2` (darker purple). Use [colorpicker.com](https://colorpicker.com) to get hex codes for your brand colors.

### Q: Can I randomize the order of scenarios?
**A:** Yes, but requires code modification. See [ADVANCED_FEATURES.md](ADVANCED_FEATURES.md).

### Q: Can I randomize the order of options?
**A:** For security reasons, we don't randomize options (prevents memorizing answers). But you can manually reorder options in `quiz-data.json` for each scenario.

### Q: Can I add images or videos to scenarios?
**A:** Not in the base template (HTML would get too large). But you can:
- Use very short descriptions instead
- Add images/videos in Rise separately and reference them
- Contact your developer if you want image support

### Q: Can I export the results?
**A:** The quiz shows results to the learner on screen. To export:
- Learner can screenshot results
- Rise gradebook might capture scores (varies by version)
- See [ADVANCED_FEATURES.md](ADVANCED_FEATURES.md) for API export options

### Q: How do I track who took the quiz?
**A:** Rise 360 tracks completion automatically. If using outside Rise, you'd need custom integration with your LMS or custom code.

### Q: Can I give partial credit?
**A:** Yes! Use scoring 0, 1, 2, 3:
- `0` = Wrong
- `1` = Partially correct
- `2` = Good but not perfect
- `3` = Excellent

### Q: Can I have different quiz versions?
**A:** Yes! Create multiple `.json` files or multiple folders. Each with their own `index.html` and `quiz-data.json`.

---

## Learning & Assessment Questions

### Q: Can I use this for compliance training?
**A:** Absolutely! Create strict right/wrong scenarios. Use scoring `3` or `0` only (no gray area).

### Q: Can I track which questions learners miss most?
**A:** The quiz doesn't have built-in analytics. But you can:
- Review results shown to learners
- Track completion in Rise
- Ask learners to report their weak areas
- Use [ADVANCED_FEATURES.md](ADVANCED_FEATURES.md) to export data

### Q: Can I require a passing score?
**A:** Yes! Add code to results section to prevent completion unless they pass (85%+).

### Q: Can I allow unlimited retakes?
**A:** Yes! The "Retake Quiz" button on results page already does this. Just click it.

### Q: Can I set a pass/fail threshold?
**A:** Yes! In `masteryLevels`, adjust thresholds:
- `threshold: 70` = Must score 70% to pass
- Adjust based on your requirements

### Q: Can I use this for self-paced learning?
**A:** Yes! Perfect for self-paced. Learners can take it anytime, anywhere (internet required for non-Rise versions).

### Q: Can I use this for instructor-led training?
**A:** Yes! Use as:
- Pre-training assessment
- In-class quiz
- Post-training assessment
- Homework assignment

### Q: How do I know if my quiz is effective?
**A:** Track these:
- Average score (target 70%+)
- Completion rate (target 90%+)
- Scores over time (should improve with retakes)
- Which scenarios have lowest scores (indicates content gaps)

---

## Customization Questions

### Q: Can I change the feedback?
**A:** Yes! Edit the `feedback` field in each option in `quiz-data.json`.

### Q: Can I change the mastery level labels?
**A:** Yes! Edit `masteryLevels` in `quiz-data.json`. Change the `label` to anything you want.

### Q: Can I add more mastery levels?
**A:** Yes! Add more objects to `masteryLevels` array. Just make sure thresholds are in descending order (85, 70, 50, 0).

### Q: Can I use different branching paths?
**A:** Yes! Add `branch` values to options. See [ADVANCED_FEATURES.md](ADVANCED_FEATURES.md).

### Q: Can I make it multilingual?
**A:** Yes, but requires code modification. Contact your developer.

---

## Deployment Questions

### Q: Will this work if my internet goes out?
**A:** Yes! Once the HTML loads in Rise, it works offline. Quiz-data is embedded in the HTML.

### Q: Does it work on mobile?
**A:** Yes! Fully responsive. Works on iPhone, Android, tablets, desktops.

### Q: Does it work on older browsers?
**A:** Modern browsers only (Chrome 90+, Safari 14+, Firefox 88+, Edge 90+). Old browsers might not work.

### Q: Can I embed it outside of Rise?
**A:** Yes! Use an `<iframe>` in any webpage or LMS:
```html
<iframe src="https://your-server.com/path/index.html" width="100%" height="800"></iframe>
```

### Q: Is my data secure?
**A:** Quiz runs 100% in the browser. No data is sent anywhere. Scoring happens locally. You control where (if anywhere) results go.

---

## Training Effectiveness Questions

### Q: How do I know if learners actually learned anything?
**A:** Compare:
- Pre-quiz score (before training)
- Post-quiz score (after training)
- Improvement = learning happened

### Q: Can I use this to assess prior knowledge?
**A:** Yes! Use as a pre-test. Then use same quiz as post-test to measure improvement.

### Q: Can I use different quizzes for pre/post testing?
**A:** Yes! Create multiple versions. Keep them similar difficulty but different content.

### Q: What's a good passing score?
**A:** Depends on your content:
- Compliance: Strict (85-100%)
- Skills training: 70%+
- Knowledge checks: 60%+
- Set based on your standards

### Q: How often should learners retake it?
**A:** Depends on your goals:
- Certification: Once, must pass
- Ongoing learning: Quarterly or annually
- Self-paced: Unlimited retakes encouraged

---

## Troubleshooting Questions

### Q: It says JSON error, what do I do?
**A:** 
1. Go to [jsonlint.com](https://www.jsonlint.com)
2. Paste your quiz-data.json
3. It tells you exactly what's wrong
4. Fix and try again

### Q: Quiz won't load when I open it locally
**A:**
1. Make sure `quiz-data.json` is in same folder as `index.html`
2. Try opening from a local web server instead
3. Or paste into Rise 360 (Rise hosts it)

### Q: Feedback doesn't show up
**A:** Check that each option has a `feedback` field:
```json
{
  "text": "Answer",
  "score": 3,
  "feedback": "This field is required!"
}
```

### Q: Scoring seems wrong
**A:** Check:
- Each answer has `score: 0, 1, 2, or 3`
- Thresholds are `85, 70, 50, 0`
- Math: 6 scenarios = 18 max points (6 × 3)

### Q: Still stuck?
See [TROUBLESHOOTING.md](TROUBLESHOOTING.md) for detailed troubleshooting guide.

---

## Getting Help

**For Questions About:**
- **This quiz template** → See the docs folder or email your learning team
- **Your quiz content** → Talk to your SME or manager
- **Technical issues** → Check [TROUBLESHOOTING.md](TROUBLESHOOTING.md)
- **Advanced customization** → Contact your development team

---

## Feedback

**Found a bug?** Open a GitHub issue.

**Have an idea?** Submit a pull request or contact your team.

**Want to share your quiz?** Fork the repo and add it to examples!
