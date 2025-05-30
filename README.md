<>
  <div className="flex flex-wrap gap-4">
    {/* Experience Table */}
    <div className="bg-white dark:bg-white/[0.03] p-6 rounded-xl shadow-md w-full lg:w-[100%]">
      <h4 className="text-lg font-semibold mb-4">Experience</h4>
      <Table>
        <TableHeader className="border-t border-gray-100 dark:border-white/[0.05]">
          <TableRow>
            <TableCell isHeader className="px-4 py-3 border border-gray-100 dark:border-white/[0.05]" />
            {[
              "Company",
              "Title",
              "Start Date",
              "End Date",
              "Is Current",
              "Duration (Months)",
            ].map((label, index) => (
              <TableCell
                key={index}
                isHeader
                className="px-4 py-3 border border-gray-100 dark:border-white/[0.05]"
              >
                <div
                  className="flex items-center justify-between cursor-pointer"
                  onClick={() =>
                    handleSort([
                      "company",
                      "Title",
                      "start_date",
                      "end_date",
                      "is_current",
                      "duration_in_months",
                    ][index] as SortKey)
                  }
                >
                  <p className="font-medium text-gray-700 text-theme-xs dark:text-gray-400">
                    {label}
                  </p>
                  <button className="flex flex-col gap-0.5">
                    <svg
                      className={`text-gray-300 dark:text-gray-700 ${
                        sortKey ===
                          [
                            "company",
                            "Title",
                            "start_date",
                            "end_date",
                            "is_current",
                            "duration_in_months",
                          ][index] && sortOrder === "asc"
                          ? "text-brand-500"
                          : ""
                      }`}
                      width="8"
                      height="5"
                      viewBox="0 0 8 5"
                      fill="none"
                    >
                      <path
                        d="M4.40962 0.585167C4.21057 0.300808 3.78943 0.300807 3.59038 0.585166L1.05071 4.21327C0.81874 4.54466 1.05582 5 1.46033 5H6.53967C6.94418 5 7.18126 4.54466 6.94929 4.21327L4.40962 0.585167Z"
                        fill="currentColor"
                      />
                    </svg>
                    <svg
                      className="text-gray-300 dark:text-gray-700"
                      width="8"
                      height="5"
                      viewBox="0 0 8 5"
                      fill="none"
                    >
                      <path
                        d="M4.40962 4.41483C4.21057 4.69919 3.78943 4.69919 3.59038 4.41483L1.05071 0.786732C0.81874 0.455343 1.05582 0 1.46033 0H6.53967C6.94418 0 7.18126 0.455342 6.94929 0.786731L4.40962 4.41483Z"
                        fill="currentColor"
                      />
                    </svg>
                  </button>
                </div>
              </TableCell>
            ))}
          </TableRow>
        </TableHeader>
        <TableBody>
          {experience.map((exp, index) => (
            <TableRow key={index}>
              <TableCell className="px-4 py-3 border border-gray-100 dark:border-white/[0.05]">
                <Checkbox />
              </TableCell>
              <TableCell className="px-4 py-3 border border-gray-100 dark:border-white/[0.05]">
                {exp.company}
              </TableCell>
              <TableCell className="px-4 py-3 border border-gray-100 dark:border-white/[0.05]">
                {exp.Title}
              </TableCell>
              <TableCell className="px-4 py-3 border border-gray-100 dark:border-white/[0.05]">
                {exp.start_date}
              </TableCell>
              <TableCell className="px-4 py-3 border border-gray-100 dark:border-white/[0.05]">
                {exp.end_date}
              </TableCell>
              <TableCell className="px-4 py-3 border border-gray-100 dark:border-white/[0.05]">
                {exp.is_current}
              </TableCell>
              <TableCell className="px-4 py-3 border border-gray-100 dark:border-white/[0.05]">
                {exp.duration_in_months}
              </TableCell>
            </TableRow>
          ))}
        </TableBody>
      </Table>
    </div>

    {/* Education Table */}
    <div className="bg-white dark:bg-white/[0.03] p-6 rounded-xl shadow-md w-full lg:w-[100%]">
      <h4 className="text-lg font-semibold mb-4">Education</h4>
      <Table>
        <TableHeader className="border-t border-gray-100 dark:border-white/[0.05]">
          <TableRow>
            <TableCell isHeader className="px-4 py-3 border border-gray-100 dark:border-white/[0.05]" />
            {["Degree", "Institution", "Start Year", "End Year"].map(
              (label, index) => (
                <TableCell
                  key={index}
                  isHeader
                  className="px-4 py-3 border border-gray-100 dark:border-white/[0.05]"
                >
                  <p className="font-medium text-gray-700 text-theme-xs dark:text-gray-400">
                    {label}
                  </p>
                </TableCell>
              )
            )}
          </TableRow>
        </TableHeader>
        <TableBody>
          {education.map((edu, index) => (
            <TableRow key={index}>
              <TableCell className="px-4 py-3 border border-gray-100 dark:border-white/[0.05]">
                <Checkbox />
              </TableCell>
              <TableCell className="px-4 py-3 border border-gray-100 dark:border-white/[0.05]">
                {edu.degree}
              </TableCell>
              <TableCell className="px-4 py-3 border border-gray-100 dark:border-white/[0.05]">
                {edu.institution}
              </TableCell>
              <TableCell className="px-4 py-3 border border-gray-100 dark:border-white/[0.05]">
                {edu.start_year}
              </TableCell>
              <TableCell className="px-4 py-3 border border-gray-100 dark:border-white/[0.05]">
                {edu.end_year}
              </TableCell>
            </TableRow>
          ))}
        </TableBody>
      </Table>
    </div>

    {/* Skills */}
    <div className="bg-white dark:bg-white/[0.03] p-6 rounded-xl shadow-md w-full lg:w-[100%]">
      <h4 className="text-lg font-semibold mb-4">Skills</h4>
      <div className="flex flex-wrap gap-4">
        {skills.map((skill, index) => (
          <span
            key={index}
            className="px-4 py-2 text-sm font-medium text-white bg-brand-500 rounded-full"
          >
            {skill}
          </span>
        ))}
      </div>
    </div>
  </div>
</>
