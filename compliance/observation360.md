# Observation360

## Data source

Observation360 app database table views \(Azure SQL database\)

Automatically records information sent back from the app in various tables

## Calculations

### Average Duration

Sum of all values from the duration time field from the Observation Header table divided by the count of observations

### Median Duration

All values from the duration time field \(including repeats\) are placed in order from smallest to largest

If there is an odd number of values, the middle value is the median

If there is an even number of values, the average of the two middle values is the median

### Completed Observations

Count of the number of rows in the Observation Header table

Each observation has a separate row in the header table

### Confirmed Observations

Count of the number of rows in the Observation Header table which have a value in the field for the confirmation timestamp

### Pct. Confirmed

\(Confirmed Observations divided by Completed Observations\) x 100. Counts and total counts for observation results are the count of rows in the Observation Header table which have the matching result category \(meets standards, required coaching, etc.\)

