# Research Notes for Custom ABI Tool

### Esri Geo Form:

•	Hosted via ArcGIS Online so it is easy for multiple agencies to work together

•	Control over who can use the form via sharing 

•	Easy to set up—hosted feature service allows for custom schema design. Domain properties allow Geo Form to control user input based on predetermined values

•	Geo Form updates the feature service once submitted so if the same feature service is driving a dashboard, the dashboard will be dynamically updated.

•	Additional coded/picklist values must be added to the database via domain properties so analysts cannot update this on the fly

•	Geo Forms must be tied to a web map service; however, the larger the feature service becomes the slower this may be to load

•	Auto-populating fields and dynamic drop downs may not be available (side note: it appears that esri’s Smart Forms offered via ArcGIS Field Map allows for these type of hierarchal relationships between domain attributes)

•	No built in QA/QC review process; if errors are made inputting the data via Geo Form there is not a quick way to modify an entry. An entire record will need to be deleted from the database manually on the backend (work arounds found via GitHub require widgets not available to us and/or require another manual push from offline editing tools powered by JS)

o	https://github.com/Esri/geoform-template-js/issues/156

o	https://community.esri.com/t5/arcgis-online-questions/geoforms/td-p/266206

o	https://github.com/Esri/geoform-template-js


### Excel User Form

•	Easy to create dynamic drop downs and auto-populate fields which cuts down on analysts data entry time and fat-finger errors

•	Can allow user to add new options to comboboxes by connecting an additional user form that allows them to input new information to the lookup tables

•	If an error is made it is really easy to delete a record or manually modify the issue in the data table (ex: type in the wrong time, can just go into the data table and type in the correct time without needing to do an entirely new submit)

•	Changes made within the data tables can dynamically update a hosted Tableau Dashboard

•	Multiple users cannot use the same excel xlms at the same time

•	Size limitations will likely quickly become an issue with the data tables

•	No easy way to “host” the user form


### Main Takeaway:

•	It appears that the capabilities that Geo Form provides us address the limitations of using Excel; however, the flexibility that Excel provides us is not available when using Geo Form. The fact that there is no easy way to edit existing data entries made with Geo Form makes it hard to consider this as a viable option. Excel is also not a realistic, long-term option for multiple users populating data in a single location. Since multiple users cannot use the same xlms at the same time, local copies will need to be saved. There is no easy way to ensure everyone is working with the most up-to-date version.

•	Proposed Solution: Explore blending the benefits of the two technologies via custom ArcMap/Pro tools (using Model Builder). Allow analysts to collect daily observations with the Excel User Form, and make any necessary edits to the data table, import new observations into .gdb in Arc, run script to update the hosted feature service. The main issue with this approach is that access to Arc will be required. If an analyst collecting observations does not have arc installed on their machine they will need a different way to share their excel doc and someone with arc will need to upload it for them. Some additional entry checks will likely need to be implemented to ensure attribute names and picklist information hasn’t been accidently modified. In order to provide analysts the flexibility to enter new information, the control that domain coded values provides will not be possible (side note: explore a QA/QC process in Excel to catch any of these potential issues prior to launching Arc).

•	It is important to note that Tableau does not currently allow us to work with WFS, only WMS. This is problematic for creating truly dynamic dashboards in Tableau. If we want to use Tableau the data will need to be ingested into Tableau some other way. Esri does provide Dashboard capabilities, but the suite of COTS tools is not as robust as Tableau (Insights may address some of these concerns).

•	We could explore storing data in a postgres database vice a hosted feature service but this would require requesting additional support and potentially limit control on customization.


### Next Steps:
•	Creating Hosted Feature Services in ArcPro

•	Creating Dashboards in ArcPro

•	How to use esri Insights
