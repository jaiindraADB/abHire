import { useEffect, useState } from "react";
import axios from "axios";

const API_BASE_URL = "https://abhirebackend.onrender.com";

export default function ProfileDetailsCard() {
  const [data, setData] = useState([]);
  const [error, setError] = useState("");

  const [showModal, setShowModal] = useState(false);
  const [dropdownData, setDropdownData] = useState([]);
  const [loading, setLoading] = useState(true);
  const [dropdownError, setDropdownError] = useState("");

  // Fetch hiring flow steps
  useEffect(() => {
    const fetchData = async () => {
      try {
        const API_URL = `${API_BASE_URL}/hiringflow/steps`;
        const response = await axios.get(API_URL);

        if (Array.isArray(response.data?.data)) {
          setData(response.data.data);
        } else {
          setData([]);
          setError("No data found in response.");
        }
      } catch (err) {
        console.error("Fetch error:", err);
        setError("Failed to fetch data.");
      }
    };

    fetchData();
  }, []);

  // Modal functions
  const openModal = () => {
    setShowModal(true);
    fetchDropdownData();
  };

  const closeModal = () => {
    setShowModal(false);
  };

  const fetchDropdownData = async () => {
    setLoading(true);
    setDropdownError("");
    try {
      const response = await fetch("https://api.example.com/priority"); // Replace with real endpoint
      const data = await response.json();
      setDropdownData(data);
    } catch (err) {
      console.error("Dropdown API Error:", err);
      setDropdownError("Error loading data");
    } finally {
      setLoading(false);
    }
  };

  return (
    <div className="flex flex-col p-6">
      <div className="bg-white dark:bg-white/[0.03] mt-6 p-6 rounded-xl shadow-md w-full">
        <div className="flex justify-between items-center mb-4">
          <h4 className="text-lg font-semibold">Experience</h4>
          <button
            onClick={openModal}
            className="bg-blue-600 text-white px-4 py-2 rounded hover:bg-blue-700"
          >
            Open Modal
          </button>
        </div>

        {error && <div className="text-red-600 font-medium mb-4">{error}</div>}

        {data.length > 0 ? (
          <table className="table-auto w-full border-collapse border border-gray-300">
            <thead className="bg-gray-100">
              <tr>
                <th className="border px-4 py-2">ID</th>
                <th className="border px-4 py-2">Step Name</th>
                <th className="border px-4 py-2">Step Code</th>
                <th className="border px-4 py-2">Description</th>
                <th className="border px-4 py-2">Level</th>
                <th className="border px-4 py-2">Configurable</th>
              </tr>
            </thead>
            <tbody>
              {data.map((step, index) => (
                <tr key={step.hiringflow_steps_master_id || index}>
                  <td className="border px-4 py-2">
                    {step.hiringflow_steps_master_id}
                  </td>
                  <td className="border px-4 py-2">{step.step_name}</td>
                  <td className="border px-4 py-2">{step.step_code}</td>
                  <td className="border px-4 py-2">{step.description}</td>
                  <td className="border px-4 py-2">{step.step_level}</td>
                  <td className="border px-4 py-2">
                    {step.is_configurable ? "Yes" : "No"}
                  </td>
                </tr>
              ))}
            </tbody>
          </table>
        ) : (
          !error && (
            <div className="text-gray-500 mt-4">Loading or no steps available.</div>
          )
        )}
      </div>

      {/* Modal */}
      {showModal && (
        <div className="fixed inset-0 z-50 bg-black bg-opacity-50 flex items-center justify-center">
          <div className="bg-white p-6 rounded-lg shadow-lg w-full max-w-md">
            <h2 className="text-xl font-semibold mb-4">Select Priority</h2>

            <select className="w-full p-2 border rounded mb-4">
              {loading && <option>Loading...</option>}
              {dropdownError && <option>{dropdownError}</option>}
              {!loading &&
                !dropdownError &&
                dropdownData.map((item, index) => (
                  <option key={index} value={item.value}>
                    {item.label}
                  </option>
                ))}
            </select>

            <a
              href="next-page.html"
              className="text-blue-600 underline mb-4 block"
            >
              Go to Next Page
            </a>

            <button
              onClick={closeModal}
              className="bg-gray-600 text-white px-4 py-2 rounded hover:bg-gray-700"
            >
              Close
            </button>
          </div>
        </div>
      )}
    </div>
  );
}
