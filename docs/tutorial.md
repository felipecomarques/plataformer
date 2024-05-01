# [Tutorial](https://youtu.be/LOhfqjmasi0?si=b-JzT8TjEheRDmNP)

## How godot works

To do anything in Godot, we use Nodes. Nodes are the fundamental building blocks of your games. The nodes can be:

- Images and sprites;
- Music and sounds;
- Add physics;
- etc...

Building a game in Godot is combining nodes for some result. But doing this could becomes confusing, so you can combine nodes in a scenes, and reuse the scene in somewhere else. A scene could be a player, weapon, menu, an entire level, etc. 

## Creating the player 1.0

We will need to create a root node. In the left, we will choose `2D Scene` type and rename it to 'game'. Save it with `Ctrl + S` inside the scenes folder. Run the game with the play icon or `F5`, and Godot will tell that there's no main scene. We will chose the current and run the project

### Creating a player

Create a new scene clicking the `+` sign above the current scene. Now, we will click the `+` sign on the left and add a `CharacterBody2D` for physics. Add a new node with `Ctrl + A` and add `AnimatedSprite2D` for a sprite with multiple frames.

#### **Adding animation to the player**

Click in the `AnimatedSprite2D`, and then on the right tab, click on 'Animation' and on 'Sprite Frames'. On the bottom of the screen, a new section will appear, and now click on 'Add frames from sprite sheet' (or `Ctrl + Shift + O`) and select the character sprite sheet. We will increase the grid from 4x4 to 8x8. Now, we will click in all frames of the animation (in this case, all 4 idle animations) and click on add frames. 

Godot will try to apply a filter to the pixel art. So we need to go on `Project > Project Settings`, and go in `Rendering > Textures > Default Texture Filter` and change to nearest. We can play the animation in the play button in the animation menu. We will increase the FPS to make the animation quicker. We will rename the animation name from 'default' to 'idle' and enable 'autoplay on load'.

#### **Adding a shape to the CharacterBody2D**

There will be a warning in the `CharacterBody2D`. That's because we didn't add a shape for the collision. We add a new node called `CollisionShape2D`, and in the right menu we will add a circle shape.

We will rename the top node to 'Player' and save the scene. After that, we will return to the main scene and drag the player there. After that, we will add a `camera2D` node and increase the zoom from '1' to '4'.

#### **Adding movement**

We will open the player scene again, click in the root node and add a new script. We will add a 'basic movement' template for the player (and make sure the script is in the 'scripts' folder). If you try running the game, the player will immediately fall. In the game scene, we will add a collision on the ground with a new node called `StaticNode2D`. It will need a collision shape, and we will add with `CollisionShape2D` and add the 'NewWorldBoundaryShape2D'. This shape will extend infinitely.

The jump is too high and the player is too fast. We can change that in the script