const profileDetails = {
  firstName: "Harmeet",
  lastName: "Arora",
  email: "harmeeta2@gmail.com",
  phone: "7972195259",
  dob: "2025-08-02",
  experience: 111,
  noticePeriod: null,
  expectedJoiningDate: null,
  cvSummary:
    "Currently working as a Content Writer with Astral Informatics Limited since Feb 2022. Expertise in management and development of content for various websites. Passionate about learning new techniques and concepts.",
  currentSalary: "Current salary",
  expectedSalary: "Expected salary",
  gender: "Female",
  city: "city"
};

const profileHighlights = {
  tenureMonths: 39,
  teamMgmtExp: null,
  awardsCount: 2,
  longestDuration: 39,
  companiesWorked: 5,
  usp: "Passionate Content Writer with expertise in managing and developing content for various websites. Skilled in SEO strategies, keyword research, and creating compelling content across different niches."
};

const experienceData = [
  {
    company: "Astral Informatics Limited",
    title: "Content Writer",
    start_date: "2022-02-01",
    end_date: "2025-05-28",
    is_current: "true",
    duration_in_months: 39,
    profile_id: 40
  },
  {
    company: "Japji Travels",
    title: "Freelancer",
    start_date: "2022-01-01",
    end_date: "2023-01-01",
    is_current: "false",
    duration_in_months: 12,
    profile_id: 40
  },
  {
    company: "Talentica Software Ltd",
    title: "",
    start_date: "2012-11-01",
    end_date: "2016-01-01",
    is_current: "false",
    duration_in_months: 38,
    profile_id: 40
  },
  {
    company: "Aricent Group",
    title: "",
    start_date: "2011-07-01",
    end_date: "2012-07-01",
    is_current: "false",
    duration_in_months: 12,
    profile_id: 40
  },
  {
    company: "Videocon Industries (Mobiles)",
    title: "",
    start_date: "2010-08-01",
    end_date: "2011-06-01",
    is_current: "false",
    duration_in_months: 10,
    profile_id: 40
  }
];

export default function ProfileView() {
  return (
    <div className="d-flex flex-col">
      <div className="flex justify-center flex-wrap">
        {/* Profile Details Card */}
        <div className="card bg-white m-3 dark:bg-white/[0.03] p-6 rounded-xl shadow-md w-full lg:w-[35%]">
          <h4 className="card-title">Profile Details</h4>
          <div className="grid grid-cols-1 gap-4 lg:grid-cols-2 lg:gap-7 2xl:gap-x-32">
            {Object.entries({
              "First Name": profileDetails.firstName,
              "Last Name": profileDetails.lastName,
              Email: profileDetails.email,
              Phone: profileDetails.phone,
              "Date of Birth": profileDetails.dob,
              "Total Experience in Months": profileDetails.experience,
              "Notice Period": profileDetails.noticePeriod ?? "-",
              "Expected Joining Date": profileDetails.expectedJoiningDate ?? "-",
              "CV Summary": profileDetails.cvSummary,
              "Current Salary": profileDetails.currentSalary,
              "Expected Salary": profileDetails.expectedSalary,
              Gender: profileDetails.gender,
              City: profileDetails.city
            }).map(([label, value]) => (
              <div key={label}>
                <p className="subheader">{label}</p>
                <p className="content">{value}</p>
              </div>
            ))}
          </div>
        </div>

        {/* Profile Highlights Card */}
        <div className="card bg-white m-3 dark:bg-white/[0.03] p-6 rounded-xl shadow-md w-full lg:w-[38%] lg:h-[20%]">
          <h4 className="card-title">Profile Highlights</h4>
          <div className="grid grid-cols-1 gap-4 lg:grid-cols-2 lg:gap-7 2xl:gap-x-32">
            {Object.entries({
              "Current company Tenure months": profileHighlights.tenureMonths,
              "Team management experience months": profileHighlights.teamMgmtExp ?? "-",
              "Awards count": profileHighlights.awardsCount,
              "Longest company duration month": profileHighlights.longestDuration,
              "Companies worked": profileHighlights.companiesWorked,
              Usp: profileHighlights.usp
            }).map(([label, value]) => (
              <div key={label}>
                <p className="subheader">{label}</p>
                <p className="content">{value}</p>
              </div>
            ))}
          </div>
        </div>
      </div>

      {/* Experience Table */}
      <div className="ml-4 overflow-x-auto w-full">
        <table className="table-auto border-collapse border border-gray-200 dark:border-white/[0.1] w-auto">
          <thead className="bg-gray-50 dark:bg-white/[0.03]">
            <tr>
              <th className="border px-4 py-2">#</th>
              {["Company", "Title", "Start Date", "End Date", "Is Current", "Duration (Months)", "Profile ID", "Action"].map(
                (col) => (
                  <th
                    key={col}
                    className="px-4 py-2 border border-gray-200 dark:border-white/[0.05] text-sm text-gray-700 dark:text-gray-400 font-semibold text-left"
                  >
                    {col}
                  </th>
                )
              )}
            </tr>
          </thead>
          <tbody>
            {experienceData.map((row, index) => (
              <tr
                key={index}
                className="bg-white dark:bg-gray-900 hover:bg-gray-50 dark:hover:bg-gray-800"
              >
                <td className="border px-4 py-2">{index + 1}</td>
                <td className="border px-4 py-2">{row.company}</td>
                <td className="border px-4 py-2">{row.title || "-"}</td>
                <td className="border px-4 py-2">{row.start_date}</td>
                <td className="border px-4 py-2">{row.end_date || "-"}</td>
                <td className="border px-4 py-2">{row.is_current}</td>
                <td className="border px-4 py-2">{row.duration_in_months}</td>
                <td className="border px-4 py-2">{row.profile_id}</td>
                <td className="border px-4 py-2">
                  <button className="text-blue-600 hover:underline dark:text-blue-400">
                    Edit
                  </button>
                </td>
              </tr>
            ))}
          </tbody>
        </table>
      </div>
    </div>
  );
}
