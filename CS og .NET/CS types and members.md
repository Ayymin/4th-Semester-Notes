Som et objektorienteret sprog understøtter C# begreberne indkapsling, arv og polymorfi. 
Metoder, der tilsidesætter virtuelle metoder i en overordnet klasse, kræver nøgleordet "override"

Eksempel:
```C#
public override string ToString() 
{
	return firstName
}
```
Det undgår tilsigtet omdefinering. 

**Structs**
I C# er det en lightweight class, sholder på variabler og data, som arbejdes med en enhed. 

```C#
struct Bil
{
 public string Mærke;
 public string Model;
}

public class Program
{
	public static void Main()
	{
	  Bil minBil = new Bil { Mærke = "Toyota", Model = "Corolla}
	}
}
```

### Klasser og objekter
Klasser er de mest grundlæggende af C#'s typer som et objektorienteret sprog. En klasse er en datastruktur, der kombinere tilstand og handlinger i en enkelt enhed. 
Klasser oprettes vha erkleringer. Starter med en overskrift. Overskriften angiver
* Klassens attributter og modifikationer
* Klassens navn
* Basisklassen (når den nedarves fra en basisklasse)
* Grænsefladerne implementeret afk lassen. 
```C#
public class Point
{
	public int X { get; }
	public int Y { get; }

	public Point(int x, int y) => (X, Y) = (x, y);
}


//Forekomster oprettes ved hjælp af new
var p1 = new Point(0, 0)
var p2 = new Point(10, 20)
```

Det kan være at man i et program eller test skal oprette flere point objekter.
```C#
public class PointFactory(int numberofPoints)
{
	public IEnumerable<Point> CreatePoints()
	{
		var generator = new Random();
		for (int i = 0; i < number numberOfPoints; i++)
		{
			yield return new Point(generator.Next(), generator.Next())
		}
	}
}


var factory = new PointFactory(10);
foreach (var point in factory.CreatePoints())
{
	Console.WriteLine($"({point.X}, {point.Y})");
}
```

**Generiske typer**
```C#
public class Pair<TFirst, TSecond>
{
    public TFirst First { get; }
    public TSecond Second { get; }
    
    public Pair(TFirst first, TSecond second) => 
        (First, Second) = (first, second);
}


var pair = new Pair<int, string>(1, "two");
int i = pair.First;     //TFirst int
string s = pair.Second; //TSecond string
```

**Basis klasser**
Eksempel med nedarvning, Point3D nedarver fra Point klassen. 
```C#

public class Point3D : Point
{
    public int Z { get; set; }
    
    public Point3D(int x, int y, int z) : base(x, y)
    {
        Z = z;
    }
}
```


**Structs**
Struct klasser understøtter ikke polymorfisme og nedarvning. De bruges primært til simpel datalagring og sendes som værdier. En struct type kan ikke nedarves fra en anden. 
```C#
public struct Point
{
    public double X { get; }
    public double Y { get; }
    
    public Point(double x, double y) => (X, Y) = (x, y);
}
```

**Interfaces**
Definere en kontrakt, der kan implementeres af klasser og structs. Et interface kan indeholde metoder, properties, events og indexer. 
Interfaces kan også nedarves fra hinanden, vises i det givet eksempel:
``` C#
interface IControl
{
    void Paint();
}

interface ITextBox : IControl
{
    void SetText(string text);
}

interface IListBox : IControl
{
    void SetItems(string[] items);
}

interface IComboBox : ITextBox, IListBox { }
```

**Enums**
En enum type definere et set af konstante værdier.
```C#
public enum SomeRootVegetable
{
    HorseRadish,
    Radish,
    Turnip
}


[Flags]
public enum Seasons
{
    None = 0,
    Summer = 1,
    Autumn = 2,
    Winter = 4,
    Spring = 8,
    All = Summer | Autumn | Winter | Spring
}

var turnip = SomeRootVegetable.Turnip;
var spring = Seasons.Spring;
var startingOnEquinox = Seasons.Spring | Seasons.Autumn;
var theYear = Seasons.All;
```

**Nullbare typer**
Variabler af enhver type kan erklæres s