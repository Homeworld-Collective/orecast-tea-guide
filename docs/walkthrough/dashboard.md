# Dashboard

The dashboard is the main summary and control panel for understanding the overall economics and adjusting sensitivities (except for bioleach assumptions). 

## Key Components

- Annualized economic summary
- Production capacity and throughput
- Unit economics ($/ton ore, $/lb copper)
- Sensitivity controls for major parameters
- Tornado chart

## Sensitivity Analysis

The sensitivity analysis works by plugging in different assumptions for each model driver, and observing the impact on the economics.

??? example "View Sensitivity Analysis Table"
    ![Sensitivity Table](../images/sensitivity_table.png)

### How the Sensitivity Analysis Works

- Each row is a "model driver" or variable that impacts some component of the mass, energy, and/or economics of the process
- The "model input" column (gray, italics) is what the other tabs of the model reference when running their calculations
- The model assumptions are automatically cycled through that column and the sensitivity impact table reflects these impacts

### How to Use It

- The model assumptions (in blue) can be changed based on your team's assumptions
- Some assumptions are in green - go to where these cells are referencing to find where you can change these assumptions (these are usually more involved / complex assumptions)
- The sensitivity impact should update automatically based on the changes

### Troubleshooting

This sensitivity analysis is run using Excel's "Data Table" feature. If you encounter issues, see the [Troubleshooting](../troubleshooting.md) section for guidance on working with data tables. 
