# 🎨 Manuja Dayawansha POS System

## Advanced Offline Point of Sale System with Print Support

A complete, feature-rich POS system built for design and printing businesses. Works completely offline with automatic data persistence.

---

## ✨ Features

### 📊 Core Features
- ✅ **Offline Operation** - Works without internet connection
- ✅ **Auto-Save** - All data saved to LocalStorage automatically
- ✅ **Print Invoices** - Professional invoice printing for any order
- ✅ **Print Last Bill** - Quick print of the most recent order
- ✅ **Real-time Clock** - Live date/time display that updates every second
- ✅ **Dynamic Window Title** - Shows current time in window title
- ✅ **Multi-format Export** - JSON, XML, and CSV export options

### 💼 Business Features
- 📝 Client management with contact information
- 🛠️ 11+ predefined service types
- 💵 Separate design fee and print cost tracking
- 📦 Quantity-based calculations
- 🎁 Percentage-based discount system
- 💳 Multiple payment methods (Cash, Card, Transfer, etc.)
- 📄 Order notes and custom descriptions
- 📈 Real-time statistics dashboard

### 📊 Dashboard Statistics
- Total number of orders
- Revenue for current day
- Grand total of all orders
- Visual stat cards with gradients

### 🖨️ Print Features
- **Print Any Invoice** - Click print button on any order
- **Print Last Bill** - Dedicated button to reprint most recent order
- **Professional Layout** - Clean, branded invoice design
- **Detailed Breakdown** - Shows design fees, print costs, discounts
- **Client Information** - Complete customer details on invoice
- **Invoice Numbering** - Unique invoice numbers based on order ID

### 📤 Export Options
- **JSON Export** - Full data export with all order details
- **XML Export** - Structured XML format for integrations
- **CSV Export** - Spreadsheet-compatible format for analysis

---

## 🚀 Setup Instructions

### Prerequisites

1. **Visual Studio 2019/2022** (Community Edition or higher)
2. **.NET Framework 4.7.2 or higher** / **.NET 6.0 or higher**
3. **Microsoft Edge WebView2 Runtime**
   - Download from: https://go.microsoft.com/fwlink/p/?LinkId=2124703
   - Usually pre-installed on Windows 10/11

### Step-by-Step Installation

#### 1. Create the Project

1. Open Visual Studio
2. Create new project: **Windows Forms App (.NET Framework)** or **Windows Forms App**
3. Name: `Pos_system`
4. Click **Create**

#### 2. Add WebView2 NuGet Package

1. Right-click on project → **Manage NuGet Packages**
2. Search for: `Microsoft.Web.WebView2`
3. Click **Install**
4. Accept license agreements

#### 3. Add WebView2 Control to Form

1. Open **Form1.cs** in Designer view
2. From **Toolbox** → search "WebView2"
3. Drag **WebView2** onto the form
4. Set properties:
   - **Name**: `webView21`
   - **Dock**: `Fill` (so it fills the entire window)

#### 4. Create the Public Folder

1. In **Solution Explorer**, right-click on project name
2. Add → **New Folder** → name it `public`
3. Right-click on `public` folder
4. Add → **Existing Item**
5. Select the `index.html` file (the POS system HTML)
6. Click **Add**

#### 5. Configure HTML File Properties

1. In **Solution Explorer**, click on `index.html`
2. In **Properties** window (press F4 if not visible), set:
   - **Build Action**: `Content`
   - **Copy to Output Directory**: `Copy if newer`

#### 6. Update Form1.cs Code

Replace the entire content of `Form1.cs` with the provided C# code.

#### 7. Build and Run

1. Press **F5** or click **Start**
2. The POS system should load in a full-screen window

---

## 📁 Project Structure

```
Pos_system/
│
├── Form1.cs                 # Main C# form code
├── Form1.Designer.cs        # Auto-generated designer code
├── Form1.resx               # Form resources
├── Program.cs               # Application entry point
│
└── public/
    └── index.html           # POS System HTML (all-in-one file)
```

---

## 🎯 Usage Guide

### Adding a New Order

1. **Enter client details:**
   - Client name (required)
   - Email/Phone (optional)

2. **Select service type:**
   - Choose from 11+ predefined options
   - Or select "Other" for custom services

3. **Enter pricing:**
   - Design Fee: The creative/design work cost
   - Print/Material Cost: Physical production cost
   - Quantity: Number of items

4. **Apply discount (optional):**
   - Enter percentage discount (0-100%)
   - Discount automatically calculated

5. **Select payment method:**
   - Cash, Card, Bank Transfer, Mobile Payment, or Check

6. **Add notes (optional):**
   - Special instructions or details

7. **Click "➕ Add Order"**

### Printing Invoices

#### Method 1: Print Any Order
- Click the **🖨️ print button** next to any order in the table
- Invoice will display in print preview
- Click Print to send to printer or save as PDF

#### Method 2: Print Last Bill
- Click the **"🖨️ Print Last"** button in the input section
- Automatically prints the most recently added order
- Perfect for immediate printing after checkout

### Exporting Data

1. **JSON Export** - Click **💾 JSON**
   - Full data backup with all fields
   - Perfect for backups or system migration

2. **XML Export** - Click **💾 XML**
   - Structured format for integrations
   - Compatible with other systems

3. **CSV Export** - Click **📊 CSV**
   - Open in Excel, Google Sheets
   - Great for analysis and reporting

