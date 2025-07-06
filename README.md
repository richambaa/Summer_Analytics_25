Dynamic Pricing for Urban Parking Lots

Overview

This project builds a real-time dynamic pricing engine for 14 urban parking lots using historical and simulated data. The objective is to price each lot intelligently based on:
  Occupancy patterns
  Queue length
  Traffic congestion
  Special events
  Vehicle type
  Competition (nearby parking lots)
Prices are updated every 30 minutes for 73 days, mimicking real-world demand fluctuations.

Tech Stack
  Python – Core language
  Pandas & NumPy – Data manipulation and model logic
  Bokeh – Real-time visualizations
  Pathway (optional) – Real-time streaming simulation
  Mermaid.js – Architecture diagram

Architecture Diagram
    A[Raw Parking Lot Dataset] --> B[Preprocessing & Feature Engineering]
    B --> C[Model 1: Linear Pricing]
    B --> D[Model 2: Demand-Based Pricing]
    B --> E[Model 3: Competitive Pricing]
    C --> F[Price Simulation]
    D --> F
    E --> F
    F --> G[Bokeh Visualization]
    
Project Workflow
Read CSV with real-time records for 14 lots
Parse timestamps and unify schema

Model 1: Linear
  Price increases with occupancy
  Price = Prev + α * (Occupancy / Capacity)

Model 2: Demand-Based
  Considers queue length, traffic, special days, vehicle types
  Normalized demand modifies price from base

Model 3: Competitive
  Adds geospatial competition logic (Haversine distance)
  Adjusts price based on nearby lot prices

Simulation
  Runs pricing per 30-min interval across all lots
  Maintains smooth, bounded price changes

Visualization
  Live line plots for each model using Bokeh
