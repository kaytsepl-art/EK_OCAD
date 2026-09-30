# Outdoor CAD functional specification

## Data model
- Project: id, name, units, drawingScale, origin, northAngle, sourcePlan, layers, zones, objects, dimensions, annotations, plugins.
- AccessoryDefinition: id, name, category, source image, width, depth, height, insertion point, default layer.
- SceneObject: id, definitionId, custom name, world position, rotation, scale, layer, metadata.
- Zone: closed 2D polygon, layer, material, elevation and optional extrusion height.
- Dimension: type, reference points, measured value, unit, style and associative references.
- Annotation: text, leader, tag, position, rotation and linked object.
- PluginManifest: id, name, version, type, permissions, settings schema and enabled state.

## 2D to 3D workflow
1. Import PNG/JPG/WebP as a source underlay.
2. Calibrate scale using a known distance.
3. Set origin, north direction, measurement unit and drawing scale.
4. Trace site boundary, paths, planting areas and facilities as closed polygons.
5. Assign CAD-style layers, materials, elevations and slopes.
6. Add real-photo or custom-image accessories and enter true dimensions.
7. Generate ground faces and image-plane 3D accessories, then review position and height.
8. Run validation plugins, inspect VR-style preview and export GLB/OBJ.

## Drag-and-drop accessory operation
1. Choose a category in the left library.
2. Drag a photo card into the 2D plan; a snap plugin aligns it to the configured grid.
3. The new instance receives an automatic sequence name.
4. Select it and edit the custom name, layer, X/Y, rotation and scale.
5. Upload a custom image and dimensions to create a reusable accessory definition.
6. The 3D view represents accessories as textured planes, not placeholder cubes.

## Layer, dimension and annotation UI
- Layer panel: visibility, color, lock state and object assignment.
- Status toolbar: drawing scale, unit and snap distance.
- Dimension tool: linear dimensions with unit-aware text.
- Annotation tool: free text labels for equipment, zones and notes.
- Property panel: custom name, layer, coordinates, angle and scale.
