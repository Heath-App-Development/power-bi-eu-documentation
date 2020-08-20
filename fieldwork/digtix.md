# DigTix

## Introduction

This report gathers information from DigTix and shows it in one place to make it easier to see historical locating information.

The report is **not** intended to replace DigTix for the day to day management of tickets.  Those tasks should always be done in DigTix.  Due to the way we are getting the data from DigTix, the information in this report will never be real-time.

## Report contents

As of this writing, the report has four visible pages:

* Ticket Summary
* Force To Load
* Performance
* Force To Load Alternate

There are two hidden pages that can be reached by drillthrough:

* Closecode Drillthrough
* Ticket Detail

The charts on these pages will be explained in more detail below.

## Information in the report:

As noted in the introduction, the information in this report is **not** in real-time.  Early every morning DigTix sends us a file that has the information for every ticket that's active as of the time that they generated the file.  On our end we pick up the file, automatically process it, and put the results into a place that the report refreshes from.  The report refresh only happens once a day, at 6:30 a.m. Central time.

