---
title: REINDEX_TESTING
deprecated: false
---
<HTMLBlock>{`
<div style={{ overflowX: 'auto' /* optional, for horizontal scroll */ }}>
  <table style={{ borderCollapse: 'collapse', width: '100%' }}>
    <thead>
      <tr>
        <th style={{ border: '1px solid #ccc', padding: '8px' }}>Parent Col 1</th>
        <th style={{ border: '1px solid #ccc', padding: '8px' }}>Parent Col 2</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td style={{ border: '1px solid #ccc', padding: '8px' }}>
          <!-- Child (nested) table -->
          <table style={{ border: '1px solid #999', width: '100%', borderCollapse: 'collapse' }}>
            <thead>
              <tr>
                <th style={{ border: '1px solid #999', padding: '6px' }}>Child H1</th>
                <th style={{ border: '1px solid #999', padding: '6px' }}>Child H2</th>
              </tr>
            </thead>
            <tbody>
              <tr>
                <td style={{ border: '1px solid #999', padding: '6px' }}>Child A1</td>
                <td style={{ border: '1px solid #999', padding: '6px' }}>Child A2</td>
              </tr>
            </tbody>
          </table>
          <!-- End child table -->
        </td>
        <td style={{ border: '1px solid #ccc', padding: '8px' }}>Parent Cell 2</td>
      </tr>
    </tbody>
  </table>
</div>
`}</HTMLBlock>

$E=mc^2$