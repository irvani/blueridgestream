# File 28: Intern Workstreams & Operational Training Playbook

> [!IMPORTANT]
> **B2B Internship Operation Manual & Technology Blueprint**:
> - **Unified Infrastructure Stack**: All operations at Blue Ridge Stream are centralized across five standard software platforms: **AWS** (S3 data buckets, EC2 spatial compute, and RDS databases), **GitHub** (version control for CAD models and code pipelines), **QuickBooks Online** (financial accounting and margin carry reconciliations), **EspoCRM** (the premier open-source Salesforce alternative, deployed via Docker on AWS EC2), and **Google Drive** (central document repositories and GIS shapefiles).
> - **12-Page Intern Field Playbook**: This document defines three specialized, 4-page operational workstreams designed to delegate active project construction, biological permitting, and B2B sourcing pipelines to incoming university interns.

## I. Workstream 1: Fluvial Geomorphology & CAD/GIS Engineering Intern
*   **Primary Position Focus**: Fluvial Geomorphology, AutoCAD Civil 3D geomorphic surface modeling, HEC-RAS 2D flow simulations, and USACE Savannah SOP credit yield calculations.
*   **University Profile**: Georgia Tech / UGA Fluvial Engineering (Advanced Civil/Hydrology majors).

### --- [WORKSTREAM 1 - PAGE 1] ---
### AutoCAD Civil 3D Surface Modeling & HEC-RAS 2D Hydraulic Flow Simulations

#### 1. Geomorphic Design Construction Layout
Interns are responsible for importing high-density field total-station and RTK GPS survey data into AutoCAD Civil 3D to construct the existing digital terrain model (DTM). The intern must then execute the following design adjustments:
- **Narrow the Width-to-Depth Ratio ($W_{bkf}/d_{bkf}$)**: Using NCD methods, design a narrow bank-full channel width to accelerate water velocity during low-flow periods, keeping sediment moving and scouring deep, cold trout holding pools.
- **Instream Log Cross-Vanes & Boulder J-Hooks**: Overlay instream wood and rock structures. J-Hooks must be angled at 20 to 30 degrees to the bank, deflecting high-velocity stream flows toward the center of the channel to protect the bank from erosion.
- **High-Gradient Bank Regrading**: Design stable bank slopes ($\le 3:1$ or $4:1$) integrating native soil lifts and geomechanical geogrids to bind unstable bank soils.

#### 2. HEC-RAS 2D Hydrodynamic Modeling
To verify that the geomorphic designs will survive peak storm events, the intern must compile and run a HEC-RAS 2D model:
- **Import the Proposed Civil 3D XML Surface**: Export the design corridor surface as LandXML and import it as the terrain layer in RAS Mapper.
- **Generate 2D Mesh & Boundary Conditions**: Set a 2-foot mesh cell spacing. Set boundary condition lines for the upstream inlet (simulating 10-year and 100-year peak-flow storm events using USGS regression equations) and downstream outlet (normal depth).
- **Run Hydraulic Stress Simulations**: Calculate instream velocity ($V$), water surface elevation (WSE), and boundary shear stress ($	au$). Verify that the geomorphic design keeps shear stress below the failure limit of the geogrids, ensuring a safety factor $SF_{shear} \ge 1.5$.

### --- [WORKSTREAM 1 - PAGE 2] ---
### Rosgen Level III Fluvial Hydrology & Sediment Transport Equations

#### 1. Fluvial Hydrology & BANCS Model Audit
Interns must audit the existing geomorphic variables using the Rosgen Level III framework to calculate sediment supply and stream bank erosion rates:
- **Bank Erosion Hazard Index (BEHI)**: Physically measure bank height, root depth, root density, bank angle, and surface protection to assign a BEHI score (Low, Moderate, High, Extreme) for each reach.
- **Near-Bank Shear Stress (NBS)**: Calculate NBS by measuring the ratio of near-bank maximum depth to mean channel depth ($d_{nb}/d_{mean}$) or using velocity profile distributions.
- **Erosion Estimation**: Plot the BEHI and NBS variables on the Savannah District validation curves to estimate stream bank erosion rates in cubic yards per linear foot per year.

