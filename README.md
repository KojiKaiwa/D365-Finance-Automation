# D365-Finance-Automation
🛡️ Finance & Compliance Automation Toolkit
This repository demonstrates advanced data validation and risk analysis workflows for Dynamics 365 Finance.
As a Finance Tech Lead, I focus on bridging the gap between ERP integrity and AI-driven insights to ensure operational excellence and financial compliance.

・Developed an AI-driven Knowledge Base matching system to accelerate incident resolution  
・Built an AI performance monitoring system to calculate the accuracy of knowledge base matching  
・Implemented a knowledge self-growth loop: AI-generated drafts for unresolved support inquiries  
・Built an AI Quality Monitoring system with automated alerts for SLA breaches  
・Established a proactive AI performance monitoring and knowledge governance system  
・Developed an AI-driven expense audit system to identify policy violations and financial risks  
・Implemented Departmental Risk Exposure Analysis to monitor financial compliance and internal controls  
・Built a Budget Forecasting tool for D365 Finance to predict year-end overruns and provide consultant recommendations  
・Visualized Budget vs. Forecast gaps using Matplotlib to support strategic financial planning  
・Developed a general ledger audit tool for D365 F&O to detect duplicate journal entries and mitigate compliance risks  
・Enhanced ledger audit tool to calculate the financial impact of duplicate entries and generate adjustment recommendations  
・Developed an Accounts Receivable Aging Analysis tool for D365 F&O to evaluate collection risks and predict cash flow impacts  
・Added portfolio analysis logic to calculate AR risk composition rates and generate working capital strategy recommendations  
・Refactored aging analytics loop to support dynamic date processing and format validation  
・Automated a prioritized debt collection task generator using multi-variable rule scoring in D365 F&O context  
・Finalized the collections automation workflow by implementing an automated CSV task-list exporter with dynamic time-stamping  
・Developed a fixed assets depreciation audit engine for D365 F&O to detect calculation variances and profile misconfigurations  
・Enhanced the asset audit engine to automatically generate IFRS/GAAP compliant journal adjustments based on materiality thresholds  
・Developed a 3-Way Matching audit engine for D365 F&O procurement to detect vendor overcharges and partial delivery discrepancies  
・Added purchase overcharge risk analysis to calculate procurement variance impacts and support internal cash control governance  
・Developed an inventory cost accounting audit engine for D365 F&O to detect standard cost variances and automate master data adjustment advice  
・Enhanced inventory cost audit toolkit to calculate financial impacts on COGS and asset valuation, simulating D365 Cost Rollup scenarios  
・Finalized the comprehensive D365 F&O Cross-Module Audit Dashboard, integrating General Ledger, Procurement, and Cost Accounting analytics  
・ Developed an automated data migration pipeline using **Python (Pandas)** to map legacy account codes to new system configurations.  
・ Implemented error-handling logic using `.isna()` to catch unmapped data, automatically exporting discrepancies to a BOM-included CSV file.  
・ Built a dynamic master-data integration loop utilizing `dict(zip())` to reprocess errors and validate data integrity with zero manual overrides.  
・Developed a post-migration ledger verification engine using **Python (Pandas)** to cross-check opening balances against legacy systems.  
・Implemented robust `how='outer'` merge and `fillna(0)` logic to ensure missing master accounts are not dropped during reconciliation.  
・Refactored calculation directions (`Legacy_Balance` - `New_Balance`) and mapped intuitive human-readable status labels to deliver accurate, audit-ready financial insights for executive stakeholders.  

・Engineered a batch transaction auditing tool using **Python (Pandas)** to verify system-to-system data migrations via record counts and monetary calculations.  
・Utilized `.abs().sum()` logic to create a robust Hash Total verification script, completely preventing the cancellation of debit/credit signs to detect data truncation.  
・Designed a line-by-line debugger using `pd.merge()` with custom `suffixes` to instantly target corrupted row identifiers (`LineID`) and automate engineering root-cause instructions.  
・Developed an automated date-standardization engine using **Python (Pandas)** to parse mixed transactional date formats (`/`, `.`, and unseparated strings) into a uniform `YYYY-MM-DD` format.  
・Leveraged `pd.to_datetime()` with `format='mixed'` and `errors='coerce'` to isolate invalid data inputs while preserving structural data integrity for complex ERP data migrations.  
・Sanitized non-uniform master files by systematically stripping full-width and half-width leading/trailing whitespaces.  
・Developed an advanced corporate-suffix normalization logic (e.g., handling legal prefixes/suffixes like "株式会社" or "(株)") using regular expressions (re) to ensure high-accuracy entity matching.  
・Executed a precise master-data deduplication pipeline utilizing keep='first' to preserve the baseline master records while eliminating duplicate vendor accounts.  
・Established rigid data integrity rules to prevent critical operational errors such as duplicate invoice payments across sub-ledgers.  
・Executed systematic testing protocols by isolating verification workspaces to prevent index corruption during the debugging phase.  
・Developed a comprehensive master data cleansing script using **Python (Pandas)** to standardize vendor nomenclature.  
・Employed `str.strip(' 　')` to truncate both full-width and half-width leading/trailing whitespace anomalies, preventing downstream multi-profile record duplication.  
・Implemented data purge mechanisms via `drop_duplicates(keep='last')` to isolate audit trail logs and automatically retain the most recent system records.  
  
