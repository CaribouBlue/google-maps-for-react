# google-maps-for-react

> The simplest customizable google maps component for react.

- Try out a live demo of the component [here](https://google-maps-for-react.herokuapp.com)

- The NPM page can be found [here](https://www.npmjs.com/package/google-maps-for-react)

- The GitHub page can be found [here]https://github.com/CaribouBlue/google-maps-for-react)

## Table of Contents

1. [Usage](#usage)
  1. [Initial Setup](#initial-setup)
  1. [Component API](#component-api)
1. [Team](#team)

## Usage

### Install Module

run ```npm install google-maps-for-react --save``` in console while in root directory to add the component to your library.

### Initial Setup

This component makes use of multiple google APIs. In order to use this component you will need a google API key. If you are unfamilar with how to do this, follow this guide to create one [Creating a Google API Console project and client ID](https://developers.google.com/identity/sign-in/web/devconsole-project).

Once you have a key, you will need to enable the following APIs:

  - Google Maps JavaScript API
  - Google Places API Web Service
  - Google Maps Geocoding API
  - Google Maps Geolocation API

This can be done in the "Library" tab.

Load this script into your index.html (Don't forget to replace YOU_API_KEY):
```
<script 
  src="https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY"
></script>
```

Import the component using ```import GoogleMap from 'google-maps-for-react;'```.

### Component API

The ```<GoogleMap />``` component can be customized by passing in a variety of properties. However, only one is required: ```apiKey```. References to this and all other properties follow.

Example: 
```
<GoogleMap
  apiKey={'abcd12345...'}    
  center={ lat: -25.363, lng: 131.044 }                   
  zoom={null}                     
  markers={exampleMarkers}               
  dimensions={null}               
  containerStyle={exampleContainerStyle} 
  containerClassName={null}         
  mapStyle={exampleMapStyle}                   
  mapClassName={null}               
  onIdle={null}   
/>
```

__apiKey__:
- \*REQUIRED
- Description: Your google maps API key
- Type: String

__center__:
- Description: The point the map will center on. Will pan the map view to when updated.
- Default: ```{ lat: -25.363, lng: 131.044 }```
- Type: Object
  - Shape: ```{ lat: Number, lng: Number }```
- Alt Type: String
  - Examples: 'New York City' 'Eiffel Tower'
  - NOTE: When a string is passed, Google API will be used to determine the coordinates of the location. This is less efficient than coordinates, but is provided for convenience.

__zoom__:
- Description: The zoom of the map view. Will zoom map view when updated. 
- Default: ```3```
- Type: Number
  - Range: 1 - 20
    - 1: World
    - 5: Landmass/continent
    - 10: City
    - 15: Streets
    - 20: Buildings

__markers__:
- Description: An array of the markers you wish to place on the map. Can be updated dynamically.
- Default: ```[]```
- Type: Array[ Marker Objects ]
  - See [More API Details](#more-api-details) below for more about Marker Objects.

__dimensions__:
- Description: Defines the height and width properties of the map view. 
- Default: ```[ '500px', '500px' ]```
- Type: Array[String (width of map), String (height of map)]
- \*Note: will be overwritten by mapStyle OR mapClassName.

__mapStyle__:
- Description: CSS styles for the map view.
- Type: Object
  - Shape: ```{ String (style name): String (style value), .... }```

__mapClassName__:
- Description: CSS class name for the map view.
- Type: String

__containerStyle__:
- Description: CSS styles for the div parent of the map view.
- Type: Object
  - Shape: ```{ String (style name): String (style value), .... }```

__containerClassName__:
- Description: CSS class name for the div parent of the map view.
- Type: String

__onIdle__:
- Description: Pass in a function to be triggered when the map is idle (not panning or zooming). 
- Type: Function
  - Params: (map, markers)
    - map:
      - Type: Google Maps Map Object
    - markers:
      - Type: Array[Google Maps Marker Objects]
- Hint: can be used to determine all the markers currently visible in the map view. Click to learn more about [Google Maps Map Object](https://developers.google.com/maps/documentation/javascript/3.exp/reference#Map) or [Google Maps Marker Object](https://developers.google.com/maps/documentation/javascript/3.exp/reference#Marker).

### More API Details

__Marker Objects__:
- Description: The data used to build markers to be placed on the map view.
- Type: Object
  - Shape: 
```
{
  position: 'Australia',       
    // Cord Obj; or Address String
  label: '',           
    // String
  title: '',          
    // String
  animation: 'drop',  
    // String = 'drop', 'bounce'; or null
  onClick: () => {},  
    // Function
}
```
  - __position__:
    - Description: Location the marker should be placed
    - Type: Object
      - Shape: ```{ lat: Number, lng: Number }```
    - Alt Type: String
      - Examples: 'New York City' 'Eiffel Tower'
      - NOTE: When a string is passed, Google API will be used to determine the coordinates of the location. This is less efficient than coordinates, but is provided for convenience.
  - __label__:
    - Description: The string to be displayed on the map view to label the marker
    - Type: String
  - __title__:
    - Description: The title of the marker, this will not be displayed but can be used to identify the marker or store other types of data about the marker
  - __animation__:
    - Description: How the marker should be rendered onto the map
    - Default: No animation
    - Type: String
      - Options: ``'drop'`` OR ``'bounce'``
  - __onCLick__:
    - Description: Function triggered when the marker is clicked on
    - Type: Function
      - Params: none

## Team

  - __Development Team Members__: 
    - Alec Draymore