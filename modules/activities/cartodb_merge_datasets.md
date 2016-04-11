# Merging data sources in CartoDB

A common mapping task is to calculate and display the number of points that are located within certain boundaries or regions -- eg the number of public toilets within each postcode region. This is easy to do in CartoDB.

## Loading the datasets

In this exercise we'll be mapping the number of playgrounds in the ACT by administrative district. We'll use two datasets from data.act.gov.au:

* [Town and district playgrounds](https://dl.dropbox.com/s/hfyuybsxcryfaf8/Town_And_District_Playgrounds.csv?dl=0)
* [ACT administrative boundaries](https://dl.dropbox.com/s/lpho1jgznh7261n/ACT%20Administrative%20Boundaries.zip?dl=0)

Download these datasets to your computer and save them somewhere obvious (such as your desktop).

Follow the instructions in the 'Uploading data' section of [Getting started with CartoDB](cartdb_getting_started.md) to load both datasets into CartoDB.

You may notice that when you upload the administrative boundaries to CartoDB you end up with three datasets. That's because there's three levels in the administrative hierarchy of the ACT -- the territory itself, its 20 districts, and its 121 divisions. Each dataset in CartoDB provides the boundaries for one of these administrative levels.

We'll be using the divisions. The easy way to identify it is to look at the number of rows in the dataset. The divisions dataset has 121 rows. Click on the title to open it.

For convenience, let's rename the dataset. Click on the title at the top left of the table and enter a new name, such as 'ACT divisions'. Click save.

Things to notice:

* Look at `the_geom` field in the divisions dataset. Instead of coordinates it says 'Polygon'. The geospatial data in this dataset represents a set of boundaries rather than a single point.
* Click on 'map view' to see the boundaries.
* Open the playgrounds dataset. What sort of spatial data does it contain?

## Merging datasets

* Open the divisions dataset.
* At the bottom right of the table you'll see three icons. Hover over them to see what they do.
* Click on the 'merge datasets' icon.
* You'll see there's a choice between a column join and a spatial join. We're going to do a spatial join -- this means we're going to look for playgrounds whose coordinates locate them within each division. Click 'Spatial join'.
* Now we have to add the playgrounds dataset. Select it from the dropdown list. The fields from the playgrounds dataset will appear.
* We have to tell CartoDB what to do with the points it finds within each region. You'll see three options -- 'sum', 'count', 'avg'. Click 'count'. This will add up the number of playgrounds per division.
* We also have to specify which fields from the divisions dataset we want to appear in the new merged table. Check 'division' in the left hand column, so that we'll have access to the names of each division.
* Click the 'Merge datasets' button. Your new merged dataset will appear!

Things to note:

* The product of our spatial merge is in the `intersect_count` column. This is how many  playgrounds were found within each division.
* Other than `carto_id` and `the_geom` the only other field in the dataset is the `division` label that we selected during the merge process. If you want other fields to be included you have to remember to select them before you merge.

## Mapping playground densities

Now we have a dataset with regions and counts -- time to make a choropleth map!

* Click on 'Map view'.
* Click on the paintbrush icon to open the 'wizards' tab and choose 'choropleth'.
* Make sure that the column value is `intersect_count`.
* We've only got a limited set of values (0 to 3), so change the 'buckets' setting to 5.
* What can you see?
* Click on the 'infowindow' tab to edit the information displayed when you click on a region.
* Check both `division` and `intersect_count`.
* Click on the edit icon to change the labels. Change 'intersect_count' to 'playgrounds'.
* Now you can click on any division and see its name and number of playgrounds.

## Adding the playgrounds 

The choropleth map gives us a quick visual representation of the density of playgrounds across ACT divisions, but what if we want to see more details about individual playgrounds? Let's add another layer to our map:

* Click on 'Add layer'.
* You'll probably get a screen telling you you need to create a map before you can add more layers -- -- just click 'OK'.
* Select the original playgrounds data from the list of datasets and click 'Add layer'.
* Markers will appear on your map for each individual playground. Click on the 'infowindow' tab and select the information you want to be displayed when you click on one of the markers.



