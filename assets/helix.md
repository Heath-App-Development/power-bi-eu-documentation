# HELIX

## Data source

SharePoint lists containing information from the HELIX app

File exports from Asset Tiger, kept in cloud storage

ADEmployeeHistory table \(Azure SQL database\), populated by a nightly process which captures information from our Active Directory about all active or LOA employees on that day

## Calculations

### Active Employees Today

Number of Rows in the ADEmployeeHistoryToday table

This is a table that recalculates on every refresh based on the current date

It evaluates every row of the ADEmployeeHistory table to check if the DateRecorded field \(the date the process ran\) matches today’s date

The matches become the ADEmployeeHistoryToday table until the next refresh

### Act. Emp. Never Scanned \(Active Employees Today who have never scanned any assets\)

Counts employees who appear in the ADEmployeeHistoryToday table but who do not have any scans at all in the SharePoint list that stores all the inventory scans

### Current Act. Emp. Scan Pct. \(Percentage of active employees who have scanned an asset at any time

\(Active Employees Today - Act. Emp. Never Scanned\)/Active Employees Today x 100

### Act. Emp. No Scans 30 Days

Counts employees who have scanned an asset in the past 30 days

### Items Shipped

Count of rows in the SharePoint list that stores all the shipping scans

### Items Received

Count of rows in the SharePoint list that have a value in the Received On field

### Items In Transit

Count of items that have been shipped but haven’t been checked in as received

