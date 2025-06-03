# ⚙️ Job Preferences – Admin Guide

This section enables administrators to **configure automated job matching and candidate shortlisting preferences** for a particular job opening. Proper configuration improves the accuracy of candidate screening through AI and automation features.

---

## 📊 Weight Configuration Settings

These weight percentages define how different factors are prioritized in the candidate shortlisting process. Enter values from **0% to 100%** based on importance.

| Field | Description |
|-------|-------------|
| **Skills Matching Threshold*** | Minimum match required between candidate and job-required skills (e.g., `70%`). |
| **Job Description Match Threshold*** | Candidate profiles must match this percentage of the job description content. |
| **Salary Expectation Weight*** | How heavily a candidate's salary expectations are weighed during shortlisting. |
| **Skill Match Weight*** | Defines the weight of skill matching in the overall ranking. |
| **Experience Weight*** | Determines how much work experience affects candidate scores. |
| **Notice Period Weight*** | Gives priority to candidates with shorter or preferred notice periods. |

---

## 🔎 Candidate Shortlisting

| Field | Description |
|-------|-------------|
| **Number of Candidates to Shortlist*** | Specify how many top-matching candidates to shortlist for review. |
| **Exclude Keywords** | Input keywords to filter out resumes. Example: `fresher`, `intern`, etc. |

This ensures irrelevant profiles are excluded during AI shortlisting.

---

## 🤖 Automation Settings

| Toggle | Function |
|--------|----------|
| **Enable Auto Screening** | Automatically screen candidates based on thresholds and weights. |
| **Enable WhatsApp Alerts** | Sends interview reminders and updates via WhatsApp. |
| **WhatsApp Alert Before Interview** | Select how long before the interview a message should be sent (e.g., `1 hour`, `1 day`). |
| **Number of AI Call Retries** | Define how many times the system should retry AI-based calling if the candidate does not respond. |

---

## 💾 Actions

- **Save Changes**: Apply all preference settings.
- **Close**: Exit without saving.

> ⚠️ Make sure all required fields (marked with `*`) are configured before saving to ensure AI-based shortlisting works effectively.

---

## 🔐 Admin Notes

Only authorized administrators should configure these settings. Improper threshold weights may result in inaccurate candidate shortlisting.

