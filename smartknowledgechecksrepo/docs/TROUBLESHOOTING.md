# Troubleshooting Guide

Common issues and how to fix them.

## Quiz Won't Load or Shows Blank Page

### Symptom
Double-click `index.html` and see a blank page or error.

### Root Causes & Solutions

**Cause 1: Corrupted HTML file**
- Make sure `index.html` is in the same folder as `quiz-data.json`
- Both files must be together for the quiz to load
- Check file names are EXACTLY spelled correctly (case-sensitive on Mac/Linux)

**Cause 2: JSON file is missing**
- The quiz looks for `quiz-data.json` in the same folder
- If it can't find it, it loads embedded example data
- Make sure file is named exactly: `quiz-data.json` (not `quiz_data.json`, not `quizdata.json`)

**Cause 3: Browser security settings**
- Some browsers block local files for security reasons
- **Solution:** Open from a web server instead of directly from disk
- Easy option: Use Visual Studio Code's "Live Server" extension
- Or upload to Rise 360 (Rise hosts it, no local file issues)

**Cause 4: Very old browser**
- Quiz requires modern browser features
- Update to Chrome 90+, Safari 14+, Firefox 88+, or Edge 90+

### How to Debug
1. Right-click on page → **Inspect** (or press F12)
2. Click **Console** tab
3. Look for red error messages
4. Screenshot the error and look it up
5. Or contact your development team

---

## JSON Syntax Error (Quiz loads but won't work)

### Symptom
Quiz page loads but shows blank content, or options don't appear.

### Root Cause
JSON file has syntax error (missing comma, mismatched quotes, etc.).

### How to Fix

