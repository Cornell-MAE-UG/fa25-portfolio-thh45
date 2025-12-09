---
layout: project
title: Analysis of Functions
description: Class project with Graphs
technologies: [MATLAB, python]
---

# Torque Wrench Design Project

## Project Overview
Design and analysis of a strain gauge-based torque wrench using FEM analysis and optimal material selection.

---

## 1. CAD Model

![CAD Model - Rendering](./assets/final-rendering.png)
*Figure 1: CAD model rendering showing key dimensions*

![CAD Model - Technical Drawing](./assets/final-drawing.jpg)
*Figure 2: Technical drawing with dimensions*

---

## 2. Material Selection: 7075-T6 Aluminum Alloy

We selected **7075-T6 aluminum alloy** for the final torque wrench design after comparing multiple material options including other aluminum alloys, steels, and titanium.

### Material Properties
- **Yield Strength:** 66.7 ksi
- **Elastic Modulus:** Lower than steel alternatives
- **Cost:** Over 11× cheaper than original M42 tool steel

### Selection Rationale

The original baseline design used **M42 tool steel**, which had a much higher tensile strength than required for the design constraints. Our analysis of alternative materials revealed:

**Aluminum Alloys Considered:**
- **7075-T6**  Selected for optimal strength-to-cost ratio
- **6061-T6**  Insufficient yield strength without major dimensional changes
- **2024-T3**  Insufficient yield strength without major dimensional changes

**Steel Alloys Considered:**
- **AISI 1050**  Required dramatic redesign due to higher elastic modulus
- **AISI 4140**  Only slightly cheaper than 7075-T6, but failed strain gauge requirements

**Titanium Alloys Considered:**
- **Grade 2 Titanium**  Significantly more expensive despite reduced volume
- **Ti-6Al-4V**  Many times more expensive than 7075-T6

The 7075-T6 aluminum provides adequate yield strength while maintaining a lower elastic modulus than steel options, which is critical for meeting strain gauge sensitivity requirements without requiring extensive geometric modifications.

---

## 3. FEM Model: Loads and Boundary Conditions

![Loads and Boundary Conditions](./assets/load-bc1.png)
![Loads and Boundary Conditions](./assets/load-bc2.png)
*Figure 3: FEM showing applied loads and boundary conditions*

### Boundary Conditions
- **Fixed Region:** All five faces of the contact region at the wrench end are constrained (zero displacement)
- **Clearance:** 0.1" clearance between fixed region and main wrench body
- **Fillet:** Smooth fillet connects the nub to main body

### Load Application
The applied force model was significantly improved from the baseline design to better reflect actual usage:

- **Load Distribution:** Force distributed evenly around entire surface of the rubber handle
- **Handle Geometry:** Large rubber handle surrounds circular region of wrench
- **Moment Arm:** Extended wrench length so handle center is 16" from fixed region
- **Torque Equivalence:** Overall applied torque maintained consistent with baseline case

---

## 4. Normal Strain Contours

![Normal Strain Contours](./assets/normal_strain_contours.png)
*Figure 4: Normal strain distribution in strain gauge direction*

---

## 5. Maximum Principal Stress

![Maximum Principal Stress](./assets/max_principal_stress.png)
*Figure 5: Maximum principal stress contour plot*

---

## 6. FEM Analysis Results Summary

![FEM Results Table](./assets/fem_results_table.png)
*Figure 6: Complete FEM analysis results*

---

## 7. Torque Wrench Sensitivity

**Sensitivity Calculation:**

```
Sensitivity = ε × GF
Sensitivity = 1.393 × 10⁻³ × 1.05
Sensitivity = 1.46 × 10⁻³ mV/V
```

Where:
- ε = Strain at gauge location
- GF = Gauge factor

---

## 8. Strain Gauge Selection

**Selected Gauge:** CEA-06-125UN-350  
**Manufacturer:** Vishay Precision Group - Micro-Measurements

### Specifications
- **Type:** Uniaxial constantan foil strain gauge
- **Gauge Factor:** 2.1
- **Dimensions:** 0.38 in × 0.19 in

The design provides adequate space to physically bond the gauge to the wrench surface at the specified measurement location.

---

## Conclusion

This design successfully optimizes material selection and geometry to create a cost-effective, accurate torque wrench. The 7075-T6 aluminum alloy provides the necessary mechanical properties while reducing material costs by over 11× compared to the baseline M42 steel design. FEM analysis validates that the design meets all structural and sensitivity requirements.


