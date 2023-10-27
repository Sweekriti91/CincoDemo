# CincoDemo

Sample app to demostrate a Shared Blazor Component Library with shared controls that are used by a Blazor Server App and a .NET MAUI Hybrid App. 

| branch | build status |
| --- | --- |
| [main(net7)](https://github.com/Sweekriti91/CincoDemo) | [![Build Status](https://dotnetcst.visualstudio.com/MobCAT/_apis/build/status%2FSweekriti91.CincoDemo?branchName=main)](https://dotnetcst.visualstudio.com/MobCAT/_build/latest?definitionId=175&branchName=main) |
| [net8](https://github.com/Sweekriti91/CincoDemo/tree/net8) | [![Build Status](https://dotnetcst.visualstudio.com/MobCAT/_apis/build/status%2FSweekriti91.CincoDemo?branchName=net8)](https://dotnetcst.visualstudio.com/MobCAT/_build/latest?definitionId=175&branchName=net8) |

## Quick Links

- [Install Steps](#install-steps)
- [Project Structure](#project-structure)
- [DevOps](#devops)
- [Other Resources](#other-resources)


## Install Steps

### Install .NET 8 Preview 
**For Mac**
- Install .NET8.0-Rc2 : https://dotnet.microsoft.com/download/dotnet/8.0
- Install .NET MAUI workload, open Terminal : `sudo dotnet workload install maui`

**For Visual Studio for Mac**
- Install Visual Studio for Mac following doc [here](https://learn.microsoft.com/en-us/visualstudio/mac/installation?view=vsmac-2022)
- Turn on Preview Flag: Visual Studio -> Preferences -> Preview Features 
<img src="https://devblogs.microsoft.com/dotnet/wp-content/uploads/sites/10/2023/07/vsm_enable_net8.png" >
- Setup Android SDK following doc [here](https://learn.microsoft.com/en-us/xamarin/android/get-started/installation/android-sdk?tabs=macos) 

**For VSCode**
- Install the [.NET MAUI Extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.dotnet-maui)
- Follow the steps to get environment setup, setup Android SDK PATH etc

**Project Updates**
- Open `.sln` file in Visual Studio/VS Code
- Make updates :
    - Change TFMs from `net7.0-*` to `net8.0-*`
    - Add Package References :
   ``` 
   <ItemGroup>
        <PackageReference Include="Microsoft.Maui.Controls" Version="$(MauiVersion)" />
        <PackageReference Include="Microsoft.Maui.Controls.Compatibility" Version="$(MauiVersion)" />
   </ItemGroup> 
   ```
- Add  `.NET MAUI` Version tag, by first checking the most recent version of the nuget packages [here](https://www.nuget.org/packages/Microsoft.Maui.Controls/8.0.0-rc.2.9373). 
```
<MauiVersion>8.0.0-rc.2.9373</MauiVersion> 
```
- Delete `bin` and `obj` folders. 
- `dotnet restore` to add these new nuget packages and fix references.

## Test Environment
File -> New .NET MAUI Blazor App and Run on all available TFMs to confirm everything works!

## Project Structure

```
.
├── CincoApp.Components => Shared Blazor Components
├── CincoApp.DataLayer => Data Abstraction Layer
├── CincoApp.MAUI => .NET MAUI Blazor App
├── CincoApp.Tests => NUnit tests
├── CincoApp.Web => Blazor Server App
├── CincoDemo.sln
├── README.md
└── azure-pipelines.yml => Azure DevOps Pipeline File
```

## DevOps

Installed Software and Tooling Versions for Azure DevOps Agents [here](https://learn.microsoft.com/en-us/azure/devops/pipelines/agents/hosted?view=azure-devops&tabs=yaml#software).

- [Getting Started with .NET MAUI and DevOps](https://devblogs.microsoft.com/dotnet/devops-for-dotnet-maui/)
- [Android Publish Docs](https://learn.microsoft.com/en-us/dotnet/maui/android/deployment/)
- [iOS Publish Docs](https://learn.microsoft.com/en-us/dotnet/maui/ios/deployment/)
- [MacCatalyst Publish Docs](https://learn.microsoft.com/en-us/dotnet/maui/mac-catalyst/deployment/)
- [Host and deploy server-side Blazor apps](https://learn.microsoft.com/en-us/aspnet/core/blazor/host-and-deploy/server?view=aspnetcore-7.0)
- [Host and deploy ASP.NET Core Blazor](https://learn.microsoft.com/en-us/aspnet/core/blazor/host-and-deploy/?view=aspnetcore-7.0&tabs=visual-studio)
- [Azure Static WebApp Deploy Azure DevOps Task](https://learn.microsoft.com/en-us/azure/devops/pipelines/tasks/reference/azure-static-web-app-v0?view=azure-pipelines)

## Other Resources

### Docs/Samples/Tutorials

- [Razor Component Sharing Doc](https://learn.microsoft.com/en-us/aspnet/core/blazor/hybrid/class-libraries?view=aspnetcore-7.0)
- Sample App : https://github.com/microsoft/dotnet-podcasts/tree/main
- Blazor Workshop : https://github.com/dotnet-presentations/blazor-workshop/tree/main

### Component Library
- [Radzen Blazor Components](https://blazor.radzen.com/) *Free, Open Source*
- [MudBlazor](https://mudblazor.com/) *Free, Open Source*
- [SyncFusion](https://www.syncfusion.com/blazor-components) *Paid*
- [Telerik](https://www.telerik.com/blazor-ui) *Paid*