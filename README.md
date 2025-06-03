# AbHire HR Knowledge Base – Company Management Module

This document serves as a step-by-step guide to help **admins** understand the functionalities of the **Company Management Module** in the AbHire portal.

---

## 📁 Module: Company Info

This section stores the fundamental details of your company and allows you to update it at any time.

### 🔹 Basic Details
- **Company Name**: The official name of the organization.
- **Location**: A general reference to where the company operates.
- **Company Domain**: This field helps classify the type of business or technical domain.
- **Country, Currency, Time Zone**: Used to localize and tailor platform features accordingly.

✅ **Admin Action**: Use the “Edit” button to update basic company profile data.

---

### 🔹 Business Details
- **Description**: Short summary about the business.
- **Industry**: Default value is set to “Software.”
- **Company Size**: Choose from standard ranges (e.g., 1–10 employees).
- **Website & Phone Number**: Contact references.
- **GST No.**: For Indian tax compliance.

✅ **Admin Action**: All fields editable by clicking **Edit**.

---

### 🔹 Location
- **Full Address, City, State, Postal Code**: Used for correspondence.
- **Logo URL**: Image representing your company.
- **Google Map URL**: Location reference via Google Maps.

---

## 👥 Manage Team

### 🔹 Invite a Team Member
- **Enter email address** ending with your company's domain (e.g., `@adbinary.com`).
- **Select role**: Assign permission level (e.g., Recruiter, Admin).
- **Click Invite** to send an invitation.

### 🔹 Team Members Table
- Shows list of active users.
- **Actions**:
  - **Change Role**: Modify user access.
  - **Remove**: Delete a team member from the portal.

🔍 Search and Pagination available for efficient management.

---

## 💼 Subscription Plans

Admins can view and select subscription plans:
- **Basic Plan** – $49/month (5 users)
- **Pro Plan** – $199/month (10 users)
- **Enterprise** – Custom pricing (Contact Sales)

✅ Click “Select” to choose the required plan.

---

## 📚 Docsify Integration

To make this documentation browsable:

### Step 1: Install Docsify
```bash
npm i docsify-cli -g
docsify init ./docs
```

### Step 2: Place this Markdown file (`Company_Management_HR_Knowledge_Base.md`) inside the `./docs` folder.

### Step 3: Run the server locally
```bash
docsify serve docs
```

This will render the documentation with:
- Sidebar Navigation
- Markdown content
- Search & images
- Simple structure for easy maintenance

---

📌 **Tip:** Regularly update this file as portal features evolve.
