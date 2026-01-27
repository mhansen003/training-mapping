# IDS Complete Training Workflow

> **System:** IDS (International Document Services)
> **Updated:** January 2026
> **Roles:** Loan Officer, Processor, Closer
> **Integration:** Byte LOS

---

## Overview

IDS (International Document Services) is CMG's vendor of choice for all disclosures and documents. IDS is fully integrated with Byte - when disclosures are sent (called a "push"), the system updates automatically. When signatures are received, information flows back (called "pushback").

**Fulfillment Dashboard URL:** https://fulfillment.idsdoc.com/Account/Login

---

## Table of Contents

1. [Login & Access Management](#login--access-management)
2. [Checking for Signatures](#checking-for-signatures)
3. [Checking Documents Left to Sign](#checking-documents-left-to-sign)
4. [Resending Disclosure Email to Borrower](#resending-disclosure-email-to-borrower)
5. [Resending Link to Loan Officer](#resending-link-to-loan-officer)
6. [Updating Borrower Email Address](#updating-borrower-email-address)
7. [Retrieving Disclosure Documents](#retrieving-disclosure-documents)
8. [Regenerating Disclosures](#regenerating-disclosures)
9. [Borrower Instructions: E-Signing Disclosures](#borrower-instructions-e-signing-disclosures)
10. [Borrower Instructions: Hybrid e-Closing](#borrower-instructions-hybrid-e-closing)
11. [Quick Reference](#quick-reference)
12. [AI Agent Opportunities](#ai-agent-opportunities)

---

## Login & Access Management

### Steps

1. **Access the Fulfillment Dashboard**
   - Open https://fulfillment.idsdoc.com/Account/Login in your browser

2. **Enter Credentials**
   - Enter your Username and Password, then click Login

### Account Types by LOS

| Account Code | LOS System | Channel |
|--------------|------------|---------|
| `BCMGR` | BytePro | Retail |
| `BCMGB` | BytePro | Brokered Retail |
| `BCMGW` | BytePro | Wholesale |
| `RECMG` | DataTrac | Retail |
| `BRKRD` | DataTrac | Brokered Retail |
| `CMGC` | DataTrac | Wholesale |

### Password Reset

1. Visit www.idsdoc.com → Login → Forgot Password
2. Enter your username and click Email Password
3. Check your email (and junk folder) for the reset link
4. **After resetting in IDS:** Update credentials in Byte: Customize → Defaults → IDS

---

## Checking for Signatures

### Steps

1. **Search for the Loan**
   - In Active Packages, type the loan number in Search field
   - Click the magnifying glass (can also search by borrower's last name)

2. **Expand Borrower Activity**
   - Click the + sign next to the Borrower name

3. **Interpret Status Colors**
   - 🟢 **Green** = Signed
   - 🟡 **Yellow** = Not Signed

---

## Checking Documents Left to Sign

### Steps

1. Search for the loan and click the + sign next to the Borrower name
2. Click the + sign next to **Completed** to see Documents Included
3. Any documents **missing a check mark** in the Completed column have not been signed

---

## Resending Disclosure Email to Borrower

### Steps

1. Search for the loan, click + sign next to Borrower name
2. Click **"Resend Signer Email"**
3. "Email Sent" pop-up appears - click **OK**

> ⚠️ **Warning:** The email is sent immediately when clicked. There is no confirmation prompt or undo.

---

## Resending Link to Loan Officer

### Steps

1. Search for the loan and expand borrower activity
2. Click **"eSign Room"** tab
3. Copy the URL from the Loan Officer Authentication window
4. Send the URL to the Loan Officer via email or message

---

## Updating Borrower Email Address

### Steps

1. Search for the loan and expand borrower details
2. Click the **Edit (pencil) button** next to Contact Info
3. Update the email address field
4. Click **Save (disk) button**
5. Click **"Resend Signer Email"** to send to new address

---

## Retrieving Disclosure Documents

When IDS pushback doesn't feed to Byte automatically, manually retrieve documents:

### Steps

1. Search for the loan, expand borrower, click **"eSign Room"**
2. Enter IDS Username and Password in authentication window
3. Click **"View/Print All"** to open documents as PDF
4. Click **Print → BytePro Print to Loan File**
5. Select **Auto-Index** to auto-store barcoded documents

> 💡 **Why Manual Retrieval?** If "Submit and Flag as Disclosed" wasn't selected when sending, IDS doesn't send pushback notifications to Byte.

---

## Regenerating Disclosures

### Steps

1. Search for the loan and click the borrower name
2. Update email if needed (Edit → Save)
3. Click **"Resend Signer Email"**

> ⚠️ **Date Change Warning:** If resending on a different day than originally sent, the Disclosure Log must be manually updated in Byte. Contact training@cmgfi.com for assistance.

---

## Borrower Instructions: E-Signing Disclosures

### Steps for Borrowers

1. **Receive Email** - Within 24-72 hours of loan registration, receive email from notifications@idsdoc.com
2. **Verify Identity** - Complete 3 validation questions (last 4 SSN, birth year, email)
3. **Review Electronic Consent** - Accept the Consent to Receive Electronic Disclosures
4. **Sign Documents** - Click "SIGN HERE" buttons, use "Jump to next signature item" to navigate
5. **Complete and Save** - On Congratulations screen, click "Print/Save Package", check "Review Acknowledged"

> 🖨️ **Ink Sign Documents:** Documents labeled "INK SIGN" must be printed, physically signed, and delivered to the loan officer.

---

## Borrower Instructions: Hybrid e-Closing

### Steps for Borrowers

1. **Review Before Closing** - Receive email with link to view documents (review only until closing day)
2. **Create Account** - Click "Create new account" (different from LE/CD process)
3. **Sign at Midnight HT** - At midnight Hawaii Time on closing day, signing becomes available
4. **Track Progress** - Green check marks appear as documents are completed
5. **Complete In-Person** - Wet-sign documents will be at the Closing Agent

### Benefits of Hybrid e-Closing

- **Convenience:** Sign from anywhere after midnight HT
- **Speed:** Reduced in-person appointment time
- **Security:** Secure and reliable process

---

## Quick Reference

| Item | Value |
|------|-------|
| **IDS Fulfillment URL** | https://fulfillment.idsdoc.com/Account/Login |
| **IDS Support Phone** | 800-554-1872 |
| **IDS Support Email** | service@idsdoc.com |
| **Borrower Emails From** | notifications@idsdoc.com |
| **Green Status** | Document/Borrower has signed |
| **Yellow Status** | Document/Borrower has NOT signed |
| **Byte Integration** | Push (send) & Pushback (receive) |

---

## AI Agent Opportunities

### 1. Signature Status Monitor (Priority: 95/100)

**Type:** Real-Time Monitoring Agent
**Impact:** 4 hours saved/day

Continuously monitors IDS for signature completions across all active loan packages. Automatically updates Byte and alerts staff when borrowers complete signing or when packages remain unsigned past thresholds.

### 2. E-Sign Reminder Agent (Priority: 88/100)

**Type:** Automated Communication Agent
**Impact:** 30% faster sign rate

Automatically sends personalized reminder emails to borrowers who haven't completed e-signing within configured time windows.

### 3. Pushback Validator (Priority: 85/100)

**Type:** Data Integrity Agent
**Impact:** 1 hour saved/loan on sync failures

Monitors IDS-to-Byte pushback synchronization. Detects when signed documents fail to transfer and triggers manual retrieval workflow.

### 4. Email Verification Agent (Priority: 78/100)

**Type:** Pre-Send Validation Agent
**Impact:** 95% error prevention

Validates borrower email addresses before disclosure packages are sent. Catches common typos and invalid addresses.

### 5. Hybrid Closing Coordinator (Priority: 72/100)

**Type:** Workflow Orchestration Agent
**Impact:** 50% faster closings

Orchestrates hybrid e-closing workflow by tracking document status and coordinating between borrowers, LOs, and closing agents.

---

*Generated by CMG Training Portal - January 2026*
