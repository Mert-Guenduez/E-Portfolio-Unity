# Tutorial - 2D Jump n' Run

## 1. Create the Project
Open Unity Hub, go to "Projects" and click on "New". Give your project a name, select the Template "2D" and click on Next. The editor will now open.

## 2. Asset Store 
Click on "Window" on the top, and then on "Asset Store", search for "Sunnyland", then download and import it.
![Asset Store](https://raw.githubusercontent.com/Mert-Guenduez/E-Portfolio-Unity/master/Tutorial/images/AssetStore.PNG)

## 3. Add a Background
In the project view, go to Sunnyland -> artwork -> Environment and drag the Background "back" into the Scene view. 

![Background](https://raw.githubusercontent.com/Mert-Guenduez/E-Portfolio-Unity/master/Tutorial/images/background.PNG)

Since it is only 384x240 pixels you can expand it by dragging it on the corners. 
Then, select the background in the Scene view, click on Sorting Layer and add a new Sorting layer called Background. Drag the background layer to the very top and add it to your background.

## 4. Add a Tilemap
In the hierarchy view, right click and select -> 2D Object -> Tilemap. This will lay a Grid over our Scene. To scale the grid properly with the resolution of our pictures, select it, and insert "5" (since we have small pictures) for the Scale values X and Y of the Transform component in the Inspector view (right). 
We need to add a Palette to this tilemap: Go to "Window" -> "2D Objects" -> "Tile Palette".
In the new Window that opens, click on "Create New Palette", give it a name and click on "Create". In the explorer window that opens up you can just select the folder you're already in.
In the Environments Folder you will see "tileset-sliced". You can drag that into the Tile Palette Window.
It should look like this:

![Tile Palette](https://raw.githubusercontent.com/Mert-Guenduez/E-Portfolio-Unity/master/Tutorial/images/tilemap.PNG)

Now you can click on the paintbrush, select a tile in the Tile Palette and start creating your level by clicking on the boxes in your grid!
The tiles will not fill out each grid unit. To change this, select the tileset-sliced in the Environment folder, and edit the "Pixels Per Unit" setting to 16, then reimport the tiles.

## 5. Add an Item
In the Project view, go to SunnyLand -> artwork -> Sprites -> Items -> Cherry. You will find 7 different pictures of cherries, which make up an animation together. Select all of them at the same time (to select all, select the first, then select the last with Shift+click), then drag it into the scene view. In the explorer that shows up, name your animation cherry.anim and save it. Place your cherry whereever you want, and click on the play button. In the game view you can now see that the cherry has an animation. Don't forget to go out of the game view by pressing the button again before continuing.
As an example, the level I have designed looks like this:
![Level](https://raw.githubusercontent.com/Mert-Guenduez/E-Portfolio-Unity/master/Tutorial/images/Example.PNG)
## 6. Add physics

Select the cherry and click on "Add Component" -> "Physics 2D" -> "Box Collider 2D". Then add another component "Physics 2D" -> "Rigidbody 2D". These will make sure that physics are applied to our cherry, making it fall down and collide.

![Component](https://raw.githubusercontent.com/Mert-Guenduez/E-Portfolio-Unity/master/Tutorial/images/Components.PNG)

Next, select the Tilemap and click on "Add Component" -> "Tilemap" -> "Tilemap Collider 2D". If you dont want certain tiles to collide, you can just select the tile in the project view, and edit the collider type to "None".
You can now see that the cherry will fall down and land on the ground.
Adjust the cherries hitbox by selecting it and clicking on the "Edit Collider" button.

## 7. Add the character
In the project view, go to Sunnyland -> artwork -> Sprites -> player -> idle and add the player (with its animation) to the scene. Additionally, add a Box Collider and Rigidbody component just like you did with the cherries.

Now it is time for the script that we will write. Select "Add Component" -> New Script, and create and add a new script.
Edit the script so it looks like this:
````csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Move2D : MonoBehaviour
{
	public float moveSpeed = 5f;
  // Start is called before the first frame update
  void Start()
  {
      
  }

  // Update is called once per frame
  void Update()
  {
	    Jump();
      Vector3 movement = new Vector3(Input.GetAxis("Horizontal"), 0f, 0f);
	    transform.position += movement * Time.deltaTime * moveSpeed;
  }
	void Jump(){
		if (Input.GetButtonDown("Jump")){
        gameObject.GetComponent<Rigidbody2D>().AddForce(new Vector2(0f, 7f), ForceMode2D.Impulse);
		}
	}
}
````
After that, you can move your character with the keys "A" and "D", and jump with Spacebar.

This is as far as this tutorial goes. what you could do next is implement a main menu, add more movement logic and include a goal in our level, but this would go beyond the scope of a compact and concise live demo. Developing a complete game can, depending on what you want to do, take a very, very long time!
