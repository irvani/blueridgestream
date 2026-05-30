# Free Domain & Web Hosting Deployment Playbook
## Blue Ridge Stream Restoration & Mitigation LLC

**Co-Founder & Managing Director**: Hunter (Fly Fishing Georgia North Mountains)  
**Board Member**: Hadi Irvani (General Partner at Infill Capital Partners, University of Virginia - UVA)  
**Strategic Advisor & Sponsor**: Hill Hardman (Granite Holdings)  
**Ultimate KPI**: Fund world-class fly fishing trip to Argentina!  

---

This playbook walks you through registering a **free, high-quality `.us.kg` domain** using the **DigitalPlat FreeDomain** network, selecting the optimal short name for the business, and pushing the web assets (`index.html`, `portal.html`, `styles.css`, and images) to a free, premium hosting provider (like GitHub Pages or Vercel) bound to your custom domain.

---

## 🌐 Part 1: How to Register Your Free `.us.kg` Domain

DigitalPlat FreeDomain is a nonprofit registry sponsored by the Hack Foundation that allows individuals and organizations to claim free delegated subdomains (such as `.us.kg`) and configure them with custom nameservers. 

### Step 1: Claim Your Account & Complete GitHub KYC
1.  **Register an Account**: Navigate to the DigitalPlat FreeDomain Dashboard:  
    👉 [https://dash.domain.digitalplat.org/auth/register](https://dash.domain.digitalplat.org/auth/register)
2.  **Verify via GitHub**: To prevent domain abuse and automated bot registrations, DigitalPlat requires a quick GitHub account verification. 
3.  **Complete the KYC Issue (If required)**: If prompted for manual verification:
    *   Go to the official issue repository: [https://github.com/DigitalPlatDev/FreeDomain-Issues](https://github.com/DigitalPlatDev/FreeDomain-Issues).
    *   Open a new issue with the title format: `Request GitHub KYC - [your_github_username]`.
    *   Once approved, your dashboard account will be fully unlocked.

### Step 2: Choose Your Domain Name
In the dashboard, click **Register Domain**, type your desired name, and select the **`.us.kg`** extension from the dropdown. 

---

## 📛 Part 2: Proposing a "Nice Short Name" under `.us.kg`

A short, memorable domain name looks highly professional on LinkedIn posts, business cards, and B2B emails. Here are the top proposed short names for Hunter's stream restoration business:

| Domain Name | Business Alignment | Brand Value | Availability Tier |
| :--- | :--- | :--- | :--- |
| **`brs.us.kg`** | **Blue Ridge Stream** | ★★★★★ (Shortest, highly B2B-friendly) | Premium Short |
| **`blueridge.us.kg`** | **Blue Ridge Stream Restoration** | ★★★★★ (Full brand authority) | Standard Brand |
| **`trout.us.kg`** | **Trout Streams** | ★★★★☆ (Highlights the ecological niche) | Category Generic |
| **`ncd.us.kg`** | **Natural Channel Design** | ★★★★☆ (Positions as technical expert) | Technical Generic |
| **`creek.us.kg`** | **Creek Restoration** | ★★★★☆ (Subtle, organic mountain aesthetic) | Category Generic |
| **`mitigation.us.kg`** | **Mitigation Banking** | ★★★☆☆ (Directly targets credit buyers) | Business Generic |
| **`restoration.us.kg`** | **Stream Restoration** | ★★★★☆ (High geographic authority) | Business Generic |
| **`acr.us.kg`** | **Anderson Creek Restoration** | ★★★☆☆ (Specific to the flagship project) | Site Specific |

*👉 **Recommendation**: First attempt to register **`brs.us.kg`** or **`blueridge.us.kg`** as they represent the highest brand value for B2B developer outreach.*

---

## 🚀 Part 3: Deploying ("Pushing") the Site and Hosting it for Free

Once your domain (e.g., `brs.us.kg`) is registered, you need to point its DNS settings to a free, fast web host. We recommend using **Cloudflare** as the DNS manager, paired with either **GitHub Pages** or **Vercel** for hosting.

```
                      WEB DEPLOYMENT PIPELINE
                      
   [ Local Folder ] ───────> [ GitHub Repo ] ───────> [ Vercel / GitHub Pages ]
  index.html, portal.html    "blueridgestream"            Free Premium Hosting
  
                                                               │
                                                               ▼
   [ Cloudflare DNS ] <─────────────────────────────── [ brs.us.kg Domain ]
   CNAME / A Records                                      DigitalPlat Dash
```

---

### Method A: GitHub Pages (Easiest Native Deploy)
GitHub Pages hosts static HTML sites directly from a GitHub repository for free.

1.  **Create a GitHub Repository**: Log in to GitHub and create a public repository named `blueridgestream`.
2.  **Push Your Files**:
    *   Initialize Git in your local folder:
        ```bash
        git init
        git add .
        git commit -m "Initial launch of Blue Ridge Stream Restoration"
        ```
    *   Link to your GitHub repo and push:
        ```bash
        git remote add origin https://github.com/[your_username]/blueridgestream.git
        git branch -M main
        git push -u origin main
        ```
3.  **Enable GitHub Pages**:
    *   In your GitHub repository, go to **Settings** > **Pages** (in the sidebar).
    *   Under *Build and deployment*, set the Source to **Deploy from a branch**.
    *   Under *Branch*, select **`main`** and **`/ (root)`**, then click **Save**.
4.  **Bind Your Custom `.us.kg` Domain**:
    *   In the GitHub Pages settings, scroll down to **Custom domain**.
    *   Type your registered domain: `brs.us.kg` and click **Save**.
    *   Check **Enforce HTTPS** to secure the connection.

---

### Method B: Vercel (Highly Premium, One-Click Deploys)
Vercel is an elite hosting provider that integrates with GitHub, offering fast global content delivery network (CDN) speeds, beautiful previews, and automated SSL.

1.  **Sign Up for Vercel**: Go to [https://vercel.com](https://vercel.com) and register for a free "Hobby" account using your GitHub login.
2.  **Import Your Repo**: 
    *   In the Vercel dashboard, click **Add New** > **Project**.
    *   Import your `blueridgestream` repository.
    *   Keep the default settings and click **Deploy**. Vercel will deploy your site in under 30 seconds!
3.  **Add Your Custom Domain**:
    *   In your Vercel project, go to **Settings** > **Domains**.
    *   Type your registered domain: `brs.us.kg` (or `www.brs.us.kg`) and click **Add**.
    *   Vercel will display the exact DNS records (CNAME or A records) you need to add to your DNS manager.

---

## 🛠️ Part 4: Configuring DNS Settings (Cloudflare Integration)

To connect your DigitalPlat domain to Vercel or GitHub Pages, you must manage its DNS zone using **Cloudflare** (which is free and provides outstanding security and speed).

### Step 1: Set Up Cloudflare
1.  Sign up for a free account at [https://dash.cloudflare.com](https://dash.cloudflare.com).
2.  Click **Add Site** and type your registered domain (e.g., `brs.us.kg`).
3.  Select the **Free Plan** ($0).
4.  Cloudflare will scan your domain and provide you with **two Nameservers** (e.g., `alisa.ns.cloudflare.com` and `ed.ns.cloudflare.com`).

### Step 2: Point Nameservers in DigitalPlat Dashboard
1.  Log in to your [DigitalPlat FreeDomain Dashboard](https://dash.domain.digitalplat.org/).
2.  Select your registered domain (`brs.us.kg`).
3.  Change the Nameservers to the two custom nameservers provided by Cloudflare.
4.  Wait 5–10 minutes for the DNS records to delegate.

### Step 3: Add Host records in Cloudflare
Once Cloudflare is active, go to the **DNS** tab in your Cloudflare dashboard and add the appropriate records based on your hosting choice:

#### 1. If Using GitHub Pages:
*   **CNAME Record**: 
    *   *Type*: `CNAME`
    *   *Name*: `@` (root)
    *   *Target*: `[your_github_username].github.io`
    *   *Proxy Status*: DNS Only (Grey Cloud - recommended for initial custom domain verification).
*   **Alternative (A Records)**: Point to GitHub's official Pages IPs:
    *   A Record -> `@` -> `185.199.108.153`
    *   A Record -> `@` -> `185.199.109.153`
    *   A Record -> `@` -> `185.199.110.153`
    *   A Record -> `@` -> `185.199.111.153`

#### 2. If Using Vercel:
*   **A Record** (For root domain, e.g., `brs.us.kg`):
    *   *Type*: `A`
    *   *Name*: `@`
    *   *IPv4 Address*: `76.76.21.21` (Vercel’s global IP)
    *   *Proxy Status*: DNS Only / Proxied
*   **CNAME Record** (For subdomain, e.g., `www.brs.us.kg`):
    *   *Type*: `CNAME`
    *   *Name*: `www`
    *   *Target*: `cname.vercel-dns.com`

---

## 🎯 Part 5: Launching Your Portals!

Once DNS propagation is complete (typically under 1 hour), Hunter's business is officially live on the internet! 

*   **Public Site**: Anyone typing **`http://brs.us.kg`** will see the beautiful, responsive B2C marketing landing page, establishing professional credibility for Mike Irby, Jeff Fuqua, or local trout estate owners.
*   **Private Operations Portal**: Hunter can access his highly confidential operational databases, CRM, and real-time USACE SOP calculator by typing **`http://brs.us.kg/portal.html`** in his browser from any computer, securely powered by his own domain!
