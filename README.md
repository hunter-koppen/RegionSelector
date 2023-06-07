## Region Selector
This is a module to help create functionality where you can select regions on a visual map. For example to select municipalities where an organization is active.

## Features
- Load regions on a map to be (de)selected
- Example implementation for all dutch municipalities
- Included data for dutch provinces and zipcodes aswell, all come with an easy generate button

## Usage
1. Add a Google Maps API key to the GoogleAPIKey constant.
2. Setup the needed userroles for the module
3. Add the SNIP_RegionData snippet to a backend page
4. Add the SNIP_MapView snippet to a frontend page
5. Run the app, navigate to the regiondata page created in step 3, click on the generate button on each tab (start with province, then municipality and then zipcodes).
6. Navigate to the front-end page and check if it works, after (de)selected the correct data you can use the Apply Changes button to save the selecting.

## Customization
*In case of reusing the dutch municipalities data*
The module comes with an example entity ("ExampleOrganization"). This is just to show you how the data can be setup so that you can attach the selected municipalities and provinces to some other data. This is because when you return to the page you ofcourse want to see what was selected previously. If you want to setup your own associated data you can simply replace the ExampleOrganization entity with your own entity and then update the SNIP_MapView to receive an object of your newly chosen entity. Ofcourse also update all the places that were using the associations "ExampleOrganization_Province" and "ExampleOrganization_Municipality".

*In case of trying to setup your own regiondata*
If you wish to setup your own regiondata the module will require quite some updates but can be used as a good example. To show other regions to be selected on the map you will have to populate an entity with a generalization of MapObject and fill the Coordinates attribute correctly so that the widget can calculate all the polygons.
Its important to note here that the widget currently does not support multipolygons or holes in a polygon. Also the required format is as follows: [[lat1,long1],[lat2,long2],[lat3,long3],[..]] in a long string.

An important tip for using your own coordinate data is to shrink the data by alot before importing it. For selecting regions you usually just need a decent shape. You can use the following online tool to shrink your data and potentionally massively improve the speed: https://mapshaper.org/
Simply upload a geojson file, click import and then use the simplify feature (top right corner) to shrink the data, in most cases setting it between 5% to 0.8% is perfect for maintaining the shape with the least amount of data.

## Future ideas
- Add support for multi-polygons polygons.

## Issues, suggestions and feature requests
https://github.com/hunter-koppen/RegionSelector/issues