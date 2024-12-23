```dart
// Demonstration of the goto statement
import stdin;
import stdout;

func main()
{
	int a;
	
	LABEL something;
	stdout("Do you want to run the program? ");
	stdin(a);
	
	while (a < 2000)
	{
		a++;
	}
	
	goto something;
	return 0;
}
```
