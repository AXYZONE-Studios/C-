Arrays in C! (equivalent to Python's *lists*) are a form of data that can store multiple values, including variables. Arrays are declared the same way as variables are, except two differences:
- To declare an array, you put the `list` keyword before the data type
- You put the values (separated by commas) in square brackets

Here's an example program that declares and prints an array:

```dart
// Sample program demonstrating the declaration and use of an array.
import stdout;

func main()
{
	list int numbers = [1, 2, 3, 4, 5]; // Creates an array that holds int values
	stdout(numbers);
	
	return 0;
}
```

The program will output the following sequence:
```
12345
```

In order to display the same array with numbers separated by spaces, you need to write the following code:

```dart
import stdout;

func main()
{
	list int numbers = [1, 2, 3, 4, 5];
	
	for (int i = 0; i < numbers:get(length); i++)
	{
		
	}
}
```

Array elements in C! are indexed starting from `0`. In order to address the `i`th element of the `array` array (and, for example, set it to `"sample"`), you write the following instruction:

```dart
array[i] = "sample";
```

Indexes can also be negative numbers, similar to how they work in Python. Here's an example C! array with each element containing information about its index.

```dart
list string indexes = [
	"My index is 0 (or -4)",
	"My index is 1 (or -3)",
	"My index is 2 (or -2)",
	"My index is 3 (or -1)"
];
```

# Manipulating arrays

Arrays in C! do not have a fixed length, unlike in C++. If you want to declare an array with a fixed length (which is great for memory optimisation), you can use the `FixedLength` keyword followed by the array's length:

```dart
import stdout;

func main()
{
	list int salaries = [4000, 4000, 5000, 5000, 5500];
	FixedLength[12] list string months = [
		"January", "February", "March", "April",
		"May", "June", "July", "August",
		"September", "October","November", "December"
	];
}
```

The `FixedLength` keyword can go anywhere relative to the `const` word, as long as it's placed before the data type declaration. For example:
```dart
// Both arrays are correctly declared and won't throw errors
FixedLength[2] const list int values1 = [2, 4];
const FixedLength[2] list int values2 = [2, 4];
```
