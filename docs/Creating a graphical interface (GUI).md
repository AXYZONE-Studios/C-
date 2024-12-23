C! has a versatile, developer-friendly library for GUI development. Its implementation is very straightforward:

```dart
import gui:*;
```

> *Click [[List of children of the C! GUI library|here]] to find a list of sub-imports from the GUI library*

Switching to a graphical interface expands the code skeleton for a C! program. For comparison, here's the required code skeleton for a text program:

```dart
import stdout;

func main()
{
	// program contents here
	return 0;
}
```

And here's the required code skeleton for a GUI program:

```dart
import gui:*;
import os;

func main()
{
	Window window = new Window(
		XPos=0, // replace with the desired X position of your window
		YPos=0, // replace with the desired Y position of your window
		width=FULL, // replace with your window's desired width
		height=FULL, // replace with your window's desired height
		color=0xFFFFFF // replace with the desired color of your window
	);
	
	Window:*:place();
	
	Renderer renderer = new Renderer();
	renderer:render(window);
	
	async OnEvent ("KEYPRESS_Q")
	{
		window:*:destroy();
		renderer:destroy();
	}
	
	return 0;
}
```

Now let's analyse this skeleton step by step:

1. `import gui:*;` - This line imports the GUI library and all its children. This is the best choice for flexibility and ease of use, however you should not import the entire library if you want to make your code lighter.
2. `import os;` - Imports functionality for communicating with many different operating systems. It has to be included because it contains the `KEYPRESS_Q` event, along with other keypress events, which are necessary for controlling the GUI and terminating it.
3. `Window window = new Window();` - Creates a new Window - the backbone of the whole program. The Window contains everything that will be rendered by your program.
   
   The Window is initiated with the following parameters:
   - `XPos=0` - the horizontal position of your window. Although it can be set to any unsigned integer, it is generally recommended to set it to `DEFAULT_WINDOWPOS_MODE` (a variable added by the OS library) - it lets your system configuration decide where your window will appear.
   - `YPos=0` - same thing as `XPos`
   - `width=FULL` and `height=FULL` - specifies the dimensions of the Window. The `FULL` keyword, provided by the GUI library, makes the window fill the entire screen.
   - `color=0xFFFFFF` - specifies the background colour of the Window as a 3-byte hex value (`hex3` type)
4. `Window:*:place();` - Takes all the children of the Window (all objects with the `parent=window` parameter are children of the Window) and places them on the Window.
5. `Renderer renderer = new Renderer();` - creates the renderer object. The renderer is responsible for making the Window actually appear on the screen.
6. `renderer:render(window);` - Renders the window.
7. `async OnEvent ("KEYPRESS_Q") window:*:destroy();` - waits for the user to press the Q key, then destroys every component of the Window.

# Example program - graphical Hello World

```dart
import gui:*; // For GUI purposes.
import os; // For accessing system settings.

func main()
{
	// Create a 600x400 window
	Window window = new Window(
		XPos=DEFAULT_WINDOWPOS_MODE,
		YPos=DEFAULT_WINDOWPOS_MODE,
		width=600,
		height=400,
		color=0xFFFFFF
	);

	// Create a Label with the message
	Label label = new Label(
		parent=window, // Place the Label on the Window
		text="Hello World!", // The text to be rendered
		font=SYS_DEFAULT_FONT, // Use the default font
		FontSize=SYS_DEFAULT_FONTSIZE, // And the default size
		XPos=0,
		YPos=0
	);
	
	// Place all children on the Window
	Window:*:place();
	
	// Create the Renderer and render the Window
	Renderer renderer = new Renderer();
	renderer:render(window);
	
	// Make the program close when Esc is pressed
	async OnEvent ("KEYPRESS_ESC")
	{
		window:*:destroy();
		renderer:destroy();
	}
	
	return 0;
}
```

Let's analyse the program step by step:

1. `import gui:*;` imports the GUI library and all its children.
2. `import os;` imports the OS library for keywrds such as `DEFAULT_WINDOWPOS_MODE` or `SYS_DEFAULT_FONT` and keypress events.
3. `Window window = new Window();` creates the Window with all necessary parameters specified.
4. `Label label = new Label();` creates a Label that will display the "Hello World" message. Here's a run-down of its parameters:
   - `parent` - Specifies the parent object for the Label. In this case, the Window needs to be the parent object, otherwise the Label will not display correctly.
   - `text` - The text to be displayed by the Label.
   - `font` - The font to render the text. In this case, the system default font (`SYSTEM_DEFAULT_FONT`) was used.
   - `FontSize` - Specifies the size of the text. Again, the system default was used.
   - `XPos` and `YPos` - The position of the upper-left corner of the Label, relative to the upper-left corner of the Window.
5. `Window:*:place();` sets all children of the Window (in this case, it's just the Label) to be displayed.
6. `Renderer renderer = new Renderer();` creates the Renderer, which will render the Window.
7. `renderer:render(window);` tells the Renderer to render the Window, which will also render the Label since it's placed on the Window.
8. `async OnEvent("KEYPRESS_ESC")` tells the program to wait for the `KEYPRESS_ESC` event without pausing execution of other instruction.
9. `window:*:destroy();` destroys the Window and all its children, including the Label. This causes the program window to disappear and the Renderer to become idle, however other instructions can still be performed in this state.
10. `renderer:destroy();` destroys the Renderer, therefore disabling the graphical interface.
11. `return 0;` reports that all execution went as expected and ends execution.
