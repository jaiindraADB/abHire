// src/components/ui/table.jsx

export function Table({ children }) {
  return (
    <table style={{ width: '100%', borderCollapse: 'collapse' }}>
      {children}
    </table>
  )
}

export function TableHeader({ children }) {
  return <thead style={{ background: '#f0f0f0' }}>{children}</thead>
}

export function TableRow({ children }) {
  return <tr>{children}</tr>
}

export function TableCell({ children }) {
  return <td style={{ padding: '8px', border: '1px solid #ddd' }}>{children}</td>
}
