SugarSharp
==========

Sugar7 C# Rest Client


Todo
* Finish data models for core objects
* Unit Testing
* Other webservice resources


###Creating Connection

```c#
string url = "https://instanceurl/rest/v10/";
string username = "username";
string password = "password";

SugarClient Sugar = new SugarClient(url, username, password);

```


###Create Record

Create records with anonymous objects
```c#
string returnID = "";

try
{
  returnID = Sugar.Create("Accounts", new
  {
      name = "Acme Inc",
      description = "full text description",
      phone_office = "555-555-5555"
  });
}
catch (SugarException E)
{
  //handle exception
}
```

Create records with defined object types

```c#
string returnID = "";

Account Account = new Account();
Account.name = "Acme Inc";
Account.description = "full text description";
Account.phone_office = "555-555-5555";

try
{
  returnID = Sugar.Create("Accounts", Account);
}
catch (SugarException E)
{
  //handle exception
}
```
