# National Grant & Contract Form

## Automated Features and Logic Primer

---

## Executive Summary

This form is no longer just a static document — it is now a dynamic system powered by custom-built JavaScript automation. Thanks to this embedded codebase, the National Grants & Contracts PDF form actively manages calculations, validations, and field logic in real time. This means:

* Manual errors are caught before submission
* Staff no longer need to rely on external calculators or notes
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
| Income             | Applies 11.8% fee                                              |
| Expenses           | Applies stacked 10% and 1.8% fees                              |
| Non-Monetary       | Fee logic bypassed completely                                  |
| Salary Builder     | Accepts role, FTE %, salary, and fringe; returns summary       |

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

## Flowchart Summary

```mermaid
flowchart TD
    Start[User begins form] -->|Inputs value in budget line| BudgetInput[Trigger: Line Mode Logic]
    BudgetInput --> RunTotals1[RunTotals → valueHandler → setFieldValues]
    RunTotals1 --> ValidateTotals1[Validate Totals → display result]

    CheckBox[User checks a mode box (PDR, Deobligation, Non-Monetary)] --> BoxToggleLogic[boxToggle processes mode switch]
    BoxToggleLogic --> UpdateFields[Update labels, visibility, and instructions]
    UpdateFields --> RunTotals2[Trigger runTotals with new mode flag]

    RunTotals2 -->|PDR Mode| PDRBranch[Use unit * rate logic → auto-calculate subtotal]
    PDRBranch --> ValidateTotals2[PDR Validator Checks (looser constraints)]

    RunTotals2 -->|Deobligation Mode| DeobBranch[Allow negatives, show pink highlight]
    DeobBranch --> ValidateTotals3[Check grant total vs expense]

    RunTotals2 -->|Non-Monetary Mode| NonMonetaryBranch[Skip fees, show white fields]
    NonMonetaryBranch --> ValidateTotals4[Confirm zeroed or non-financial fields only]

    AnyValidation[Validation Step] --> Validator[Display message, color, success or error]
```

---

## Leadership Summary

This system enables:

* Faster and more accurate budget entry
* Reduced staff time correcting form errors
* Visual confirmation of validation success
* Adaptive logic for all major grant types

The codebase is modular, scalable, and built for sustainable national use with minimal upkeep.

For technical support, contact: Division Grants and Contracts Analyst
