# Deploying to Rise 360

Step-by-step guide to get your interactive quiz live in Rise 360.

## Prerequisites

- Rise 360 account with course creation permissions
- Your completed `index.html` file with `quiz-data.json` in same folder
- Modern browser (Chrome, Safari, Firefox, Edge)

## Step-by-Step Deployment

### Step 1: Test Locally First

Before deploying to Rise, test your quiz locally:

1. Open `index.html` in your browser
2. Complete the entire quiz
3. Verify:
   - All scenarios load
   - Scoring calculates correctly
   - Feedback displays properly
   - Results summary shows all responses
4. Test on mobile browser too

**If anything is broken, fix it NOW before copying to Rise.**

### Step 2: Copy the HTML Code

1. Open `index.html` in any text editor (Notepad, VS Code, etc.)
2. Select all code:
   - **Windows:** Ctrl+A then Ctrl+C
   - **Mac:** Cmd+A then Cmd+C
3. Code is now in your clipboard

### Step 3: Create a Lesson in Rise

1. In your Rise course, click **Add Lesson**
2. Give it a name (e.g., "Sales Objection Handler")
3. Click **Create**

### Step 4: Add Content Block

1. In the lesson, click **Add Content Block**
2. A menu appears with content types
3. Find and select **Web Object**

### Step 5: Choose Custom HTML

1. After selecting Web Object, you get more options
2. Select **Custom HTML**
3. A code editor box appears

### Step 6: Paste Your Code

1. Click in the code editor box
2. Paste your HTML code:
   - **Windows:** Ctrl+V
   - **Mac:** Cmd+V
3. The entire `index.html` code is now in Rise

### Step 7: Save

1. Click **Save** button
2. Rise processes your code

### Step 8: Preview & Test

1. In the lesson, click **Preview**
2. Take the quiz from start to finish
3. Verify:
   - Looks good visually
   - All scenarios appear
   - Scoring works correctly
   - Feedback shows properly
   - Results display at end
   - Mobile view looks okay

**If something's broken, you can still edit:**
- Click the content block
- Click **Edit**
- Fix the issue
- Save again

### Step 9: Publish

1. Close preview
2. Click **Publish** to publish the lesson
3. The lesson is now live

### Step 10: Add to Course

1. Go back to your course
2. Add the lesson where you want it
3. The quiz is now in your course!

### Step 11: Assign to Learners

1. Publish the course
2. Assign to learners
3. Learners see the quiz in their course
4. They take it and earn a score
5. Scores appear in Rise gradebook

## Important Notes

### Scores in Rise Gradebook

✅ **Good news:** Rise tracks completion and can show scores
⚠️ **Limitation:** Rise may not automatically capture individual response scores (this depends on your Rise version)

**Workaround:** 
- The quiz shows results to the learner
- Ask learners to screenshot results if you need records
- Or download quiz data separately if needed

### Mobile Experience

✅ **Works on mobile!**
- Quiz is fully responsive
- Touch-friendly option buttons
- Works on iPhone, Android, tablets
- Test on actual mobile devices before deploying

### Offline vs Online

✅ **Works offline in Rise**
- Learners can take the quiz without internet (within Rise)
- Quiz data (quiz-data.json) is embedded in the HTML
- Scores are calculated client-side

### Browser Compatibility

✅ **Tested on:**
- Chrome 90+
- Safari 14+
- Firefox 88+
- Edge 90+
- Mobile Safari (iOS)
- Chrome Mobile (Android)

## Updating Your Quiz

If you need to update the quiz after deploying:

### Option 1: Update the Content Block (Simple)

1. Go to the lesson
2. Click the quiz content block
3. Click **Edit**
4. Update the code
5. Click **Save**
6. The quiz updates for all learners (next time they access it)

### Option 2: Create a New Version

If you want learners who already took the quiz to retake an updated version:

1. Create a new lesson with the updated quiz
2. Add it to your course
3. Publish

## Troubleshooting

### Quiz won't load / shows blank page

**Problem:** Maybe your HTML got corrupted when pasting

**Solution:**
1. Check your HTML in the code editor for obvious errors
2. Try copying directly from a text editor instead of clipboard
3. Make sure the entire HTML is there (check file size is same as original)

### Feedback not showing

**Problem:** Likely JSON syntax error in quiz-data.json

**Solution:**
1. Validate your JSON at [jsonlint.com](https://www.jsonlint.com)
2. Fix any errors shown
3. Update the HTML with corrected JSON
4. Save in Rise

### Styling looks wrong

**Problem:** Rise might be overriding some CSS

**Solution:**
1. The core quiz still works, styling is secondary
2. If critical, reach out to Rise support
3. Most styling issues are visual only, functionality is fine

### Scoring seems off

**Problem:** Check your scoring in quiz-data.json

**Solution:**
1. Verify each option has correct `score` value (0-3)
2. Verify mastery level thresholds (85, 70, 50, 0)
3. Example: 6 scenarios = 18 points max (6 × 3)
4. Validate JSON at [jsonlint.com](https://www.jsonlint.com)

## Tips for Success

1. **Test locally first** - Catch issues before Rise
2. **Keep a backup** - Save your original files in a folder
3. **Document your quiz** - Add notes on what it covers
4. **Monitor completion** - See who's taking it and their scores
5. **Iterate** - Collect feedback and improve over time

## Alternative: Host on GitHub Pages (Optional)

Want to host the quiz publicly?

1. Create a GitHub repo
2. Push your files
3. Enable GitHub Pages
4. Get a live URL: `https://your-org.github.io/your-repo/index.html`
5. Share the link or embed in Rise using an iFrame

See [GitHub Pages Guide](../GITHUB_SETUP_GUIDE.md) for details.

---

## Next Steps

- **Done?** Share the quiz with your team!
- **Questions?** See [TROUBLESHOOTING.md](TROUBLESHOOTING.md)
- **Want to customize?** See [CUSTOMIZATION_GUIDE.md](CUSTOMIZATION_GUIDE.md)
