import Button from "../../components/ui/button/Button";
import { Modal } from "../../components/ui/modal";
import { useModal } from "../../hooks/useModal";
import { useState } from "react";
import {
  Table,
  TableBody,
  TableCell,
  TableHeader,
  TableRow
} from "../../components/ui/table";
import { SearchIcon } from "../../icons";
import Label from "../../components/form/Label";
import { Controller, useForm } from "react-hook-form";
import Select from "../../components/form/Select";
import { schema } from "../JobOpenings/JobEditor";
import { zodResolver } from "@hookform/resolvers/zod";

type SortKey =
  | "Client_Name"
  | "country"
  | "Location"
  | "Time_Zone"
  | "Contact_Person_Name"
  | "Email"
  | "Postal_code";

type SortOrder = "asc" | "desc";

const columnKeys: SortKey[] = [
  "Client_Name",
  "country",
  "Location",
  "Contact_Person_Name",
  "Email",
  "Time_Zone",
  "Postal_code"
];

const columnLabels = [
  "Client Name",
  "Country",
  "Location",
  "Contact Person Name",
  "Email",
  "Time Zone",
  "Postal Code",
  "Contact Phone",
  "Notes",
  "Address1",
  "Address2",
  "City",
  "State",
  "Landmark",
  "Google Maps URL"
];

const initialFormData = {
  Client_Name: "",
  Location: "",
  country: "",
  Time_Zone: "",
  Contact_Person_Name: "",
  Email: "",
  contact_phone: "",
  Notes: "",
  Address1: "",
  Address2: "",
  City: "",
  State: "",
  Postal_code: "",
  Landmark: "",
  Google_Maps_Url: ""
};

