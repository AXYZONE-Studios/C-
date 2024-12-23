C! offers four main forms of logical flow control:
- the IF statement

```dart
import stdout;
import stdin;

func main()
{
	int a;
	
	stdout("Enter a number: ");
	stdin(a);
	
	if (a > 100):
	{
		stdout("That's a lot!\n");
	}
	
	return 0;
}
```

- the IF/ELSE statement

```dart
import stdout;
import stdin;

func main()
{
	int a;
	
	stdout("Enter a number: ");
	stdin(a);
	
	if (a > 100):
	{
		stdout("That's a lot!\n");
	}
	else
	{
		stdout("More!\n");
	}
	
	return 0;
}
```

- the ELSE-IF statement

```dart
import stdout;
import stdin;

func main()
{
	int a;
	
	stdout("Enter a number: ");
	stdin(a);
	
	if (a > 100):
	{
		stdout("That's a lot!\n");
	}
	else if (a > 10):
	{
		stdout("More!\n");
	}
	else
	{
		stdout("Are you kidding me?\n");
	}
	
	return 0;
}
```

- the SWITCH statement

```dart
import stdout;
import stdin;

func main()
{
	int choice;
	
	LABEL start;
	
	stdout("Choose an action:\n\n1. Exit\n2. Continue");
	stdin(a);
	
	switch (a):
	{
		case (1)
		{
			goto exit;
		}
		case (2)
		{
			stdout("Continuing...\n")
		}
		else
		{
			stdout("Invalid number!\n");
			goto start;
		}
	}
	
	LABEL exit;
	return 0;
}
```

The SWITCH statement in C! does not have fall-through behaviour, unlike C++, though it can be induced by incrementing the `choice` variable at the end of each case block.
