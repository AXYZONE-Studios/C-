C! is a strongly typed language, so here's a list of all recognised variable types:

| Type             | Description                      | Example valid values         | Value range (for numerical types)       |
| ---------------- | -------------------------------- | ---------------------------- | --------------------------------------- |
| `int`            | Integer numbers                  | 91238, 18, -9                | -2147483648; 2147483647                 |
| `float`          | Numbers with decimals            | 912, -314.5, 256.55          | $1.4\times10^{-45}$; $3.4\times10^{38}$ |
| `string`         | Text                             | "string", "wow", "text"      | Not a numerical data type               |
| `char`           | Single characters                | 'A', 'o', '4'                | Not a numerical data type               |
| `auto`           | Automatically assigns type       | 'o', 0, 9999.99              |                                         |
| `short`          | `int` but limited to 2 bytes     | 32699, -9934, 7712           | -32768 to 32767                         |
| `byte`           | `int` but limited to 1 byte      | 71, -12                      | -128; 127                               |
| `bool`           | True/false values                | true, false                  | true, false                             |
| `unsigned int`   | `int` without negative numbers   | 0, 10923, 41341984           | 0; 4294967295                           |
| `unsigned short` | `short` without negative numbers | 32699, 9934, 7712            | 0 to 65535                              |
| `unsigned byte`  | `byte` without negative numbers  | 0, 129, 33                   | 0; 255                                  |
| `bin`            | Binary number                    | 1110101001, 101, 111111      | 0 to 11111111111111111111111111111111   |
| `byte bin`       | Binary byte                      | 11011100, 10110010, 11111111 | 0 to 11111111                           |
| `hex`            | Hexadecimal value                | 0xF9, 0xA4, 0x664            | 0x0 to 0xFFFFFFFF                       |
| `byte hex`       | Hexadecimal byte                 | 0xFF, 0xE3, 0x44             | 0x0 to 0xFF                             |
| `short hex`      | Same as `byte hex`               | 0xFF, 0xE3, 0x44             | 0x0 to 0xFF                             |

Syntax for declaring a variable:

`type VariableName value;`

where:
- `type` is the variable type,
- `VariableName` is the variable name,
- `value` is the assigned value (optional)

Example:
- `bool ButtonClicked = false;`
- `byte users;`
- `char LastKey;`
# Variable naming conventions

In C!, variables are usually given names in PascalCase, unless the name is just one word long.

| Identifier       | Allowed? | Conventional? |
| ---------------- | -------- | ------------- |
| `index`          | Yes      | Yes           |
| `exchangeRate`   | Yes      | No            |
| `X`              | Yes      | No            |
| `MemberName`     | Yes      | Yes           |
| `_93`            | Yes      | No            |
| `#1`             | No       | No            |
| `Absolute value` | No       | No            |
| `NewMembername`  | Yes      | No            |
| `variable_value` | Yes      | No            |
If you need to declare a variable, but there already is a variable with the same name, you may include underscores before the variable name (e.g. `_name` or `___index`), though this is generally not recommended because it makes debugging harder.
# Changing variable values

```dart
// A basic program that demonstrates a variable whose value changes mid-execution
import stdout;

func main()
{
	int a = 2000;
	
	stdout("Variable before change: " + a + '\n');
	a = 4000;
	stdout("Variable after change: " + a + '\n');
	
	return 0;
}
```

Ways to change a variable's value:

`a = b` - sets the value of `a` to the value of `b`
`a += b` - same as `a = a + b`
`a -= b` - same as `a = a - b`
`a *= b` - same as `a = a * b`
`a /= b` - same as `a = a / b`
`a++` - same as `a = a + 1`
`a--` - same as `a = a - 1`

# Comparing variables

Logical operators:

`a == b` - `a` equals `b`
`a != b` - `a` does not equal `b`
`a > b` - `a` is greater than `b`
`a < b` - `a` is less than `b`
`a >= b` - `a` is greater or equal to `b`
`a <= b` - `a` is less or equal to `b`

Bitwise operators:

`a && b` or `a and b` - `a` and `b` are true
`a || b` or `a or b` - `a` or `b` is true
`a !& b` or `a nand b` - either `a` or `b` is true but not both (same as `!(a && b)`)
// more to come

# Constants

In C!, just like in C, C++ and C#, constants are created using the `const` keyword before the variable type. Constants cannot have their value changed, which can be useful for memory optimisation.

```dart
// Example program incorporating variables and constants
import stdout;
import stdin;

func main()
{
	const float PI = 3.14159;
	float radius;
	
	stdout("Enter the circle's radius: ");
	stdin(radius);
	stdout("The circumference of the circle is: ", 2 * PI * radius);
	
	return 0;
}
```

```dart
import stdout;

func main()
{
	const int NUMBER = 5;
	
	stdout("Before change: ", NUMBER);
	NUMBER++; // Will return an error
	stdout("After change: ", NUMBER);
	
	return 0;
}
```
