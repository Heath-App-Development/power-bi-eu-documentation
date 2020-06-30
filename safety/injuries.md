# Injuries

## Data source

Injury tracking SharePoint lists

Data from Injury Investigation App is combined with the information from the SharePoint list that was manually maintained. Status updates are done in a separate portal app

Payroll Hour table in HCIDataTables database \(Azure SQL database\)

Reports from TriNet are manually cleaned and inserted into the table

## Calculations

### Recordables \(Total Recordable Injuries\)

Count of all injuries in the SharePoint list that have a disposition of “Recordable”

### Hours \(Total Hours\)

Sum of the Hours column from the Payroll Hour table

### TRIR

\(Total Recordable Injuries x 200,000\) divided by Total Hours

### Running Total Hours \(Hidden\)

Cumulative total of Total Hours

### Running Total Recordable Injuries \(Hidden\)

Cumulative total of Total Recordable Injuries

### Running TRIR

\(Running Total Recordable Injuries x 200,000\) divided by Running Total Hour

