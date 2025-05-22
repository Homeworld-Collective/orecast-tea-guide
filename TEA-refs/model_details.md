# TEA Breakdown
The model is structured across multiple interconnected sheets, each serving a specific purpose in calculating and analyzing the project's feasibility.

## I. Model Overview and Purpose

The primary **purpose** of this TEA model, as outlined in the **cover** sheet (Source 21-24), is to offer a simplified yet robust starting point for researchers and practitioners in the bio-mining industry. It aims to help evaluate the techno-economics of emerging technologies by providing a baseline example of a copper chalcopyrite bio-leaching operation at scale. The process boundaries considered span from ore extraction through to copper cathode production.

**Getting Started:**
The **cover** sheet suggests beginning with the **PFD (Process Flow Diagram)** to understand the overall operation, then moving to the **process** sheet for detailed logic and assumptions, and finally to the **dashboard** for economic summaries and sensitivity analyses.

## II. Core Model Sheets

**1. Dashboard (`dashboard.csv`)** (Source 5-11)
This is the central control panel and summary sheet.
* **Annualized Economic Summary:** Displays key financial metrics like Sales, Cost of Goods Sold (COGS), Gross Margin, Operating Expenses (OPEX), Operating Income, Annualized Capital Expenditures (CAPEX), and Simplified Net Income (EBIT). Values are presented in total dollars, dollars per tonne of copper, and dollars per pound of copper.
* **Sensitivity Testing:** Allows for "What-If" analysis by showing the economic impact (on Simplified Net Income) of changing various model assumptions. Key drivers tested include bio-leach yield, leach speed, sulfuric acid loading and recycling rates, organic acid recycling, extraction rates, operating days, ore grade, electricity cost, sulfuric acid cost, and copper cathode price. Instructions are provided to run the sensitivity analysis using Excel's Data Table feature.
* **Operational and Economic Breakdown:** Provides detailed calculations for:
    * **Sales:** Based on copper cathode production and price.
    * **COGS:** Includes direct mining costs, consumables (sulfuric acid, organic solvent), energy (crushing, electrowinning), direct labor, and other operating costs.
    * **OPEX:** Covers administrative labor and other overhead like maintenance and property insurance.
    * **CAPEX:** Summarizes annualized costs for each stage of the process flow.
* **Process Details:** Lists key operational parameters like operating hours per year, capital cost scalar, capital recovery factor (CRF), and tonne-to-pound conversion.
* **Waterfall Chart:** Visually breaks down the cost components and margin per tonne of copper.

**2. Process Flow Diagram (`PFD.csv`)** (Source 1-4)
This sheet visually outlines the sequence of operations in the copper bio-leaching process. Each step is briefly described:
* **Extraction & Ore Preparation:** Initial mining and removal of copper-bearing ore.
* **Crushing & Sizing:** Reduction of ore size for optimal leaching.
* **Agglomeration & Microbe Addition:** Mixing ore with acid and microbes to create uniform particles. This is the biotech input stage.
* **Stacking:** Placement of agglomerated ore onto leach pads.
* **Leach Cycle:** Percolation of acid solution (potentially with microbes) through the ore heap to dissolve copper.
* **Solvent Extraction (SX):** Selective removal and concentration of copper from the leach solution.
* **Electrowinning (EW):** Electrochemical plating of copper onto cathodes to produce high-purity copper metal.
* **Storage:** Handling and storage of copper cathode sheets before shipping.

**3. Process Details (`process.csv`)** (Source 12-20)
This sheet forms the core of the model's calculations, detailing the mass and energy flows for each unit operation.
* **Operational Details:** Defines overall parameters like operating hours, annual extraction (ore + waste), and copper cathode production.
* **Unit Operations (A1-A8, B1):** For each step in the PFD, this sheet details:
    * **Inputs:** Raw materials, ore characteristics (e.g., Cu grade), reagents, water.
    * **Process Assumptions:** Key parameters such as particle size, acid loading rates, cycle times, recovery rates, equipment efficiencies, and recycle rates for reagents like sulfuric acid and organic solvents. Specific calculations like Bond's Law for crushing energy and Faraday's Law for electrowinning are included.
    * **Outputs:** Products (e.g., crushed ore, pregnant leach solution, copper cathode), waste streams, and unrecovered materials.
* **Biotech (Microbial) Step (B1):** Details inputs (seed microbes, growth medium, nutrients), microbial cultivation process assumptions, and outputs (microbes produced, excess culture).
* **Utilities:** Calculates makeup water requirements for various stages.

