Author: Tim Sherratt
Date: 7 April 2016

# Creating a map with Google My Maps

## Getting started

You'll need to have a Google account to create and share maps using My Maps.

To open up the My Maps editor you can either:

* go to [Google Maps](https://www.google.com.au/maps/), choose 'My Maps' from the menu, and then click 'Create Map';
* or go to your [Google Drive](https://www.google.com.au/drive/) account and choose 'New > More > Google My Maps'.

Add a point to your new map:

* Click on the marker icon (the cursor will change from a hand to crosshairs)
* Click anywhere on the map.
* Add a title and description in the info box. Click save.

Search for a place to add to your map:

* Type a query in the search box to find a place -- try  'University of Canberra'.
* The map will recenter and a marker will appear.
* To add this marker to your map, click 'Add to map'.
* Click on the pencil icon to edit the content of the info box. You can also add a photo by clicking on the camera icon.

Try:

* Draw an area or a line using the polygon tool. What might you use this for?

## Working with layers

Once you've added some points you'll notice that they appear in the left-hand side menu box under 'Untitled layer'. A layer is a way of grouping together particular features. A single map might have multiple layers.

Try:

* Untick the box next to 'Untitled layer'. What happens?
* Tick the box to make the layer visible again.

## Adding a new layer

We're now going to import some external data to populate a new layer.

* Our dataset is a list of bus stops in Canberra -- [download the CSV file](https://dl.dropbox.com/s/61pwz2g7ako8rxm/Bus_stop_locations_around_the_ACT.csv?dl=0) to your desktop.
* In the My Maps menu box click on 'Add layer'. A new 'Untitled layer' will appear.
* Click on 'Import', then select and upload the CSV file from your desktop.
* You'll then be asked which fields in your file provide spatial data -- the latitude and longitude of the bus stops. 
* Despite its name, both coordinates are included in the `stop_lat` field. To see a sample of the data, click on the question mark after the field name.
* Check the box next to `stop_lat` box. You'll then be asked what the order of the coordinates is -- choose 'Latitude, Longitude'. Click 'Continue'.
* Now choose the field to use as  label for the markers -- choose `stop_name` and click 'Finish'.

You'll now have a map with lots of markers. Examine it carefully -- do you notice anything odd? You'll probably find that large areas of Canberra have no bus stops at all. Why?

Google My Maps lets you add a maximum of 2000 points to any layer. There are more than 2000 bus stops in Canberra so My Maps has truncated the data set without telling you -- beware!

Try:

* My Maps styling abilities are limited, but if you hover over a marker (or set of markers) in the menu box you see a paint bucket. Click on it to open up the style options.

## Sharing maps

Once you've created a map you probably want to share it. In My Maps you can:

* Create a shareable link
* Embed the map in your own website
* Download the map data for use in another program.



