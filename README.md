import React, { useState } from "react";
import { FaEdit, FaTrash, FaPlus } from "react-icons/fa";

export default function AddressFieldsModal() {
  const [fields, setFields] = useState([]);
  const [formData, setFormData] = useState({
    fieldName: "",
    description: "",
    icon: "",
  });

  const handleAdd = () => {
    if (!formData.fieldName || !formData.description || !formData.icon) return;
    setFields([...fields, { ...formData }]);
    setFormData({ fieldName: "", description: "", icon: "" });
  };

  const handleDelete = (index) => {
    const updated = [...fields];
    updated.splice(index, 1);
    setFields(updated);
  };

  const handleInputChange = (e) => {
    setFormData({ ...formData, [e.target.name]: e.target.value });
  };

  return (
    <div className="fixed inset-0 bg-black bg-opacity-30 backdrop-blur-sm flex justify-center items-center z-50">
      <div className="bg-white rounded-xl shadow-lg p-6 w-[90%] max-w-3xl">
        <h2 className="text-2xl font-bold mb-4">Address Fields Configuration</h2>

        {/* Input fields */}
        <div className="grid grid-cols-1 sm:grid-cols-3 gap-4 mb-4">
          <input
            type="text"
            name="fieldName"
            value={formData.fieldName}
            onChange={handleInputChange}
            placeholder="Field Name"
            className="border p-2 rounded"
          />
          <input
            type="text"
            name="description"
            value={formData.description}
            onChange={handleInputChange}
            placeholder="Description"
            className="border p-2 rounded"
          />
          <input
            type="text"
            name="icon"
            value={formData.icon}
            onChange={handleInputChange}
            placeholder="Suggested Icon (Emoji or Text)"
            className="border p-2 rounded"
          />
        </div>

        <button
          onClick={handleAdd}
          className="bg-blue-600 text-white px-4 py-2 rounded flex items-center gap-2"
        >
          <FaPlus /> Add Field
        </button>

        {/* Table */}
        <div className="mt-6 overflow-x-auto">
          <table className="w-full border text-sm">
            <thead className="bg-gray-100 text-gray-700">
              <tr>
                <th className="p-2 text-left">Field Name</th>
                <th className="p-2 text-left">Description</th>
                <th className="p-2 text-left">Icon</th>
                <th className="p-2 text-center">Action</th>
              </tr>
            </thead>
            <tbody>
              {fields.map((field, idx) => (
                <tr key={idx} className="border-t">
                  <td className="p-2">{field.fieldName}</td>
                  <td className="p-2">{field.description}</td>
                  <td className="p-2 text-xl">{field.icon}</td>
                  <td className="p-2 text-center">
                    <button
                      onClick={() => handleDelete(idx)}
                      className="text-red-600 hover:text-red-800"
                    >
                      <FaTrash />
                    </button>
                  </td>
                </tr>
              ))}
              {fields.length === 0 && (
                <tr>
                  <td colSpan="4" className="p-4 text-center text-gray-500">
                    No fields added yet.
                  </td>
                </tr>
              )}
            </tbody>
          </table>
        </div>

        {/* Close button */}
        <div className="mt-6 text-right">
          <button className="bg-gray-200 px-4 py-2 rounded hover:bg-gray-300">
            Close
          </button>
        </div>
      </div>
    </div>
  );
}
![image](https://github.com/user-attachments/assets/add9c3ed-c9df-4138-868b-60f73bc53651)