### Managing Orders

- **View All Orders** - Displayed in reverse chronological order (newest first)
- **Delete Order** - Click **🗑️** button on any order
- **Reset System** - Click **🗑️ Reset All** (requires double confirmation)

---

## 🔧 Customization

### Changing Business Name

Edit the invoice header in the `generateInvoiceHTML` function:

```javascript
<h1>🎨 YOUR BUSINESS NAME</h1>
<p>Your Tagline Here</p>
```

### Adding Service Types

In the HTML, find the service type dropdown and add options:

```html
<select id="serviceType">
    <option value="Your New Service">Your New Service</option>
    <!-- Add more options -->
</select>
```

### Changing Colors

Modify CSS variables at the top of the `<style>` section:

```css
:root {
    --primary: #2563eb;    /* Main blue color */
    --success: #10b981;    /* Green for success */
    --danger: #ef4444;     /* Red for danger */
}
```

### Contact Information on Invoice

Update the footer in `generateInvoiceHTML`:

```javascript
<p style="font-size: 0.85rem; color: #6b7280; margin-top: 10px;">
    For inquiries: yourmail@business.com | Phone: (XXX) XXX-XXXX
</p>
```

---

## 💾 Data Storage

### LocalStorage

All data is stored in browser's LocalStorage:
- **Key**: `manujaOrders`
- **Format**: JSON array
- **Persistence**: Data survives browser/app restarts
- **Location**: User-specific, isolated storage

### Data Backup

**Automatic**: Every order is auto-saved to LocalStorage

**Manual Backup Options**:
1. Export JSON (recommended for full backup)
2. Export CSV (for spreadsheet analysis)
3. Export XML (for system integrations)

### Data Recovery

If data is accidentally deleted:
- LocalStorage data persists until manually cleared
- Use JSON export regularly for backups
- Can import JSON back into LocalStorage if needed

---

## 🖨️ Print Configuration

### Default Printer Setup

Windows will use your default printer. To change:
1. Go to Settings → Devices → Printers & scanners
2. Set your desired printer as default

### Save as PDF

Instead of printing:
1. When print dialog appears
2. Select "Microsoft Print to PDF" as printer
3. Choose save location
4. Click Print

### Print Settings

For best results:
- **Paper Size**: A4 or Letter
- **Orientation**: Portrait
- **Margins**: Default (0.5" or 1.27cm)
- **Scale**: 100%

---

## ⚙️ Troubleshooting

### Issue: HTML file not found

**Solution:**
1. Verify `public` folder exists in project
2. Check `index.html` is inside `public` folder
3. Right-click `index.html` → Properties
4. Set "Copy to Output Directory" to "Copy if newer"
5. Rebuild project (Ctrl + Shift + B)

### Issue: WebView2 Runtime error

**Solution:**
1. Download WebView2 Runtime: https://go.microsoft.com/fwlink/p/?LinkId=2124703
2. Install the runtime
3. Restart the application
4. Restart computer if issue persists

### Issue: Print button doesn't work

**Solution:**
1. Check browser print permissions
2. Ensure default printer is set
3. Try "Microsoft Print to PDF" instead
4. Check print preview appears

### Issue: Data disappeared

**Solution:**
1. Check if LocalStorage was cleared
2. Restore from JSON export backup
3. Check if running in InPrivate/Incognito mode (doesn't save data)

### Issue: Page won't load

**Solution:**
1. Check Developer Tools (F12) for errors
2. Verify HTML file path in error message
3. Check file permissions
4. Try running Visual Studio as Administrator

---

## 🔐 Security Notes

- **LocalStorage** is isolated per application
- Data is stored locally on user's machine
- No internet connection required
- No external data transmission
- Regular backups recommended (use JSON export)

---

## 📈 Future Enhancements

Potential features to add:
- [ ] Customer database
- [ ] Inventory management
- [ ] Email invoice sending
- [ ] Multi-currency support
- [ ] Tax calculations
- [ ] Payment tracking
- [ ] Report generation
- [ ] Barcode scanning
- [ ] Receipt printer integration
- [ ] Multi-user support
- [ ] Cloud backup option

---

## 🆘 Support

### Common Questions

**Q: Can I use this commercially?**
A: Yes, this is a complete, production-ready system.

**Q: Does it work without internet?**
A: Yes, completely offline. No internet required.

**Q: Can I customize the invoice design?**
A: Yes, edit the `generateInvoiceHTML` function in the HTML.

**Q: How do I backup my data?**
A: Click the "💾 JSON" button to export all data.

**Q: Can I run this on multiple computers?**
A: Yes, but each will have separate data. Use JSON export/import to sync.

---

## 📝 License

This is a custom-built POS system. Modify and use as needed for your business.

---

## 👨‍💻 Technical Details

- **Frontend**: HTML5, CSS3, Vanilla JavaScript
- **Backend**: C# Windows Forms
- **WebView**: Microsoft Edge WebView2
- **Storage**: Browser LocalStorage
- **Print**: Native browser print API
- **Export Formats**: JSON, XML, CSV

---

## 🎉 Credits

Built for **Manuja Design** - Professional Design & Printing Services

**Version**: 2.0  
**Last Updated**: February 2026  
**Platform**: Windows Desktop Application

---

**Happy Selling! 🚀**
