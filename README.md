https://abhirebackend.onrender.com/hiringflow/steps
import React, { useEffect, useState } from 'react';
import axios from 'axios';
import {
  Table,
  TableBody,
  TableCell,
  TableHeader,
  TableRow
} from "../../components/ui/table";

export default function Practice() {
  const [data, setData] = useState([]);
  const [error, setError] = useState('');

  useEffect(() => {
    const fetchData = async () => {
      try {
        const API_URL = `https://abhirebackend.onrender.com/hiringflow/steps`;
        const response = await axios.get(API_URL);
        setData(Array.isArray(response.data) ? response.data : [response.data]);
      } catch (err) {
        console.error('Fetch error:', err);
        setError('Failed to fetch data.');
      }
    };

    fetchData();
  }, []);

  if (error) return <div className='text-red-600'>{error}</div>;
  if (data.length === 0) return <div>Loading...</div>;

  return (
    <div className="overflow-hidden rounded-2xl bg-white dark:bg-white/[0.03] border border-gray-200 dark:border-gray-800 ml-[-6vw] lg:w-[119%]">
      <Table>
        <TableHeader>
          <TableRow>
            <TableCell>Id</TableCell>
            <TableCell>Step Name</TableCell>
            <TableCell>Code</TableCell>
            <TableCell>Description</TableCell>
            <TableCell>Level</TableCell>
            <TableCell>Configurable</TableCell>
            <TableCell>Active</TableCell>
            <TableCell>Created At</TableCell>
          </TableRow>
        </TableHeader>
        <TableBody>
          {data.map((step) => (
            <TableRow key={step.hiringflow_steps_master_id}>
              <TableCell>{step.hiringflow_steps_master_id}</TableCell>
              <TableCell>{step.step_name}</TableCell>
              <TableCell>{step.step_code}</TableCell>
              <TableCell>{step.description}</TableCell>
              <TableCell>{step.step_level}</TableCell>
              <TableCell>{step.is_configurable ? 'Yes' : 'No'}</TableCell>
              <TableCell>{step.is_active ? 'Yes' : 'No'}</TableCell>
              <TableCell>{new Date(step.created_at).toLocaleString()}</TableCell>
            </TableRow>
          ))}
        </TableBody>
      </Table>
    </div>
  );
}
