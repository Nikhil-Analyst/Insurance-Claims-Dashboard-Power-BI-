# Insurance Claims Dashboard (Power BI)

### Dashboard link: https://app.powerbi.com/groups/6d3dc93a-cd0e-4655-b070-6dd6073d299f/reports/6a096a8e-570b-4659-96cb-f66ff6b4bcd5/ReportSection?experience=power-bi

##  Overview  
This project analyses insurance policy and claims data to uncover insights into **premium distribution, claim settlements, customer demographics, and policy performance**. The dashboard enables stakeholders to monitor active/inactive policies, evaluate claim statuses, and track financials across different policy types.  

---

## Key Features  
- **KPIs**:  
  - Total Premium Collected: **₹5.97M**  
  - Total Coverage Amount: **₹600.33M**  
  - Total Claim Amount: **₹16.90M**  

- **Demographic Analysis**:  
  - Gender distribution of policyholders (5K Male, 5K Female).  
  - Claim amounts segmented by **Age Groups** (Young Adults, Adults, Elderly).  

- **Claims Insights**:  
  - Claims by Status: **Settled (3.4K), Rejected (4.4K), Pending (2.3K)**.  
  - Policy Type vs. Claim Status matrix for deeper performance comparison.  

- **Policy Insights**:  
  - Active vs. Inactive Policy ratio (**58% Active, 42% Inactive**).  
  - Premium distribution across **Travel, Health, Auto, Life, and Home** policies.  

---

## Visuals Used  
- **Cards**: Key KPIs (Premium, Coverage, Claims)  
- **Bar/Column Charts**: Premium by Policy Type, Claim Amount by Age Group  
- **Stacked Column Chart**: Claims by Status (Rejected, Settled, Pending)  
- **Donut Chart**: Active vs. Inactive Policy share  
- **Matrix Table**: Policy Type breakdown with Pending, Rejected, and Settled claim amounts  

---

## DAX Measures  
Some of the calculated measures created in Power BI:  
```DAX
Total Premium Amount = SUM(Policies[PremiumAmount])


Total Coverage Amount = SUM(Policies[CoverageAmount])
Total Claim Amount   = SUM(Policies[ClaimAmount])

Active Policy % =
DIVIDE(
    COUNTROWS(FILTER(Policies, Policies[Status] = "Active")),
    COUNTROWS(Policies)
)

Inactive Policy % = 1 - [Active Policy %]

Claim Amount by Age Group =
SWITCH(TRUE(),
    Policies[Age] <= 25, "Young Adult",
    Policies[Age] <= 60, "Adult",
    "Elder"
)
```

---
## Tools & Technologies

Power BI (Data Modeling, DAX, Interactive Dashboarding)

Excel / CSV (Raw Data Source)

--- 
## Key Insights

Travel insurance dominates both premium collection and claim amounts.

Adults are responsible for the largest claim amounts (~₹8.8M).

Significant portion of claims (~42%) remain pending or rejected, signaling possible inefficiencies in claims processing.

Nearly half of policies are inactive, suggesting opportunities for customer re-engagement.

