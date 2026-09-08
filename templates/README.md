# Quiz Template

This folder contains the base template for creating interactive scenario quizzes.

## Files

- **`scenario-quiz-template.html`** - The main quiz application (self-contained, works standalone)
- **`quiz-data.template.json`** - Your data file template (edit this with your scenarios)

## 3-Step Setup

### Step 1: Copy Files
1. Copy `scenario-quiz-template.html` → rename to `index.html`
2. Copy `quiz-data.template.json` → rename to `quiz-data.json`
3. Keep both files in the same folder

### Step 2: Edit quiz-data.json
Open in any text editor and customize:
- Quiz title and description
- Scenarios (situations/objections)
- Response options
- Coaching feedback for each option
- Scoring (0-3 points per option)

### Step 3: Open index.html
1. Double-click `index.html` → opens in browser
2. Take the quiz to test it
3. Refresh browser after editing JSON to see changes

## Deploy to Rise 360

1. Open `index.html` in text editor
2. Copy all code (Ctrl+A → Ctrl+C)
3. In Rise 360:
   - Click **Add Content Block**
   - Select **Web Object**
   - Choose **Custom HTML**
   - **Paste code** → Save
4. Done! Your quiz is live.

## See Examples

Check the `examples/` folder for 4 working quizzes you can customize:
- Sales Objection Handler
- Compliance Training
- Product Knowledge
- Soft Skills Coaching

---

**Start here:** Pick an example from `examples/` folder and copy its structure!
