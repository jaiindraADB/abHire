const [formData, setFormData] = useState({
  Client_Name: "",
  Location: "",
  country: "",
  Time_Zone: "",
  Contact_Person_Name: "",
  Email: "",
  contact_phone: "",
  Notes: "",
});
const adddTolist = () => {
  if (!formData.Client_Name || !formData.Location || !formData.country) {
    alert("Please fill all required fields.");
    return;
  }

  setClientProfile([...clientProfile, formData]);
  setFormData({
    Client_Name: "",
    Location: "",
    country: "",
    Time_Zone: "",
    Contact_Person_Name: "",
    Email: "",
    contact_phone: "",
    Notes: "",
  });
  closeModal();
};
<input
  type="text"
  name="Client_Name"
  value={formData.Client_Name}
  onChange={handleChange}
  placeholder="Field Name"
  className="..." // keep your classes
/>
