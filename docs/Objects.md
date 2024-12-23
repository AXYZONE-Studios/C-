C! enables object-oriented programming, using a model similar to that found in C++.

Here's the syntax for creating a class in C!:
```dart
class ClassName
{
	public ClassName() {} // Constructor (public)
	public int MemberVariable = 0; // Member variables (public)
	private func MemberMethod() {} // Member methods (private)
}
```

where:
- `ClassName` can be replaced with any valid identifier
- The **constructor** isn't a necessary part of a class, but if you decide to implement one, you have to make sure it's named the same as the class.
# Destroying objects

Here's how you destroy an object (for example `Renderer renderer` from the GUI library)

```dart
renderer:destroy();
```

And here's how you destroy an object and all children:

```dart
Window window = new Window(
	...
);

Label label = new Label(
	parent=window,
	...
);

Window:*:destroy(); // will destroy window and label
```
