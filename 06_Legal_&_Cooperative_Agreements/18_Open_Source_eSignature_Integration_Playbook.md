# Open-Source Electronic Signature Integration Playbook
## Blue Ridge Stream Restoration & Mitigation LLC

**Founder & Managing Director**: Hunter Morris (*Fly Fishing North Georgia*, bookings@flyfishingnorthgeorgia.com)  
**Co-Founder & Board Member**: Hadi Irvani (General Partner at Infill Capital Partners, University of Virginia - UVA)  
**Strategic Advisor & Sponsor**: Hill Hardman (Granite Holdings)  
**Ultimate KPI**: Fund world-class fly fishing trip to Argentina!  

---

## 1. Executive Summary

To execute stream mitigation landowner agreements (such as the **File 16 Anderson Creek Joint Venture**) and credit sales contracts with zero recurring licensing overhead, Blue Ridge Stream Restoration & Mitigation LLC can deploy **Docuseal** or **OpenSign**—the leading enterprise-grade, fully open-source alternatives to DocuSign.

This playbook provides Hunter Morris with a complete engineering blueprint to deploy, configure, and operate a self-hosted e-signature platform. Additionally, it details the legal framework governing electronic signatures in the State of Georgia to ensure our contracts are 100% legally binding under both federal and state laws.

---

## 2. Open-Source Alternatives to DocuSign

```
                       DOCUSEAL DEPLOYMENT PIPELINE
                       
   [ Developer Local ] ───────> [ self-Hosted Server ] ───────> [ Secure e-Sign ]
    cooperative JV              Docker / Vercel / Render          100% Legally Binding
    Contract PDF                Docuseal Platform                 Zero Monthly Fees
```

### A. Docuseal (Recommended)
*Docuseal is a highly polished, fully featured open-source platform designed to create, send, and execute documents electronically. It provides a drag-and-drop fields manager identical to DocuSign.*

