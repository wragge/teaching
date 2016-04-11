# Cleaning data: splitting coordinate values in Google Sheets

## The problem

You've got a CSV file containing geolocated place data that you want to import into  mapping program, but the coordinates are combined in a single column. How can you separate the latitude and longitude into separate columns?

## The solution

### Splitting the data

Here's a CSV file plotting locations of bus stops in Canberra. If you open it up you'll see that the `stop_lat` field actually contains both the latitude and longitude. Let's split them into separate columns.

* Upload your CSV file to Google Drive and open it in Sheets.
* Hover over the `stop_lat` column header (Column E in this example) and click on the down arrow. Choose 'Insert 1 right' to add a new empty column.
* Repeat the step above so there are two empty columns ready to hold the latitude and longitude.
* Find the first row containing data (Row 2 in this example) and select the first empty cell next to the `stop_lat` field. In this example it would be cell F2.
* In the function box type `=SPLIT(E2, ", ")`. Hit enter. Magic! The contents of E2 have been split between F2 and G2.
* What just happened? the `SPLIT` function takes two parameters: the thing you want to split into parts, and a delimiter (a combination of characters) that tell the function where the split should take place. In this example, we're splitting the text in E2 using ", " (comma and space) as the delimiter.
* What about all the other rows? Just select the cell where you created the function (F2 in this example) and double-click on the little blue square in the bottom right-hand corner. The function will be repeated for every row with data.

### Cleaning up

All that's left is to remove the brackets from our new columns. First we have to replace the formulas in our new columns with their calculated values.

* Select the two new columns (F2 and G2 in this example), click on the down arrow in the column header and choose 'Copy'.
* With the columns still selected, click on the down arrow again and choose 'Paste special > Paste values only'.
* Now we can get rid of the brackets. Select the first column and choose 'Edit > Find & replace' from the menu. Enter `(` in the 'Find' box and click 'Replace all'.
* Repeat for the other column to remove all the `)`.
