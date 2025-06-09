import React, { useState, useEffect } from "react";
import { Link } from "react-router-dom";

function PriorityModal() {
  const [isModalOpen, setIsModalOpen] = useState(false);
  const [priorities, setPriorities] = useState([]);
  const [loading, setLoading] = useState(false);
  const [error, setError] = useState(null);

  // Fetch priorities from API when modal opens
  useEffect(() => {
    if (isModalOpen) {
      setLoading(true);
      fetch("https://yourapi.com/priorities")  // Replace with actual Priority API URL
        .then((res) => {
          if (!res.ok) throw new Error("Failed to fetch priorities");
          return res.json();
        })
        .then((data) => {
          setPriorities(data); // Adjust based on API response structure
          setLoading(false);
        })
        .catch((err) => {
          setError(err.message);
          setLoading(false);
        });
    }
  }, [isModalOpen]);

  return (
    <>
      <button onClick={() => setIsModalOpen(true)}>
        Open Priority Modal
      </button>

      {isModalOpen && (
        <div style={modalStyles.overlay}>
          <div style={modalStyles.content}>
            <h2>Select Priority</h2>

            {loading && <p>Loading priorities...</p>}
            {error && <p style={{ color: "red" }}>{error}</p>}

            {!loading && !error && (
              <select>
                <option value="">Select Priority</option>
                {priorities.map((priority) => (
                  <option key={priority.id} value={priority.id}>
                    {priority.name}
                  </option>
                ))}
              </select>
            )}

            <div style={{ marginTop: "20px" }}>
              <Link to="/some-route" onClick={() => setIsModalOpen(false)}>
                Go to Some Page
              </Link>
            </div>

            <button
              style={{ marginTop: "10px" }}
              onClick={() => setIsModalOpen(false)}
            >
              Close
            </button>
          </div>
        </div>
      )}
    </>
  );
}

const modalStyles = {
  overlay: {
    position: "fixed",
    top: 0,
    left: 0,
    right: 0,
    bottom: 0,
    backgroundColor: "rgba(0,0,0,0.5)",
    display: "flex",
    justifyContent: "center",
    alignItems: "center",
  },
  content: {
    background: "#fff",
    padding: "20px",
    borderRadius: "5px",
    width: "300px",
    boxShadow: "0 2px 10px rgba(0,0,0,0.3)",
    textAlign: "center",
  },
};

export default PriorityModal;
