## .NET Demo day


## Table of content

2. [Exam 2](#exam-2)


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


## Exam 2

1. Create a new Solution
2. Create two projects (One Class Library .DLL (no entry point (main))) and one Console App (Has entry point)
3. Make a Models folder in the *class library*
4. Create class(es) (Worker, Employee and Employer) (The two latter inherits a Worker)
5. Create approx. 7-10 Properties and some Methods (Age calculated, RaiseSalary())
6. Use the classes in your Console App (Reference needed)
7. Create three SQL Tables (Worker, Employee and Employer) (Foreign keys) (Join in select)
8. Use Dapper
9. Populate all Employees and Employer using Dapper (con.Query<Employee>) and use *foreach* to very that all fields and all rows are shown
10. Try mics. **LINQ** (Where, OrderBy...)

```

Worker (Name, DOB, Salary)


1 Morten
2 Lærke 


Employee

1 Salary F


Employeer 
2 Bonus


select *
from employer 
inner join
worker
on ((ID = ID))


--> Name, DOB, Salary, Bonus

```

[Back to top](#table-of-content)