#### 2. Sediment Transport & Spawning Bed Flushing Mechanics
To prevent siltation of wild trout spawning gravels, interns must apply the dual-Shields bed flushing equations:
- **Determine Critical Shear Stress ($	au_c$)**: Calculate the shear stress required to move the median bed material ($d_{50} = 15\text{--}40\text{ mm}$):
  $$\tau_c = \theta_c \cdot (\gamma_s - \gamma_w) \cdot d_{50}$$
  where $\theta_c = 0.045$ is the dimensionless Shields parameter, $\gamma_s$ is sediment unit weight, and $\gamma_w$ is water unit weight.
- **Flushing Stress Window**: Verify that under bank-full velocity, the channel shear stress satisfies the flushing window ($1.46\text{ N/m}^2 < \tau < 21.85\text{ N/m}^2$). This ensures that high water flows self-clean fine clay silt without moving the heavy trout spawning gravels.

### --- [WORKSTREAM 1 - PAGE 3] ---
### AWS Spatial Compute Clusters & GitHub Version-Controlled CAD DWG Pipelines

#### 1. AWS EC2 Spatial Compute Cluster Setup
Large-scale AutoCAD Civil 3D rendering and HEC-RAS 2D hydraulic simulations require intensive CPU compute. Interns must deploy spatial compute nodes on AWS:
- **Spin Up AWS EC2 Compute Node**: Deploys an AWS EC2 instance (e.g. `c6i.4xlarge` featuring 16 vCPUs and 32GB RAM) running Ubuntu Server.
- **Install Geospatial Software Dependencies**: Install the GDAL spatial libraries and compile the USACE HEC-RAS engine locally:
  ```bash
  sudo apt-get update && sudo apt-get install -y gdal-bin libgdal-dev build-essential gfortran
  # Sync terrain and bathymetry data from the central AWS S3 spatial bucket
  aws s3 sync s3://blueridgestream-spatial-data/terrain/ ./local_terrain/
  ```
- **Execute Batch Hydraulic Simulations**: Execute HEC-RAS batch command simulations via the AWS CLI, outputting high-fidelity flood inundation spatial datasets.

#### 2. GitHub Version-Controlled CAD Pipelines
Because CAD binary drawings (`.dwg` or `.dxf` formats) are large and cannot be natively compared using line-by-line Git diffs, interns must deploy a version-controlled CAD pipeline on GitHub:
- **Setup Git LFS (Large File Storage)**: Initialize Git LFS in the project GitHub repository to handle binary CAD files:
  ```bash
  git lfs install
  git lfs track "*.dwg"
  git lfs track "*.dxf"
  git add .gitattributes
  ```
- **Version-Control & Pull Request Workflows**: Establish a feature-branch system. Every geomorphic design iteration must be committed with a detailed Markdown commit message describing the geomorphic slope changes. Merge changes into the `main` branch only after a peer review by Hunter Morris.

### --- [WORKSTREAM 1 - PAGE 4] ---
### Stream SOP Credit Yield Calculations & USACE Savannah District SOP Verification Protocols

#### 1. Savannah SOP Credit Yield Math
Interns must calculate the net credit yield of proposed projects using the USACE Savannah District Standard Operating Procedure (SOP) formulas:
- **Formula for Net Credit Lift ($CL_{net}$)**:
  $$CL_{net} = (M_{post} - M_{pre}) \cdot L_{reach} \cdot S_{factor}$$
  where $M_{pre}$ is the pre-restoration mitigation matrix score (typically 1.2 to 2.2), $M_{post}$ is the post-restoration design score (targeting 6.8 to 8.6 under Priority 1 NCD rules), $L_{reach}$ is reach length, and $S_{factor}$ is the watershed significance factor.
