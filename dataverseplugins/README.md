# Building Dataverse plugins using Power Platform CLI (pac)


## Create Solution containuing Plugins

### Initialize solution
```
> pac solution init ---publisher-name soulsoftware --publisher-prefix soul
> dotnet build
```

### Import solution to environment

localize the zip in `bin\Debug` and use it in the follow command 

```
> pac solution import --path <solution's zip path> --async
```

## Create a Plugin invoked over a step


### Create plugin project

make a directory `plugin-src/<Plugin Folder>` and move in after that, run commands:
```
> pac plugin init
> dotnet build
``` 

### Plugin registration (Once only on Windows 🥲)

Plugin registration has done throught a [Plugin Registration Tool](PRT) available only on Windows platform 🥲.

The easy way to install and run [Plugin Registration Tool](PRT) is :
```
> pac tool prt
```

Using  [Plugin Registration Tool](PRT) we can register into dataverse either the assembly and the dataverse action associated (step) with it

### Add plugin reference into solution

Make sure that the `<Solution>.cdsproj` has a reference to the `<plugin assembly>.cdsproj` to ensure that Dll get built when the solution is built, then go to in solution folder and run:
```
> pac add-reference --path <plugin's project folder>
```


### Push plugin update 



# References 

* [Building Dataverse plugins using Power Platform CLI (You Tube)](https://youtu.be/wzHLWNWcY2Q)


[PRT]: https://learn.microsoft.com/en-us/power-apps/developer/data-platform/register-plug-in#about-the-plug-in-registration-tool