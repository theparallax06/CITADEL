# CITADEL

## Climate-Aware. Thermally Optimized. Field-Ready.

**Area-Specific Passive Shelter Design & Thermal Evaluation Platform**

**Team: THE PARALLAX**

CITADEL is an area-specific shelter design and thermal evaluation platform developed for **Smart India Hackathon 2026**. It connects location-specific climate conditions with parametric shelter design and physics-based thermal analysis to evaluate how geometry, materials, insulation, openings, orientation, occupancy, and environmental conditions influence shelter thermal behaviour.

---

## 1. Smart India Hackathon 2026

- **Problem Statement ID:** SIH26051
- **Problem Statement:** Software Based Model Development for Design of Area Specific Shelter for Thermal Comfort Maintenance
- **Organization:** DRDO – Department of Defence R&D
- **Category:** Software
- **Theme:** Miscellaneous
- **Team:** The Parallax

---

## 2. Problem Statement

Generic shelters may be designed without sufficient consideration of the climatic conditions of their deployment region. Variations in temperature, solar radiation, humidity, orientation, materials, insulation, geometry, and openings can significantly affect indoor thermal conditions.

A location-aware and physics-based approach is required to support area-specific passive shelter design, improve thermal comfort, and reduce unnecessary dependence on external heating or cooling.

---

## 3. Proposed Solution

CITADEL provides an end-to-end **location-to-design thermal decision workflow**:

```text
Location
   ↓
Climate Profile
   ↓
Shelter Requirements
   ↓
Parametric Design
   ↓
Thermal Physics Engine
   ↓
Thermal Evaluation
   ↓
Design Comparison
   ↓
Optimization
   ↓
Explainable Recommendation
   ↓
Engineering Report
```

The platform evaluates shelter configurations against regional climate conditions and uses a physics-based thermal model to compare their thermal behaviour under defined constraints.

---

## 4. Key Innovation

- **Location-to-Design:** Starts from the deployment environment rather than a generic shelter configuration.
- **Physics-First Approach:** Thermal physics forms the computational foundation; optimization and ML are supporting layers.
- **Constraint-Aware Design:** Considers occupancy, dimensions, transport weight, available materials, and manufacturable thickness.
- **Multi-Design Comparison:** Evaluates multiple configurations under the same climate and simulation conditions.
- **Explainable Decisions:** Recommendations are traceable to climate data, material properties, geometry, simulation results, and constraints.
- **Offline-First Capability:** Core design and thermal evaluation functions are designed for remote and connectivity-limited environments.
- **Engineering Transparency:** Inputs, assumptions, data sources, model version, and validation status can be recorded with each design.

---

## 5. Core Features

### 5.1 Location & Orientation

- Device GPS/GNSS or manual location input
- Latitude and longitude capture
- Built-in device compass using available motion/orientation sensors
- Manual orientation fallback when sensor data is unavailable
- Offline-capable location and orientation workflow

### 5.2 Climate Intelligence

- Temperature profiles
- Solar radiation
- Humidity and wind where available
- Hourly/daily environmental profiles
- Climate data source and confidence information
- Design implications derived from the selected climate profile

### 5.3 Shelter Requirements

Supports configuration of:

- Occupancy
- Required shelter area
- Maximum transport weight
- Maximum panel/module dimensions
- Available materials
- Design priority: thermal performance, low weight, low energy, or balanced

### 5.4 Parametric Shelter Design

Users can configure:

- Shelter geometry
- Length, width, and height
- Orientation
- Openings and opening area
- Material layers
- Insulation thickness
- Thermal mass
- Composite wall assemblies

Supported shelter geometries can include **A-Frame, Box/Rectangular, Dome, Gable Roof**, and other configured forms.

### 5.5 Material Library

Material data can include:

- Thermal conductivity
- Density
- Specific heat capacity
- Emissivity where applicable
- Available thickness
- Engineering/reference information

Composite material assemblies can be created and evaluated as layered structures.

### 5.6 3D Visualization

Interactive 3D shelter visualization using:

- Three.js
- React Three Fiber
- Drei

The 3D view allows users to understand shelter geometry and configuration changes before evaluation.

---

## 6. Thermal Physics Engine

The Thermal Physics Engine is the primary computational layer of CITADEL.

