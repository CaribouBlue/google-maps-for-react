# google-maps-for-react

> Highly customizable google maps component for react.

- Try out a live demo of the component [here]()!

## Table of Contents

1. [Usage](#usage)
  1. [Initial Setup](#initial-setup)
  1. [Component API](#component-api)
1. [Team](#team)

## Usage

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

__apiKey__:
- \*REQUIRED
- Type: String
- Description: Your google maps API key
- Example: ```const myApiKey = '123456789' 
<GoogleMap apiKey={myApiKey} />```

## Team

  - __Development Team Members__: 
    - Alec Draymore