*   **GitHub Repository**: [https://github.com/docusealco/docuseal](https://github.com/docusealco/docuseal)
*   **Official Site**: [https://www.docuseal.com](https://www.docuseal.com)
*   **Key Advantages**:
    *   **Self-Hosted for Free**: Can be deployed on a free-tier hosting provider (e.g., Render, Railway, or Fly.io) or a local machine.
    *   **Custom Form Creator**: Drag-and-drop signature, initials, date, text, and checkbox fields directly onto our contract PDFs.
    *   **API-First Architecture**: Allows automated landing page form submissions (like our Landowner Sourcing Form) to generate contracts instantly.
    *   **Zero Limits**: Send unlimited documents to unlimited signers with zero monthly fees.

### B. OpenSign
*OpenSign is another powerful, secure open-source e-signature platform focused on compliance, audit trails, and document security.*

*   **GitHub Repository**: [https://github.com/OpenSignLabs/OpenSign](https://github.com/OpenSignLabs/OpenSign)
*   **Official Site**: [https://www.opensignlabs.com](https://www.opensignlabs.com)
*   **Key Advantages**:
    *   **Cryptographic Verification**: Generates PDF certificates with unique cryptographic hashes for every completed signature.
    *   **Comprehensive Audit Logs**: Tracks signers' IP addresses, emails, timestamps, and browser configurations.
    *   **Multi-Tenant Architecture**: Supports different organizational teams (e.g., land sourcing vs. credit sales).

---

## 3. Step-by-Step Self-Hosting Deployment Guide

Hunter can deploy **Docuseal** in under 10 minutes using **Docker** or free-tier cloud platforms.

### Method A: One-Click Cloud Deployment (Railway or Render)
1.  Create a free account on **Railway** ([https://railway.app](https://railway.app)) or **Render** ([https://render.com](https://render.com)).
2.  Click **New Project** and search for the pre-configured **Docuseal** template in their template registry.
3.  Fill in the environment variables (keep defaults) and click **Deploy**.
4.  Railway/Render will compile the image and provide a secure, private URL (e.g., `https://blueridgesign.up.railway.app`).
5.  Open the URL, create your master admin account, and upload your logo to brand the interface!

### Method B: Local or Virtual Private Server (VPS) Docker Deployment
If you own a dedicated server or VPS (such as a DigitalOcean droplet), deploy Docuseal using Docker Compose:

```yaml
version: '3.8'

services:
  docuseal:
    image: docusealco/docuseal:latest
    ports:
      - "3000:3000"
    environment:
      - DATABASE_URL=postgres://user:password@db:5432/docuseal
      - PORT=3000
    volumes:
      - docuseal_data:/var/lib/docuseal
    restart: always

volumes:
  docuseal_data:
```

Run the container:
```bash
docker-compose up -d
```
Access the platform at `http://[your-server-ip]:3000`.

---

## 4. Contract Template & Signer Mapping

Once Docuseal is running, Hunter should configure the **Roya's Cabin Anderson Creek Mitigation Agreement** template:

```
                      DOCUSEAL FIELD PLACEMENT MAP
                      
  ┌─────────────────────────────────────────────────────────────┐
  │                                                             │
  │  IN WITNESS WHEREOF, the Parties have executed this JV...   │
  │                                                             │
  │  LANDOWNER:                           DEVELOPER:            │
  │                                                             │
  │  Signature: [ [Signature 1] ]         Signature: [ [Sig 2] ]│
  │                                                             │
  │  Name: Roya Irvani                    Name: Hunter Morris   │
  │  Date: [ [Date 1] ]                   Date: [ [Date 2] ]    │
  │                                                             │
  └─────────────────────────────────────────────────────────────┘
```

1.  **Generate Contract PDF**: Save the finalized **File 16** (`16_Roya_Cabin_Anderson_Creek_Mitigation_Agreement.pdf`) to your computer.
2.  **Upload to Docuseal**: Click **Templates** > **Create Template** and upload the PDF.
3.  **Define Signer Roles**:
    *   *Role 1*: **Landowner** (Roya Irvani)
    *   *Role 2*: **Developer** (Hunter Morris / Hadi Irvani)
4.  **Drag-and-Drop Fields**:
    *   Scroll to the signature block page.
    *   Drag a **Signature Field** and assign it to the *Landowner*. Add a **Date Field**.
    *   Drag a **Signature Field** and assign it to the *Developer*. Add a **Date Field**.
5.  **Publish Template**: Save the template as "Anderson Creek Mitigation JV Agreement".
6.  **Send for Signature**: Click **Send**, enter Roya's email (`roya.irvani@example.com`) and Hunter's email (`bookings@flyfishingnorthgeorgia.com`), and click **Send**. The platform will securely email both parties unique links to sign.

---

## 5. Electronic Signature Legal Compliance (State of Georgia)

To ensure our joint-venture agreements and credit sales contracts hold 100% legal weight in a court of law, Docuseal/OpenSign must satisfy the strict standards of both federal and state electronic signature statutes:

### A. The Federal ESIGN Act (15 U.S.C. Chapter 96)
Enacted in 2000, this federal statute grants electronic signatures the exact same legal status as traditional wet-ink pen signatures, stating that a contract "may not be denied legal effect, validity, or enforceability solely because an electronic signature was used in its formation."

### B. The Georgia Uniform Electronic Transactions Act (UETA) (O.C.G.A. § 10-12-1 et seq.)
Georgia's state-level statute directly reinforces the federal ESIGN Act, confirming the validity of electronic records and signatures. To fully comply with Georgia UETA, our e-signature pipeline must satisfy four core legal pillars:

1.  **Intent to Sign**: The signer must demonstrate clear intent to execute the contract. Selecting a pre-drawn signature or drawing on a canvas and clicking "Agree & Sign" legally establishes this intent.
2.  **Consent to Do Business Electronically**: The platform must present a standard disclosure before signing (e.g., *"By clicking agree, you consent to execute this stream mitigation agreement electronically"*).
3.  **Association of Signature to Record**: The cryptographic signature data must be securely locked and hardcoded directly into the resulting PDF file, preventing modifications to the contract text post-execution.
4.  **Retention & Access**: The system must automatically email a completed, flattened PDF copy containing the signature stamps to both the Landowner and Developer for their corporate files.

---

## 6. Sourcing Siting Economics & e-Signature Checklist

When Hunter meets a potential landowner to secure a new stream restoration reach, he can execute this 5-step sourcing process to ensure mutual confidence:

1.  **Run Siting Calculator**: Proactively model the stream reach length using the operations portal calculator (e.g., a $220,000 budget for a 1,500-LF reach yields **12,900 credits** valued at **$2.32M**).
2.  **Present 70/30 JV Economics**: Walk the landowner through the project's financials. Emphasize that they receive **30% of the credits ($696,600 value)** with **zero financial risk**, while we absorb all CapEx and engineering liabilities.
3.  **Confirm Easement Boundaries**: Align on the perpetual 100-foot buffer boundaries and explain the long-term conservation benefits for trout populations.
4.  **Select Signature Method**:
    *   *Method A (On-Site)*: Open the **Digital Contract Signer** tab directly in our Operations Portal on a tablet, review the terms with the landowner, and draw signatures instantly.
    *   *Method B (Remote)*: Email a secure e-signature packet via your self-hosted **Docuseal** platform.
5.  **File with USACE**: Immediately forward the signed PDF contract to Mitigation Branch Lead **Justin Hammonds** (`justin.a.hammonds@usace.army.mil`) as the legal binding land asset baseline for our Draft Prospectus filing.