It uses a time-step based **1D Resistance-Capacitance (RC) thermal model** to estimate shelter thermal behaviour.

### Modelled Factors

- Conduction through wall/material layers
- Thermal resistance and capacitance
- Solar gain based on orientation and surface exposure
- Thermal mass and heat storage
- Surface heat exchange with ambient conditions
- Time-dependent thermal response
- Window/opening effects where implemented
- Internal heat gain from occupants where implemented

### Main Outputs

- Indoor temperature vs. time
- Solar thermal energy/gain
- Heat-flow behaviour
- 24-hour thermal profile

CFD/FEM and other high-fidelity numerical methods are considered validation/future extensions rather than requirements for normal CITADEL execution.

---

## 7. Design Comparison

CITADEL allows multiple shelter configurations to be evaluated under comparable conditions.

Examples include:

- Baseline design
- Higher-insulation design
- Higher-thermal-mass design
- Alternative material assembly
- Alternative orientation
- Alternative opening configuration

The comparison uses actual simulation outputs rather than arbitrary improvement claims.

---

## 8. Optimization & Design Exploration

The optimization layer explores feasible shelter configurations using the thermal engine.

### Objectives

- Reduce deviation from the target thermal condition
- Reduce material mass
- Reduce energy requirement

### Constraints

- Transport weight
- Shelter dimensions
- Panel/module limits
- Available materials
- Occupancy requirements
- Manufacturable layer thickness

The system can present multiple feasible candidates and their trade-offs rather than assuming that one configuration is universally optimal.

---

## 9. Explainable Recommendation

CITADEL explains why a particular configuration performs differently by referring to:

- Selected climate conditions
- Material properties
- Shelter geometry
- Orientation
- Insulation
- Opening configuration
- Thermal simulation results
- Deployment constraints
- Design trade-offs

The recommendation is intended to remain traceable to model inputs and calculated results.

---

## 10. What-If & Sensitivity Analysis

### What-If Explorer

Users can modify parameters such as:

- Insulation thickness
- Orientation
- Material
- Opening area
- Thermal mass
- Geometry

The modified design can be simulated and compared with the previous configuration.

### Sensitivity Analysis

The system can examine the influence of key parameters such as:

- Material conductivity
- Insulation thickness
- Orientation
- Opening area
- Thermal mass
- Geometry

Results are interpreted for the selected location and scenario.

---

## 11. Validation & Model Transparency

CITADEL supports transparent model evaluation through:

```text
Reference Case
      ↓
Expected Response
      ↓
CITADEL Model Output
      ↓
Comparison
      ↓
MAE / RMSE
```

Accuracy values are reported only where real reference data is available.

The design record can include:

- Input values
- Climate data source/version
- Material data
- Simulation period
- Model version
- Assumptions
- Boundary conditions
- Validation status
- Known limitations

**ANSYS** can be used as an independent high-fidelity validation environment for selected 3D geometries and thermal cases. It is not required for normal CITADEL execution.

---

## 12. Offline-First Architecture

CITADEL is designed to support remote and connectivity-constrained deployment environments.

```text
Local UI
   ↓
Local Climate / Material Data
   ↓
Local Shelter Model
   ↓
Local Thermal Physics Engine
   ↓
Local Results
   ↓
Local Design Storage / Report
```

Key offline-oriented components include:

- PWA/service-worker caching
- Locally available climate and material profiles
- LocalStorage-based design persistence
- Offline thermal computation
- Offline report generation
- Device GPS and orientation sensors
- Capacitor-based Android packaging

The core workflow does not depend on continuous online weather access.

---

## 13. Saved Designs & Reports

CITADEL supports persistent design management through **My Designs**.

Users can:

- Save evaluated designs
- Reopen previous designs
- Continue editing saved designs
- Compare saved configurations
- Store thermal evaluation results
- Generate offline reports
- Download reports to the device

The objective is to maintain a reusable design history for later review and comparison.

---

## 14. Engineering Report

The generated report can contain:

- Location and coordinates
- Shelter orientation
- Climate profile
- Shelter geometry
- Dimensions
- Material assembly
- Insulation
- Openings
- Simulation period
- Thermal results
- Design comparison
- Selected configuration
- Recommendation rationale
- Assumptions
- Validation status

Where supported, the reporting workflow can also be extended toward a deployment-oriented design record containing material quantities and assembly information.

