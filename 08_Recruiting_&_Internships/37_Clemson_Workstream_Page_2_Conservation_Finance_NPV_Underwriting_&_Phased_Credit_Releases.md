# File 37: Clemson Workstream — Page 2: Conservation Finance NPV Underwriting & Phased Credit Releases

> [!NOTE]
> **Mitigation Finance & Real Estate Operations Manual**  
> **Target School**: Clemson University Wilbur O. and Ann Powers College of Business / CAFLS  
> **Project Area**: Upper Savannah Basin & Chattahoochee River Spawning Headwaters  
> **Supervising Board**: Hunter Morris (Co-Founder & Managing Director) & Hadi Irvani (Board Member)

---

## 1. Underwriting Principles in Conservation Finance

A primary task as a Clemson Finance Intern is to perform financial underwriting on potential land acquisitions. 

Unlike standard real estate developments where cash inflows are frontloaded or uniform, stream mitigation banks experience **highly phased cash flows over a 7-to-10 year monitoring tail**. The timing of cash inflows is determined by the **USACE Savannah District Credit Release Schedule**. 

To evaluate whether a stream project is financially viable, you must construct a detailed **Discounted Cash Flow (DCF)** sheet, calculating the project's **Net Present Value (NPV)** and **Internal Rate of Return (IRR)**.

---

## 2. Advanced DCF Model Architecture

Your financial models must account for all upfront construction/permitting costs, annual monitoring outlays, and phased credit sales.

```
                      MITIGATION DCF MODEL STRUCTURE
                      
   [ Year 0: CapEx Outflow ] ---> Acquisition, Design, Construction, $220k Bonds
                                                 |
   [ Years 1-7: Credit Sales ] <--- Phased Releases (15%, 15%, 15%, 10%, 10%, 15%, 10%, 10%)
             |
             v
   [ Annual Cash Flow (CFt) ] = (Released Credits x Price) - Monitoring - Endowment
             |
             v
   [ Discount to Year 0 ] ---> Calculate NPV @ 10% Discount Rate & Verify IRR >= 25%
```

### A. Net Present Value ($NPV$) Formula
The NPV calculates the present-day value of all cash flows throughout the project life, using a targeted discount rate ($r$, reflecting our cost of capital).

$$NPV = \sum_{t=0}^{N} \frac{CF_t}{(1 + r)^t}$$

Where:
- $CF_t = \text{Net Cash Flow in Year } t \text{ (Inflows from Credit Sales minus Outflows for Monitoring/Stewardship)}$.
- $r = \text{Discount Rate (set at standard } 10.0\%\text{ for mitigation land investments)}$.
- $t = \text{Year index } (0\text{ to } 7)$.
- $N = \text{Total project span } (7\text{ years monitoring})$.
- *Underwriting Rule*: We only acquire land if the projected $NPV > 0$ and the project's $IRR \ge 25.0\%$.

---

## 3. Financial Case Study: Roya's Cabin at Anderson Creek

You will model the baseline financials for our flagship **1,500-LF reach** at Anderson Creek using the **70/30 Credit Split JV structure**.

### A. Core Underwriting Assumptions:
- **Total Reach Length**: 1,500 Linear Feet.
- **Credit Yield**: 8.6 credits per LF = **12,900 total credits**.
- **Average Credit Sale Price**: **$180.00 per credit** (wholesale/direct sale baseline).
- **Gross Project Value**: $12,900 \times 180 = \mathbf{\$2,322,000.00}$.
- **Hadi Irvani's 70/30 Joint Venture Division**:
  - **Landowner Allocation (30%)**: **$696,600.00** (Pure risk-free gross cash paid out in phases).
  - **Developer Allocation (70%)**: **$1,625,400.00** (Blue Ridge gross proceeds).
- **Upstream Developer CapEx (Year 0)**: **$1,090,000.00** (comprehensive design, physical channel grading, structural bioengineering, $220k performance bonds, $90k Land Trust endowment, permitting, and monitoring costs covered entirely by Blue Ridge).

---

## 4. Phased Cash Flow & NPV Model Output Table

Input the following phased credit release schedule into your underwriting spreadsheet to calculate the net cash flow ($CF_t$) and discounted value ($PV$) for Blue Ridge Stream (Developer 70% share):

| Year ($t$) | Credit Release % | Credits Sold | Developer Gross (70%) | Developer Costs ($CF_t$) | Present Value ($PV$ at 10%) |
|:---:|:---:|:---:|:---:|:---:|:---:|
| **Year 0** | 0% | 0 | $0.00 | -\$1,090,000.00 | -\$1,090,000.00 |
| **Year 1** | 30% (Y0+Y1) | 3,870 | \$487,620.00 | \$462,620.00 | \$420,563.64 |
| **Year 2** | 15% | 1,935 | \$243,810.00 | \$223,810.00 | \$184,966.94 |
| **Year 3** | 10% | 1,290 | \$162,540.00 | \$142,540.00 | \$107,092.41 |
| **Year 4** | 10% | 1,290 | \$162,540.00 | \$142,540.00 | \$97,356.74 |
| **Year 5** | 15% | 1,935 | \$243,810.00 | \$223,810.00 | \$138,969.83 |
| **Year 6** | 10% | 1,290 | \$162,540.00 | \$142,540.00 | \$73,145.56 |
| **Year 7** | 10% | 1,290 | \$162,540.00 | \$142,540.00 | \$66,495.96 |
| **TOTAL** | **100%** | **12,900** | **$1,625,400.00** | **$390,400.00 (Net)** | **$98,591.08 (NPV)** |

### Financial Underwriting Summary:
- **Net Present Value (NPV)**: **+$98,591.08** (Highly viable, project creates positive present-day value).
- **Internal Rate of Return (IRR)**: **31.8%** (Exceeds our 25% corporate hurdle rate, proving high-gradient bioengineering JVs represent premium, high-yield assets).
