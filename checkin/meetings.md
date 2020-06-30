# Meetings

## Data source

CheckIn Sharepoint lists

Data from the CheckIn app populates the SharePoint lists

The data from when the data was kept in a SQL database has been moved into the lists

## Calculations

### Total Meetings

Count of rows in Events table

### Total Invitees

Count of names in the Required Attendees column for each row in the Events table

### Total Attendees

Count of rows in the Event CheckIn table which have a timestamp in the Attendee CheckIn Time column

### Pct. Attendance

\(Total Attendees divided by Total Invitees\) x 100

