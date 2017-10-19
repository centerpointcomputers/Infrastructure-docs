This is a log of recent activity and updates:

##### 10/19/2017

- Filtered the spreadsheet by the Household_ID column, eliminating all but blank records to isolate names that are already part of an existing household.
- Removed all records from the People CSV that are already assigned to a household.  No need to import them again.
- Removed the filter to restore all records that are NOT part of a household.

_Note: The next part is a bit tricky.  People has a specific field to identify which records are part of a specific household.  It appears to be a randomly or sequential number assigned to the Household_ID column (currently column AV [this will change if more custom fields are created])  When importing multiple records, People looks for this column.  If the column is in the import file, it will create a household for each unique ID that it finds.  The unique ID can be anything.  So, using Google Sheets function RANDBETWEEN, the following formula is run on each cell in the column._

```IF(NOT(G2=G1),RANDBETWEEN(900000,1000000),G1)```

Column G is the Last Name column.  This formula looks at the row above it and compares the last names.  If the names match, the result will be the actual last name.  If the names do NOT match, it is assumed that this is a new household and an automatic random number is inserted.

The purpose of this forumula is to easily assign a unique number every time a new last name is encountered.  The spreadsheet must be sorted by Last Name prior to filling the cells in the column with this formula.

##### 10/18/2017

- Analyzed Roll Call data and compared to People database.  Determined best course of action was to simply remove all adults from the Roll Call exported list, and import only the children into People.
- 2nd Step will be to compare adult records in Roll Call against existing People database and import only the adult records that are missing.
- Imported all children's records from Roll Call into Planning Center People.

##### 10/05/2017:  

- Explored companion app called Adjace <http://adjace.com> which synchronizes with People to create a front end church directory.  Free for Administrators, subscription based for congregation access.
- Connected People to Adjace, created background header, uploaded logo.  System is accessible only by Administrators.  Working on understanding what can and cannot be done with it.  

##### 10/04/2017:  

- Exported all People records to CSV format, uploaded to Google Sheets to evaluate the layout.
- Exported 311 records from Roll Call to tab delimited text file.
- Created Google Sheets workbook to begin working on a data migration routine to merge Planning Center People database with Roll Call data.