# CincoDemo

Sample app to demostrate a Shared Blazor Component Library with shared controls that are used by a Blazor Server App and a .NET MAUI Hybrid App. 


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

## Test Environment
File -> New .NET MAUI Blazor App and Run on all available TFMs to confirm everything works!

## Project Structure


## DevOps

## Other Resources