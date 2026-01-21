


# lib_Geocoding_ui_ngx

<iframe style='width:100%; border:none; height:300px' border='0' src='https://www.convertigo.com/addtional-connectors-and-data-sources-for-convertigo-no-code-studio'></iframe>


For more technical informations : [documentation](./project.md)

- [Installation](#installation)
- [Mobile Library](#mobile-library)
    - [Shared Actions](#shared-actions)
        - [getBoundingBoxFromPosition](#getboundingboxfromposition)
        - [getCurrentPosition](#getcurrentposition)
        - [getLocationByLatAndLong](#getlocationbylatandlong)
    - [Shared Components](#shared-components)
        - [geoCoding](#geocoding)


## Installation

1. In your Convertigo Studio click on ![](https://github.com/convertigo/convertigo/blob/develop/eclipse-plugin-studio/icons/studio/project_import.gif?raw=true "Import a project in treeview") to import a project in the treeview
2. In the import wizard

   ![](https://github.com/convertigo/convertigo/blob/develop/eclipse-plugin-studio/tomcat/webapps/convertigo/templates/ftl/project_import_wzd.png?raw=true "Import Project")
   
   paste the text below into the `Project remote URL` field:
   <table>
     <tr><td>Usage</td><td>Click the copy button at the end of the line</td></tr>
     <tr><td>To contribute</td><td>

     ```
     lib_Geocoding_ui_ngx=https://github.com/convertigo/c8oprj-lib-geocoding-ui-ngx.git:branch=8.4.0.0
     ```
     </td></tr>
     <tr><td>To simply use</td><td>

     ```
     lib_Geocoding_ui_ngx=https://github.com/convertigo/c8oprj-lib-geocoding-ui-ngx/archive/8.4.0.0.zip
     ```
     </td></tr>
    </table>
3. Click the `Finish` button. This will automatically import the __lib_Geocoding_ui_ngx__ project


## Mobile Library

Describes the mobile application global properties

### Shared Actions

#### getBoundingBoxFromPosition

**variables**

<table>
<tr>
<th>name</th><th>comment</th>
</tr>
<tr>
<td>latitude</td><td></td>
</tr>
<tr>
<td>longitude</td><td></td>
</tr>
<tr>
<td>margin</td><td></td>
</tr>
</table>

#### getCurrentPosition

**variables**

<table>
<tr>
<th>name</th><th>comment</th>
</tr>
<tr>
<td>enableHighAccuracy</td><td>Is a Boolean that indicates the application would like to receive the best possible results. If true and if the device is able to provide a more accurate position, it will do so. Note that this can result in slower response times or increased power consumption (with a GPS chip on a mobile device for example). On the other hand, if false, the device can take the liberty to save resources by responding more quickly and/or using less power. Default: true.</td>
</tr>
<tr>
<td>maximumAge</td><td>Is a positive long value indicating the maximum age in milliseconds of a possible cached position that is acceptable to return. If set to 0, it means that the device cannot use a cached position and must attempt to retrieve the real current position. If set to Infinity the device must return a cached position regardless of its age. Default: 0.</td>
</tr>
<tr>
<td>timeout</td><td>Is a positive long value representing the maximum length of time (in milliseconds) the device is allowed to take in order to return a position. The default value is Infinity, meaning that getCurrentPosition() won't return until the position is available.</td>
</tr>
</table>

#### getLocationByLatAndLong

**variables**

<table>
<tr>
<th>name</th><th>comment</th>
</tr>
<tr>
<td>Address</td><td></td>
</tr>
<tr>
<td>AdminDivision1</td><td></td>
</tr>
<tr>
<td>AdminDivision2</td><td></td>
</tr>
<tr>
<td>CountryRegion</td><td></td>
</tr>
<tr>
<td>latitude</td><td></td>
</tr>
<tr>
<td>longitude</td><td></td>
</tr>
<tr>
<td>Neighborhood</td><td></td>
</tr>
<tr>
<td>PopulatedPlace</td><td></td>
</tr>
<tr>
<td>Postcode1</td><td></td>
</tr>
</table>

### Shared Components

#### geoCoding

**variables**

<table>
<tr>
<th>name</th><th>comment</th>
</tr>
<tr>
<td>coordinates</td><td></td>
</tr>
<tr>
<td>showAddress</td><td></td>
</tr>
<tr>
<td>showCoordinates</td><td></td>
</tr>
<tr>
<td>showFabButton</td><td></td>
</tr>
<tr>
<td>showFields</td><td></td>
</tr>
<tr>
<td>showMap</td><td></td>
</tr>
<tr>
<td>showMarkers</td><td></td>
</tr>
</table>



