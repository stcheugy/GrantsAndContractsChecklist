# National Grant & Contract Form

## Automated Features and Logic Primer

---

## Executive Summary

This form is no longer just a static document — it is now a dynamic system powered by custom-built JavaScript automation. Thanks to this embedded codebase, the Grants & Contracts Checklist and Review Log actively manages calculations, validations, and field logic in real time. This means:

* Service units will gain a more complete and accurate understanding of grant budgets
* Understaffed service units gain the opportunity to plan for new types of funding (e.g. per diem, deboligations, valued gifts-in-kind, etc)
* Manual errors are caught before submission
* Staff no longer need to rely on external calculators or memorizing internal fee rates
* Programs of all sizes and funding types are supported, including Per Diem, Non-Monetary, and Deobligation modes

What once required manual workarounds is now automated, accurate, and responsive. This form is ready for national standardization and scalable implementation across all territories. Its modular code structure also allows for future enhancements with minimal maintenance.

---

## Purpose

This document outlines the automated features and embedded logic in the National Grants & Contracts Adobe PDF form. These enhancements streamline data entry, ensure accurate budget validation, and provide responsive visual feedback for program budgets.

---

## Dynamic Input Modes

## Input Types Supported:

| Mode                | Description                                      |
| ------------------- | ------------------------------------------------ |
| Standard Line Items | Manual entry of up to 12–20 budget lines         |
| Per Diem Mode       | Calculates totals from units and days            |
| Non-Monetary        | Disables fee logic for exemptions and allotments |

How It Works:

* Checkbox selections activate specific input modes
* Field labels and visibility adjust based on selected mode

---

## Automated Calculations

| Calculation Target | Description                                                    |
| ------------------ | -------------------------------------------------------------- |
| Subtotals          | Auto-calculated based on input method (line items or per diem) |
| Income             | Calculates and applies a cumulative THQ and DHQ fee            |
| Expenses           | Calculates and apllies standard 10% THQ and 2% DHQ fees        |
| Per Diem           | Caculates contract max by multiplying rate by units by days    |
| Non-Monetary       | Fee logic bypassed completely                                  |
| Fee Exempt         | Fee logic is bypassed for EFSP/FEMA income                     |
| Deobligation       | Bypass fee logic & duplicate negative value to balance amount  |
| Salary Calculator  | Dynamically detects salary or fringe benefits                  |
| Salary Detail      | Dynamically displays salary details in standard format         |

---

## Validation System

Automatic Checks:

* Totals compared between related categories:

  * Cash vs. Grant
  * Match Income vs. Match Expense
* Missing or imbalanced totals trigger field warnings

Special Modes:

* Deobligation: Negative values allowed and auto-balanced
* Per Diem: Accepts unit-based inputs
* Non-Monetary: Excludes from fee logic and validation scope

## Visual Feedback Key:

| Color  | Meaning                  |
| ------ | ------------------------ |
| Green  | Totals are balanced      |
| Red    | Totals are unbalanced    |
| Yellow | Per Diem mode is active  |
| Pink   | Deobligation mode active |
| White  | Idle or zero values      |

---

## User Guidance Tools

| Feature            | Behavior                                            |
| ------------------ | --------------------------------------------------- |
| Inline Messaging   | Contextual instructions shown near input fields     |
| Dynamic Visibility | Fields hidden/cleared automatically as modes change |
| Validator Summary  | Displays success messages, errors, or current mode  |

---

## Error Handling & Safety Measures

* Field access is cached to improve performance
* Defensive programming prevents calculation errors from bad inputs
* Internal console logging supports testing and troubleshooting

---

## Leadership Summary

This system enables:

* Faster and more accurate budget entry
* Reduced staff time correcting form errors
* Visual confirmation of validation success
* Adaptive logic for all major grant types

The codebase is modular, scalable, and built for sustainable national use with minimal upkeep.

For technical support, contact: Division Grants and Contracts Analyst
