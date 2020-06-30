# Hours Summary

## Data source

Payroll Hour table in HCIDataTables database \(Azure SQL database\)

Reports from TriNet are manually cleaned and inserted into the table

## Calculations

### Total Other Hours

Sum of hours column in the Payroll Hour table which have “Other” as an hour type

Other hours are defined as all PTO, PTI, and Holiday hours

### Total Regular Hours

Sum of hours in the Payroll Hour table which have “Regular” as an hour type

Regular hours are defined as all hours not classified as “Other” up to 40 hours per week outside of California or 8 hours a day in California

### Total Overtime Hours

Sum of hours in the Payroll Hour table which have “Overtime” as an hour type

Overtime hours are defined as the “Regular” hours in excess of 40 hours per week outside of California or 8 hours a day in California

TriNet automatically calculates the amount of overtime hours and displays it in a separate column in the report that we use

### Total Working Hours \(Hidden\)

Total Regular Hours plus Total Overtime Hours

### Overtime Pct.

\(Total Overtime Hours divided by Total Working Hours\) x 100

