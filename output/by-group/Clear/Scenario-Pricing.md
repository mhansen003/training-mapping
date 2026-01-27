# CLEAR 2.0 - Scenario Pricing

> **System**: CLEAR 2.0 (Loan Origination System)
> **Module**: Rates → Scenario Pricing 2.0
> **Last Updated**: January 12, 2026
> **Primary Role**: Loan Officer
> **Secondary Roles**: Sales Staff

📊 **[View Interactive Workflow Diagram →](./Scenario-Pricing-Workflow.html)**

---

## Purpose & Business Value

Scenario Pricing allows Loan Officers to **quote rates to potential borrowers without requiring a formal loan application or credit pull**. This is a critical pre-qualification tool that enables:

- Quick rate comparisons across multiple loan programs
- Client conversations without commitment
- Side-by-side product analysis
- Optimization recommendations via Optimal Blue integration

### When to Use This Feature

| Use Case | Scenario Pricing Appropriate? |
|----------|------------------------------|
| Initial client inquiry about rates | ✅ Yes |
| Comparing programs for a prospect | ✅ Yes |
| Running "what-if" scenarios | ✅ Yes |
| Formal loan application | ❌ No - Use full application |
| Overnight rate quotes | ❌ No - Not available overnight |

---

## Access Path

```
CLEAR Menu (☰) → Rates → Scenario Pricing 2.0
```

---

## Process Overview

### Phase 1: Basic Scenario Input

Enter the fundamental loan parameters to generate rate quotes.

#### Required Fields (marked with *)

| Field | Default | Notes |
|-------|---------|-------|
| Applicant Last Name* | — | Use borrower name or identifier |
| Purchase Price* | — | Or Estimated Value for refinance |
| FICO* | — | Must enter a value |
| DTI* | 0.00% | Must be greater than 0.00% |
| Zip Code* | — | Required for rate lookup |
| State* | — | Auto-populates from Zip |
| County* | — | Auto-populates from Zip |

#### Optional Fields

| Field | Default | Notes |
|-------|---------|-------|
| Applicant First Name | — | Optional identifier |
| Loan Purpose | Purchase | Drop-down: Purchase, Refinance, Cash-Out |
| Estimated Closing | — | MM/DD/YYYY format |
| Mortgage Type(s) | Conforming | **Multiple selections allowed** |
| Loan Term(s) | 30 Yr, 15 Yr | Can select multiple |
| ARM Fixed Term(s) | 7 Yr | For ARM products |
| Desired Lock Period | 30 Days | Options: 21, 30, 45, 60 Days |
| Down Payment | — | Enter $ or % |
| Monthly Qualifying Income | — | May trigger income-limited products |

#### Calculated Fields (Auto-populated)

- **Base Loan Amount**: Purchase Price - Down Payment
- **Base LTV**: Loan Amount ÷ Property Value × 100

---

### Phase 2: Property Details

#### Community Lending Toggle

When **enabled**:
- Street Address becomes **required**
- County auto-populates from address
- Unlocks community-specific loan programs

#### Occupancy Type

| Option | Description |
|--------|-------------|
| Primary Residence | Owner-occupied (default) |
| Second Home | Vacation/seasonal property |
| Investment Property | Rental/non-owner occupied |

> ⚠️ **Note**: Only ONE occupancy type can be selected per scenario

#### Property Type Options

| Type | Special Handling |
|------|------------------|
| Single Family | Default selection |
| Condo | May require # of Stories |
| Condotel | Additional requirements |
| Coop | Limited programs |
| Detached Condo | — |
| Manufactured/Single-Wide | Enables MH Advantage checkbox |
| Manufactured/Double-Wide | Enables MH Advantage checkbox |
| Non-Warrantable Condo | Limited programs |
| PUD | — |
| Townhouse | — |

#### Units & Stories

- **Number of Units**: 1-4 (affects program eligibility)
- **Number of Stories**: Primarily for Condominiums

