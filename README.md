Optimizing NYC Food Waste Distribution

Interim project summary based on our report (PDF in repo)

Project Description

This project develops an optimization model to improve how surplus restaurant food in New York City is collected and redistributed to neighborhoods experiencing food insecurity. We leverage the city’s existing food scrap drop-off centers as donation hubs and model the movement of food across three sets of nodes:

R — Restaurants (supply)

D — Donation centers (transshipment points)

N — Neighborhoods (demand)

The goal is to design an allocation system that is both efficient and equitable, ensuring high-need neighborhoods receive food while keeping transportation distance low.

Data

We use datasets from NYC Open Data, including:

Food scrap drop-off center locations (coordinates, operating hours)

Neighborhood food supply gaps (demand in pounds + socioeconomic indicators)

Neighborhood boundaries (used to compute centroids)

Restaurant locations and surplus quantities are simulated using industry reports due to lack of public data.

Distances between nodes use Manhattan distance.

Optimization Formulation

We implement two linked optimization models:

1. Minimum-Distance Objective

Minimizes total transportation cost from:

Restaurants → Donation centers

Donation centers → Neighborhoods

Subject to:

Restaurant supply limits

Neighborhood demand limits

Flow-balance at donation centers

Big-M penalty to avoid the trivial “no shipments” solution

2. Equity Objective

Minimizes the maximum unmet demand across neighborhoods.

This ensures the distribution does not concentrate food only in nearby, easy-to-serve areas.

Expected Outcomes

Identification of cost-optimal and equity-optimal distributions

Exploration of the Pareto frontier between efficiency and fairness

Benchmarking against simple heuristics (e.g., nearest-neighbor routing, demand-first allocation)

Policy insights for NYC food rescue programs, including which donation centers act as critical hubs and which neighborhoods remain underserved even under optimal allocations
