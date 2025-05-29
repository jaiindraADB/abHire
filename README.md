<div className="overflow-x-auto w-full flex justify-center">
  <table className="table-auto border-collapse border border-gray-200 dark:border-white/[0.1] w-auto">
    <thead className="bg-gray-50 dark:bg-white/[0.03]">
      <tr>
        <th className="border border-gray-200 dark:border-white/[0.05] px-4 py-2">#</th>
        {[
          { key: "company", label: "Company" },
          { key: "title", label: "Title" },
          { key: "start_date", label: "Start Date" },
          { key: "end_date", label: "End Date" },
          { key: "is_current", label: "Is Current" },
          { key: "duration_in_months", label: "Duration (Months)" },
          { key: "profile_id", label: "Profile ID" }
        ].map(({ key, label }) => (
          <th
            key={key}
            className="px-4 py-2 border border-gray-200 dark:border-white/[0.05] text-sm text-gray-700 dark:text-gray-400 font-semibold text-left"
          >
            {label}
          </th>
        ))}
        <th className="px-4 py-2 border border-gray-200 dark:border-white/[0.05] text-sm text-gray-700 dark:text-gray-400 font-semibold text-left">
          Action
        </th>
      </tr>
    </thead>
    <tbody>
      {[
        {
          company: "Birla Opus",
          title: "Frontend Intern",
          start_date: "2024-01-10",
          end_date: "2024-06-10",
          is_current: "No",
          duration_in_months: 5,
          profile_id: "USR123"
        },
        {
          company: "OpenAI",
          title: "AI Research Intern",
          start_date: "2025-02-01",
          end_date: "",
          is_current: "Yes",
          duration_in_months: 3,
          profile_id: "USR456"
        }
      ].map((row, index) => (
        <tr key={index} className="bg-white dark:bg-gray-900 hover:bg-gray-50 dark:hover:bg-gray-800">
          <td className="border px-4 py-2 text-sm text-gray-800 dark:text-gray-200">{index + 1}</td>
          <td className="border px-4 py-2">{row.company}</td>
          <td className="border px-4 py-2">{row.title}</td>
          <td className="border px-4 py-2">{row.start_date}</td>
          <td className="border px-4 py-2">{row.end_date || "-"}</td>
          <td className="border px-4 py-2">{row.is_current}</td>
          <td className="border px-4 py-2">{row.duration_in_months}</td>
          <td className="border px-4 py-2">{row.profile_id}</td>
          <td className="border px-4 py-2">
            <button className="text-blue-600 hover:underline dark:text-blue-400">Edit</button>
          </td>
        </tr>
      ))}
    </tbody>
  </table>
</div>