**Step 1: Validate your JSON**
1. Go to [jsonlint.com](https://www.jsonlint.com)
2. Copy your `quiz-data.json` and paste it
3. Click **Validate**
4. It tells you exactly what's wrong

**Common Errors:**

❌ **Missing comma:**
```json
{
  "title": "Quiz"
  "description": "Missing comma before this"
}
```
✓ **Fix:** Add comma after `"Quiz"`

❌ **Mismatched quotes:**
```json
{
  "title": 'Quiz with single quotes'
}
```
✓ **Fix:** Use double quotes: `"Quiz with double quotes"`

❌ **Trailing comma:**
```json
{
  "options": [
    { "text": "Option 1" },
    { "text": "Option 2" },  ← Remove comma after last item
  ]
}
```
✓ **Fix:** Remove comma after last item in array

❌ **Unmatched braces:**
```json
{
  "scenarios": [
    { "id": 1 }
  ]
}  ← Need another closing brace here
```
✓ **Fix:** Make sure every `{` has a matching `}`

---

## Feedback Not Showing

### Symptom
Click an answer, but no feedback appears.

### Root Cause
Option is missing `feedback` field in JSON.

### How to Fix
1. Open `quiz-data.json`
2. Find the option with no feedback
3. Add the `feedback` field:
```json
{
  "text": "Your option text",
  "score": 3,
  "feedback": "Add your feedback here!"
}
```
4. Save and refresh browser

---

## Scoring Seems Wrong

### Symptom
Final score doesn't match what you expected.

### Root Cause
Check your scoring setup.

### How to Fix

**Check 1: Each option has correct score**
```json
{
  "text": "Best answer",
  "score": 3,      ← Should be 0, 1, 2, or 3
  "feedback": "..."
}
```

**Check 2: Mastery levels make sense**
```json
"masteryLevels": [
  { "threshold": 85 },   ← Highest score
  { "threshold": 70 },
  { "threshold": 50 },
  { "threshold": 0 }     ← Lowest
]
```

**Check 3: Math adds up**
- Total possible = number of scenarios × 3
- Example: 5 scenarios = 15 points max
- Percentage = (score ÷ max) × 100
- Example: 12 points ÷ 15 = 80%

**Check 4: Validate JSON**
- Use [jsonlint.com](https://www.jsonlint.com)
- Syntax errors can cause scoring bugs

---

## Quiz Looks Bad on Mobile

### Symptom
Quiz displays strangely on phone/tablet.

### Root Cause
Usually browser issue, not quiz design (quiz is responsive).

### How to Fix

**Step 1: Update your browser**
- Make sure you're using recent version
- iOS: Update Safari in Settings → General → Software Update
- Android: Update Chrome from Play Store

**Step 2: Test in different browser**
- Try Safari, Chrome, Firefox
- One might work better than others

**Step 3: Check screen size**
- Some phones have unusual aspect ratios
- Quiz should still work, might just look different
- Core functionality works on all modern mobile browsers

**Step 4: Test locally vs in Rise**
- Try opening the HTML file on phone
- Also try opening via Rise 360
- One might work better than the other

---

## Can't Download Quiz or File Issues

### Symptom
When trying to copy `index.html` code, getting text corruption or incomplete text.

### Root Cause
Large files sometimes don't copy completely.

### How to Fix

**Option 1: Use a text editor**
1. Right-click `index.html`
2. Open with → Notepad (Windows) or TextEdit (Mac)
3. Select all (Ctrl+A or Cmd+A)
4. Copy (Ctrl+C or Cmd+C)
5. Then paste into Rise

**Option 2: Copy from the repo directly**
- If using from GitHub, download the whole file
- Don't copy/paste from a web browser view
- Download the raw file instead

**Option 3: Use a different method**
- Try uploading via Rise's file upload (if available)
- Or use different browser
- Or different text editor

---

## Rise 360 Specific Issues

### Scores not appearing in gradebook

**Root Cause:** Rise version or permission settings

**Solution:**
- Quiz WILL calculate scores locally
- Learners will SEE their score
- Rise gradebook might not capture it (depends on version)
- Workaround: Ask learners to screenshot results or note their score

### Custom HTML code box too small

**Root Cause:** Rise's default code editor is small

**Solution:**
1. Copy your code in a text editor first
2. Paste into Rise slowly or in chunks
3. Or use Rise's "expand" button if available
4. Save frequently to avoid losing work

### Quiz works locally but not in Rise

**Root Cause:** Usually file path issues

**Solution:**
1. Make sure `quiz-data.json` is in SAME folder as `index.html`
2. When you copy to Rise, you're pasting HTML only
3. The quiz-data.json needs to be embedded OR in same rise lesson
4. Easiest: Use the template that embeds data in HTML

---

## Colors Not Changing

### Symptom
Changed color codes in HTML but colors don't update.

### Root Cause
Cache or incorrect color code.

### How to Fix

**Step 1: Clear browser cache**
- Hard refresh: Ctrl+Shift+R (Windows) or Cmd+Shift+R (Mac)
- Or clear cookies/cache in browser settings

**Step 2: Verify color code format**
- Colors should be hex: `#667eea`
- Not rgb: `rgb(102, 126, 234)`
- Not named: `purple`
- Use [colorpicker.com](https://colorpicker.com) to get hex codes

**Step 3: Find all instances**
- Primary color `#667eea` might appear multiple times
- Search for the old color and replace ALL instances
- Save and refresh

---

## Text Overlapping or Layout Issues

### Symptom
Text is overlapping, buttons are too small, or layout is broken.

### Root Cause
CSS values or very unusual screen size.

### How to Fix

**Quick fix:**
1. Open the file in a different browser
2. Or try a different device
3. Or update your browser to latest version

**Detailed fix:**
1. Right-click → **Inspect** (or F12)
2. Look for CSS issues in the `<style>` section
3. Or in the Elements inspector
4. Adjust `padding`, `margin`, or `font-size` values
5. Refresh to see changes

---

## Quiz Works in Browser but Not in Rise

### Symptom
Opens fine locally, but blank/broken when pasted into Rise.

### Root Cause
Likely HTML got corrupted during copy/paste or file path issue.

### How to Fix

**Option 1: Copy-paste again**
1. Close Rise
2. Re-copy from original file in text editor
3. Paste into Rise again
4. Save

**Option 2: Check for file errors**
1. Open Browser developer tools (F12)
2. Click **Console**
3. Look for red error messages
4. Screenshot and investigate

**Option 3: Upload instead of paste**
- If Rise allows file upload, try that instead
- Sometimes file upload works better than copy-paste

---

## Getting Help

**If you're still stuck:**

1. **Check the documentation:**
   - [CUSTOMIZATION_GUIDE.md](CUSTOMIZATION_GUIDE.md) - How to edit
   - [JSON_SCHEMA.md](JSON_SCHEMA.md) - Data structure
   - [RISE_INTEGRATION.md](RISE_INTEGRATION.md) - Rise deployment

2. **Validate your files:**
   - JSON: [jsonlint.com](https://www.jsonlint.com)
   - HTML: Right-click → View Page Source

3. **Check browser console:**
   - Press F12 → Console tab
   - Look for error messages
   - Screenshot them

4. **Contact support:**
   - Ask your learning development manager
   - Or contact your IT team
   - Include screenshot of the error

---

## Still Need Help?

See the FAQ or contact your team's learning development lead.
