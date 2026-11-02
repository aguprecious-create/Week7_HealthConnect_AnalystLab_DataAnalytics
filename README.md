# HealthConnect Rwanda: Data Analytics Testing & Refinement (Week 7)

This folder holds the Week 7 Data Analytics submission. Week 7 tests and refines the Week 6 analytical outputs. It does not repeat the Week 5 exploratory analysis or rebuild the Week 6 dashboard.

## Folder contents

| Folder | Contents |
|---|---|
| `Report/` | `HealthConnect_Week7_Testing_Refinement_Report.docx` and `.pdf`: testing approach, testing register, KPI validation, analytical results, refinements, updated insights and recommendations, cross-track record, limitations and Week 8 recommendations. |
| `Dashboard/` | `HealthConnect_Rwanda.pbix`: the dashboard after Week 7 refinements. |
| `Data/` | The source data, as used in Week 6: the healthcare tables and the billing table. |

## What was tested

- **KPI reconciliation:** 10 headline KPIs recalculated from the source tables. All match the reference values after two display and labelling fixes.
- **Dashboard behaviour:** the date slicer and the Status, City, Location, Gender, Province, Facility, Department and Rating slicers. Charts and cards respond to each one, and totals return to the full figure when cleared.
- **Statistical validation:** matched and unmatched bills, the monthly billing trend, facility and department rating differences, and linked and unlinked feedback.
- **Timing and leakage review:** each feature used in the cross-track admission model was checked for whether it is known at the stated prediction point.

## Key refinements

- The date slicer now filters the clinical cards (Emergency visits and Total appointments).
- Card numbers show in full (for example 1,650), not rounded to K.
- Patient experience rankings are built on linked feedback. Before the fix, every facility showed 2.99.
- The revenue summary table was removed. It does not reconcile with billing (1.13bn against 9.31bn).
- The complaints card shows the complaint count (8,518), not an unlabelled figure.
- Facility and department rating differences are reported as not statistically significant, so no site is singled out.
- All amounts are in RWF, from the countries table.

## Limitations

- Only 5,000 of 60,000 appointments link to facility, department and clinical detail.
- Bills have no dates, so the monthly trend covers the matched subset only.
- The dataset has no attendance or no-show field. Attendance findings cannot be tested.
- The Admissions sheet has a length of stay for each appointment but no admitted flag. Admission status cannot yet be defined from this copy.
- The high-acuity proxy has 544 positive cases, so small real effects cannot be detected.

## Cross-track collaboration (Data Science)

Validated findings and timing rules were shared with the Data Science track. The re-test results, from the partner's model, are reported as theirs. Their refined model reached a hold-out ROC-AUC of 0.519, which is not distinguishable from chance, and it is not recommended for deployment. Confirmations on the target, the feature list and the hold-out set are outstanding. They will be integrated in Week 8.

## Source data

The data is synthetic and was created for training purposes.
