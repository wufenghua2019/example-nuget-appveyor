# Black Duck CoPilot NuGet/AppVeyor

[![Build status](https://ci.appveyor.com/api/projects/status/6968j1og6kvx06xt/branch/master?svg=true)](https://ci.appveyor.com/project/BlackDuckCoPilot/example-nuget-appveyor/branch/master) [![Black Duck Security Risk](https://copilot.blackducksoftware.com/github/repos/BlackDuckCoPilot/example-nuget-appveyor/branches/master/badge-risk.svg)](https://copilot.blackducksoftware.com/github/repos/BlackDuckCoPilot/example-nuget-appveyor/branches/master)

Shows a working setup for using Black Duck CoPilot to analyze the risk of project dependencies

## AppVeyor Setup
The `appveyor.yml` file has been modified to upload dependency information to Black Duck CoPilot:

```yaml
on_success:
- curl -s -o upload https://copilot.blackducksoftware.com/ci/appveyor/scripts/upload
- bash upload
```