---

### Phase 3: Advanced Options

Expand the **Advanced** section for additional parameters:

| Option | Purpose | Default |
|--------|---------|---------|
| Desired Price/Rate | Lock in specific price or rate target | Price: 100.000 |
| Waive Escrows | No escrow account | Unchecked |
| Interest Only | I/O payment structure | Unchecked |
| Buydown | Temporary rate reduction | None |
| First Time Home Buyer | FTHB program eligibility | Unchecked |
| 2nd Mortgage | Fixed 2nd or HELOC | None |
| Non Occupant Additional Borrower | Co-signer scenario | Unchecked |
| Months of Reserves | Asset verification | 12 |
| Citizenship | US Citizen, Permanent Resident, etc. | US Citizen |
| Automated U/W System | DU, LP, Investor AUS, Manual | Not Specified |
| Number of Financed Properties | Investment property count | 1 |

---

### Phase 4: Monthly Housing Expenses (Optional)

Complete this section to view **full PITI breakdown** in results.

| Expense | Input Type | Notes |
|---------|------------|-------|
| Annual Property Tax | $ or % | Annual assumed on Purchase |
| Annual Homeowner's Insurance | $ or % | Annual assumed on Purchase |
| HOA Dues | $ | Select frequency: Monthly/Quarterly/Semi-Annually/Annually |

**Additional Housing Expenses** (expandable):
- Assessment
- City/School/Town/Village Property Tax
- Earthquake Insurance
- Flood Insurance
- Hazard Insurance
- Windstorm Insurance
- Other

---

### Phase 5: Mortgage Insurance

#### Decision Tree: Which MI Module?

```
Loan Type?
├── Conventional (LTV > 80%) → Mortgage Insurance - Conventional
│   ├── BestX MI (automated cross-provider comparison)
│   └── Manual MI (enter known factor)
│
└── Government Loan → Mortgage Insurance - Government
    ├── FHA → UFMIP + MIP
    ├── VA → Funding Fee
    └── USDA → Guarantee Fee
```

#### Conventional MI: BestX MI

**Auto-compares rates across all PMI providers:**
- Arch MI
- Enact
- Essent
- MGIC
- National MI
- Radian

**Required Inputs:**
| Field | Description |
|-------|-------------|
| Borrower Pays MI / Financed | Payment method selection |
| HTI without MI* | Housing-to-Income ratio |
| DTI without MI* | Debt-to-Income ratio |
| FICO* | Borrower credit score |
| Add Co Borrower | Adds CB1 FICO field |
| Self-Employed | Checkbox if applicable |
| Foreclosure (7 Yrs) | Recent foreclosure flag |
| Bankruptcy (7 Yrs) | Recent bankruptcy flag |

**Coverage Types:**
| Type | Use Case |
|------|----------|
| Standard GSE | Default - meets standard guidelines |
| Standard GSE - Reduced Coverage | Lender-paid MI or reduced cost programs |
| Non-Standard | Unique characteristics, portfolio products |

#### Conventional MI: Manual

Use when you have a **known MI factor**:
1. Select PMI Type: Monthly, Split, or Upfront
2. Enter MI Factor as percentage (e.g., 0.32% = 0.0032 decimal)
3. System calculates dollar amount

#### Government MI: FHA

| Field | Notes |
|-------|-------|
| Financed | UFMIP typically financed |
| Section of Act | 203(b), 203(k), 234(c), 203(h), 255, 184 |
| Previous Endorsement | Refinance only - prior closing date |

**FHA Section Reference:**
| Section | Loan Type |
|---------|-----------|
| 203(b) | Standard FHA (Fixed/ARMs) |
| 203(k) | FHA Rehab Loan |
| 234(c) | FHA Condominium Loan |
| 203(h) | Disaster Loan Assistance |
| 255 | HECM - Reverse Mortgage |
| 184 | Indian Home Loan Guarantee |

#### Government MI: VA

