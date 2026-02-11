---
title: My First Page with Content
deprecated: false
hidden: false
icon: far fa-arrows-maximize
metadata:
  robots: index
---
<HTMLBlock>{`
<div class="overflow-x-auto mb-0">
  <table class="min-w-full">
    <thead>
      <tr>
        <th class="text-left text-gray-500! dark:text-white!">Field</th>
        <th class="text-left text-gray-500! dark:text-white!">Values</th>
        <th class="text-left text-gray-500! dark:text-white!">Description</th>
      </tr>
    </thead>

    <tbody>
      <tr>
        <td>mti</td>
        <td>
          <b>0100</b>: auth. request<br>
          <code>0110</code>: auth. response<br>
          <code>0120</code>: auth. advice<br>
          ...
        </td>
        <td>
          Message type indicator. For more information, see
          <a href="https://en.wikipedia.org/wiki/ISO_8583#Message_type_indicator_(MTI)" target="_blank" rel="noreferrer">MTI</a>
        </td>
      </tr>

      <tr>
        <td>anti_fraud_url</td>
        <td>URL</td>
        <td>
          Your anti-fraud webhook URL. For example:
          <a href="https://api.ext.client.info/webhook/provider/client/authorize" target="_blank" rel="noreferrer">
            https://api.ext.client.info/webhook/provider/client/authorize
          </a>
        </td>
      </tr>

      <tr>
        <td>processing_code</td>
        <td>
          <ul>
            <li><code>00</code>: p urchase</li>
            <li><code>01</code>: withdrawal</li>
            <li><code>20</code>: credit (also used to simulate cancellation)</li>
            <li><code>28</code>: payment</li>
          </ul>
        </td>
        <td>
          Type of operation to be performed. For more information, see
          <a href="doc:processing-codes-and-transaction-types">Processing codes and transaction types</a>
        </td>
      </tr>

      <tr>
        <td>local_currency and settlement_currency</td>
        <td>
          String<br>
          Examples:<br>
          <code>986</code> - Brazil<br>
          <code>840</code> - US
        </td>
        <td>ISO 4217 currency codes</td>
      </tr>

      <tr>
        <td>entry_mode</td>
        <td>
          string<br>
          Example: <code>901</code>
        </td>
        <td>
          This field is required and must have 3 or 4 digits. For example, try
          <code>901</code> or <code>9010</code> for magnetic stripe transaction simulation.
        </td>
      </tr>

      <tr>
        <td>installments</td>
        <td>object(s)</td>
        <td>
          Object to send the installment information.<br>
          <strong>Note:</strong> For cash transactions, do not send the installments object.
        </td>
      </tr>

      <tr>
        <td>&nbsp;&nbsp;&nbsp;&nbsp;is_crediario</td>
        <td><code>true</code> or <code>false</code></td>
        <td>Is this a crediário transaction - a Brazil specific installment plan?</td>
      </tr>

      <tr>
        <td>&nbsp;&nbsp;&nbsp;&nbsp;number</td>
        <td>Numeric value</td>
        <td>Number of installments.</td>
      </tr>

      <tr>
        <td>&nbsp;&nbsp;&nbsp;&nbsp;with_interest</td>
        <td><code>true</code> or <code>false</code></td>
        <td>Is this a purchase with interest or without interest?</td>
      </tr>

      <tr>
        <td>merchant</td>
        <td>object</td>
        <td></td>
      </tr>

      <tr>
        <td>&nbsp;&nbsp;&nbsp;&nbsp;country</td>
        <td>
          Examples:<br>
          <code>BR</code> - Brazil<br>
          <code>US</code> - United States
        </td>
        <td>ISO 3166 country codes</td>
      </tr>
    </tbody>
  </table>
</div>
`}</HTMLBlock>

<br />