**4. Bio-leach Details (`bio-leach.csv`)** (Source 27-29)
This sheet focuses specifically on the assumptions related to the bio-leaching aspects and their impact on the process.
* **Impact on Yield:** Models how bio-leaching can increase the total amount of copper extracted (e.g., by reducing passivation). It shows a base case extraction percentage over several years and how it's adjusted.
* **Impact on Extraction Rate:** Models how bio-leaching can accelerate the copper extraction process (e.g., through faster leach kinetics due to more ferric iron or higher temperatures), shifting production to earlier years.
* **Sensitivity Drivers:** Links to the sensitivity analysis on the dashboard, allowing users to test the economic effects of varying bio-leach parameters like "Reduce passivation" and "Faster leach."
* **Gut Checks:** Includes model checks to ensure the logic of yield and rate adjustments is consistent.

## III. Economics-Related Sheets

**1. Variable Costs (`variable.csv`)** (Source 25-26)
This sheet houses the assumptions for operating and variable costs.
* **COGS Assumptions:**
    * **Sulfuric Acid:** Details the calculation of sulfuric acid cost per kg/tonne based on container price, concentration, and target concentration. Includes a model input value that can be referenced from validation data.
    * **Organic Solvent:** Calculates the cost per liter of organic solvent based on extractant and diluent costs and their respective volumes.
    * **Other COGS:** Includes estimated costs per tonne for mining-related direct costs and processing. A scalar is applied to consumables, energy, and direct labor to estimate "Other operating costs."
* **Labor Costs:**
    * **FTE Cost Breakdown:** Lists various positions (e.g., Mine Maintenance, Mine Operations, Engineering, Geology), their salaries, baseline FTE numbers, scaled FTEs (based on production volume using the "six-tenths rule"), and total salary categorized into direct labor or administrative.
    * **Benefits & Additional Costs:** Applies factors for benefits to calculate the total cost per FTE for direct and administrative labor.
* **Other Overhead (OPEX):**
    * **Maintenance:** Calculated as a percentage of Total Direct Costs (TDC) from the `capex` sheet.
    * **Property Insurance:** Calculated as a percentage of Fixed Capital Investment (FCI) from the `capex` sheet.

**2. Capital Expenditures (`capex.csv`)** (Source 30-51)
This sheet details all capital cost assumptions.
* **Summary of Unit Operations:** For each process step (Extraction, Crushing, Agglomeration, Biotech input, Stacking, Leach Cycle, SX, EW, Storage), it lists:
    * Purchased Cost
    * Install Factor (illustrative)
    * Installed Cost
    * All-in Cost (scaled up)
    * Annualized Cost (calculated using the Capital Recovery Factor)
* **CAPEX Overhead:**
    * **Total Purchased Cost:** Sum of purchased costs for all unit operations.
    * **Direct Costs (TDC):** Calculated by adding costs for instrumentation, piping, electrical, buildings, service facilities, and land (as percentages of purchased cost or TDC itself). These percentages are noted as illustrative and set to fit validation data.
    * **Indirect Costs:** Includes engineering/supervision, legal expenses, construction expense/fee, and contingency (as percentages of TDC).
    * **Fixed Capital Investment (FCI):** Sum of TDC and Total Indirect Costs.
    * **Working Capital:** Calculated as a percentage of FCI.
    * **Total Capital Investment (TCI):** Sum of FCI and Working Capital. This is the "All-in Cost" used in the summary.
* **Annualized Capital Cost Assumptions:**
    * **Six-Tenths Rule:** A scale factor used for cost estimations.
    * **Funding Structure:** Assumed percentages of debt and equity.
    * **Rates:** Interest rate for debt and expected return for equity.
    * **Debt Term, Tax Rate, Project Life.**
    * **Weighted Average Cost of Capital (WACC):** Calculated based on funding structure and rates.
    * **Capital Recovery Factor (CRF):** Used to annualize the TCI over the project life.