| Field | Notes |
|-------|-------|
| VA Funding Fee Type | Regular Military, Reserves, etc. |
| Exempt Funding Fee | Disabled Veteran exemption |
| Financed | Typically financed |

#### Government MI: USDA

| Field | Notes |
|-------|-------|
| Financed | Guarantee Fee typically financed |
| USDA Case # Assigned | On/After 10/01/2016 for new originations |

---

### Phase 6: Product Types

**Standard** is checked by default. Additional options:

| Product Type | Description |
|--------------|-------------|
| Standard | Conforming conventional |
| Affordable | Income/area restricted programs |
| HARP | Home Affordable Refinance Program |
| Hero/Champion | First responder/military programs |
| HFA/Bond | Housing Finance Agency products |
| HUD Specialty | Special HUD programs |
| Reno/Rehab | Renovation loans |
| Student Loan C.O. Refi | Student loan cash-out |
| USDA Streamline | Simplified USDA refi |
| Expanded Guidelines | Non-QM programs |

> 💡 **Tip**: Use "Select all / Unselect all" for bulk selection

---

### Phase 7: Expanded Guidelines (Non-QM)

When **Expanded Guidelines** is selected, additional fields appear:

#### Mortgage Late Payments Grid

| Severity | 1-12 Months | >12-24 Months |
|----------|-------------|---------------|
| 30 Days | 0 | 0 |
| 60 Days | 0 | 0 |
| 90 Days | 0 | 0 |
| 120 Days | 0 | 0 |

#### Income Verification Types

- Full Doc
- 1 Year Alt Doc / 2 Year Alt Doc
- 1099: 1 Year / 2 Years
- Asset Related
- Business Bank Statement: 1-24 Months
- Personal Bank Statement: 1-24 Months
- P&L: 1 Year / 2 Years
- Restricted Stock
- Stated
- Written VOE
- **Investor - DSCR** → Enables DSCR field
- **Investor - No Ratio** → DSCR defaults to 0.00, disabled

#### Additional Non-QM Fields

| Field | Options |
|-------|---------|
| Unique Property | Checkbox |
| Debt Consolidation | Checkbox |
| Prepayment Penalty | 1-5 Years |
| Bankruptcy Type | None, Chapter 7, 11, 13 |
| Self-Employed | Checkbox |
| Housing Event Type | None, Deed-In-Lieu, Forbearance, Foreclosure, Modification, Short Sale |

---

## Pricing Results

### Click "Run Pricing" to Generate Results

### Results Navigation

| View | Description |
|------|-------------|
| **All** | Shows Eligible AND Ineligible products |
| **Best Pricing** | Best price within each product group |
| **Compare Products** | Side-by-side comparison (max 6) |

### Understanding Results Columns

| Column | Description |
|--------|-------------|
| Loan Product | Program name and code |
| Rate | Interest rate |
| P&I | Principal & Interest payment |
| MI | Mortgage Insurance (if applicable) |
| Discount/Rebate % | Points percentage |
| Discount/Rebate $ | Points dollar amount |
| Price | Loan price (100 = par) |
| Compare Product | Toggle for comparison |

### Grouping Options

- Mortgage Type
- Loan Term
- Amortization Type
- **Loan Term & Amort. Type** (default)
- No Grouping

### Ineligible Products

Click **"Ineligible"** badge to see disqualification reason:
- Example: "1st Mtg Loan Amt (Total) < 400000"

### Payment Display Toggle

| Option | Shows |
|--------|-------|
| P&I | Principal & Interest only |
| PITI | Full payment including Taxes, Insurance, MI |

> ⚠️ **Note**: PITI requires Monthly Housing Expenses section completion

---

## Scenario Optimizer (Optimal Blue Integration)

### Purpose
Analyzes current scenario and suggests adjustments to improve pricing.

### How It Works

