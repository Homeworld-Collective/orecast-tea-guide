# Adding a New Sensitivity

## Objectives for this Example
- Create and modify sensitivity analyses in the TEA model
- Visualize sensitivity results using tornado charts

## Background
Sensitivity analysis is a powerful technique for understanding which variables have the greatest impact on project economics. This example guides you through creating custom sensitivity analyses to evaluate technological or market uncertainties.

## Step-by-Step Guide

### 1. Identify target for sensitivity analysis

Before adding a new sensitivity parameter, determine:
 
 - Which technical or economic variable you want to test
 - The reasonable range of values for this variable
 - How this variable connects to the broader model
 - What hypothesis you're testing with this sensitivity

**Example parameters to consider:**

- Microbial growth rate or cost
- Ore mineralogy/copper speciation
- Equipment efficiency
- Reagent substitution effects
- Market factors (commodity prices, inflation)
- Technological improvements

### 2. Navigate to the sensitivity testing section

1. Go to the "dashboard" sheet
2. Locate the sensitivity testing table (typically in the middle-right section)

### 3. Prepare the table for modification

The sensitivity table is linked to an Excel data table, which requires specific preparation:

1. Select the existing data table cells (the calculated values, not the input parameters)
2. Delete only these cells to break the existing data table
3. Save your work before proceeding (data tables can sometimes cause Excel to freeze)

### 4. Add your new sensitivity parameter

1. Insert a new row in the sensitivity table
2. In the first column, enter a descriptive name for your parameter
3. In the second column, enter the formula that points to the cell in the model you wish to modify
     - Click on the cell in the model that contains the value you want to test
     - Excel will create a reference, e.g., =Process!$D$45
4. In the third column (Model Input), copy the formula from another row in this column
     - This cell uses an IF statement to select between Low/Mid/High values

### 5. Set your test values

1. In the Low/Mid/High columns, enter appropriate test values:
     - **Mid**: Usually the base case or current assumption
     - **Low**: A conservative or worst-case estimate
     - **High**: An optimistic or best-case estimate
   
2. Use reasonable ranges based on:
     - Literature data
     - Expert judgment
     - Historical variability
     - Technological possibilities

### 6. Connect the model to your new sensitivity driver

1. Locate the cell in the model that should vary based on your sensitivity
2. Replace its current value with a reference to the "Model Input" cell
3. Test the connection by manually changing the sensitivity selector
4. Verify that your target cell updates and that results flow through the model

### 7. Rebuild the data table

1. Select the entire range that will contain your data table, including:
     - All driver rows (including your new one)
     - All data columns (Driver through High Net Income)
2. Go to Data > What-If Analysis > Data Table
3. Set the row input cell to the cell that controls which scenario is active
4. Set the column input cell (optional, usually left blank for this type of table)
5. Click OK to generate the data table

### 8. Update the tornado chart

The tornado chart visualizes the relative impact of each sensitivity parameter:

1. Navigate to the "tornado" sheet
2. Verify that your new sensitivity parameter is included in the data range
3. If not, adjust the data range to include your additional row
4. Check that the chart formulas pull from the correct cells
     - The chart normally takes the "Full delta" for each parameter
     - Parameters are typically sorted by impact magnitude

### 9. Copy the updated tornado chart to the dashboard

1. Copy the completed tornado chart from the tornado sheet
2. Paste it onto the dashboard in the designated area
3. Adjust formatting as needed for clarity
