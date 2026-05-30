# File 39: Clemson Workstream — Page 4: Open Source Business Systems Integration & Accounting Systems Audit

> [!NOTE]
> **Mitigation Finance & Real Estate Operations Manual**  
> **Target School**: Clemson University Wilbur O. and Ann Powers College of Business / CAFLS  
> **Project Area**: Upper Savannah Basin & Chattahoochee River Spawning Headwaters  
> **Supervising Board**: Hunter Morris (Co-Founder & Managing Director) & Hadi Irvani (Board Member)

---

## 1. Executive Summary: Systems Integration & Efficiency

For a boutique ecological restoration firm like **Blue Ridge Stream Restoration & Mitigation LLC**, operational margins depend heavily on keeping overhead low. 

By avoiding expensive commercial SaaS suites (e.g., Salesforce's $150/user/mo fees) and instead using self-hosted, robust **open-source business systems** integrated with industry-standard platforms (AWS, GitHub, QuickBooks, Google Drive), we maintain high efficiency and data transparency. 

As a Clemson Real Estate & Finance Intern, you will audit, maintain, and integrate our enterprise systems architecture.

---

## 2. The 5-Layer Corporate Systems Architecture

Our company operates on a modular, secure, and low-cost digital foundation:

```
                      ENTERPRISE SYSTEMS FLOW
                      
   +-----------------------------------------------------------------+
   |   1. Google Drive (Document Storage & Operational Folders)       |
   +-----------------------------------------------------------------+
                                  |
                                  v
   +-----------------------------------------------------------------+
   |   2. GitHub & GitHub Pages (VCS, CI/CD, & Public Web Portal)    |
   +-----------------------------------------------------------------+
                                  |
                                  v
   +-----------------------------------------------------------------+
   |   3. AWS Cloud (Amazon S3 and EC2 secure backup servers)        |
   +-----------------------------------------------------------------+
                                  |
                                  v
   +-----------------------------------------------------------------+
   |   4. QuickBooks Online (General Ledger & Joint Venture Escrow)   |
   +-----------------------------------------------------------------+
                                  |
                                  v
   +-----------------------------------------------------------------+
   |   5. Open-Source CRM (Odoo/Corteza self-hosted sales pipelines) |
   +-----------------------------------------------------------------+
```

---

## 3. Detail Layer Integrations

### Layer 1: Google Drive (Structured Document Repository)
We maintain a pristine, numbered folder hierarchy in Google Drive to store all legal, regulatory, and engineering records. This mirrors the exact repository layout on our GitHub portal. Your role is to ensure all compiled PDFs, Word files, and design spreadsheets are immediately filed under their respective folders:
- `01_Strategic_&_Business_Plans` (Business plan, board recruiting, Hunter's guide)
- `02_Regulatory_&_USACE_Frameworks` (Georgia SOP SOP guides, bioengineering manuals)
- `03_Project_Case_Studies` (Anderson Creek and Goldmine Hollow blueprints)
- `04_Market_&_Competitor_Intelligence` (Competitor analysis, data center databases)
- `05_Sales_&_Outreach_Playbooks` (Outreach playbooks, cold templates)
- `06_Legal_&_Cooperative_Agreements` (Landowner JVs, risk bylaws, signature logs)
- `07_Marketing_&_Social_Content` (LinkedIn B2B posts, SEO metadata guides)
- `08_Recruiting_&_Internships` (University postings, intern training workstreams)
- `09_Operations_&_Technical_Playbooks` (Domain setup, hosting guides)
- `10_Outreach_&_Relationship_Banking` (Banker and lawyer databases, Sapelo Island SEO links)

### Layer 2: GitHub & GitHub Pages (VCS, CI/CD, and Web Portal)
- **Version Control**: All code, web styling (`styles.css`), and geomorphic manual assets are tracked in our public GitHub repository `https://github.com/irvani/blueridgestream`.
- **Automatic Deployment**: We utilize GitHub Actions. When changes are pushed to `main`, the portal is compiled and deployed to **GitHub Pages** within seconds, serving the live site at `https://irvani.github.io/blueridgestream/portal.html` at **$0.00 hosting cost**.
- **Intern Action Item**: You must review git branches and coordinate with our GT engineering intern to ensure AutoCAD DXF files and PDF design plans are committed to the repository cleanly without cluttering files.

### Layer 3: AWS Cloud Infrastructure (Secure Storage and Compute)
- **Amazon S3**: While public marketing assets live on GitHub Pages, confidential contracts, bank accounts, and high-resolution LiDAR drone scans are backed up securely on **Amazon S3 (Simple Storage Service)** with strict access controls.
- **Amazon EC2**: We host our self-hosted applications (like our open-source CRM and Docuseal/OpenSign eSignature platforms) on a low-cost, secure **Amazon EC2** virtual server utilizing Docker containers.

### Layer 4: QuickBooks Online (Financial Ledger & Escrow Audits)
We utilize **QuickBooks Online (QBO)** for all financial operations. You will manage the general ledger, mapping accounts to the specialized **PeachDish Condensed Chart of Accounts**:
- **Escrow Accounting**: Set up a designated **Working Capital Reserve Escrow (WCRE)** sub-account. For every credit sale, QBO must route exactly $12.5\%$ of gross proceeds into the WCRE to build our geomorphic CapEx reserve.
- **Invoicing Developers**: Generate professional invoices to B2B buyers (e.g., QTS or Microsoft data centers) detailing credit quantities, HUC basins, and transaction totals.
- **Landowner JV Payouts**: Upon receiving cash, generate $30\%$ split payouts to the landowner (e.g., Roya Irvani) within 5 business days, logging the expense against the corresponding stream reach project class.

### Layer 5: Open-Source CRM (Odoo / Corteza)
Instead of paying exorbitant licensing fees to Salesforce, we deploy a self-hosted instance of **Corteza** or **Odoo Community Edition**.
- **CRM Setup**: Customize lead pipelines to track B2B sales leads:
  - **Prospects**: Profiled from the **15 Data Center Projects** (File 22), **50 Bankers** (File 24), and **50 Lawyers** (File 25).
  - **Pipeline Stages**: *Initial Contact / Cold Email sent -> Stream Walk scheduled -> USACE Permit Audit -> Credit Option Agreement drafted -> Contract signed -> Escrow closed -> Credit transfer recorded in RIBITS*.
- **Credit Inventory Ledger**: Maintain an active, real-time database showing released credits, pending releases, sold credits, and HUC basin availability to prevent double-selling.