export default function ClientInformation() {
  const [formData, setFormData] = useState(initialFormData);
  const [clientProfile, setClientProfile] = useState<any[]>([]);
  const { isOpen, openModal, closeModal } = useModal();
  const [sortKey, setSortKey] = useState<SortKey>("Client_Name");
  const [sortOrder, setSortOrder] = useState<SortOrder>("asc");
  const [searchTerm, setSearchTerm] = useState("");

  const {
    control,
    formState: { errors }
  } = useForm({
    resolver: zodResolver(schema),
    mode: "onChange"
  });

  const handleChange = (e: React.ChangeEvent<HTMLInputElement>) => {
    const { name, value } = e.target;
    setFormData((prev) => ({
      ...prev,
      [name]: value
    }));
  };

  const handleSort = (key: SortKey) => {
    if (sortKey === key) {
      setSortOrder(sortOrder === "asc" ? "desc" : "asc");
    } else {
      setSortKey(key);
      setSortOrder("asc");
    }
  };

  const filteredClients = clientProfile.filter((client) =>
    Object.values(client)
      .join(" ")
      .toLowerCase()
      .includes(searchTerm.toLowerCase())
  );

  const sortedClients = [...filteredClients].sort((a, b) => {
    const aVal = a[sortKey] || "";
    const bVal = b[sortKey] || "";
    return sortOrder === "asc"
      ? aVal.localeCompare(bVal)
      : bVal.localeCompare(aVal);
  });

  const adddTolist = () => {
    const requiredFields = [
      "Client_Name",
      "Location",
      "country",
      "Contact_Person_Name",
      "Email"
    ];
    const hasMissing = requiredFields.some(
      (field) => !formData[field as keyof typeof formData]
    );

    if (hasMissing) {
      alert("Please fill all required fields.");
      return;
    }

    setClientProfile([...clientProfile, formData]);
    setFormData(initialFormData);
    closeModal();
  };

  const countryOptions = [
    { value: "USA", label: "USA" },
    { value: "India", label: "India" },
    { value: "UK", label: "UK" },
    { value: "Germany", label: "Germany" }
    // You can fetch these dynamically if needed
  ];

  return (
    <div className="flex flex-col">
      <div className="mt-6 p-6 rounded-xl shadow-md w-full bg-white dark:bg-white/[0.03]">
        <div className="flex justify-between items-center mb-4">
          <h4 className="text-lg font-semibold">Client Information</h4>
          <Button variant="outline" size="sm" onClick={openModal}>
            Add New Clients
          </Button>
        </div>

        <div className="flex justify-end py-4">
          <div className="relative">
            <SearchIcon className="absolute left-4 top-1/2 transform -translate-y-1/2 text-gray-500" />
            <input
              type="text"
              value={searchTerm}
              onChange={(e) => setSearchTerm(e.target.value)}
              placeholder="Search..."
              className="h-11 pl-11 pr-4 w-72 border rounded-lg text-sm dark:bg-gray-900 dark:text-white"
            />
          </div>
        </div>

        <Table>
          <TableHeader>
            <TableRow>
              {columnLabels.map((label, index) => (
                <TableCell
                  key={index}
                  isHeader
                  onClick={() => {
                    if (columnKeys[index]) handleSort(columnKeys[index]);
                  }}
                  className="cursor-pointer"
                >
                  <div className="flex items-center justify-between">
                    {label}
                    <div className="flex flex-col gap-0.5">
                      <svg
                        className={`h-2 ${
                          sortKey === columnKeys[index] && sortOrder === "asc"
                            ? "text-brand-500"
                            : "text-gray-300"
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
                        className={`h-2 ${
                          sortKey === columnKeys[index] && sortOrder === "desc"
                            ? "text-brand-500"
                            : "text-gray-300"
                        }`}
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
                    </div>
                  </div>
                </TableCell>
              ))}
            </TableRow>
          </TableHeader>

          <TableBody>
            {sortedClients.map((data, idx) => (
              <TableRow key={idx}>
                {[
                  data.Client_Name,
                  data.country,
                  data.Location,
                  data.Contact_Person_Name,
                  data.Email,
                  data.Time_Zone,
                  data.Postal_code,
                  data.contact_phone,
                  data.Notes,
                  data.Address1,
                  data.Address2,
                  data.City,
                  data.State,
                  data.Landmark,
                  data.Google_Maps_Url
                ].map((value, i) => (
                  <TableCell key={i}>{value}</TableCell>
                ))}
              </TableRow>
            ))}
          </TableBody>
        </Table>
      </div>

      {/* Modal Section */}
      <Modal isOpen={isOpen} onClose={closeModal} className="pl-7 pt-20 pb-10">
        <div className="ml-4">
          <h2 className="text-lg font-semibold mb-4">Basic Information</h2>
          <div className="grid grid-cols-2 gap-5 mb-6">
            {Object.keys(formData).map((key) => {
              if (key === "country") {
                return (
                  <div key={key}>
                    <Label htmlFor={key}>Country</Label>
                    <Controller
                      name={key}
                      control={control}
                      render={({ field }) => (
                        <Select
                          {...field}
                          options={countryOptions}
                          placeholder="Select country"
                          className="dark:bg-dark-900"
                          error={!!errors[key]}
                          hint={errors[key]?.message}
                          onChange={(value) => {
                            field.onChange(value);
                            setFormData({ ...formData, country: value });
                          }}
                        />
                      )}
                    />
                  </div>
                );
              }

              return (
                <div key={key}>
                  <Label htmlFor={key}>{key.replace(/_/g, " ")}</Label>
                  <input
                    type={
                      key === "Email"
                        ? "email"
                        : key === "Postal_code" || key === "contact_phone"
                        ? "number"
                        : "text"
                    }
                    name={key}
                    id={key}
                    value={formData[key as keyof typeof formData]}
                    onChange={handleChange}
                    className="w-full h-10 border rounded-md px-3 dark:bg-dark-900"
                  />
                </div>
              );
            })}
          </div>
          <div className="flex justify-end gap-3 mt-6">
            <Button variant="ghost" onClick={closeModal}>
              Cancel
            </Button>
            <Button onClick={adddTolist}>Save</Button>
          </div>
        </div>
      </Modal>
    </div>
  );
}
