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
