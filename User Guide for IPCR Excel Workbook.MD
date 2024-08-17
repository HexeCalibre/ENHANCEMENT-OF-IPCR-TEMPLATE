## 📘 User Guide for IPCR Excel Workbook

## Overview
This guide provides step-by-step instructions on how to use the IPCR (Individual Performance Commitment and Review) Excel workbook. The workbook has been enhanced to improve user experience, scalability, and maintainability.

## Getting Started

## Notes
- **Do not edit any formulas unless necessary.** All calculations are automated to minimize errors.
- **Ensure all fields are filled out accurately** to reflect your performance correctly.
- **If you encounter any issues,** refer to this guide or contact the support team for assistance.

### 1. **Opening the Workbook**
- **Step 1:** Open the appropriate Excel workbook based on your scenario:
    - **SOY-CFY:** Use this workbook if you have both Strategic Objectives and Core Functions.
    - **SON-CFY:** Use this workbook if you have Strategic Objectives but no Core Functions.
    - **SOY-CFN:** Use this workbook if you have Core Functions but no Strategic Objectives.

### 2. **Filling Out Employee Information**
- **Step 1:** Navigate to the **Edit Area** section in cells `L2:N19`.
- **Step 2:** Enter your full name in cell `M6`. Your name will automatically populate related fields across the workbook.
- **Step 3:** Enter your position in cell `M7`. This will update corresponding fields for your position.
- **Step 4:** Specify your office or department in cell `M8`.
- **Step 5:** Fill in the performance period start and end dates in cells `M9` and `M10`, respectively.

### 3. **Generating the Commitment Statement**
- **Step 1:** Once all the required employee information is entered, a formal commitment statement will be generated in cell `M4`.
- **Step 2:** Copy the generated statement from cell `M4` and paste it into cell `A4`.
- **Step 3:** Apply any necessary formatting (bold, underline) to the text within cell `A4`.

### 4. **Inputting Strategic and Core Functions**
- **Step 1:** In the **Functions** section, fill in the relevant details in cells `M15:M16`:
    - **M15:** Indicate if the Strategic Objective applies (`Y` or `N`).
    - **M16:** Indicate if the Core Functions apply (`Y` or `N`).
- **Step 2:** Based on your input, the workbook will automatically calculate the percentage allocation for Strategic, Core, and Support Functions in cells `M18:M20`.

### 5. **Logging Accomplishments**
- **Step 1:** Navigate to the **Accomplishments** section.
- **Step 2:** Record your actual accomplishments in the corresponding cells. If you need to add more accomplishments than the existing rows allow:
    - **Step 2a:** Right-click on the row number where you want to insert a new row.
    - **Step 2b:** Select **Insert** from the context menu to add a new row.
    - **Step 2c:** Fill in the new row with the additional accomplishment details.
- **Step 3:** The workbook will automatically count your accomplishments and display the totals in cells `C67`, `C68`, and `C69`. If you insert new rows, you may need to double-check the formulas used for counting accomplishments to ensure they include the new rows. Adjust the formulas as needed to capture all entries accurately.

### 6. **Understanding Automated Calculations**
- **Step 1:** The workbook includes several automated calculations to streamline the review process:
    - **Raw Scores Calculation:** Raw scores for support functions are summed using the formula `=SUM(RANGE)`.
    - **Average Scores Calculation:** Averages are calculated by dividing the total raw score by the count in cells like `C69`.
    - **Rating Computation:** Ratings for core and support functions are calculated and displayed in cells like `D67` and `F67`.

### 7. **Finalizing the Review**
- **Step 1:** Review the automatically calculated ratings and ensure all data is accurate.
- **Step 2:** The final average rating is displayed in cell `D69`, summarizing your performance.
- **Step 3:** The adjectival rating (e.g., "Outstanding", "Very Satisfactory") is automatically generated in cell `D70`.

### 8. **Saving and Submitting**
- **Step 1:** Once all information has been filled out and reviewed, save the workbook with your name and the performance period as the file name.
- **Step 2:** Submit the completed workbook to your supervisor or the relevant department.
