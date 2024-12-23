```dart
// Simple demonstration of the FOR loop
import stdout;
import stdin;

func main()
{
	int a;
	
	stdout("Enter a number: ");
	stdin(a);
	
	for (int i = 0; i < 10; i++)
	{
		a++;
	}
		
	stdout("The new number is: " + a + '\n');
	return 0;
}
```

```dart
// Simple demonstration of the WHILE loop
import stdout;
import stdin;

func main()
{
	string answer;
	
	while (answer != "no")
	{
		stdout("Yes or no? ");
		stdin(answer);
	}
	
	return 0;
}
```

```dart
// Simple demonstration of the DO WHILE loop
import stdout;
import stdin;

func main()
{
	int number;
	
	stdout("Enter a number: ");
	stdin();
	
	do
	{
		number++;
	} while (number < 1000);
	
	return 0;
}
```

```dart
// Simple demonstration of the FOREACH loop
import stdout;
import stdin;

func main()
{
	list int numbers = [1, 2, 3, 4, 5];
	int number;
	
	foreach (number in numbers)
	{
		stdout(number);
		number++;
	}
		
	return 0;
}
```
