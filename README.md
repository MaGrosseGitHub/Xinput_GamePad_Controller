# Xinput GamePad Controller (v2.5)

Slightly better version of the xinput implementation for unity based on the amazing work done by speps (https://github.com/speps/XInputDotNet), allows to control four gamepads with a very simple to use API and easily map computer inputs to gamepad button using a custom inspector.

##How to use :
Simply drag the **"LaunchGamePadController"** script on any object in your scene (preferably an empty). Then in your character controller script for instance, add the following :
```
GamePadController.Controller gamePad; //Declaring a variable for our gamepad
void Start()
{
    gamePad = GamePadController.GamePadOne; //GamePadOne for first controller GamePadTwo for the second one, and so on...
}
```
And then to use the buttons just write :
```
gamePad.A.Pressed (if you want to check that the button A has been pressed [one frame])
gamePad.A.Held (if you want to check that the button A is held)
gamePad.A.Released (if you want to check that the button A has been released [one frame])
gamePad.A.Zero (is the default state)
```
To get the axis inputs just use :
```
gamePad.LeftStick.X (for the x axis of the leftstick).
```
Thanks to speps' work you can also use vibrations :
```
gamePad.SetVibration(100,100) //for 100% intensity on both motors
gamePad.StopVibration() //to stop the vibration
gamePad.SetVibration(100,100,5) //to have the gamepad vibrate for 5 seconds then stop
```
You can also very easily map computer inputs to the gamepad inputs, for example, the 'v' key of your keyboard could represent the A button of your gamePad, that way :
```
if(gamePad.A.Pressed)
    Debug.Log("Pressed")
```   
this code will allow you to have both inputs (computer and gamepad) working at the same time or only one at a time (if the gamePad is not connected) with a single line of code.

```
//--> Additional Objectives
//add dualstick for 2d games
//add deadzone function
//add more than 4 controllers to gamepadcontroller
//change gamepad number classes to enum, ex : GamePad.One

//-->Computer Inputs
//First controllers values get copied in all other controllers (so as not to rewrite them)
//allow change of key or button or axis at runtime (public class and variables plus custom functions)
//Check if button is axis and transform axis values to button
//make some deafult parameters (Ex : Right Stick is always axis, if button is axis, then only one direction)
//Add other default Parameters (Ex : LeftStick X&Y already have Horizontal and Vertical written, etc...)
//Add smart autocomplete
//Use custom editor for "enable controller"
//Save/Load preconfigured inputs in a file
```
