## .NET Demo day


.dll = Class Library (C# .NET Framework) (Project)
.exe = Console App / Win Forms etc. (Project) (har PRÆCIS een Main method)




Visual Studio:


Solution .sln (Den vi typisk åbner)
 -blot en container
 
 
Indeholder projekt(er) .csproj




automatic using (and other tooltips) (CRTL + .)

Run all Tests

(CTRL + r) a 



Extensions (Add methods to existing classes)

```csharp

public static class GeneralExtensions
{
	public static string Reverse(this string input)
	{
	
	}
}

```


### execise 1

- Create new C# Console App
- Console.Writeline Hello World
- Build test in *powershell*


Extension that can Print both an array string[] and a List<String>

Hint: Use IEnumable<string>


## Final exam

- Create a new console App Project
- Create a class library
- Create a test project for the class library

> Examine existing solutions!
> Only 1 solution with three projects


- In the class library make a Models folder
- Make an interface IPerson (Name, Age, Hobby)
- Make two classes (Child and Adult) both has to implement the IPerson interface

- Make an extension method for IEnumable<IPerson> called **Print**  (The method should return all names delimited by a *comma* (string not void as return)) -> **Morten, Lærke** -> Good for unit-testing

- In the console App Create both an Array and a List with people and **Console.Writeline** the result from Print to the *Console*


## Dapper


```csharp

                string connectionString = @"Server=WIN-IE5HKVPLVKT;Database=Test;Integrated Security=True;";
                SqlConnection connection = new SqlConnection(connectionString);
                connection.Open();

                string sql = @"
select
*
 from
dbo.Sports;
";

                IEnumerable<Sport> sports = connection
                                            .Query<Sport>(sql)
                                            .Where(sp => sp.NumberOfPlayers > 5);


```

```SQL

create table dbo.Sports (
	Id int identity(1,1) primary key,
	[Name] varchar(50),
	NumberofPlayers int,
	HasBall bit --Boolean in SQL world!!
)

```


