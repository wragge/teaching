# Getting started with CartoDB

[CartoDB](https://cartodb.com/) is a powerful web-based platform for managing and visualising geospatial data. In this exercise we'll import some data into CartoDB and look at the ways we can represent that data on a map.

## Requirements

* A free CartoDB account

## Uploading data

For this exercise we'll be working with a CSV file containing data about [bicycle accidents in Canberra](https://www.dropbox.com/s/nf7qtckth8blhen/Cyclist_Crashes.csv?dl=0). Download the file to your computer and save it somewhere convenient. Now we'll upload the CSV file to CartoDB.

* Login in to CartDB and select 'Your datasets' from the dropdown at the top of the page.
* Click on the 'New dataset' button.
* Click on 'Browse' to find the file on your computer.
* Once the file is selected, click on the 'Connect dataset' button.
* CartoDB will import the data. When it's finished you'll see the results in the 'Data view' -- which looks pretty much like a regular spreadsheet.

Some things to note:

* Two columns have been added to the original dataset -- `cartodb_id` and `the_geom`. The first is pretty obvious, but `the_geom` is where CartoDB puts the information it needs to display your data on a map.
* CartoDB has already found the latitude and longitude columns in our data and used them to populate `the_geom`. But if it hadn't, you could click on the little orange 'Geo' button to tell it where the spatial data is, or to geocode an address field.

## Making your first map

With the data uploaded, and the geospatial data identified, it's easy to view the data on a variety of different maps.

* On the 'Data view' page click 'Map view'.
* Yep, that's all you need to do -- CartoDB will open up a map of Canberra and add a little orange dot for every cycle accident.

### Editing the infowindows

If you click on one of the orange dots you'll see the popup 'infowindow' is empty. Let's fix that.

* Click on the message icon in the toolbar on the right-hand side of the screen. This opens up the 'infowindow' configuration options.
* Note there are two tabs -- click and hover -- to control what happens when you interact with the map.
* On the 'Click' tab, move the slider to select `reported_location`. Click on one of the markers and see what's changed.
* Add some other fields, such as `severity` and `crash_type`. What happens if you uncheck the 'Title' box?
* Click and drag fields to change the order in which they're displayed.

Try:

* Use the select box near the top of the tab to change the colour of the header.
* Click the edit icon to change the field labels.
* If you understand HTML, click on the code icon to directly edit the infowindow HTML.
* Switch to the 'Hover' tab and change what happens when you move your mouse over a marker.

### Filtering data

But what if you don't want to see all the data at once -- filtering to the rescue!

* Click the histogram icon on the toolbar to open the filters tab.
* From the dropdown box choose the `severity` field.
* The values and counts for this field are displayed. Click on 'Property damage only' to remove those markers from the map. Do the same for `injury`. Now the map only displays fatal accidents.
* To quickly remove all your filters, click on 'clear view' in the bar above the map.

Try:

* When you create a filter you're building a query for the underlying database. While you have a filter applied, click on the 'SQL' icon to see the query. You can edit the SQL directly to change your query.

## Other types of maps

CartoDB has predefined styles for different types of maps. Just click on the paintbrush icon to open the map 'wizards'.

### Choropleth

A choropleth map uses colour to represent the size of a numeric value associated with each point.

* From the 'wizards' tab select 'choropleth'.
* The 'Column' value tells CartoDB which field to use to generate the colours -- it has be a field with a numeric value.
* Select `cyclist_casualities`.
* The 'Bucket' field determines the number of gradations to have in the data. Choose 3.
* What can you see on the map now?
* Obviously most accidents resulted in a single casualty, but a couple were more serious -- can you find them?

Try:

* Fiddle with some of the other settings.
* What happens when you change the 'Quantification' and 'Bucket' settings?
* What does 'Composite operation' do?

### Category

A category map assigns colours to markers according to the value of a selected field.

* From the 'wizards' tab select 'category'.
* The 'Column' value determines which field will be used as the source of the categories. Obviously it will work best if the field has a limited and consistent set of values!
* Select `crash_type` from the Column list.

### Heatmap

A heatmap groups markers together to give an overall picture of intensity.

* From the 'wizards' tab select 'heatmap'.
* Where are the hot spots?

### Intensity

Like the heatmap, the intensity map gives an indication of hot spots, but while keeping individual markers.

* From the 'wizards' tab select 'intensity'.
* Zoom in on one of the red dots -- what happens to it?

### Torque

The torque map adds a temporal dimension to your map, enabling you to see changes over time.

Before we create a torque map using this data we need to make some changes to the fields.

* Click on 'Data view' to go back to the table.
* Look for the column called `crash_date`. You'll notice that underneath the title is the word 'string'. This means that when CartoDB imported this field it didn't recognise it as a date. We can change this.
* Click on the down arrow next to the `crash_type` heading. Choose 'Change data type...'.
* Select 'Date' and confirm the change.
* That's it! You'll see the values in the column have changed into a standard date format. Now we can use this field in out torque map.

Now we have a date field let's make the torque map. Switch back to 'Map view'.

* From the 'wizards' tab select 'torque'.
* Select `crash_date` from the 'Time column' dropdown. The animation will automatically start playing.
* Click the pause button to stop the animation. Drag the slider to change the date.
* Switch on 'Cumulative' and start the animation playing again. What happens now?

Try:

* You can also add a time-based animation to heatmaps. Choose 'heatmap' and then check 'Animated'. Set the 'Time column' to 'crash_date'.


