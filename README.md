# 🧾 Interview Scheduling Interface – Admin Guide

This page is designed to help **Admins and Recruiters** schedule interviews efficiently by selecting job openings, candidates, and interviewers—all in one unified interface.

---

## 1️⃣ Select Job Post

This section allows the admin to select the **job opening** for which the interview is being scheduled.

### 📌 Columns Explained:

| Field            | Description                               |
|------------------|-------------------------------------------|
| **Job Code**     | Unique identifier for the job posting     |
| **Title**        | Job title (e.g., Python Developer)        |
| **Location**     | Job location (e.g., Hyderabad)            |
| **Department**   | Department under which the job falls      |
| **Client**       | Associated client for this role           |
| **Open Positions** | Number of open slots to hire            |
| **Experience**   | Required experience level                 |
| **Salary**       | Offered salary                            |
| **Status**       | Job status (Active/Closed)                |
| **Recruiter**    | Assigned recruiter                        |
| **Notes**        | Any admin notes relevant to the posting   |

✅ **Action**: Click a job row to select it. This filters candidates and interviewers based on the selected job.

---

## 2️⃣ Select Candidate

Once a job is selected, eligible **candidates** appear here for scheduling interviews.

### 📌 Columns Explained:

| Field             | Description                                      |
|-------------------|--------------------------------------------------|
| **Name**          | Candidate's full name                            |
| **Phone**         | Contact number                                   |
| **Email**         | Email ID                                         |
| **Matching Score**| AI-generated score for job relevance             |
| **Status**        | Application status (e.g., Applied, Shortlisted)  |
| **Interview Stage** | Current round (e.g., Technical 1)              |
| **Notice Period** | Remaining notice period in days                  |
| **Expected CTC**  | Candidate’s expected salary                      |
| **Location**      | Candidate’s location                             |
| **AI Tip**        | AI-generated insight                             |
| **Notes**         | Recruiter notes                                  |

✅ **Action**: Click a candidate row to select and link to the job.

---

## 3️⃣ Interviewer and Recruiter

This section allows assigning interviewers for each interview round.

### 📌 Columns Explained:

| Field             | Description                                     |
|-------------------|-------------------------------------------------|
| **Selected**      | Checkbox to include this interviewer            |
| **Round No**      | Round number (e.g., 1, 2)                        |
| **Round Name**    | Round label (e.g., Tech, HR)                    |
| **Interviewer Name** | Full name of interviewer                     |
| **Duration**      | Interview time duration                         |
| **Interview Mode**| Online or In-person                             |
| **Calendar Type** | Type of calendar (Google, Outlook, etc.)        |
| **Email**         | Interviewer’s email                             |
| **TimeZone**      | Time zone of interviewer                        |
| **Interview Status** | Current scheduling status                    |
| **Interview Result** | Outcome (to be filled post-interview)       |

✅ **Action**: Fill in and select the checkbox to confirm the interviewer.

---

## 4️⃣ Interview Mode (Special Instruction)

If you choose **“In-person”**, this section becomes **mandatory**:

- **Add Location**: Specify the physical location.
- A **popup/modal** will appear to enter the address.

---

## 5️⃣ Interviewer Availability

This section reflects interviewer calendar availability.

| Field       | Description                              |
|-------------|------------------------------------------|
| **Date Time** | Suggested interview date and time     |
| **Availability** | Shows whether the slot is free     |
| **Schedule** | Slot available for scheduling           |

---

## ✅ Final Step: Save and Schedule

Once everything is configured:

1. Confirm selected Job Post and Candidate.
2. Assign Interviewers.
3. Set Interview Mode and Location (if needed).
4. Click **Schedule** to finalize and trigger calendar invites.

---

## 📌 Summary for Admins

| Task              | What to Do                            |
|-------------------|----------------------------------------|
| Select Job        | From “Select Job Post” section         |
| Choose Candidate  | From filtered list                     |
| Assign Interviewer| Tick checkbox, fill details            |
| Add Location      | If In-person mode selected             |
| Finalize          | Click “Schedule” to trigger invites    |