* **Unit Operation Equipment Costs:** Provides a detailed breakdown for each unit operation, listing specific equipment (e.g., Jaw Crusher, Vibrating Screen, Agglomeration Drum, Bioreactor, Mixer-Settler). For each piece of equipment, it includes:
    * Description
    * Reference Value and Units (e.g., capacity)
    * Cost per Unit (reference)
    * Count
    * System Value (model's required capacity)
    * System Cost per Unit (scaled from reference using the six-tenths rule)
    * Total Cost
    * An "Other equipment" cost is added as a percentage of the sub-total for listed equipment.

**3. Sales (`sales.csv`)** (Source 52)
This sheet contains assumptions related to revenue.
* **Copper Cathode Price:** The primary input is the price per tonne of copper cathode. A reference link to IndexMundi is provided.
* It notes that other products or co-products and their respective prices can be added here if applicable.

## IV. Utilities & Validation Sheets

**1. Tornado Chart (`tornado.csv`)** (Source 58-69)
This sheet is set up to automatically generate a tornado chart, which visually represents the sensitivity of the project's net income to various input parameters.
* **Sensitivity Data:** It pulls the sensitivity testing results from the **dashboard** (model driver, input metric, low/mid/high values, and corresponding low/mid/high net income).
* **Delta Calculation:** Calculates the "Full delta" (the difference in net income between the high and low input values) for each driver.
* **Ranking and Chart Preparation:** Ranks the drivers by their full delta and prepares the data for plotting the tornado chart (left and right bars representing negative and positive impacts).
* **Error Checking:** Includes checks to ensure the tornado chart can be generated correctly (e.g., no drivers having the exact same full delta).
* **Top 10 Levers:** The chart typically displays the top 10 most impactful variables.

**2. Validation (`validation.csv`)** (Source 53-57)
This sheet is crucial for comparing the model's outputs with real-world data from various mining operations and technical literature. This helps to assess the reasonableness of the model's assumptions and results.
* **Comparison Structure:** It typically lists a parameter (e.g., acid consumption, PLS concentration, operating cost), its value from a reference source, the corresponding model output, and the reference source details.
* **Areas of Validation:**
    * **Leaching:** Acid consumption (kg acid/t ore, with and without recycle), irrigation rate, PLS copper concentration.
    * **Market Pricing:** Costs for power, sulfuric acid, and copper price.
    * **Operating Costs:** Costs for sulfide leach, SX/EW, labor.
    * **Cash Costs:** C1 Cash Costs and C3 Cash Costs (All-in Sustaining Costs - AISC).
    * **Cost Breakdown:** Ratio of mining vs. processing operating costs.
    * **Operating Parameters:** Ore grade, mining rate, annual copper production.
    * **SX/EW:** Energy usage, cost breakdown (organic solvent, acid, electricity, capex).
* **Note:** Some variables might not have a direct model output shown if the reference data itself is used as a direct input assumption in the model.

**3. Validation Detail Sheets (`vld - Cactus.csv`, `vld - FM.csv`, `vld - Nifty.csv`, `vld - other.csv`)** (Source 70-96)
These sheets provide the raw data and detailed information from specific reference projects or sources used in the **validation** sheet.
* **`vld - Cactus.csv` (Arizona Sonoran - Cactus Mine Project):** (Source 78-96) Contains extensive data including mineralogy, acid consumption, consumable costs, SX/EW costs, power consumption, copper recovery, production timing, economic analyses (operating costs, capital costs, financials), detailed capital cost breakdowns (WBS levels, equipment lists), open pit design parameters, tonnage schedules, and salary/labor rate details.
* **`vld - FM.csv` (Freeport-McMoRan - Cerro Verde Mine):** (Source 74-77) Provides economic and technical assumptions such as metal prices, various mining, leaching, and milling costs, G&A, sustaining capital, commodity costs (acid, power, diesel), technical parameters (bench height), and consumables data.
* **`vld - Nifty.csv` (Cyprium - Nifty Mine):** (Source 73) Offers high-level data points like ore grade and production tonnage.
* **`vld - other.csv` (Miscellaneous Sources):** (Source 70-72) Includes data from sources like Hudbay - Copper World and Taguas Heap Leach Project, covering capital and operating cost breakdowns, financial metrics, and production sizing.

## V. How the Sheets Interconnect

The strength of this TEA model lies in the interconnection between its sheets:
* **Core Process & Bio-leach (`process.csv`, `bio-leach.csv`):** These define the technical parameters, mass balances, and recovery rates.
* **Cost Assumptions (`variable.csv`, `capex.csv`):** Unit costs for consumables, labor, and equipment are defined here. These are often scaled based on production rates or equipment sizes derived from the `process` sheet. For example, labor FTEs in `variable.csv` are scaled based on the system's production volume, and equipment costs in `capex.csv` are scaled using the six-tenths rule based on capacities determined in `process.csv`.
* **Sales Assumptions (`sales.csv`):** Defines the revenue per unit of copper.
* **Dashboard (`dashboard.csv`):** Aggregates all the data.
    * Production volumes from `process.csv` are multiplied by the sales price from `sales.csv` to get total sales.
    * Resource consumption (e.g., acid, solvent, power) from `process.csv` is multiplied by unit costs from `variable.csv` to calculate COGS components.
    * Labor and overhead costs from `variable.csv` feed into COGS and OPEX.
    * Annualized CAPEX is taken from the `capex.csv` summary.
    * The sensitivity analysis on the `dashboard` directly pulls and modifies key assumptions from `process.csv`, `bio-leach.csv`, `variable.csv`, `sales.csv`, and other input cells on the `dashboard` itself to show their impact on profitability.
* **Validation Sheets (`validation.csv` and `vld - *.csv`):** Provide external benchmarks to check if the outputs generated on the `dashboard` (which are based on the interconnected calculations from all other sheets) are reasonable. For instance, the model's calculated acid consumption per tonne of ore (derived from `process.csv` inputs) is compared against figures in `validation.csv` which are sourced from `vld - Cactus.csv` or `vld - FM.csv`.
* **Tornado Chart (`tornado.csv`):** Directly uses the sensitivity output from the `dashboard` to visualize the most critical economic drivers.
