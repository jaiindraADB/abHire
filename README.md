import { useState } from "react";
import axios from "axios";

const API_BASE_URL = "https://abhirebackend.onrender.com";

export default function ProfileDetailsCard() {
  const [showModal, setShowModal] = useState(false);
  const [modalData, setModalData] = useState([]);
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState("");

  const openModal = async () => {
    setShowModal(true);
    setLoading(true);
    setError("");
    try {
      const response = await axios.get(`${API_BASE_URL}/hiringflow/steps`);
      if (Array.isArray(response.data?.data)) {
        setModalData(response.data.data);
      } else {
        setModalData([]);
        setError("No data found.");
      }
    } catch (err) {
      console.error("Modal fetch error:", err);
      setError("Failed to load data.");
    } finally {
      setLoading(false);
    }
  };

  const closeModal = () => {
    setShowModal(false);
    setModalData([]);
    setError("");
  };

  return (
    <div className="p-6">
      <button
        onClick={openModal}
        className="bg-blue-600 text-white px-4 py-2 rounded hover:bg-blue-700"
      >
        Open Modal
      </button>

      {showModal && (
        <div className="fixed inset-0 z-50 bg-black bg-opacity-40 flex items-center justify-center">
          <div className="bg-white rounded-lg shadow-xl p-6 w-full max-w-4xl relative">
            <h2 className="text-xl font-bold mb-4">Hiring Flow Steps</h2>

            {loading && (
              <div className="text-gray-600 mb-4">Loading data...</div>
            )}

            {error && (
              <div className="text-red-600 font-medium mb-4">{error}</div>
            )}

            {!loading && !error && modalData.length > 0 && (
              <table className="table-auto w-full border-collapse border border-gray-300">
                <thead className="bg-gray-100">
                  <tr>
                    <th className="border px-3 py-2">ID</th>
                    <th className="border px-3 py-2">Step Name</th>
                    <th className="border px-3 py-2">Step Code</th>
                    <th className="border px-3 py-2">Description</th>
                    <th className="border px-3 py-2">Level</th>
                    <th className="border px-3 py-2">Configurable</th>
                  </tr>
                </thead>
                <tbody>
                  {modalData.map((step, index) => (
                    <tr key={step.hiringflow_steps_master_id || index}>
                      <td className="border px-3 py-2">
                        {step.hiringflow_steps_master_id}
                      </td>
                      <td className="border px-3 py-2">{step.step_name}</td>
                      <td className="border px-3 py-2">{step.step_code}</td>
                      <td className="border px-3 py-2">{step.description}</td>
                      <td className="border px-3 py-2">{step.step_level}</td>
                      <td className="border px-3 py-2">
                        {step.is_configurable ? "Yes" : "No"}
                      </td>
                    </tr>
                  ))}
                </tbody>
              </table>
            )}

            {!loading && !error && modalData.length === 0 && (
              <div className="text-gray-500">No data available.</div>
            )}

            <button
              onClick={closeModal}
              className="absolute top-3 right-3 text-gray-500 hover:text-black"
            >
              ✕
            </button>
          </div>
        </div>
      )}
    </div>
  );
}
