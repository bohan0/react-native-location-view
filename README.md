# react-native-location-view

Simple location picker with maps and Google Places API support.

This fork initially added countryCode restriction for autocomplete results, language and onCancel props (along with a close button on top left to match). Also improved the Google API calls to reduce costs (via sessionToken and only requesting the fields required).

Please note that you need to install `react-native-uuid` and `buffer` npm packages.

This fork intends to (in progress) to add support for use of ArcGIS Suggest API for addresses autocomplete (at the moment completely free), which is much more affordable than Google Maps API Places Autocomplete. Also intend use ArcGIS for address details/coordinates extraction as well (at least 90% more affordable than Google Places Details API as of 2019)

### Preview

![](https://github.com/superapp/react-native-location-view/blob/master/screenrecording/screengrab.gif?raw=true)

### Installation

Download an install the library

```npm install react-native-location-view --save```

Or if you are using yarn

```yarn add react-native-location-view```

This library depends upon 2 other native libraries

1. [react-native-maps](https://github.com/react-community/react-native-maps)
2. [react-native-vector-icons](https://github.com/oblador/react-native-vector-icons)

Make sure to install these before you install react-native-location-view

For Google Places API go to [this](https://developers.google.com/places/documentation/) page and enable "Google Places API Web Service" (NOT Android or iOS) in the console.

### Example

```jsx
import React from 'react';
import LocationView from "react-native-location-view";
import {View} from "react-native";


export default class SelectLocationScreen extends React.Component {
  state = {

  };

  render() {
    return(
      <View style={{flex: 1}}>
        <LocationView
          apiKey={"MY_GOOGLE_API_KEY"}
          initialLocation={{
            latitude: 37.78825,
            longitude: -122.4324,
          }}
        />
      </View>
    );
  }
}
```

### Supported Props

| Prop | Type | Required | 
| ---- | ---- | -------- |
| apiKey | string | Yes |
| initialLocation | object | Yes |
| markerColor | string | No |
| actionButtonStyle | object (style) | No |
| actionTextStyle | object (style) | No
| actionText | string | No |
| onLocationSelect | function | No |
| debounceDuration | number | No |
