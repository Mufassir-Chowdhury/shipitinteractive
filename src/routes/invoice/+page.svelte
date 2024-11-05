<script>
    import { onMount } from "svelte";

    onMount(() => {
        function toggleWatermark() {
          const isPaid = document.getElementById('paidToggle').checked;
          const watermark = document.getElementById('watermark');
          watermark.style.display = isPaid ? 'none' : 'block';
        }
        // Initialize watermark on load
        toggleWatermark();
    });
  </script>
  
<div class="body">

    <div class="controls no-print">
      <button on:click={window.print()} class="print-button">
        <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2">
          <path d="M6 9V2h12v7M6 18H4a2 2 0 01-2-2v-5a2 2 0 012-2h16a2 2 0 012 2v5a2 2 0 01-2 2h-2"></path>
          <path d="M6 14h12v8H6z"></path>
        </svg>
        Print Invoice
      </button>
      <div class="status-toggle">
        <span>Paid:</span>
        <label class="toggle-switch">
          <input type="checkbox" id="paidToggle" on:change={toggleWatermark()}>
          <span class="slider"></span>
        </label>
      </div>
    </div>
  
    <div class="watermark" id="watermark">UNPAID</div>
  
    <div class="invoice-header">
      <div class="company-details flex items-center gap-4">
        <img src="favicon.png" height="32px" width="64px" alt="Company Logo">
        <div>
            <h2 class="text-xl font-semibold">Ship It Interactive</h2>
            <p>shipitinteractive.pages.dev</p>
        </div>
      </div>
      <div class="invoice-title">
        <h1>INVOICE</h1>
        <p><strong>Invoice #:</strong> 2024-001<br>
           <strong>Date:</strong> November 5, 2024<br>
      </div>
    </div>
  
    <div class="invoice-info">
      <div class="invoice-grid">
        <div>
          <h3>Bill To:</h3>
          <p><span class="text-xl font-bold">KishorKantha Readers Forum</span><br>
             Sylhet City<br>
        </div>
      </div>
    </div>
  
    <table>
      <thead>
        <tr>
          <th>Description</th>
          <th class="text-right">Amount</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>Domain (kkrfsylhet.org)</td>
          <td class="text-right">৳800.00</td>
        </tr>
        <tr>
          <td>UI/UX Design</td>
          <td class="text-right">৳4,000.00</td>
        </tr>
        <tr>
          <td>Development and Testing</td>
          <td class="text-right">৳5,500.00</td>
        </tr>
        <tr>
            <td>Deployment</td>
            <td class="text-right">৳700.00</td>
        </tr>
      </tbody>
    </table>
  
    <div class="total-section">
      <!-- <p><strong>Subtotal:</strong> .00</p> -->
      <p class="total-amount">Total: ৳11,000.00</p>
    </div>
  
    <!-- <div class="payment-terms">
      <h3>Payment Terms & Conditions</h3>
      <p>Payment is due within 14 days of invoice date. Please include invoice number with your payment. A late payment fee of 1.5% per month will be charged on overdue amounts.</p>
      <p>Thank you for your business!</p>
    </div> -->
</div>

  <style>
    .body {
      font-family: system-ui, -apple-system, sans-serif;
      line-height: 1.5;
      max-width: 800px;
      margin: 40px auto;
      padding: 20px;
      background: #f9fafb;
      position: relative;
    }
    
    @media print {
      .body {
        background: white;
        margin: 0;
        padding: 20px;
      }
      .no-print {
        display: none !important;
      }
      .watermark {
        display: block !important;
      }
    }

    .controls {
      position: sticky;
      top: 0;
      background: #f9fafb;
      padding: 10px 0;
      margin-bottom: 20px;
      z-index: 1000;
      display: flex;
      gap: 12px;
      align-items: center;
    }

    .print-button {
      background: #1f2937;
      color: white;
      border: none;
      padding: 8px 16px;
      border-radius: 6px;
      cursor: pointer;
      display: flex;
      align-items: center;
      gap: 6px;
      font-size: 14px;
    }

    .print-button:hover {
      background: #374151;
    }

    .status-toggle {
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .toggle-switch {
      position: relative;
      display: inline-block;
      width: 50px;
      height: 24px;
    }

    .toggle-switch input {
      opacity: 0;
      width: 0;
      height: 0;
    }

    .slider {
      position: absolute;
      cursor: pointer;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background-color: #ccc;
      transition: .4s;
      border-radius: 24px;
    }

    .slider:before {
      position: absolute;
      content: "";
      height: 16px;
      width: 16px;
      left: 4px;
      bottom: 4px;
      background-color: white;
      transition: .4s;
      border-radius: 50%;
    }

    input:checked + .slider {
      background-color: #10b981;
    }

    input:checked + .slider:before {
      transform: translateX(26px);
    }

    .watermark {
      display: none;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%) rotate(-45deg);
      font-size: 100px;
      color: rgba(255, 0, 0, 0.1);
      pointer-events: none;
      z-index: 1000;
      white-space: nowrap;
    }
    
    .invoice-header {
      display: flex;
      justify-content: space-between;
      align-items: start;
      margin-bottom: 40px;
    }
    
    .company-details {
      flex: 1;
    }
    
    .invoice-title {
      text-align: right;
      color: #1f2937;
    }
    
    .invoice-info {
      background: white;
      border-radius: 8px;
      padding: 20px;
      margin-bottom: 30px;
      box-shadow: 0 1px 3px rgba(0,0,0,0.1);
    }
    
    .invoice-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 40px;
    }
    
    table {
      width: 100%;
      border-collapse: collapse;
      margin: 30px 0;
      background: white;
      border-radius: 8px;
      overflow: hidden;
      box-shadow: 0 1px 3px rgba(0,0,0,0.1);
    }
    
    th {
      background: #1f2937;
      color: white;
      text-align: left;
      padding: 12px;
    }
    
    td {
      padding: 12px;
      border-bottom: 1px solid #e5e7eb;
    }
    
    tr:last-child td {
      border-bottom: none;
    }
    
    .total-section {
      text-align: right;
      margin-top: 20px;
      padding: 20px;
      background: white;
      border-radius: 8px;
      box-shadow: 0 1px 3px rgba(0,0,0,0.1);
    }
    
    .total-amount {
      font-size: 24px;
      font-weight: bold;
      color: #1f2937;
    }
    
    .payment-terms {
      margin-top: 30px;
      padding: 20px;
      background: #e5e7eb;
      border-radius: 8px;
      font-size: 14px;
    }
  </style>