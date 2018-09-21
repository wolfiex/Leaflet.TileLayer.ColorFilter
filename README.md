# Leaflet.TileLayerColorize
A simple and lightweight Leaflet plugin to apply CSS filters on map tiles.

![alt text](https://github.com/xtk93x/Leaflet.TileLayerColorize/blob/master/samples/sidebyside.png)

## Demo
- [Leaflet.TileLayerColorize Demo](https://xtk93x.github.io/Leaflet.TileLayerColorize/)

# Basic Usage
```js
var map = L.map('map').setView([51.505, -0.09], 14);
    
var colorSettings = {
    blur: '0px',     
    brightness: '100%',
    contrast: '100%',
    grayscale: '0%',
    hue: '0deg',
    opacity: '100%',
    invert: '0%',
    saturate: '100%',
    sepia: '0%'
}

L.tileLayerColorize('https://maps.wikimedia.org/osm-intl/{z}/{x}/{y}.png', {
    attribution: '<a href="https://wikimediafoundation.org/wiki/Maps_Terms_of_Use">Wikimedia</a>',
    colorize: colorSettings
}).addTo(map);
```
    
# Reference

#### L.tileLayerColorize(url, options)

The only difference between L.tileLayerColorize and the original L.tileLayer is the new option `colorize` inside `options` parameter. 

`colorize` accepts an object with the following attributes:
 - **blur**: applies a Gaussian blur filtering measured in pixels, e.g., `{ blur: '2px' }`. Default: `'0px'`.
 - **brightness**: controls the brightness of tile image, e.g., `{ brightness: '150%' }`. Default `100%`.
 - **contrast**: changes the color contrast of tiles, e.g., `{ contrast: '120%' }`. Default `100%`.
 - **grayscale**: changes the color of tiles to a grayscale, e.g., `{ grayscale: '100%' }`. Default `0%`.
 - **hue**: applies a hue rotation in degrees on tile colors, e.g., `{ hue: '30deg' }`. Default `0deg`.
 - **opacity**: defines the opacity of the tiles, e.g., `{ opacity: '90%' }`. Default `100%`.
 - **invert**: invert the tile colors, e.g., `{ invert: '100%' }`. Default `0%`.
 - **saturate**: saturates the tile colors, e.g., `{ saturate: '130%' }`. Default `100%`.
 - **sepia**: converts the tile colors to sepia, e.g., `{ sepia: '100%' }`. Default `0%`.
 
# Useful Tips

This plugin is very useful to easily make dark map layers. 

**The following settings is enough to make most of the light maps to become dark:**

```js
var colorSettings = {
    grayscale: '100%',
    invert: '100%',
    }
```
![alt text](https://github.com/xtk93x/Leaflet.TileLayerColorize/blob/master/samples/dark.png)

**To keep water and street colors, a hue rotation around 180deg is very helpful to correct the color invertion:**

```js
var colorSettings = {
    hue: '180deg',
    invert: '100%',
}
```
![alt text](https://github.com/xtk93x/Leaflet.TileLayerColorize/blob/master/samples/dark-colorized.png)
    
**Light maps may also look good:**

```js
var colorSettings = {
    brightness: '110%',
    hue: '90deg',
    saturate: '120%',
}
```
![alt text](https://github.com/xtk93x/Leaflet.TileLayerColorize/blob/master/samples/colorized.png)



# Changelog

## 2018.09.20
- Plugin created