- **Compute Project Yield**: For Roya's Cabin Anderson Creek case study ($L_{reach} = 1,500\text{ LF}$): Calculate the geomorphic lift ($M_{post} - M_{pre} = 8.6 - 2.2 = 6.4$) to yield **12,900 stream credits**.

#### 2. USACE Savannah District IRT Verification Package Compilation
The intern must compile the final Mitigation Banking Instrument (MBI) coordinate documents for the Interagency Review Team (IRT) submission:
- **GIS Shapefiles**: Export AutoCAD boundary lines as ESRI Shapefiles, projecting them in UTM Zone 17N (NAD83 Georgia State Plane).
- **savannah District SOP Worksheet**: Complete the Excel SOP worksheets. Ensure every field is fully calculated with zero placeholders, including the Soil Erodibility Factor (K-value) and drainage basin square mileage.
- **USACE MBI Package Checklist**: Compile the 2D HEC-RAS flood maps, the Rosgen Level III geomorphic BANCS charts, and the water temperature monitoring logs into the final USACE Savannah District submittal package on Google Drive.


## II. Workstream 2: Coldwater Ecology & Environmental Permitting Intern
*   **Primary Position Focus**: Coldwater fisheries biology, wild trout habitat spawning restoration, thermal budget shading analysis, macroinvertebrate sampling, and Georgia EPD stream buffer variance permitting.
*   **University Profile**: UGA Odum School of Ecology / Clemson Environmental Sciences (Biology majors).

### --- [WORKSTREAM 2 - PAGE 1] ---
### Brook Trout Spawning Gravel Geomorphic Specs & Native Rhododendron Buffer Shade Formula Audits

#### 1. Spawning Gravel Geomorphic Specifications
To ensure the successful re-colonization of wild Brook, Rainbow, and Brown trout, interns must physically measure and sort the spawning gravel substrates:
- **Median Substrate Size ($d_{50}$)**: Substrate samples must fall within the range of **15 to 40 mm** (clean, rounded mountain river gravels).
- **Fine Sediment Constraint**: Sieve analysis must demonstrate that fine clays and sands ($<2\text{ mm}$) represent less than **8 percent** of the total substrate volume, preventing the smothering of trout eggs in spawning nests.
- **Instream Placement**: Place sorted spawning gravels directly at pool tailouts where upwelling water provides oxygen to the eggs.

#### 2. Thermal Cooling Shade Budget & Solar Attenuation Formulas
Interns must audit the shading canopy design to ensure stream summer water temperatures stay below the critical **65 degrees F** wild trout spawning limit:
- **Solar Radiation Attenuation Model**: Calculate the solar heat load reduction ($Q_{net}$) under the mature native Rhododendron maximum buffer canopy:
  $$Q_{net} = Q_{incoming} \cdot e^{-\kappa \cdot \text{LAI}}$$
  where $Q_{incoming}$ is open solar radiation, $\kappa = 0.65$ is the light extinction coefficient, and $\text{LAI} = 5.2$ is the leaf area index of the Rhododendron canopy.
- **Verify Attenuation**: Calculate that the mature canopy blocks **96 percent** of incoming solar radiation, maintaining the coldwater trout spawning thermal window.

### --- [WORKSTREAM 2 - PAGE 2] ---
### Macroinvertebrate EPT Index Bio-Assessments & Stream Water Quality/Thermal Sampling Logs

#### 1. Macroinvertebrate EPT Index Bio-Assessments
To verify the biological recovery of the stream, interns must conduct regular macroinvertebrate sampling and calculate the Ephemeroptera, Plecoptera, and Trichoptera (EPT) index:
- **Field Sampling**: Collect samples from three riffle sections using a standard 500-micron D-frame kick net.
- **Laboratory Identification**: Identify specimens to the family level using a dissecting microscope. Count the total families belonging to the three critical clean-water orders:
  - *Ephemeroptera (Mayflies)*: Baetidae, Heptageniidae.
  - *Plecoptera (Stoneflies)*: Perlidae, Pteronarcyidae.
  - *Trichoptera (Caddisflies)*: Hydropsychidae, Limnephilidae.
