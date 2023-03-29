Using Tiled for this project

To make a new level, you can either copy the existing one and use as a template or create a new map.

Creating a new map: Map size should be Fixed (can be changed later), Width 64px, Height 64px
A map should have three layers: Objects (object layer), Terrain (tile layer), and Board (tile layer). It's easier to start with the map size as Infinite and change it to Fixed in Map Properties later.

<<<<<<< Updated upstream
Add tiles for the terrain in the Terrain layer.
=======
## Editing a level
Add tiles for the terrain in the Terrain layer. Then press Map -> Automap to make them look nice.
>>>>>>> Stashed changes

Add tiles for enemy paths in the Board layer. Blue = floor, Red = ceiling, Green = ladder.

Add player, exit, gum, enemies in Objects layer as an object. Each of them should be a Tile Object. All you have to do is add the object and set the name either "Player", "Gum", "Enemy", or "Exit". For enemies, you also have to set their class to "smallrobot" or "mediumrobot".

To add a new type of object, just go to the objects tileset (objects.tsx) and click add tiles. You will need to change the parsing code in LevelModel to support a new object type.

To add the level to the game, just do Export as JSON and put it in the jsons folder for the game, then change the level json value in assets.json. If you added a new object type, you also have to export the tileset as a json and replace objects.json with it in the jsons folder.

Before exporting, make sure the following Map Properties are set in Custom Properties:
- gravity (currently -15)
- numenemies