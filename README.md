# ⚡ Power Anomaly Detector

A free, open-source tool to identify physically impossible and statistically improbable energy consumption patterns in your utility bills.

**🌐 Use Online:** [https://gridsense.us](https://gridsense.us)

## 🎯 What This Tool Does

Analyzes your electrical usage data to detect potential billing errors and meter malfunctions:

- **Impossible Readings** (Red): Usage exceeding your electrical service capacity
  Example: 165 kWh in 1 hour with 200A service (max possible: 48 kWh)

- **Improbable Readings** (Orange): Statistical outliers and sudden spikes
  Example: Usage suddenly 10x higher than normal with no explanation

## 🚀 Quick Start

### Option 1: Use Online (Recommended)
Visit **[gridsense.us](https://gridsense.us)** and upload your utility CSV file. No installation required.

### Option 2: Run Locally
1. Download `index.html`
2. Open it in your browser
3. Works completely offline - no server needed

## 📊 How It Works

### Physical Impossibility Detection
```
200A service @ 240V = 48 kW maximum power
Maximum in 1 hour = 48 kWh
A reading of 165 kWh = 3.4x capacity = IMPOSSIBLE
```

### Statistical Analysis
- Calculates monthly baseline (mean, standard deviation)
- Flags top 2% most extreme readings
- Detects sudden spikes (>5x previous hour)

## 📁 Getting Your Data

### For AEP Ohio Customers
1. Log in to **aepohio.com**
2. Go to "My Usage" → "Export Usage Data"
3. Select date range (up to 1 year)
4. Choose **15-minute intervals** and **CSV format**
5. Download and upload to this tool

### Supported Formats
Works with standard utility CSV exports containing:
- Date, Time, Usage (kWh), Cost

## ⚙️ Configuration

- **Service Amperage**: 100A, 200A, 400A, or custom
- **Voltage**: 120V, 240V, or custom
- **Improbable Threshold**: Top 1-20% most extreme readings (default: 2%)

## 📤 Found Anomalies? Take Action

### 1. Share Your Findings
One-click sharing to social media with auto-generated posts:
- **Twitter/X**: Concise, attention-grabbing stats
- **Facebook**: Detailed explanation of the issue
- **LinkedIn**: Professional angle on billing quality
- **Reddit**: Community discussion format

Pre-formatted posts include:
- Number of impossible readings
- Specific examples (e.g., "165 kWh in 1 hour = 3.4x impossible")
- Dollar amount overcharged
- Link to gridsense.us

Help spread awareness and protect other consumers!

### 2. Export Your Report
Click "Export to CSV" to download detailed findings

### 3. File a Complaint with PUCO
The tool includes step-by-step instructions for filing with the Public Utilities Commission of Ohio:
- Online at **puco.ohio.gov**
- Call: **1-800-686-PUCO (7826)**
- Include your exported report as evidence

### 4. Share Your Data (Optional)
Help document billing errors:
- Click "Submit Anonymous Data"
- Your data is automatically anonymized
- One-click email submission (no account needed)
- Cases appear on gridsense.us/cases.html

## 🛡️ Privacy First

- ✅ **All processing is local** - data never leaves your browser
- ✅ **Works offline** - no internet required after loading
- ✅ **No tracking or analytics**
- ✅ **Open source** - inspect the code yourself

## 📂 Repository Structure

```
├── index.html              # Complete application (single file)
├── cases/                  # Anonymized user-submitted data
│   └── README.md          # Case documentation
├── CONTRIBUTING.md        # How to contribute
└── README.md              # This file
```

## 🤝 Contributing

We welcome contributions! See [CONTRIBUTING.md](CONTRIBUTING.md) for:
- Submitting your anomalous usage data
- Reporting bugs
- Suggesting features
- Code contributions

## 📊 Submitted Cases

**Browse Online:** [gridsense.us/cases.html](https://gridsense.us/cases.html)

See real-world examples of billing anomalies with:
- PUCO case numbers and status
- Detailed anomaly statistics
- Downloadable anonymized data
- Social sharing for each case

All cases are automatically displayed on the website after submission. See [`CASE_DATABASE.md`](CASE_DATABASE.md) for complete documentation.

## ⚖️ Legal Disclaimer

This tool is provided for informational purposes to help consumers identify potential billing discrepancies. Results should be verified and used as supporting evidence when disputing utility bills. We make no claims about the accuracy of utility readings without proper investigation. Individual cases may have various causes and require professional review.

## 🔧 Technical Details

- **Zero dependencies** (except Chart.js CDN)
- **Single HTML file** - no build process
- **~800 lines of code** - easy to audit
- **Works in all modern browsers**

Built with vanilla JavaScript, CSS, and HTML5.

## 📝 Example Case

From real submitted data (anonymized):

**Anomaly:** December 30, 2025
**Service:** 200A @ 240V (48 kW maximum)
**Readings:**
- Hour 14:00: **160.76 kWh** (3.3x impossible)
- Hour 15:00: **165.22 kWh** (3.4x impossible)
- Hour 16:00: **174.6 kWh** (3.6x impossible)

**Impact:** ~$75 overcharge in 3 hours

These readings would require 160-174 kW of continuous power, which is physically impossible with residential 200A service.

## 🌟 Why This Matters

Billing errors happen. Meters malfunction. Estimates can be wildly inaccurate. This tool empowers consumers to:
- Verify their bills with physics-based calculations
- Document anomalies with hard data
- File informed complaints with regulators
- Share evidence of systemic issues

## 📞 Support

- **Issues/Bugs:** Open an issue on GitHub
- **PUCO (Ohio):** 1-800-686-PUCO (7826)
- **Documentation:** See guides built into the tool

## 📜 License

MIT License - Free to use, modify, and distribute.

---

**Made with ⚡ by frustrated consumers, for frustrated consumers.**