## Feature Update: Enterprise 3-Way Matching (PO-GR-INV Reconciler)  
### Architectural Workflow  
1. **Multi-Stage Inner Joins:** Combines data feeds from Procurement (Purchase Orders), SCM/Warehouse (Goods Receipts), and Accounts Payable (Invoices).  
2. **Composite Key Alignment:** Performs strict joins on composite primary keys (`PO_Number` + `Item_Code`) to ensure line-level auditing granularity.  
3. **Discrepancy Matrix Generation:** Computes boolean flag vectors (`Qty_Match` & `Amount_Match`) to instantaneously evaluate system alignment.  
### Target Anomalies Isolated  
・**Quantity Mismatch (Under/Over-delivery):** Catches instances where items received at the warehouse do not match the contractual PO volume.  
・**Financial Mismatch (Over-billing):** Proactively flags supplier invoice variations against approved purchasing thresholds before general ledger posting.  
・Automated Discrepancy Detection:Utilizes Pandas `merge` with join indicators to compare transactional sub-ledgers against the master registry, flagging any unregistered or unauthorized vendor accounts (e.g., catching unmapped accounts like `VEND099`).  
・Audit Trail Generation:Isolates discrepancy logs, filters out unnecessary processing artifacts, and automatically compiles the exceptions into a dedicated audit report (`Audit_Alert_Report.xlsx`).  
・Sub-ledger Safeguards:Provides immediate visibility into internal control gaps, ensuring all purchase orders tie out to valid master profiles to mitigate the risk of financial leakage or inaccurate general ledger mapping.  
## Feature Update: Automated Cash Reconciliation & Variance Analyzer
A high-performance cash reconciliation module was integrated to simulate automated clearinghouse (ACH) and bank lockbox processing. This tool automates the validation loop between transactional merchant sales and actual cash receipts, which is a foundational requirement for high-volume FinTech and payment systems.

### Key Capabilities
・**Automated Clearing & Matching:** Leverages left outer joins on unique transaction identifiers (`Transaction_ID`) to verify whether sales records have successfully cleared the banking sub-ledger.
・**Dual-Tier Anomaly Detection:** 
  - **Uncredited Revenue Alert:** Automatically catches unmapped/unpaid ledger items where transactions exist but corresponding bank records are missing.
  - **Calculation Variance Alert:** Proactively flags processing errors or incorrect fee deductions by running delta calculations (`Expected_Net` vs. `Actual_Net`).
・**Production-Grade Code Quality:** Implemented explicit deep copies (`.copy()`) during data frame slicing to mitigate pointer ambiguity and prevent `SettingWithCopyWarning`, ensuring deterministic data integrity.
## Feature Update: Automated Cash Reconciliation & Variance Analyzer
A high-performance cash reconciliation module was integrated to simulate automated clearinghouse (ACH) and bank lockbox processing. This tool automates the validation loop between transactional merchant sales and actual cash receipts, which is a foundational requirement for high-volume FinTech and payment systems.

### Key Capabilities  
・**Automated Clearing & Matching:** Leverages left outer joins on unique transaction identifiers (`Transaction_ID`) to verify whether sales records have successfully cleared the banking sub-ledger.  
・**Dual-Tier Anomaly Detection:**   
  - **Uncredited Revenue Alert:** Automatically catches unmapped/unpaid ledger items where transactions exist but corresponding bank records are missing.  
  - **Calculation Variance Alert:** Proactively flags processing errors or incorrect fee deductions by running delta calculations (`Expected_Net` vs. `Actual_Net`).  
・**Production-Grade Code Quality:** Implemented explicit deep copies (`.copy()`) during data frame slicing to mitigate pointer ambiguity and prevent `SettingWithCopyWarning`, ensuring deterministic data integrity.  