---

## 15. Technical Architecture

```text
User Interface
      ↓
Location & Orientation
      ↓
Climate / Material Data
      ↓
Shelter Configuration
      ↓
Thermal Physics Engine
      ↓
Thermal Results
      ↓
Comparison & Optimization
      ↓
Explainability / Validation
      ↓
Engineering Report
```

The **Thermal Physics Engine** remains the primary computational foundation. ML/surrogate modelling, where integrated, is intended to accelerate repeated prediction and design-space exploration rather than replace the underlying physics model.

---

## 16. Technology Stack

| Technology | Purpose |
|---|---|
| React 19 + TypeScript | Application interface and frontend |
| Vite | Development and production build |
| Custom TypeScript Thermal Engine | 1D RC thermal computation |
| Three.js | 3D visualization |
| React Three Fiber + Drei | Interactive 3D shelter visualization |
| Recharts | Thermal data visualization |
| LocalStorage | Local design/result persistence |
| Vite PWA | Offline-capable web deployment |
| Capacitor Android | Android application deployment |
| Lucide React | Interface icons |
| jsPDF + AutoTable | Offline report generation |
| ANSYS | Independent 3D thermal validation reference |

---

## 17. Application Workflow

1. Start a new design.
2. Enter or identify the deployment location.
3. Determine shelter orientation using the device compass or manual input.
4. Review the relevant climate profile.
5. Define shelter requirements and deployment constraints.
6. Configure shelter geometry, materials, insulation, openings, and dimensions.
7. Visualize the shelter in 3D.
8. Run the thermal analysis.
9. Review the 24-hour thermal profile.
10. Compare multiple configurations.
11. Explore optimization and what-if scenarios.
12. Review the explainable design reasoning.
13. Save the design to My Designs.
14. Generate and download the engineering report.

---

## 18. Project Status

The project currently focuses on an integrated software prototype containing:

- React-based application interface
- Android application through Capacitor
- 3D shelter visualization
- TypeScript-based 1D RC thermal engine
- Parametric shelter configuration
- Design comparison
- Optimization/design exploration
- Local design persistence
- Offline report generation
- Offline-oriented location and orientation support

Advanced CFD/FEM validation, expanded climate datasets, physical field validation, and additional ML acceleration capabilities can be extended in future development.

---

## 19. Deployment & Project Links

- **Live Application:** https://the-parallax-citadel.netlify.app/
- **GitHub Repository:** https://github.com/theparallax06/CITADEL
- **Android APK:** https://github.com/theparallax06/CITADEL/releases/tag/v1.0.0
- **Project Demo Video:** https://youtu.be/3vmsluk5_XE

---

## 20. SIH Alignment

| SIH Requirement | CITADEL Approach |
|---|---|
| **Area Specific** | Location-specific climate and environmental context |
| **Shelter Design** | Parametric geometry, materials, insulation, openings and orientation |
| **Thermal Comfort Maintenance** | Physics-based thermal evaluation and comparative design analysis |
| **Software-Based Model** | Integrated software thermal engine and design workflow |
| **Design Decision Support** | Comparison, optimization, sensitivity and explainable results |
| **Field Deployment** | Offline-first workflow and Android application support |

---

## 21. Future Scope

- Expanded regional and seasonal climate datasets
- Advanced transient thermal modelling
- Ventilation and ground-contact modelling
- CFD/FEM integration for high-fidelity validation
- Physical instrumented shelter validation
- Field sensor integration
- ML surrogate models for faster repeated simulations
- Full multi-objective optimization
- Advanced 3D visualization
- Expanded material and durability database
- Multi-season and worst-case scenario analysis

---

## 22. Limitations & Disclaimer

CITADEL is a **software-based engineering decision-support and comparative thermal evaluation platform**.

Its thermal outputs are model-based estimates using simplified 1D resistance-capacitance physics. Results should be independently validated using higher-fidelity engineering simulation or physical measurements before real-world physical deployment.

CITADEL does not provide certified guarantees regarding structural integrity, construction safety, or life-safety parameters.

---

## 23. Team

**THE PARALLAX**

**Project:** CITADEL  
**Smart India Hackathon 2026**  
**Problem Statement:** SIH26051  
**Organization:** DRDO – Department of Defence R&D  
**Category:** Software
