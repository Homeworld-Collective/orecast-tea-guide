# Process Flow Sheets

The Process Flow sheets are the core of the TEA model, tracking all material and energy flows throughout the system.

## "Process" Sheet

This is the main engine that tracks all mass and energy flows throughout the system:

- Maps the mass balance from ore extraction through copper cathode production
- Tracks flows of ore, solution, and copper at each respective stage
- Aggregates utilities consumption (electricity, water, reagents)
- References other sheets for validation and further detail

## "Bioleach" Sheet

This sheet tracks assumptions specific to the biological leaching process:

- Purposefully generalized so teams can embed their own assumptions based on their specific technology
- Higher yield - increases the total yield (really impactful because of top-line impact)
- Faster leach - pulls forward the recovery per year. For modeling purposes, we assumed that there's some reduction of the amount of sulfuric acid needed for leaching. This also reduces the amount of leach pad capital costs

## "PFD" (Process Flow Diagram) Sheet

This sheet provides a visual representation of the unit operations laid out for our illustrative example:

- Block flow diagram of the entire process
- Serves as a reference point for understanding process scope and boundaries

## Tips for Modifying Process Flow

When modifying the process flow to reflect your own technology:

1. Start with the "PFD" sheet to understand the current process configuration
2. Identify where your technology would impact the flow
3. Update the "Bioleach" sheet with your specific parameters
4. Make corresponding changes to the "Process" sheet to reflect your technology's impacts on mass/energy balances
5. Ensure that changes cascade properly through the economic sheets 