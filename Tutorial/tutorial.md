# Tutorial - 2D Jump n' Run

## 1. Create the Project
Open Unity Hub, go to "Projects" and click on "New". Give your project a name, select the Template "2D" and click on Next. The editor will now open.

## 2. Asset Store 
Click on "Window" on the top, and then on "Asset Store", search for "Sunnyland", then download and import it

## 3. Add a Background
In the project view, go to Sunnyland -> artwork -> Environment and drag the Background "back" into the Scene view. Since it is only 384x240 pixels you can expand it by dragging it on the corners. Select the background in the Scene view, click on Sorting Layer and add a new Sorting layer called Background. Drag the background layer to the very top and add it to your background.

## 4. Add a Tilemap
In the hierarchy view, right click and select -> 2D Object -> Tilemap. This will lay a Grid over our Scene. To scale the grid properly with the resolution of our pictures, select it, and insert "5" (since we have small pictures) for the Scale values X and Y of the Transform component in the Inspector view (right). 
We need to add a Palette to this tilemap: Go to "Window" -> "2D Objects" -> "Tile Palette".
In the new Window that opens, click on "Create New Palette", give it a name and click on "Create". In the explorer window that opens up you can just select the folder you're already in.
In the Environments Folder you will see "tileset-sliced". You can drag that into the Tile Palette Window. Now you can click on the paintbrush, select a tile in the Tile Palette and start creating your level by clicking on the boxes in your grid!
The tiles will not fill out each grid unity. To change this, select the tileset-sliced in the Environment folder, and edit the "Pixels Per Unit" setting to 16, then reimport the tiles.

## 5. Add an Item
In the Project view, go to SunnyLand -> artwork -> Sprites -> Items -> Cherry. You will find 7 different pictures of cherries, which make up an animation together. Select all of them at the same time (to select all, select the first, then select the last with Shift+click), then drag it into the scene view. In the explorer that shows up, name your animation cherry.anim and save it. Place your cherry whereever you want, and click on the play button. In the Game view you can now see that the cherry has an animation. Don't forget to go out of the game view by pressing the button again before continuing.

## 6. Add physics

Select the cherry and click on "Add Component" -> "Physics 2D" -> "Box Collider 2D". Then add another component "Physics 2D" -> "Rigidbody 2D".
Next, select the Tilemap and click on "Add Component" -> "Tilemap" -> "Tilemap Collider 2D".
You can now see that the cherry will fall down and land on the ground.
You can adjust the cherries hitbox by selecting it and clicking on the "Edit Collider" button.

## 7. Add the character
