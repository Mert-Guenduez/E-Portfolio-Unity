# Tutorial - 2D Jump n' Run

## 1. Create the Project
Open Unity Hub, go to "Projects" and click on "New". Give your project a name, select the Template "2D" and click on Next. The editor will now open.

## 2. Asset Store 
Click on "Window" on the top, and then on "Asset Store", search for "Sunnyland", then download and import it

## 3. Add a Background
In the project view, go to Sunnyland -> artwork -> Environment and drag the Background "back" into the Scene view. Since it is only 384x240 pixels you can scroll in a bit.

## 4. Add a Tilemap
In the hierarchy view, right click and select -> 2D Object -> Tilemap. This will lay a Grid over our Scene. To scale the grid properly with the resolution of our pictures, select it, and insert "0.1" for the Scale values X and Y of the Transform component in the Inspector view (right). 
We need to add a Palette to this tilemap: Go to "Window" -> "2D Objects" -> "Tile Palette".
In the new Window that opens, click on "Create New Palette", give it a name and click on "Create". In the explorer window that opens up you can just select the folder you're already in.
In the Environments Folder you will see "tileset-sliced". You can drag that into the Tile Palette Window. Now you can click on the paintbrush, select a tile in the Tile Palette and start creating your level by clicking on the boxes in your grid!
The tiles will not fill out each grid unity. To change this, select the tileset-sliced in the Environment folder, and edit the "Pixels Per Unit" setting to 16, then reimport the tiles.

## 5. Add an Item
In the Project view,
