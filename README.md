# AbHire HR Knowledge Base – Job Openings Module

## Overview
The **Job Openings** module allows HR administrators to manage all open job posts effectively. This includes adding new job listings, viewing current openings, and monitoring their status, experience requirements, assigned recruiters, and more.

---

## Features and Field Descriptions

| Field            | Description |
|------------------|-------------|
| **ID**           | Unique identifier for the job entry in the system. |
| **Code**         | Job code generated for internal tracking. |
| **Title**        | Title or designation of the job position (e.g., "Front End Developer"). |
| **Location**     | Geographic or remote location of the job. |
| **Open Posts**   | Number of openings for this job role. |
| **Created at**   | Date the job post was created. |
| **Status**       | Current progress of the hiring pipeline. E.g., `Active`, `Deleted`, `Initial Screening`, `Interview Scheduled`. |
| **Experience Level** | Indicates the level of experience required (e.g., Entry Level (0-2 Years), Mid Level (3-5 Years), etc.). |
| **Recruiters**   | HR staff assigned to this job post. |
| **Action**       | Options to edit or update the job post details. |

---

## Actions Available

- **Add New Job**: Opens a form to add a new job listing.
- **Show Entries**: Allows users to toggle between 10, 25, or 50 job entries per page.
- **Search**: Quickly search job posts by title, ID, recruiter, or location.
- **Status Options**:
  - `Active`: Job is visible and accepting applications.
  - `Initial Screening`: Job is in the first stage of hiring.
  - `Interview Scheduled`: Candidates are being interviewed.
  - `Deleted`: The job post is removed but retained for records.

---

## Usage Notes

- If no experience level is selected, the system defaults to **Mid Level (3-5 Years)**.
- Ensure job titles and codes are correctly filled for reporting accuracy.
- The `Action` column is important for updating or removing job posts.
- Use the **Search** feature to quickly locate job posts across large datasets.

---

## Screenshot Reference

> You can include UI screenshots under this section once available. Ensure each field mentioned above is annotated clearly in the image.

---

## Future Enhancements

- Filter jobs by experience level and recruiter.
- Bulk delete or archive inactive job posts.
- Export job listings as Excel or PDF.
