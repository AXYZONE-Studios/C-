A **map** is the C! equivalent of Python's *dictionaries* or C++/C#'s maps. They are sets of key-value pairs.

```dart
// Simple program that creates a map and does basic operations on it.
import map;
import stdin;
import stdout;

func main()
{
	(string, string) map EnglishToSwedish = [
		"butter": "smör",
		"meat": "kött",
		"bread": "bröd",
		"tea": "te",
	];
	
	EnglishToSwedish:add(last, "coffe": "kaffe");
	
	stdout(EnglishToSwedish["tea"]);
	
	return 0;
}
```

The `add()` method inserts a key-value pair in the desired spot in a map. It accepts two arguments:
- the position of the new key-value pair. It can be expressed using the following methods:
	- `last()` - places the new pair at the end of the map
	- `before(KeyValuePair)` - places the new pair before a specified existing key-value pair
	- `after(KeyValuePair)` - places the new pair after a specified existing key-value pair
- the key-value pair to be added

Generally, the formula to declare the map is as follows:

```dart
(KeyType, ValueType) map MapName = [
	KEY: VALUE,
	// insert as many key-value pairs as you need
];
```
