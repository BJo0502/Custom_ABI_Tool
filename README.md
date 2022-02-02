# ArcPro Notes

### Issue:
We want the analysts to be able to add new options to the existing picklists if necessary so they can continue to work through their daily observations. We can accomplish this in Excel; however, in order for these changes to be reflected in the hosted feature service we need to update the new information in the domain properties within the .gdb too. This will need to be one of the first steps completed in the overall workflow or additional tools will not work properly.

### Proposed Solution:
When a user selects the option in Excel to add a new item to a picklist, also output the new values into a new Excel Workbook Sheet. We can import this particular Workbook Sheet into Arc’s Table to Domain Tool to update the .gdb’s existing coded values:

https://desktop.arcgis.com/en/arcmap/latest/tools/data-management-toolbox/table-to-domain.htm

### Question?

Can we use ArcGIS Workflow Manager as a pseudo Geo Form?

https://www.youtube.com/watch?v=aiG8AlGGWzg

