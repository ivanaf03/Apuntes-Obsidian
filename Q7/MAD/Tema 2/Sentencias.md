[[Tema 2-El lenguaje CSharp]]

## Sentencias condicionales
Las sentencias condicionales típicas son `if-else` y `switch`.

```CSharp
int num = 6;

if (if num < 10) {
	Console.WriteLine("Es menor");
} else {
	Console.WriteLine("Es mayor");
}
```

```CSharp
int num = 6;
int x = 0;

switch (num) {
	case 1: x += 1; break;
	case 6: x += 6; break;
	default: x += 10; break;
}
```

## Sentencias iterativas
Las sentencias iterativas típicas son `while`, `do-while`, `for` y `foreach`.

```CSharp
while (1 == 1) {
	Console.WriteLine("Loop");
}
```

```CSharp
do {
	Console.WriteLine("Loop");
} while (1 == 1);
```

```CSharp
for (int i=0; i<10; i++) {
	Console.WriteLine("i = " + (i + 1));
}
```

```CSharp
String[] days = {"Monday", "Tuesday", "Wednesday", "Thursday", "Friday"};

foreach (string day in days) {
	Console.WriteLine(day);
}
```