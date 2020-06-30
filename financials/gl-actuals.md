# GL Actuals

## Notes for this report page

{% hint style="danger" %}
Before interacting with any visuals on this page, please read the following:

Due to miscoded entries in the GL reports, a custom table was made to connect the payroll information with the GL information.

This means that depending on which context the financials are looked at on this page you will see information in either a department context or project context. Any slicers or filters that you choose will affect what you see just like they always do, but in this case it can be very useful to see miscoded values.

To make the table, the department code and project code were combined to make a composite code. It’s simply the department code, a period, and the project code \(e.g. 25.1065RGE\). In the payroll data, it’s the department code and the project code as reported to TriNet through the payroll app. From the financials, it uses the department code and project code as read from the GL account code as explained below in the calculations section.
{% endhint %}

The connecting table is made from the unique composite codes from each table, so each possible composite code is represented once. This is maintained automatically because the composite codes from each table are handled in the report script and the connecting table is re-calculated every time the report refreshes. The composite codes are not visible in the report, they act in the background as a way to tie the tables together. All you will see in the report are the department codes and project codes like you normally would.

The end result is two different contexts for the information that you see in the charts, especially the matrix visual at the bottom that has the GL detail information.

There is a department context and a project context.

**Department context**: If no slicers are selected OR a department slicer is selected, the visuals on this page will show all payroll and GL info that have the selected department in the composite code. This means that you might see info for projects that are not in your region, even if the amount of hours or dollars is zero.

**Project Context**: If no department slicer is picked AND at least one project slicer is picked, the visuals on this page will show all payroll and GL info for the projects you’ve picked that have the selected project codes in the composite code. This means that you will see all the different departments that are not normally associated with the projects you’ve picked.

## Data source

GL Detail flat files \(.csv\) exported by Accounting from Epicor

Moved to cloud storage

## Matrix visual drilldown order

1. Department/RegionProject Code
2. FY
3. FY and Period \(e.g. 2019-04\)
4. Account Description \(e.g. Airfare, Meals, Hotels, Depreciation Vehicles, etc.\)
5. GL Account Code \(e.g. 01.01.0000.92251\)
6. Journal Entry Description \(e.g. JE104 - Reclass Capital Lease - PD07\)

## GL Account breakdown

Use  **01.25.1200.50505.1065RGE** as an example

* 01 - Company Code
* 25 - Department \(Region for SBU Field\) Code
* 1200 - Line of Business Code
* 50505 - Account Code
* 1065RGE - Project Code

## Calculations

### Revenue

Sum of all amounts where Account Code is between 40000 and 49999.

### Oper. Exp. \(Operating Expense\)

Sum of all amounts where Account Code is NOT between 40000 and 49999 minus Admin Exp. minus Non-Oper. Exp.

### Gross Margin

Revenue - Oper. Exp.

### Gross Margin Pct.

\(Gross Margin divided by Revenue\) x 100.

### Admin Exp.

Sum of all amounts where Line of Business Code is 0000 and the Account Code is between 60000 and 89999.

### Non-Oper. Exp.

Sum of all amounts where Account Code is between 90000 and 99999.

### Contribution

Revenue minus Oper. Exp. minus Admin Exp. minus Non-Oper. Exp.

### Contribution Pct.

\(Contribution divided by Revenue\) x 100.

### Payroll Headcount

Count of unique IDs appearing in the payroll file for the matching time period and project code.

{% hint style="warning" %}
**NOTE: THIS IS DIFFERENT FROM THE HEADCOUNT ON THE TURNOVER REPORT BECAUSE THIS IS SHOWING ONLY THE NUMBER OF PEOPLE WHO WERE PAID, NOT THE NUMBER OF PEOPLE ASSIGNED TO THE PROJECT IN AN ACTIVE OR LOA STATUS IN HCM**.

Remember, this is counting **DIFFERENT** people who have been paid between the start and end dates you have set in the filters and the projects you’ve selected with the slicers. This is why the number is as high as it is.
{% endhint %}

### Total Hours

Sum of all hours regardless of type \(Regular, Overtime, Other\)

### Exp./Hr. \(Gross\)

\(Oper. Exp. divided by Total Hours\)

### Exp./Hr. \(Full\)

\(\(Oper. Exp. minus Admin Exp. minus Non-Oper. Exp.\) divided by Total Hours\) x 100

