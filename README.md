# Residential HEMS Optimization with V2G and V2H Integration

A Mixed-Integer Linear Programming (MILP) optimization model for residential
Home Energy Management Systems (HEMS), integrating photovoltaic generation,
stationary battery storage, and Vehicle-to-Everything (V2X) capable electric
vehicles with deferrable and dimmable load scheduling.

## Overview

This model minimizes the total operational cost of a residential household
over a configurable time horizon by optimally scheduling:

- PV generation allocation across loads, battery, EVs, and grid export
- Stationary battery charge/discharge cycles
- Electric vehicles with V2G and V2H capabilities and charger assignment
- Deferrable loads (Type 1: non-interruptible, Type 2: interruptible)
- Dimmable loads with adjustable power levels
- Fixed loads with predefined consumption profiles


## Usage

The script is designed to run on **Google Colab** with input data stored
in a multi-sheet Excel file on Google Drive. To run it:

1. Mount your Google Drive in Colab
2. Place your input Excel file at the expected path
3. Run the script

To run locally, replace the Drive mount and file path sections with
your local paths.


## Input Data Format

The model expects a multi-sheet Excel file with the following structure:

| Sheet | Contents |
|-------|----------|
| 0 | Time horizon, PV generation, electricity prices, battery parameters |
| 1 | Load types, total energy, and duration |
| 2 | Base consumption profiles (fixed and dimmable loads) |
| 3 | Deferrable load availability windows |
| 4 | Comfort penalty weights |
| 5 | Dimmable load reduction limits |
| 6+ | One sheet per EV (SoC, availability, driving consumption, limits) |