- **EPT Index Calculation**: Calculate the EPT score. A clean, healthy mountain stream must yield an EPT score **> 15**, verifying excellent water quality.

#### 2. Water Quality & Thermal Logger Protocols
Interns must maintain the network of on-site water quality sensors and loggers:
- **Deploy HOBO Water Temp Loggers**: Secure HOBO loggers inside steel protective pipes anchored deep within pools. Program them to log water temperatures every 15 minutes.
- **Download & Calibrate Data**: Download data monthly using the HOBO Mobile app. Calibrate the loggers against a NIST-certified thermometer to ensure high data quality.
- **Water Quality Testing Logs**: Measure dissolved oxygen (DO must be $\ge 7.0\text{ mg/L}$), pH ($6.5\text{--}8.0$), and turbidity ($<10\text{ NTU}$) using a calibrated multi-parameter water quality probe, logging all measurements in the central Google Drive database.

### --- [WORKSTREAM 2 - PAGE 3] ---
### DNR EPD State Stream Buffer Variance Filing Protocols & NEPA Permitting Review Cycles

#### 1. DNR EPD State Stream Buffer Variance Applications
Under Georgia law, any activity within the standard **25-foot state stream buffer** (or **50-foot trout stream buffer**) requires a variance from the Georgia DNR Environmental Protection Division (EPD). Interns must compile and file these applications:
- **Select the Buffer Variance Category**: File under *Category 1 (Restoration Projects)*, which allows buffer modifications that improve water quality and stream geomorphology.
- **Prepare the Buffer Mitigation Plan**: Draft a detailed revegetation plan incorporating only native streamside vegetation (such as mature native Rhododendron maximum, Mountain Laurel, and Black Willows) at a density of 400 plants per acre.
- **Compile the Engineering Exhibits**: Coordinate with the geomorphology intern to attach HEC-RAS 2D flood maps and AutoCAD drawings showing that the bioengineered restoration will not increase water velocity or erosion.

#### 2. USACE Nationwide Permit 27 (NWP 27) & NEPA Compliance
Stream restorations are typically permitted under USACE Nationwide Permit 27 (Aquatic Habitat Restoration). Interns must track compliance with the National Environmental Policy Act (NEPA):
- **Complete the Pre-Construction Notification (PCN)**: Complete the USACE Form 4345. Attach the geomorphic designs, the biological EPT baselines, and the EPD buffer variance application.
- **Coordinate with Regulatory Agencies**: Coordinate with USACE, EPA, Fish and Wildlife Service, and DNR EPD during the 45-day agency review period. Keep track of all regulatory comments on the central project Google Drive.

### --- [WORKSTREAM 2 - PAGE 4] ---
### AWS S3 Database Syncing of Field Drone Telemetry & Thermal Mapping Spatial Datasets

#### 1. AWS S3 Field Data Storage Architecture
To support the interactive canvas drone simulator on the portal, interns must organize and sync field drone data using AWS S3 storage buckets:
- **AWS S3 Bucket Structure**: Organize the `blueridgestream-field-telemetry` bucket into logical subdirectories for each project:
  `s3://blueridgestream-field-telemetry/projects/anderson-creek/orthomosaics/`
  `s3://blueridgestream-field-telemetry/projects/anderson-creek/thermal-scans/`
  `s3://blueridgestream-field-telemetry/projects/anderson-creek/hobo-temperature-logs/`
- **Setup AWS S3 Lifecycle Policies**: Configure lifecycle policies to transition raw drone footage and heavy orthomosaics to AWS S3 Glacier Deep Archive after 90 days, reducing storage costs by 75 percent.

