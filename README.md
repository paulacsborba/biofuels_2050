Brazil Bioenergy–Energy System Model (Calliope)
Overview

This repository contains a national-scale energy system optimization model for Brazil developed using Calliope. The model focuses on the integration of bioenergy, land-use constraints, and emerging fuels into long-term energy planning.

The framework co-optimizes energy supply, conversion, storage, and transport across multiple sectors, with a particular emphasis on biofuel production pathways and their interaction with land availability and sustainability constraints.

Model Scope
Sectors included
Electricity
Light-duty vehicles (LDV)
Heavy-duty vehicles (HDV)
Aviation
Shipping
Hydrogen and Power-to-X (PtX)
Energy carriers
Electricity
Hydrogen
Ethanol (1G and 2G)
Biodiesel / HVO
Sustainable Aviation Fuel (SAF)
E-kerosene and e-methanol
Ammonia

The model explicitly represents cross-sectoral interactions, enabling competition between electrification, biofuels, and synthetic fuels.

Bioenergy Module (Core Contribution)

A dedicated bioenergy subsystem is developed based on original work, with the following features:

Feedstocks and conversion
Sugarcane → ethanol (1G and 2G pathways)
Soybean → biodiesel / HVO
Ethanol → SAF and e-fuels (indirect pathways)
Spatial differentiation
Production zones classified by high, medium, and low suitability
Region-specific technologies and yields
Land-use constraints
Explicit available area constraints per region
Multiple land regimes implemented via overrides:
Full potential
Conservation + SIGEF restrictions
Land constraints without forest
Direct linkage between land availability and biofuel production capacity

These constraints are implemented through scenario-dependent parameters such as available_area .

Model Structure

The model is modular and organized into:

Technologies

Defined in separate YAML files:

Conversion (biofuels, hydrogen, PtX)
Storage (CO₂, hydrogen, fuels)
Transport (pipelines, shipping, electricity transmission)
Demand (sector-specific)
Locations
High spatial resolution (state-level zones, e.g., MG_Z1, SP_Z2)
Differentiated by resource quality (high/medium/low)
Includes:
Production sites
Demand nodes
Transport infrastructure
Temporal resolution
Representative year (e.g., 2019)
Resampled time series (e.g., 360h resolution)
Optimization Framework
Linear optimization using Gurobi
Cost-minimization objective (monetary)
Includes:
Capacity expansion
Dispatch optimization
Storage dynamics (cyclic storage enabled)
Exploration of near-optimal solutions

The model uses SPORES (Spatially-explicit Practically Optimal REsults) to explore alternative system configurations:

Multiple near-optimal solutions
Cost slack (e.g., 10–20%)
Diversity of pathways beyond the single optimum
Scenarios

Scenarios are defined in a structured way combining:

Cost assumptions
Demand projections
Land-use constraints

Examples include:

Baseline
Reference demand and cost assumptions
Net-zero pathways
Electrification-focused
Electrification + biofuels
PtX-driven pathways
Land-constrained variants
With conservation restrictions
With limited agricultural expansion

Scenario definitions are managed in scenarios.yaml .

Key Research Capabilities

This model enables analysis of:

Trade-offs between electrification, biofuels, and PtX
Impacts of land-use constraints on energy system configuration
Spatial redistribution of bioenergy production
Interaction between energy planning and environmental constraints
Alternative near-optimal pathways under uncertainty (SPORES)
Intended Use

The model is designed for:

Long-term energy planning studies
Policy analysis (land use, decarbonization pathways)
Academic research on energy–land–climate interactions
Key Features
High spatial resolution for Brazil
Explicit land–energy coupling
Multi-sector integration
Advanced scenario design
Exploration of non-cost-optimal solutions
