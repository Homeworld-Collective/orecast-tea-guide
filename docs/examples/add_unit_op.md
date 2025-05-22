# Adding a New Unit Operation

## Objectives for this Example
- Incorporate new technologies into the process flow
- Track mass and energy balances
- Evaluate capital and operating costs for new process components

## Background
This example guides you through incorporating a new unit operation that's personalized to your process, while maintaining technical and economic consistency throughout the model.

## Step-by-Step Guide

### 1. Define your new unit operation

Before making any changes to the model, clearly define:

- **Purpose** of the unit operation
- **Inputs and outputs** (mass and energy flows)
- **Key performance parameters** (efficiency, recovery, etc.)
- **Capital and operating cost basis**

**Example:** Atmospheric Leach Enhancement Unit

- Purpose: Increase copper leaching kinetics through controlled aeration
- Primary inputs: PLS solution, air, electricity
- Outputs: Enhanced PLS with higher copper concentration
- Key parameters: 15% increase in leach kinetics, 95% aeration efficiency

### 2. Update the Process Flow Diagram (PFD)

Navigate to the "PFD" sheet and modify the diagram:

1. Identify the logical insertion point in the process flow
2. Add a new box representing your unit operation
3. Update the connecting arrows to show the revised flow path
4. Add a brief description of the unit operation's function

**Example insertion points:**

- Between Agglomeration and Stacking (pre-leach treatment)
- Between Leach Cycle and SX (solution enhancement)
- Parallel to an existing process (bypass or split stream)

### 3. Update the Capital Expenditure (CAPEX) sheet

#### A. Add to the summary table
1. Insert a new row in the unit operations summary
2. Name your new unit operation

#### B. Add detailed equipment list
1. Navigate to the detailed equipment section
2. Create a new section for your unit operation
3. List all major equipment items with:
    - Equipment name and description
    - Reference capacity and cost
    - Required capacity for your process
    - Calculated cost for each item

**Example equipment list for Atmospheric Leach Enhancement:**

| Equipment | Description | Reference Capacity | Reference Cost | Required Capacity | Calculated Cost |
|-----------|-------------|-------------------|----------------|-------------------|-----------------|
| Aeration tanks | Forced air mixing vessels | 100 m³ | $250,000 | 250 m³ |  $447,214 |
| Air blowers | Positive displacement | 100 HP | $75,000 | 150 HP | $96,623 |
| Control system | PLC-based | - | $50,000 | - | $50,000 |

#### C. Reference detailed section in summary section
1. Navigate to the purchased cost column for the new unit operation in the summary table
2. Set the purchased cost value to the total purchased cost of the unit operation

### 4. Update the Process sheet

#### A. Add a new section for your unit operation
1. Create a logical section identifier (e.g., A4.5 if between A4 and A5)
2. Add header and description of the operation

#### B. Define inputs
1. List all feed streams from previous operations
2. Add new inputs (reagents, utilities, etc.)
3. Define operating conditions (temperature, pressure, etc.)

#### C. Define process calculations
1. Add mass balance equations
2. Include energy requirements
3. Calculate recovery/efficiency metrics

#### D. Define outputs
1. Specify product streams to next operation
2. Account for waste/loss streams
3. Ensure conservation of mass

#### E. Connect to adjacent operations
1. Update the output from the previous operation to feed your new unit
2. Update the input to the subsequent operation

**Example mass balance update:**
```
Previous operation output: 1000 t/day PLS @ 1.5 g/L Cu
New unit enhancement: Increases concentration by 20%
New output: 1000 t/day PLS @ 1.8 g/L Cu
Subsequent operation input: Updated to 1.8 g/L Cu
```

### 5. Update operating costs in the Variable sheet

#### A. Add reagent costs
1. Add new reagents with unit costs
2. Calculate annual consumption based on process calculations
3. Determine total annual cost

#### B. Add utility costs
1. Calculate electricity consumption (kWh)
2. Add water, compressed air, steam as needed
3. Multiply by respective unit costs

#### C. Add labor requirements
1. Determine additional FTEs required
2. Calculate labor cost impact

#### D. Add maintenance costs
1. Typically calculated as percentage of capital cost
2. Update if your unit has different maintenance requirements

### 6. Verify model integration

After all updates, check that:

1. Mass balances close throughout the process
2. Economics are properly calculated on the dashboard
3. All totals and subtotals include your new addition
4. The tornado chart captures sensitivity to your new parameters
