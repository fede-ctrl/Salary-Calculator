# Argentina Salary Calculator 2025 | Executive Edition

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Status](https://img.shields.io/badge/Status-Educational_Prototype-blue.svg)]()
[![Stack](https://img.shields.io/badge/Stack-HTML5_|_JS-orange.svg)]()

**A single-file, client-side application for projecting Argentine executive and standard salary compensations under December 2025 tax regulations.**

---

## ⚠️ Important Disclaimer
This software is an **independent educational tool** tailored for compensation analysis. It is **not** an official application from ARCA (ex-AFIP) or the Argentine Government.

**Note on Projections:** The calculations utilize projected tax brackets and deductions for **December 2025**, based on estimated IPC (Consumer Price Index) adjustments. Actual values may vary significantly based on future government decrees, union agreements (Paritarias), and specific payment dates. **Do not use this tool for official tax affidavits.**

---

## Overview
The **Argentina Salary Calculator 2025** is designed to provide clarity on the complex "Impuesto a las Ganancias" (Income Tax) regime. It bridges the gap between Gross Salary and Net "Pocket" Money, specifically addressing the needs of executive compensation packages which often include foreign currency components and complex deductions.

### Key Features
* **Multi-Currency Logic**: Calculate salaries denominated in **ARS**, **USD**, or **EUR** with real-time exchange rate configuration.
* **Executive Focus**: Toggle between **Standard Monthly** salaries and **Annual Packages** (incorporating SAC/Aguinaldo and bonuses).
* **Tax Engine 2025**: Implements the projected 4th Category Income Tax scales (Alícuotas) for the second semester of 2025.
* **Smart Deductions**: Automatically caps deductions (Rent, Domestic Staff, Life Insurance) based on statutory limits (e.g., 40% of Non-Taxable Minimum or GNI).
* **Privacy First**: Runs entirely in the browser. No data is sent to any server.

---

## Technical Architecture

* **Format**: Single-File Application (SPA).
* **Frontend**: HTML5, CSS3 (CSS Variables for theming).
* **Logic**: Vanilla JavaScript (ES6+).
* **Dependencies**: None. Zero external libraries or frameworks.

---

## Data Privacy & Security
*Compliance with Data Processing Standards*

1.  **Local Processing**: All calculations are performed strictly within the user's web browser (`client-side`).
2.  **No Data Persistence**: This tool does not use cookies, LocalStorage, or SessionStorage. Data is lost upon refreshing the page.
3.  **No Transmission**: No financial data, salary inputs, or family details are transmitted over the network.

## Configuration Guide
The calculator allows for granular configuration to ensure accuracy:

1. Income Parameters
Currency: Select the currency of the gross contract. If USD/EUR is selected, an Exchange Rate field appears to convert values to the ARS tax base.

Mode:

Monthly: Standard payroll calculation.

Annual: Useful for verifying total yearly compensation packages including bonuses.

2. Family & deductions
Family Group: Toggles the specific deduction for Spouse (requires no income) and Children (under 18).

Overtime: Separate input for 50% overtime hours to calculate the specific tax exemptions/allocations if applicable.

3. Allowable Deductions (Ganancias)
Enter monthly values. The system automatically calculates the annual cap and applies the lower value.

Domestic Staff: Capped at the Non-Taxable Minimum.

Rent: 10% of rent paid, capped at 40% of the Non-Taxable Minimum.

Prepaga (Health): Only the differential paid by the employee. Capped at 5% of Net Cumulative Income.

Education: For children under 18 or up to 24 (if studying).

## Calculation Logic
The tool follows this waterfall model for estimation:

Gross Normalization: Converts all inputs to an annualized ARS Taxable Base.

Social Security: Deducts 17% (Jubilación, PAMI, Obra Social) up to the statutory cap (Tax Data: CAP_BASE).

Net Cumulative Income: Gross - Social Security - Union Fees.

Taxable Base: Net Cumulative - (Personal Deductions + General Deductions).

Tax Determination: Applies the 9-tier progressive scale (5% to 35%) on the surplus.

Final Net: Gross - (Social Security + Union + Income Tax).

## License
This project is licensed under the MIT License. You are free to modify and distribute this tool for educational or corporate internal use.

---

## Installation & Usage

Since this is a lightweight, zero-dependency tool, no installation is required.

### Option A: Direct Usage
1.  Download the `index.html` file.
2.  Double-click to open it in any modern web browser (Chrome, Edge, Safari, Firefox).

### Option B: Hosting
You can deploy this file to any static hosting service (GitHub Pages, Vercel, Netlify) or an internal corporate intranet.

```bash
# Example: Serving locally with Python
python3 -m http.server 8000
# Open http://localhost:8000 in your browser

---
