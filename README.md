/* Container */
.d-flex {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  padding: 1rem;
  background-color: #f9fafb; /* light background */
  min-height: 100vh;
}

/* Card */
.bg-white {
  background-color: #ffffff;
  border-radius: 1rem; /* rounded-xl */
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); /* subtle shadow */
  padding: 1.5rem; /* p-6 */
  max-width: 100%;
  overflow-x: auto; /* horizontal scroll on small screens */
}

/* Heading */
h4 {
  font-size: 1.125rem; /* text-lg */
  font-weight: 600; /* font-semibold */
  margin-bottom: 1rem; /* mb-4 */
  color: #111827; /* dark text */
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

/* Table */
table {
  width: 100%;
  border-collapse: collapse;
  border: 1px solid #d1d5db; /* border-gray-300 */
  font-family: Arial, sans-serif;
  font-size: 0.9rem;
}

/* Table Head */
thead {
  background-color: #f3f4f6; /* bg-gray-100 */
}

thead th {
  border: 1px solid #d1d5db;
  padding: 0.5rem 1rem;
  text-align: left;
  font-weight: 600;
  color: #374151; /* gray-700 */
}

/* Table Body */
tbody td {
  border: 1px solid #d1d5db;
  padding: 0.5rem 1rem;
  color: #4b5563; /* gray-600 */
}

/* Alternate Row Coloring */
tbody tr:nth-child(even) {
  background-color: #f9fafb; /* light gray */
}

/* Responsive: scroll horizontally on small screens */
@media (max-width: 640px) {
  table {
    display: block;
    overflow-x: auto;
    white-space: nowrap;
  }
}
