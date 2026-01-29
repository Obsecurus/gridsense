# Submitted Cases

This directory contains anonymized usage data from users who have detected billing anomalies using the GridSense tool.

## Browse Cases Online

Visit **[gridsense.us/cases.html](https://gridsense.us/cases.html)** to browse all submitted cases with:
- PUCO case numbers
- Anomaly statistics
- Overcharge amounts
- Current status (filed, resolved, etc.)
- Download links for raw data
- Social sharing buttons

## What's Here

Each CSV file represents a case where:
- Usage readings exceeded the physical capacity of the electrical service
- Data has been anonymized (names, addresses, account numbers removed)
- Only usage patterns and timestamps are included
- Metadata is stored in `cases.json` for the web interface

## File Naming Convention

Files are named using one of these formats:
- `case-XXXXXXXX.csv` - Where XXXXXXXX is the PUCO case number (preferred)
- `case-YYYYMMDD.csv` - Where YYYYMMDD is the date of first anomaly (if no case number yet)

## Adding Your PUCO Case Number

If you submitted data without a PUCO case number but later filed with PUCO:

1. Email cases@gridsense.us with your case number and the filename you submitted
2. We'll update your entry in `cases/cases.json` with your PUCO case number and status
3. Your CSV file will be renamed to include the case number

Example entry in cases.json:
```json
{
  "filename": "case-00947795.csv",
  "pucoCase": "00947795",
  "dateDetected": "2025-12-30",
  "impossibleCount": 23,
  "improbableCount": 45,
  "serviceAmperage": 200,
  "maxUsage": "174.6 kWh in 1 hour",
  "overcharge": "$75.00",
  "status": "Filed with PUCO",
  "submittedDate": "2026-01-28",
  "notes": "Multiple hours exceeding 3x service capacity"
}
```

## Real Example Workflow

**Case #00947795** (your first case!):

1. ✅ Analyzed data using GridSense
2. ✅ Found 23 impossible readings on 2025-12-30
3. ✅ Max usage: 174.6 kWh in 1 hour (200A service = 48 kWh max)
4. ✅ Filed complaint with PUCO → received case #00947795
5. ✅ Submitted anonymized CSV via email
6. ✅ **Now visible at gridsense.us/cases.html**
7. 🔄 Will update status when PUCO resolves

## Updating Your Case Status

As your case progresses, you can update the status:

1. Email cases@gridsense.us with your update
2. Include your case number or filename
3. Provide the new status information:
   - New status (e.g., "Resolved - Refund Issued")
   - Any notes (e.g., "PUCO ruled in my favor, received $75 refund on 2026-03-15")

We'll update your case entry in the database within 48 hours.

This helps track outcomes and shows the effectiveness of filing complaints!

## Purpose

This collection serves to:
1. Document patterns of potential meter malfunctions or billing errors
2. Help researchers identify systemic issues
3. Provide evidence for regulatory review
4. Support other consumers in identifying similar issues

## Submitting Your Data

### Via the Tool (Easiest)

1. Use the tool at [gridsense.us](https://gridsense.us) to analyze your usage
2. Click "Submit Your Anonymous Data"
3. Enter your PUCO case number (optional - can add later)
4. Download the anonymized CSV file
5. Click "Open Email to Submit" to send via email to cases@gridsense.us

### Email Submission

**Send to:** cases@gridsense.us

**Include:**
- Your anonymized CSV file (attached)
- PUCO case number (if you have one)
- Brief description of the anomaly

**What happens next:**
- You'll receive confirmation when your case is live on gridsense.us/cases.html

**That's it!** No account needed, no complex forms. Just email and done.

## Privacy

All submissions must be anonymized:
- ✅ Usage amounts, dates, and times (preserved)
- ❌ Names, addresses, account numbers (removed)
- ❌ Any personally identifiable information (removed)

## Legal Disclaimer

The data in this directory is provided as-is for informational and research purposes. Individual cases may require investigation to determine the cause of anomalies. This collection does not constitute proof of wrongdoing by any utility company, but rather documents instances where readings appear to exceed physical limitations.
