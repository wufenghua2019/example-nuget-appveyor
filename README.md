# Black Duck CoPilot NuGet/AppVeyor

[![Build status](https://ci.appveyor.com/api/projects/status/6968j1og6kvx06xt/branch/master?svg=true)](https://ci.appveyor.com/project/BlackDuckCoPilot/example-nuget-appveyor/branch/master)

Shows a working setup for using the Black Duck CoPilot integration to analyze the risk of project dependencies

## AppVeyor Setup
The `appveyor.yml` file has been modified to use the [hub-nuget integration](https://github.com/blackducksoftware/hub-nuget) to generate and upload to Black Duck CoPilot:

```yaml
on_success:
 - nuget install Hub-Nuget -Version 1.0.0
 - Hub-NuGet.1.0.0\tools\buildBom.exe --hub_deploy_bdio=false
 - curl -s https://copilot.blackducksoftware.com/batch/appveyor > appveyor.bat
 - appveyor
```