#### 2. Programmatic Syncing via AWS CLI
Interns must run programmatic scripts to sync field datasets directly from on-site laptops to AWS S3:
- **Write the AWS S3 Upload Script**: Interns write a Python script that runs locally on field laptops to sync newly collected HOBO water temperature logs and drone thermal scans:
  ```python
  import boto3
  import os
  
  s3 = boto3.client('s3')
  bucket_name = 'blueridgestream-field-telemetry'
  local_folder = './field_data/anderson-creek/'
  
  for filename in os.listdir(local_folder):
      if filename.endswith('.csv') or filename.endswith('.tif'):
          local_path = os.path.join(local_folder, filename)
          s3_path = f'projects/anderson-creek/{filename}'
          s3.upload_file(local_path, bucket_name, s3_path)
          print(f'Uploaded {filename} to AWS S3!')
  ```
- **Setup Google Drive Backup Integration**: Automate a daily sync between Google Drive folder updates and the AWS S3 raw backup bucket to keep the entire team aligned.


## III. Workstream 3: B2B Business Development, Landowner Sourcing & CRM Intern
*   **Primary Position Focus**: B2B sales development, landowner joint-venture sourcing, county records search, open-source CRM architecture, and project carry-cost financial reconciliations.
*   **University Profile**: Clemson / UGA Terry College of Business (Real Estate/Finance/B2B Sales majors).

### --- [WORKSTREAM 3 - PAGE 1] ---
### Open-Source CRM (EspoCRM/SuiteCRM) Pipeline Architecture & Google Drive CRM Integrations

#### 1. Open-Source CRM Deployment & Lead Pipeline Architecture
To avoid expensive Salesforce licensing fees, Blue Ridge Stream uses **EspoCRM**, the leading open-source CRM alternative. Interns are responsible for managing EspoCRM, deployed via Docker on an AWS EC2 instance with an AWS RDS MySQL database:
- **EspoCRM Custom Fields**: Set up custom fields for the stream business, including HUC-8 River Basin, Stream Length (Linear Feet), Estimated USACE Credit Yield, and Landowner JV Split Ratio.
- **Sales Pipeline Stage Mapping**: Interns track deals through five specific pipeline stages:
  `1. Lead Sourcing (County Deed Audit)` $\rightarrow$ `2. Outreach (Initial Call/Stream Walk)` $\rightarrow$ `3. Geomorphic Valuation` $\rightarrow$ `4. USACE IRT Permitting` $\rightarrow$ `5. Signed JV (70/30 Contract)`

#### 2. Automated Google Drive & CRM Integrations
To keep land deeds and survey maps organized, interns manage automated integrations between the CRM and Google Drive:
- **Setup Automated Folder Generation**: Using EspoCRM Webhooks connected to Google Drive, configure the CRM to automatically generate a standard Google Drive folder structure when a lead is moved to the 'Geomorphic Valuation' stage:
  `Google Drive/ACR Stream Restoration/03_Project_Case_Studies/[Project_Name]/`
    `├── 01_AutoCAD_Designs/`
    `├── 02_USACE_SOP_Permitting/`
    `├── 03_Land_Deeds_&_Contracts/`
    `└── 04_Field_Drone_&_Photos/`
- **Maintain Google Drive Database Integrity**: Ensure all signed land option agreements and USACE SOP worksheets are saved in their respective project folders.

### --- [WORKSTREAM 3 - PAGE 2] ---
### County Record Deed Audits, Senior Mortgage Liens, & Escrow Covenants Sourcing Steps

#### 1. County Tax Assessor Sourcing Steps
Interns use county GIS platforms (such as Qpublic) to identify properties in North Georgia (Fannin, Union, Gilmer, Lumpkin counties) with degraded streams:
- **Filter Properties**: Filter for agricultural, forestry, or recreational parcels with at least 50 acres and 1,000 linear feet of stream channel.
- **Analyze Erosion via Orthomosaics**: Inspect high-resolution aerial imagery to locate severe stream bank erosion, mud-laden cattle access points, or washed-out crossings.
- **Export Owner Metadata**: Extract the owner's legal name, parcel ID, mailing address, and deed book/page numbers, importing them directly into EspoCRM.

