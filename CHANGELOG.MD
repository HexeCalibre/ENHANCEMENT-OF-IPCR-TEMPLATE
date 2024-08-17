# 📝 IPCR Change Logs

## Overview
This document outlines the changes and enhancements made to the IPCR (Individual Performance Commitment and Review) Excel template to improve user experience, scalability, and maintainability.

## ✨ Enhancements Summary

### 1. **Editable Area Added**
- **Cells `L2:N19`**: Designated as the editable area for inputting specific details related to employee information and performance metrics.

### 1.1. **Cell M4 (Concatenated Statement Generator)**
- **Formula**: `=CONCATENATE("I, ",M5,", ",M6," of the ",M7," commit to deliver and agree to be rated on the attainment of the following targets in accordance with the indicated measures of the period ",M8," to ",M9,".")`
- **Function**: Generates a formal statement based on user inputs in cells `M5:M10`. The result is intended to be copied and pasted into `A4`, where users can apply formatting (bold and underline) as needed.

### 1.2. **Employee Information Labels**
- **L5 (Employee Name Label)**: Label for input in cell `M5` (Employee Full Name). This input is reflected in cells `H5` and `A59`, preventing repetitive data entry.
- **L6 (Position Label)**: Label for input in `M6` (Position), reflected in `H6`.
- **L7 (Department/Office Label)**: Label for input in `M7` (Department/Office Name).
- **L8 (Period From Label)**: Label for the starting period date input in `M8`.
- **L9 (Period To Label)**: Label for the ending period date input in `M9`.
- **L10 (Immediate Supervisor's Name Label)**: Label for input in `M10`, reflected in `A12`.

### 1.3. **Additional Cell Labels and Behaviors**
- **L11 (PMT Chairman's Name Label)**: Updates `C57` based on user input.
- **L12 (PMT Chairman's Position Label)**: Updates `C59`.
- **L13 (Head of Agency's Name)**: Updates `D12`.

### 1.4. **Strategic, Core, and Support Functions**
- **L15 (Strategic Objective Label)** and **L16 (Core Functions Label)**: Labels for inputs in cells `M15:M16`, calculating percentages in cells `M18:M20`.
    - **M18 (Strategic Objective %)**:
      - Formula: `=IF(AND(M15="y", M16="y"), 0.45, IF(AND(M15="y", M16="n"), 0.7, IF(AND(M15="n", M16="y"), 0, 0)))`
    - **M19 (Core Functions %)**:
      - Formula: `=IF(AND(M15="y", M16="y"), 0.45, IF(AND(M15="y", M16="n"), 0, IF(AND(M15="n", M16="y"), 0.7, 0)))`
    - **M20 (Support Functions %)**:
      - Formula: `=IF(AND(M15="y", M16="y"), 0.1, IF(AND(M15="y", M16="n"), 0.3, IF(AND(M15="n", M16="y"), 0.3, 0)))`

### 1.5. **Automated Formula Adjustments**
- **Cell C67 (Accomplishments Counter for Strategic Objectives)**: 
  - Formula: `=COUNTA(I20:I20)`
- **Cell C67 (Accomplishments Counter for Core Functions)**: 
  - Formula: `=COUNTA(I22:I22)`
- **Cell C68 (Accomplishments Counter for Support Functions)**:
  - Formula: `=COUNTA(A24:A45)`

### 1.6. **Improved Formula Readability**
- **Cells for Support Functions Total Raw Score**:
  - Old Formula: Summation using individual cell addition.
  - New Formula: `=SUM(RANGE)`, simplifying readability, scalability, and maintainability.

### 1.7. **Calculation of Averages**
- **Strategic Objectives (I19/C48) for Cell `J19`**: 
  - Formula: `=I19/C48`, where `I21` represents the total raw score, and `C48` contains the count of core functions.
- **Core Functions (I21/C49) for Cell `J21`**: 
  - Formula: `=I21/C49`, where `I21` represents the total raw score, and `C49` contains the count of core functions.
- **Support Functions (I23/C50) for Cell `J23`**: 
  - Formula: `=I23/C50`, where `I23` represents the total raw score, and `C50` contains the count of core functions.

### 1.8. **Strategic Objectives Concatenation**
- **Cell A19**: 
  - **Formula**: 
    ```excel
    =CONCATENATE(
        "STRATEGIC OBJECTIVES: 6-POINT S.T.R.I.K.E. PROGRAM ",
        IF(N25="Y", CONCATENATE(L25, "-", M25), ""),
        IF(N26="Y", CONCATENATE(L26, "-", M26), ""),
        IF(N27="Y", CONCATENATE(L27, "-", M27), ""),
        IF(N28="Y", CONCATENATE(L28, "-", M28), ""),
        IF(N29="Y", CONCATENATE(L29, "-", M29), ""),
        IF(N30="Y", CONCATENATE(L30, "-", M30), "")
    )
    ```
  - **Function**: Dynamically generates a concatenated string of strategic objectives based on "Y" values in cells `N25:N30`, paired with labels from `L25:L30` and descriptions from `M25:M30`.
  
  - **Labels and Descriptions**:
    - **L25**: S - **M25**: SOCIAL, HEALTH & INTEGRATED SERVICES
    - **L26**: T - **M26**: TRANSFORMATIVE, ADMINISTRATION & E-GOVERNANCE
    - **L27**: R - **M27**: REVENUE, FINANCIAL & ECONOMIC ENTERPRISES
    - **L28**: I - **M28**: INFRASTRUCTURE & DEVELOPMENT MANAGEMENT
    - **L29**: K - **M29**: KEY FACILITIES, PROPERTY & ENGINEERING
    - **L30**: E - **M30**: ENVIRONMENT & SANITATION, SECURITY, PEACE & ORDER

## 🔍 Automation of Rating Computation
- **D48:D50 (Automated Rating Computation for Core Functions)**:
    - **Old Template**: Manual hard-coding of the formula for computing the rating.
    - **New Automation**: Automated formula generation, reducing user effort and calculation errors.
    - **Formula for Strategic Objectives**: `=CONCATENATE(TEXT(I19,"0.000")," / ",C48," = ",TEXT(J19,"0.000")," x ",M17)`
    - **Formula for Core Functions**: `=CONCATENATE(TEXT(I21,"0.000")," / ",C49," = ",TEXT(J21,"0.000")," x ",M18)`
    - **Formula for Support Functions**: `=CONCATENATE(TEXT(I23,"0.000")," / ",C50," = ",TEXT(J23,"0.000")," x ",M19)`
    - **Displayed Output**: Format like `Total Raw Score / Accomplishment Count = Average Raw Score x Corresponding Percentage`.

## 🔗 Final Adjustments and Improvements
- **Cell D69 (Final Average Rating)**:
    - Formula: `=SUM(F48:F50)`, providing a consolidated average rating across all performance metrics.

- **D70 (Adjectival Rating Function)**:
    - Formula: `=IF(D51>=4.5, "Outstanding", IF(D51>=3.5, "Very Satisfactory", IF(D51>=2.5, "Satisfactory", IF(D51>=1.5, "Unsatisfactory", "Poor"))))`
    - Generates the adjectival rating based on the final average rating.

- **Conditional Formatting for Final Average Score (D49)**
    - **Outstanding**: RGB(99, 190, 123)
    - **Very Satisfactory**: RGB(255, 235, 132)
    - **Satisfactory**: RGB(255, 233, 134)
    - **Unsatisfactory**: RGB(253, 185, 76)
    - **Poor**: RGB(248, 105, 107)

- **Conditional Formatting for Adjectival Rating (D50)**
    - **Outstanding**: RGB(99, 190, 123)
    - **Very Satisfactory**: RGB(255, 235, 132)
    - **Satisfactory**: RGB(255, 233, 134)
    - **Unsatisfactory**: RGB(253, 185, 76)
    - **Poor**: RGB(248, 105, 107)