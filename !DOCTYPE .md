<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Job Posting Summary</title>
  <script src="https://cdn.tailwindcss.com"></script>
</head>
<body class="bg-gray-50 p-6 font-sans text-gray-800">

  <!-- Job Form Summary -->
  <div class="mb-6 rounded-2xl shadow-lg border border-gray-200 p-6 bg-white">
    <details open class="space-y-4">
      <summary class="text-xl font-semibold cursor-pointer text-blue-700">📘 Job Posting Interface Summary</summary>

      <!-- Section 1 -->
      <div>
        <h2 class="text-lg font-semibold text-gray-800">1. Job Overview Section</h2>
        <p class="text-gray-600">Capture core job metadata including title, client name, location, type, and more.</p>
        <table class="table-auto w-full mt-2 text-sm text-gray-700 border border-gray-200">
          <tbody>
            <tr><td class="border px-4 py-2 font-medium">Job Title</td><td class="border px-4 py-2">e.g., Frontend Developer</td></tr>
            <tr><td class="border px-4 py-2 font-medium">Job Code</td><td class="border px-4 py-2">Internal reference</td></tr>
            <tr><td class="border px-4 py-2 font-medium">Client Name</td><td class="border px-4 py-2">Company name</td></tr>
            <tr><td class="border px-4 py-2 font-medium">Location</td><td class="border px-4 py-2">City or work location</td></tr>
            <tr><td class="border px-4 py-2 font-medium">Job Type</td><td class="border px-4 py-2">Contract, Full-Time, etc.</td></tr>
            <tr><td class="border px-4 py-2 font-medium">Work Hours</td><td class="border px-4 py-2">Optional time slot</td></tr>
            <tr><td class="border px-4 py-2 font-medium">Work Model</td><td class="border px-4 py-2">Hybrid, Remote, etc.</td></tr>
            <tr><td class="border px-4 py-2 font-medium">Open Positions</td><td class="border px-4 py-2">Number of vacancies</td></tr>
            <tr><td class="border px-4 py-2 font-medium">Industry</td><td class="border px-4 py-2">Field/domain like Technology</td></tr>
          </tbody>
        </table>
      </div>

      <!-- Section 2 -->
      <div>
        <h2 class="text-lg font-semibold text-gray-800">2. Salary Section</h2>
        <p class="text-gray-600">Define the compensation details for the position.</p>
        <table class="table-auto w-full mt-2 text-sm text-gray-700 border border-gray-200">
          <tbody>
            <tr><td class="border px-4 py-2 font-medium">Salary Currency</td><td class="border px-4 py-2">INR, USD, etc.</td></tr>
            <tr><td class="border px-4 py-2 font-medium">Salary Range</td><td class="border px-4 py-2">Minimum & Maximum Salary</td></tr>
          </tbody>
        </table>
      </div>

      <!-- Section 3 -->
      <div>
        <h2 class="text-lg font-semibold text-gray-800">3. Job Details Section</h2>
        <p class="text-gray-600">Detailed job expectations, qualifications, and internal notes.</p>
        <table class="table-auto w-full mt-2 text-sm text-gray-700 border border-gray-200">
          <tbody>
            <tr><td class="border px-4 py-2 font-medium">Job Description</td><td class="border px-4 py-2">Responsibilities, tools, etc.</td></tr>
            <tr><td class="border px-4 py-2 font-medium">Skills Required</td><td class="border px-4 py-2">Tags for filtering</td></tr>
            <tr><td class="border px-4 py-2 font-medium">Experience Level</td><td class="border px-4 py-2">Entry, Mid, Senior</td></tr>
            <tr><td class="border px-4 py-2 font-medium">Education Level</td><td class="border px-4 py-2">Bachelor's, Master's, etc.</td></tr>
            <tr><td class="border px-4 py-2 font-medium">Recruiter</td><td class="border px-4 py-2">Internal team member responsible</td></tr>
            <tr><td class="border px-4 py-2 font-medium">Notes</td><td class="border px-4 py-2">Private or client instructions</td></tr>
          </tbody>
        </table>
      </div>

      <!-- Section 4 -->
      <div>
        <h2 class="text-lg font-semibold text-gray-800">4. Interview Rounds Table</h2>
        <p class="text-gray-600">Configure multi-stage interviews with duration and automation.</p>
        <table class="table-auto w-full mt-2 text-sm text-gray-700 border border-gray-200">
          <tbody>
            <tr><td class="border px-4 py-2 font-medium">Add Round</td><td class="border px-4 py-2">Append new interview stages</td></tr>
            <tr><td class="border px-4 py-2 font-medium">AI Scheduling</td><td class="border px-4 py-2">Enable automated scheduling</td></tr>
            <tr><td class="border px-4 py-2 font-medium">Search Bar</td><td class="border px-4 py-2">Filter rounds efficiently</td></tr>
          </tbody>
        </table>
      </div>

      <!-- Section 5 -->
      <div>
        <h2 class="text-lg font-semibold text-gray-800">5. Additional Questions Table</h2>
        <p class="text-gray-600">Add screening questions for candidate evaluation.</p>
        <table class="table-auto w-full mt-2 text-sm text-gray-700 border border-gray-200">
          <tbody>
            <tr><td class="border px-4 py-2 font-medium">Add Question</td><td class="border px-4 py-2">Custom question & answer</td></tr>
            <tr><td class="border px-4 py-2 font-medium">Expected Answer</td><td class="border px-4 py-2">Optional correct response</td></tr>
            <tr><td class="border px-4 py-2 font-medium">Is Mandatory</td><td class="border px-4 py-2">Make field compulsory</td></tr>
          </tbody>
        </table>
      </div>

      <!-- Section 6 -->
      <div>
        <h2 class="text-lg font-semibold text-gray-800">6. Functional Highlights</h2>
        <ul class="list-disc list-inside text-gray-600 ml-4">
          <li>Responsive layout using <strong>Tailwind CSS</strong></li>
          <li>Expandable cards for better UX</li>
          <li>Future-ready: AI Job Post, Template Import, etc.</li>
        </ul>
      </div>

    </details>
  </div>

  <!-- Placeholder for job form -->
  <div class="bg-white p-6 border rounded-2xl shadow">
    <h2 class="text-xl font-semibold mb-4">📝 Job Posting Form</h2>
    <form>
      <!-- Your form elements go here -->
    </form>
  </div>

</body>
</html>
lets implement this code in an md file and link