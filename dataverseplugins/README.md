# Building Dataverse plugins using Power Platform CLI (pac)

## Create a Plugin invoked over a step


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

### Create a plugin

make a directory `plugin-src/<Plugin Folder>` and move in after that, run commands:
```
> pac plugin init
> dotnet build
``` 

# References 

* [Building Dataverse plugins using Power Platform CLI (You Tube)](https://youtu.be/wzHLWNWcY2Q)