#### 2. Legal Due Diligence: Title Audits & Mortgage Subordinations
Before Blue Ridge can invest capital into a stream restoration JV, interns must perform a title audit to manage financial risk:
- **Conduct Deed Registry Search**: Log into the Georgia Superior Court Clerks' Cooperative Authority (GSCCCA) database. Search the property's historical title chain to identify any outstanding mortgages, tax liens, or easements.
- **Manage Mortgage Lien Risks**: If the property is mortgaged, the land easement requires a recordable **Mortgage Subordination Agreement**. The intern must draft this agreement using the Blue Ridge legal resolution template, ensuring that the conservation easement survives foreclosure.
- **Establish Landowner Mitigation Escrow Account (LMEA)**: For mortgaged properties, structure an escrow account to capture a portion of credit sales, providing a backup to pay down the mortgage and secure the bank's approval.

### --- [WORKSTREAM 3 - PAGE 3] ---
### 70/30 Landowner JV Split Pitching Playbooks & Bank Special Asset Relationship Management

#### 1. Managing Bankers & Lawyers Referrals
Interns are responsible for managing relationships with the 50 relationship bankers (File 24) and 50 environmental/real estate lawyers (File 25) in Georgia:
- **Execute Sourcing Campaigns**: Send targeted email campaigns via EspoCRM, using the banker and lawyer outreach templates. Manage follow-ups and schedule virtual meetings.
- **Bank Special Assets Pitches**: Track bank foreclosures on Fannin and Union county land holdings. Pitch special asset managers on using a zero-CapEx stream JV to monetize non-performing land assets, helping the bank recover outstanding debt.

#### 2. Sourcing Landowners with the 70/30 Trout Pitch
Interns use a structured B2B sales playbook to close JVs with private landowners, presenting a premium alternative to high-overhead corporate competitors:
- **The RES Flat-Rate Sourcing Counter-Play**: Educate landowners that RES and EIP offer flat-rate credit royalties ($12–$25 per credit) which capture all the upside. Under Blue Ridge's 70/30 split, the landowner collects 30 percent of the actual market price ($33/credit at $110/credit), generating **more than double** the corporate payout.
- **Aesthetic & Financial Value Comparison**: Present a custom project model demonstrating how a 1,500-foot stream bank JV (such as Anderson Creek) yields **425,700 USD** in cash proceeds for the landowner, while building a pristine Brook Trout fly-fishing creek at **0 USD cost** to the owner.

### --- [WORKSTREAM 3 - PAGE 4] ---
### QuickBooks Online Financial Reconciliation & Project Margin Carrying Cost Math

#### 1. QuickBooks Online Accounting & Reconciliation
Interns manage the corporate books and track capital accounts in **QuickBooks Online**:
- **Invoice B2B Credit Sales**: When stream credits are sold (e.g. 5,000 credits sold to a data center client at $110/credit, totaling $550,000), generate the invoice in QuickBooks.
- **Reconcile JV Escrow Distributions**: Reconcile cash allocations according to the 70/30 contract. Transfer the landowner's 30 percent share ($165,000) and allocate the developer's 70 percent share ($385,000) to operational accounts.
- **Fund the Operational Escrows**: Transfer 12.5 percent of gross proceeds to the Working Capital Reserve Escrow (WCRE) account in QuickBooks, ensuring strict compliance with the bylaws.

#### 2. Project Margin & Carry Cost Math
Interns run financial models to evaluate capital carry costs and investment return (ROI) metrics:
- **Calculate Developer Project Carrying Cost ($CC$)**:
  $$CC = \text{CapEx} \cdot (1 + r)^t - \text{CapEx}$$
  where $\text{CapEx} = 345,000\text{ USD}$, $r = 8.5\%$ is the annual bank construction interest rate, and $t = 1.25\text{ years}$ is the permitting/construction cycle.
- **Verify Margin Calculations**: Reconcile carry costs ($CC = 37,284\text{ USD}$) against developer net proceeds ($993,300\text{ USD}$) to ensure the project Net Profit Margin exceeds **40 percent**, verifying the financial health of the stream venture.
