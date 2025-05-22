# Chalcopyrite Heap Leach TEA Manual

<aside>
📌

Welcome to our supporting document for the Chalcopyrite Heap Leach TEA, part of Homeworld’s Orecast project!

Refer to the table of contents below, or mouse over the right sidebar to access a more detailed set of contents & headers.  

- On Notion, these blocks are expandable sections (click on the triangle to expand)
    
    [we include more content and notes within these expandable sections] 
    

We’ll include screenshots to the model throughout; FYI - the numbers and exact format may differ slightly. 

</aside>

Link to model ([here](https://1drv.ms/x/c/147876eee33501b9/EQPpl4ljGOJMrgbxcQLHN2UB-NKCfIsGOYR3Qath6lANzw?e=GNcRNC))

Contents: 

# Introduction - Our Vision for Climate Bio Impact

---

Biology can transform mining, but too often the scientific conversation starts at “protein optimization” rather than “industry appropriateness”. If we hope to see genuine impact—especially for more sustainable processes like biomining—we need to speak the language of the mining industry. That means translating promising lab breakthroughs into the metrics that matter at scale.

Scientists are best equipped when they are familiar with the financial language of industry; this allows them to discover entry points for better and cleaner technologies. We are thrilled to announce an open-source techno-economic analysis (TEA) resource specifically built around copper extraction from chalcopyrite in heap leach operations. This Excel-based tool is designed to put scientists in the “Command Center” of a mine, showing how value is truly created—and how biology can move the needle on real-world costs and revenues.

### Our intended audience

Scientists, innovators, funders, researchers, miners, and other ecosystem participants who are developing biotechnology and other green solutions for mining applications.

### Our objective

To level the knowledge playing field by providing both a framework (TEA Excel model) and embedded expertise to help early-stage innovators establish reference points for their technologies' economic potential.

### The TEA as a scaffold

This TEA serves as a starting scaffold for teams developing mining-related biotechnologies, especially focused on heap leaching where biological interventions can make meaningful differences in efficiency, costs, and environmental impact.

Our focus has been on building the Excel scaffold (formulas, sheets, etc.), using rough assumptions for illustrative purposes. We've created an example where 100% of the copper-bearing mineralogy in the ore is chalcopyrite, and the only product is copper cathode. We recognize that every mining operation differs significantly, and these assumptions will need refinement for specific applications.

### Our goal for you

For those using this model for your specific applications, we strongly encourage you to thoroughly understand how all components interconnect. Examine every number and assumption to ensure relevance to your context and find appropriate references. This is more than a disclaimer—we want climate bio founders and ecosystem participants to develop robust mental models around TEA. There are no shortcuts beyond investing time to understand the model's mechanics. While this model required approximately 100 hours of collective time to build, you should spend at least 10 hours customizing it before considering it suitable for your specific analysis.

### Questions and feedback?

We’d love to hear from you — reach out to Jayme ([jayme@homeworld.bio](mailto:jayme@homeworld.bio)) at Homeworld Collective and Jesse ([jesse@conductor-labs.com](mailto:jesse@conductor-labs.com)) at Conductor Labs with any questions or feedback!

# Getting Started

---

### Accessing the Model

The model is hosted on Microsoft OneDrive as an online Excel file

- To edit: Go to File → Create a Copy → Create a Copy Online to utilize the sensitivity analysis features. You can also download a copy of the model and directly edit that copy.
    
    ![image.png](image.png)
    
- Note: you’ll need to use or [create](https://account.microsoft.com/account/Account) a Microsoft account to create a version for yourself
- We chose Excel over Google Sheets for its more robust formula support. If converted into Google Sheets, the model will not function entirely as designed.

### For Those Learning TEA

If you're new to techno-economic analysis, we recommend exploring these additional resources that come with video guides, rich databases of templates, data, and more:

1. University of Michigan AssessCCUS ([resource link](https://assessccus.globalco2initiative.org/tea/))
2. Activate - TEA guide and example templates ([resource link](https://www.activate.org/techonomics))
- You’ll see that different numeric assumptions are color-coded differently. We similarly use best practices adopted by finance and accounting analysts for building easy-to-audit models. (example [here](https://www.wallstreetprep.com/knowledge/financial-modeling/))
    
    ![image.png](image%201.png)
    

### Recommended Approach

Based on our experience working with TEAs, we suggest:

1. **Skim this entire manual before beginning to work through the examples**
2. Ground yourself in the process flow first (”PFD”, “process”, and “bioleach” sheets) - understand inputs, outputs, and core unit operations
3. Review the economic overview to identify which costs or levers drive the economic "story"
4. Understand the sensitivity levers - their ranges and the hypotheses they test. See [Sensitivity Analysis details](https://www.notion.so/Chalcopyrite-Heap-Leach-TEA-Manual-1db55996e9ff808c801fcca770514491?pvs=21) for more information
5. Review the tornado chart to visualize sensitivity impacts on unit economics
6. Step through the process flow from top to bottom to understand the sources of different assumptions
7. Consider how the model can be useful for your purposes - whether as a gut-check or as a foundation for your own analysis

### Model Layout

The model is organized into several sections:

![image.png](image%202.png)

1. Dashboard: Main summary and control panel for understanding overall economics and adjusting sensitivities (except for bioleaching assumptions)
2. Process Flow:
    - "Process" - The main engine tracking all mass and energy flows
    - "Bioleach" - Tracks assumptions, purposefully generalized for teams to embed their own parameters
    - "PFD" - Set of unit operations for our illustrative example
3. Economic Assumptions:
    - "Variable" - Variable costs (both COGS and OpEx)
    - "CapEx" - Capital expenditures for each unit operation, with framework to aggregate and annualize costs
    - "Sales" - Assumptions on copper pricing
4. Utilities:
    - "Tornado" - Excel formulas driving the tornado chart visualization
    - "Validation" - Tracking comparisons across mining-related reference models from public sources

# Scope Overview: Chalcopyrite Bioleaching

---

We model an illustrative chalcopyrite extraction and processing operation based on industry references, expertise, and input from across the ecosystem of mining operators and researchers.

### Why Chalcopyrite?

- Offers significant decarbonization impact, especially related to electrification
- Represents a massive market opportunity, accounting for 70-80% of copper reserves ([ref](https://link.springer.com/article/10.1007/s11837-005-0252-5))
- With declining ore grades globally, low-grade copper ores are becoming increasingly economic options for industrial-scale mining operations ([ref](https://www.spglobal.com/market-intelligence/en/news-insights/research/copper-project-pipeline-project-shortage-to-see-supply-lag-demand-post-2025))
- Biology has historically played a major role in the recovery of copper from low-grade chalcopyrite

### Focus on Heap Leaching

Heap leaching is the most cost-effective way to process low-grade ore, with high operational expenses primarily from acid use to dissolve copper from refractory rock. This is a prime area where biological processes can be applied to improve efficiency and reduce costs.

### Unit Operations in Our Model

The operation includes the following unit operations:

1. **Ore Extraction**: The initial mining process of removing copper-bearing ore from the ground through drilling, blasting, and excavation methods.
2. **Crushing & Screening**: Size reduction of large ore pieces to optimal dimensions for leaching, typically through multiple crushing stages and screening to separate particles by size.
3. **Agglomeration**: Mixing of crushed ore with acid and sometimes binding agents to create uniformly sized particles that promote better leach solution percolation. This is also where microbes are often introduced in industrial operations to the agglomerated ore flow.
4. **Stacking**: Placement of the agglomerated ore onto prepared leach pads in layers designed to optimize solution flow and minimize compaction.
5. **Leach Cycle**: The core process where acid solution (modified with microbes or additives) percolates through the heap to dissolve copper from the ore over a period of months.
6. **Solvent Extraction**: Chemical process that selectively removes and concentrates copper from the leach solution (pregnant leach solution) into an electrolyte solution.
7. **Electrowinning**: Electrochemical process where copper is plated onto cathodes from the concentrated solution, producing copper metal with 99.99% purity.
8. **Copper Cathode Storage**: Final handling and storage of copper cathode sheets before shipping to customers.

We also include a small unit operation placeholder for the biotech input - depending on application, this could be specialized microbes, bioproducts, or additives that impact the microbial community within heap leaches. 

- See “Bioleach” tab for more details
    
    ![image.png](image%203.png)
    

### Scope Boundaries

While we model the entire process, our focus is primarily on the leaching process, with illustrative placeholders for other unit operations based on industry data. Extraction, though critical to the end-to-end process, is outside our detailed parameterization scope.

We assume all copper production is focused on copper cathode - the main commodity and transferrable unit for copper.

# A Few Things to Try Out for Yourself

---

Here are some practical examples to help you understand and customize the TEA model.

As you’re going through the examples - it’s extremely important to critically think about the numbers that results. If it doesn’t make sense, if it’s unintuitive, or if it’s a surprise - use it as an opportunity to follow the trail and understand where the difference is coming from.  

When doing these mini analyses, you can create a ‘peek’ section to quickly see the impact without jumping between sheets all the time.  

- Here’s an example peeking at the dashboard from the bioleach tab. You can add other datapoints that would be relevant.
    
    ![image.png](image%204.png)
    

### Example 1: Sensitivity Analysis on Bioleach Recovery Rate

1. Navigate to the “bioleach” sheet
2. Find the different parameters for recovery rates, leach rates, etc.
    - Recovery rate per year
        
        ![image.png](image%205.png)
        
    - Yield impact (this assumption is set from the sensitivity driver section further below in the sheet)
        
        ![image.png](image%206.png)
        
    - Leach rate impact (also set further below in the sheet)
        
        ![image.png](image%207.png)
        
3. Test different scenarios:
    - Try setting different assumptions here, and seeing the impact on overall economics
        
        ![image.png](image%208.png)
        
4. Observe how changes in recovery rate cascade through the model, affecting:
    - Total copper recovered
    - Acid consumption
    - Overall economics on the dashboard

### Example 2: What if microbes, acid, inputs were free?

1. Navigate to “dashboard”
2. Find cost assumptions related to a particular input:
    - Summary table
        
        ![image.png](image%209.png)
        
    - Or within the process flow
3. Create sensitivities around it or set it manually to zero to observe impact
4. See how changes cascade through the model

### Example 3: Add a Unit Operation

1. Identify where your new unit operation fits in the process flow
2. Update the “PFD” sheet’s diagram to show where the unit operation would sit 
3. Update the “capex” sheet:
    - Add the new unit operation to the summary table
    - Verify that totals are pulling correctly (check SUM formulas)
    - Add detailed equipment estimates in the section below
    - Include references/citations for your equipment cost estimates
    - Ensure the dashboard's summary CapEx is accounting for the new unit operation
    - Check that respective 'total' formulas include your new additions
4. Update the “process” sheet:
    - Add a new section for your unit operation
    - Account for input and output streams with appropriate mass and energy balances
    - If inserting in the middle of the process flow, ensure that operations above and below properly account for the conversions in your new unit operation
    - Update any efficiency or recovery calculations that may be affected
5. If there are OpEx costs associated with your new unit operation:
    - Add them to the “variable” (variable costs) sheet
    - Include reagents, utilities, labor, and maintenance as applicable
    - Update any formulas that calculate totals

### Example 4: Add a Sensitivity

1. Navigate to the sensitivity testing table in the “dashboard” tab
2. First delete the data table cells (just the cells with manually-entered numbers in them, as opposed to calculated numbers) - note that you can't modify rows in a data table without rebuilding it
    - see notes on working with the Data Table function [here](https://www.notion.so/Chalcopyrite-Heap-Leach-TEA-Manual-1db55996e9ff808c801fcca770514491?pvs=21)
    - also reference a guide from Microsoft [here](https://support.microsoft.com/en-us/office/calculate-multiple-results-by-using-a-data-table-e95e2487-6ca6-4413-ad12-77542a5ea50b)
3. Insert a new row for your sensitivity parameter:
    - Copy the formulas from the row above
    - Gray-text cells are formula-based and don't need modification
    - Set appropriate low/medium/high estimates based on your research or technology parameters
4. Link the model to your new sensitivity driver:
    - Ensure the relevant part of the model you want to affect is linking to the cell in the 'Model Input' driver
    - As this number swaps between L/M/H values, the corresponding value within the model (e.g., in the process flow tab) should change
5. Test your new sensitivity driver:
    - Manually change the value in 'Model Input' and verify that the model summary updates as expected
    - Check impacts on costs, revenues, and other key metrics
    - Once verified, copy over the formula from another sensitivity row
6. Rebuild the data table: 
    - Select the range that will contain your data table
    - Go to Data > What-If Analysis > Data Table
    - Set the row and column input cells as required
7. Verify the tornado chart is updated:
    - When inserting a row in your main sheet, the formulas in “tornado” will be offset. Start with the first row of sensitivities and copy down the formulas again to account for the new sensitivity driver.
    - The tornado chart formulas on the right should update. Make sure the tornado chart is pulling from the right fields. You can see this by clicking on any of the tornado chart bars.
    - Once updated - copy the tornado chart into the dashboard tab.

# Detailed Walkthroughs Through Each Sheet

---

### Cover

This gives a high level overview of the TEA, and also has contact information if you’d like to reach out with feedback or questions.

- You’ll see that different numeric assumptions are color coded differently. We similarly use best practices adopted by finance and accounting analysts for building easy-to-audit models) (example [here](https://www.wallstreetprep.com/knowledge/financial-modeling/))
    
    ![image.png](image%201.png)
    

### Dashboard

This is the main summary and control panel for understanding the overall economics and adjusting sensitivities (except for bioleach assumptions). Key features include:

- Annualized economic summary
- Production capacity and throughput
- Unit economics ($/ton ore, $/lb copper)
- Sensitivity controls for major parameters
- Tornado chart

Sensitivity analysis

The sensitivity analysis works by plugging in different assumptions for each model driver, and observing the impact on the economics. 

- Sensitivity table overview
    
    ![image.png](image%2010.png)
    
- The way this sensitivity analysis works:
    - Each row is a “model driver” or variable that impacts some component of the mass, energy, and/or economics of the process
    - The “model input” column (gray, italics) is what the other tabs of the model reference when running their calculations
    - The model assumptions are automatically cycled through that column and the sensitivity impact table reflects these impacts
- How you can use it
    - The model assumptions (in blue) can be changed based on your team’s assumptions
        - Some assumptions are in green - go to where these cells are referencing to find where you can change these assumptions (these are usually more involved / complex assumptions)
    - The sensitivity impact should update automatically based on the changes
- Having issues? This sensitivity analysis is run using Excel’s “Data Table” feature — you can reference [this section](https://www.notion.so/Chalcopyrite-Heap-Leach-TEA-Manual-1db55996e9ff808c801fcca770514491?pvs=21) to see common issues

## Process Flow Sheets

---

**"Process" Sheet**

The main engine that tracks all mass and energy flows throughout the system:

- Maps the mass balance from ore extraction through copper cathode production
- Tracks flows of ore, solution, and copper at each respective stage
- Aggregates utilities consumption (electricity, water, reagents)
- References other sheets for validation and further detail

**"Bioleach" Sheet**

Tracks assumptions specific to the biological leaching process:

- Purposefully generalized so teams can embed their own assumptions based on their specific technology
- Higher yield - increases the total yield (really impactful because of top-line impact)
- Faster leach - pulls forward the recovery per year. For modeling purposes, we assumed that there’s some reduction of the amount of sulfuric acid needed for leaching. This also reduces the amount of leach pad capital costs

**"PFD" (Process Flow Diagram) Sheet**

Visual representation of the unit operations laid out for our illustrative example:

- Block flow diagram of the entire process
- Serves as a reference point for understanding process scope and boundaries

## Economic Assumption Sheets

---

**"Variable" Sheet**

Detailed breakdown of variable costs, both COGS (Cost of Goods Sold) and OpEx (Operating Expenses):

- Reagent costs (acid, extractants, etc.)
- Labor requirements and costs
- Consumables and replacement parts

**"CapEx" Sheet**

Capital expenditures for each unit operation, with framework to aggregate and annualize costs:

**CapEx Overhead**

- Uses an illustrative breakdown designed more for chemical plants than mining for two reasons:
    1. The processing steps resemble a chemical manufacturing process more than extraction
    2. There's more literature and finer parameterization around indirect/auxiliary cost breakdowns

**Install Factors**

- Given the roughness of CapEx estimates, install factors are kept illustrative
- Can be adjusted based on specific site conditions and equipment types

**Annualizing CapEx**

- We use a capital recovery factor approach to estimate annual CapEx cost, instead of a discounted cash flow
    - Capital Recovery Factor ([ref](https://en.wikipedia.org/wiki/Capital_recovery_factor)) - estimates the percentage of initial principal payment needed annually
        
        ![image.png](image%2011.png)
        
    - Requires only two inputs: number of payment periods (years) and annual interest rate
    - Trade-off: Simpler annualized CapEx estimate that's more easily auditable vs. a full discounted cash flow (DCF) sheet
- Uses a weighted average cost of capital (WACC) that blends equity and debt costs
    - Standard TEAs often assume a 10% discount rate, which we parameterize further

**Unit Operation Equipment Costs**

- Identifies major pieces of equipment for each unit operation
- Illustrative costs
- Scales equipment based on throughput using appropriate scaling factors

**"Sales" Sheet**

Assumptions related to copper pricing and revenue generation:

- Historical and projected copper prices

## Utility Sheets

---

**"Tornado" Sheet**

Contains Excel formulas that drive the tornado chart visualization:

- Sensitivity analysis on key parameters

**"Validation" Sheets**

Provides comparison across mining-related reference models from public sources:

- Benchmarking against public mining project data
- Comparative metrics from NI 43-101 reports and other public materials
- Sanity checks for key parameters
- Industry averages and standards for reference

These sheets contain the raw data sources that feed into the summary comparisons on the main validation sheet. Refer to these if you want to understand the context of a specific reference number or explore more detailed benchmark data.

# Troubleshooting

---

### General Approach to Troubleshooting

When encountering issues in the model, track where the error is originating from whether in the same or different sheet

1. For #REF errors:
    - Check for circular references
    - Verify that all referenced cells exist
    - Ensure formulas are pointing to valid ranges
    - Check for deleted sheets or renamed ranges
2. For unexpected results:
    - Trace dependencies via “Formulas” → “Trace Dependents” or “Trace Precedents”
    - Check units consistently throughout calculations

### Tornado Chart

Troubleshooting sensitivity analysis issues:

- Ensure that the sensitivity table (column B → P) mirror the dashboard via formulas
    
    ![image.png](image%2012.png)
    
- Make sure the calculations for the low-to-high deltas are correct and not error-ing out
    
    ![image.png](image%2013.png)
    
- Check the ‘creating chart’ section to identify where there could be issues
    
    ![image.png](image%2014.png)
    
- If two drivers have exactly the same impact across low-to-high, there results in 2 levers at the same rank, and creates an error for the tornado chart. To fix - tweak the input assumptions slightly so there isn’t an exact duplicate
    
    ![image.png](image%2015.png)
    

For other tips, refer to best practices ([reference](https://www.f1f9.com/wp-content/uploads/2019/05/F1F9_TornadoCharts_EBook_03a.pdf))

### Sensitivities - Data Tables

Tips for working with and troubleshooting data tables

- Ensure that data tables reference the Row Input and Column Input cells. It doesn’t actually matter which cells are referenced, but we set these here on the side to avoid accidentally setting cells that could be populated with other values. These reference cells just need to be kept clean and separated.
    
    ![image.png](image%2016.png)
    
- Ensure parameter ranges (low, base, high) are properly defined
    
    ![image.png](image%2017.png)
    
- Check that the output metric is referenced correctly in the top left corner of the data table (columns S through V in this example)
    
    ![image.png](image%2018.png)
    

### Adapting the Model to Your Specific Context

For technology-specific adaptations:

- Identify key differentiating factors of your biotechnology
- Focus on parameterizing those specific advantages
- Create additional calculation sections if needed
- Consider creating custom sensitivity analyses for your key innovation parameters