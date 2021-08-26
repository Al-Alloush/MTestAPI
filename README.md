# MarAPI

## Add Add main Solution Structure and First Projects:
```
dotnet new sln
dotnet new webapi -o API
dotnet new Classlib -o Infrastructure
dotnet new Classlib -o Core
```

### Add all projects to solution:
```
dotnet sln add API
dotnet sln add Infrastructure
dotnet sln add Core
```
---
### Create Project Reference:
```
dotnet add API/API.csproj reference Infrastructure
dotnet add API/API.csproj reference Core
dotnet add Infrastructure/Infrastructure.csproj reference Core
```
### then:
```
dotnet restore
```


### Core Packages/Tools
- install ``Microsoft.Extensions.Identity.Stores``, Select version the same .NET SDK version  //  AppUser class will derive from an IdentityUser class in this Package


### Infrastructure Packages/Tools
- insatll ``Pomelo.EntityFrameworkCore.MySql 5.0.0-alpha.1``
```
	alpha.1 version to avoid Error: "Cannot convert from 'string' to 'Microsoft.EntityFrameworkCore.ServerVersion" in startup.cs :
	services.AddDbContext<AppDbContext>(x => x.UseMySql(Configuration.GetConnectionString("MySqlConnection")));
```
- install ``Microsoft.AspNetCore.Identity``, Select Latest version 
- install ``Microsoft.AspNetCore.Identity.EntityFrameworkCore``, Select version the same .NET SDK version