1. Click **"Run"** in Scenario Optimizer column
2. System adjusts FICO, DTI, and Base Loan Amount by ±5%
3. Returns recommendations if better pricing exists
4. Click **"Pre-Fill New Scenario"** to apply suggestions
5. Re-run pricing with optimized values

### Requirements
- No MI selected, OR
- MI option set to Manual (not BestX MI)

### Example Optimization
```
Current: FICO 771, Rate 6.990%, Price 100.353
Suggested: Adjust FICO from 771 to 780
Result: Rate 6.990%, Price 100.353, Rebate -$1,462.00
```

---

## Scenario Management

### Saving Scenarios

1. Check box next to desired product/rate
2. Expand product (>) to select specific rates
3. Click **"Save X New Scenarios"**

### Scenarios Tab

Toggle between **List View** and **Card View**:

#### List View
- Sortable columns
- Bulk selection for delete
- Click scenario to reload in Pricing tab

#### Card View
- Front: Key summary data
- Back: Full details (click "See Full Details")
- Hover over name to reload scenario

### Sorting Options

- Scenario Name
- Product Name
- Applicant Last Name
- PMI / MIP / FF / G Fee [%] Monthly
- Loan Term
- Loan Purpose
- Purchase Price / Estimated Value
- Base Loan Amount / Base LTV
- Monthly P&I
- Interest Rate
- Discount/Rebate $ / %
- Price
- Lock Period
- Last Priced
- Zip Code / DTI
- Waive Escrows
- PMI Type / Occupancy Type

### Filtering
Search across: Scenario Name, Applicant Last Name, Product Name, Street Address, State, County

### Deleting Scenarios
1. Select scenario(s) via checkbox
2. Click **Delete**
3. Confirm deletion in modal

---

## Exception Handling & Edge Cases

### Common Ineligibility Reasons

| Reason | Resolution |
|--------|------------|
| Loan amount below minimum | Increase loan amount or try different product |
| LTV exceeds maximum | Increase down payment |
| FICO below minimum | Different product type or wait for score improvement |
| DTI exceeds limit | Reduce debt or increase income |
| Property type not allowed | Select appropriate product |

### MI Refresh Requirements

- **BestX MI**: Click Refresh to include Radian results (not included in first run)
- **ARM products**: Must click Run MI individually for each option
- **PMI Type change**: Requires scenario resubmission

### Scenario Optimizer Limitations

- Only returns recommendations for FICO, DTI, Base Loan Amount
- ±5% adjustment range
- Not available with BestX MI (use Manual MI)

---

## Related Processes

- [Ordering Credit in CLEAR 2.0](./Ordering-Credit.md)
- [LO Workflow in CLEAR](./LO-Workflow.md)
- [Request Initial Disclosures](./Request-Initial-Disclosures.md)
- [Pipeline Views](./Pipeline-Views.md)

---

## Quick Reference Card

```
┌─────────────────────────────────────────────────────────────┐
│                 SCENARIO PRICING QUICK START                 │
├─────────────────────────────────────────────────────────────┤
│ ACCESS: Menu → Rates → Scenario Pricing 2.0                 │
│                                                              │
│ MINIMUM REQUIRED:                                            │
│ ✓ Last Name    ✓ Purchase Price    ✓ FICO                   │
│ ✓ DTI > 0%     ✓ Zip Code                                   │
│                                                              │
│ FOR FULL PITI: Complete Monthly Housing Expenses            │
│                                                              │
│ MI TRIGGERS:                                                 │
│ • Conventional + LTV > 80% → MI Required                    │
│ • Government loans → MIP/Funding Fee/Guarantee Fee          │
│                                                              │
│ PRO TIPS:                                                    │
│ • Compare up to 6 products side-by-side                     │
│ • Use Scenario Optimizer for pricing improvements           │
│ • Save scenarios for client follow-up                       │
│ • Not available overnight                                    │
└─────────────────────────────────────────────────────────────┘
```

---

*Document generated from CMG Training materials. For questions, contact Training Department.*
