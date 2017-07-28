### Project Creation

![](_misc/Creating%20an%20Extensibility%20project.PNG)

### Initial Page

![](_misc/Getting%20Started%20Page.PNG)

### Initial Project Structure

![](_misc/Initial%20Project%20Structure.PNG)

### Initial Project Contents

*HelloWorld/HelloWorld/Properties/AssemblyInfo.cs*

```cs
﻿using System.Reflection;
using System.Runtime.CompilerServices;
using System.Runtime.InteropServices;

// General Information about an assembly is controlled through the following 
// set of attributes. Change these attribute values to modify the information
// associated with an assembly.
[assembly: AssemblyTitle("HelloWorld")]
[assembly: AssemblyDescription("")]
[assembly: AssemblyConfiguration("")]
[assembly: AssemblyCompany("")]
[assembly: AssemblyProduct("HelloWorld")]
[assembly: AssemblyCopyright("")]
[assembly: AssemblyTrademark("")]
[assembly: AssemblyCulture("")]

// Setting ComVisible to false makes the types in this assembly not visible 
// to COM components.  If you need to access a type in this assembly from 
// COM, set the ComVisible attribute to true on that type.
[assembly: ComVisible(false)]

// Version information for an assembly consists of the following four values:
//
//      Major Version
//      Minor Version 
//      Build Number
//      Revision
//
// You can specify all the values or you can default the Build and Revision Numbers 
// by using the '*' as shown below:
// [assembly: AssemblyVersion("1.0.*")]
[assembly: AssemblyVersion("1.0.0.0")]
[assembly: AssemblyFileVersion("1.0.0.0")]
```

*HelloWorld/HelloWorld/HelloWorld.csproj*

```csproj
﻿<?xml version="1.0" encoding="utf-8"?>
<Project ToolsVersion="15.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <PropertyGroup>
    <MinimumVisualStudioVersion>15.0</MinimumVisualStudioVersion>
    <VSToolsPath Condition="'$(VSToolsPath)' == ''">$(MSBuildExtensionsPath32)\Microsoft\VisualStudio\v$(VisualStudioVersion)</VSToolsPath>
  </PropertyGroup>
  <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" Condition="Exists('$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props')" />
  <PropertyGroup>
    <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>
    <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
    <SchemaVersion>2.0</SchemaVersion>
    <ProjectTypeGuids>{82b43b9b-a64c-4715-b499-d71e9ca2bd60};{FAE04EC0-301F-11D3-BF4B-00C04F79EFBC}</ProjectTypeGuids>
    <ProjectGuid>{08CD5955-070B-40E6-A4CF-93731F0AFA1C}</ProjectGuid>
    <OutputType>Library</OutputType>
    <AppDesignerFolder>Properties</AppDesignerFolder>
    <RootNamespace>HelloWorld</RootNamespace>
    <AssemblyName>HelloWorld</AssemblyName>
    <TargetFrameworkVersion>v4.6</TargetFrameworkVersion>
    <GeneratePkgDefFile>false</GeneratePkgDefFile>
    <IncludeAssemblyInVSIXContainer>false</IncludeAssemblyInVSIXContainer>
    <IncludeDebugSymbolsInVSIXContainer>false</IncludeDebugSymbolsInVSIXContainer>
    <IncludeDebugSymbolsInLocalVSIXDeployment>false</IncludeDebugSymbolsInLocalVSIXDeployment>
    <CopyBuildOutputToOutputDirectory>false</CopyBuildOutputToOutputDirectory>
    <CopyOutputSymbolsToOutputDirectory>false</CopyOutputSymbolsToOutputDirectory>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' ">
    <DebugSymbols>true</DebugSymbols>
    <DebugType>full</DebugType>
    <Optimize>false</Optimize>
    <OutputPath>bin\Debug\</OutputPath>
    <DefineConstants>DEBUG;TRACE</DefineConstants>
    <ErrorReport>prompt</ErrorReport>
    <WarningLevel>4</WarningLevel>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Release|AnyCPU' ">
    <DebugType>pdbonly</DebugType>
    <Optimize>true</Optimize>
    <OutputPath>bin\Release\</OutputPath>
    <DefineConstants>TRACE</DefineConstants>
    <ErrorReport>prompt</ErrorReport>
    <WarningLevel>4</WarningLevel>
  </PropertyGroup>
  <ItemGroup>
    <Compile Include="Properties\AssemblyInfo.cs" />
  </ItemGroup>
  <ItemGroup>
    <None Include="source.extension.vsixmanifest">
      <SubType>Designer</SubType>
    </None>
  </ItemGroup>
  <ItemGroup>
    <Content Include="index.html" />
    <Content Include="stylesheet.css" />
  </ItemGroup>
  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
  <Import Project="$(VSToolsPath)\VSSDK\Microsoft.VsSDK.targets" Condition="'$(VSToolsPath)' != ''" />
  <!-- To modify your build process, add your task inside one of the targets below and uncomment it. 
       Other similar extension points exist, see Microsoft.Common.targets.
  <Target Name="BeforeBuild">
  </Target>
  <Target Name="AfterBuild">
  </Target>
  -->
</Project>
```

*HelloWorld/HelloWorld/HelloWorld.csproj.user*

```xml
﻿<?xml version="1.0" encoding="utf-8"?>
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <PropertyGroup Condition="'$(Configuration)|$(Platform)' == 'Debug|AnyCPU'">
    <StartAction>Program</StartAction>
    <StartProgram>C:\Program Files %28x86%29\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\devenv.exe</StartProgram>
    <StartArguments>/rootsuffix Exp</StartArguments>
  </PropertyGroup>
  <PropertyGroup Condition="'$(Configuration)|$(Platform)' == 'Release|AnyCPU'">
    <StartAction>Program</StartAction>
    <StartProgram>C:\Program Files %28x86%29\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\devenv.exe</StartProgram>
    <StartArguments>/rootsuffix Exp</StartArguments>
  </PropertyGroup>
</Project>
```

*HelloWorld/HelloWorld/index.html*

```html
﻿<!DOCTYPE html>
<html>
<head>
    <meta charset='utf-8'>

    <link rel="stylesheet" type="text/css" href="stylesheet.css" media="screen">

    <title>Getting Started</title>
</head>

<body>
    <div class="container">
        <div id="header">
            <h1>Getting Started</h1>
            <h2>Visual Studio Extensions</h2>
        </div>

        <div id="main_content">
            <div id="lpanel">
                <h1>Creating a Visual Studio Extension</h1>

                <p>This project enables developers to create an extension for Visual Studio. The solution contains a VSIX project that packages the extension into a VSIX file. This file is used to install an extension for Visual Studio.</p>
                <h2>Add new features</h2>

                <ol>
                    <li>Right-click the project node in Solution Explorer and select Add&gt;New Item.</li>
                    <li>In the Add New Item dialog box, expand the Extensibility node under Visual C# or Visual Basic.</li>
                    <li>Choose from the available item templates: Visual Studio Package, Editor Items (Classifier, Margin, Text Adornment, Viewport Adornment), Command, Tool Window, Toolbox Control, and then click Add.</li>
                </ol>

                <p>The files for the template that you selected are added to the project. You can start adding functionality to your item template, press F5 to run the project, or add additional item templates.</p>

                <h2>Run and debug</h2>
                <p>To run the project, press F5. Visual Studio will:</p>

                <ul>
                    <li>Build the extension from the VSIX project.</li>
                    <li>Create a VSIX package from the VSIX project.</li>
                    <li>When debugging, start an experimental instance of Visual Studio with the VSIX package installed.</li>
                </ul>

                <p>In the experimental instance of Visual Studio you can test out the functionality of your extension without affecting your Visual Studio installation.</p>

            </div>
            <div id="rpanel">
                <div>
                    <h1>Visual Studio Extensibility Resources</h1>

                    <ol>
                        <li><a target="_blank" href="https://aka.ms/o5gv1m">Visual Studio documentation</a><br />Detailed documentation and API reference material for building extensions.</li>
                        <li><a target="_blank" href="https://aka.ms/pauhge">Extension samples on GitHub</a><br />Use a sample project to kickstart your development.</li>
                        <li><a target="_blank" href="https://aka.ms/l24u91">Extensibility chat room on Gitter</a><br />Meet other extension developers and exchange tips and tricks for extension development.</li>
                        <li><a target="_blank" href="https://aka.ms/spn6s4">Channel 9 videos on extensibility</a><br />Watch videos from the product team on Visual Studio extensibility.</li>
                        <li><a target="_blank" href="https://aka.ms/ui0qn6">Extensibility Tools</a><br />Install an optional helper tool that adds extra IDE support for extension authors.</li>
                    </ol>
                    <h1>Give us feedback</h1>
                    <ul>
                        <li><a target="_blank" href="https://aka.ms/uonulm">Submit a new feature idea or suggestion</a></li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</body>
</html>
```

*HelloWorld/HelloWorld/source.extension.vsixmanifest*

```xml
<?xml version="1.0" encoding="utf-8"?>
<PackageManifest Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vsx-schema/2011" xmlns:d="http://schemas.microsoft.com/developer/vsx-schema-design/2011">
  <Metadata>
    <Identity Id="HelloWorld.Deepak Yalamanchili.aa699eb3-15e2-4b04-a597-7bd6a317539e" Version="1.0" Language="en-US" Publisher="Deepak Yalamanchili" />
    <DisplayName>HelloWorld</DisplayName>
    <Description>Empty VSIX Project.</Description>
  </Metadata>
  <Installation>
    <InstallationTarget Id="Microsoft.VisualStudio.Community" Version="[15.0]" />
  </Installation>
  <Dependencies>
    <Dependency Id="Microsoft.Framework.NDP" DisplayName="Microsoft .NET Framework" d:Source="Manual" Version="[4.5,)" />
  </Dependencies>
  <Prerequisites>
    <Prerequisite Id="Microsoft.VisualStudio.Component.CoreEditor" Version="[15.0,16.0)" DisplayName="Visual Studio core editor" />
  </Prerequisites>
</PackageManifest>
```

*HelloWorld/HelloWorld/stylesheet.css*

```css
body {
  margin: 0;
  padding: 0;
  border: 0;
  color: #1E1E1E;
  font-size: 13px;
  font-family: "Segoe UI", Helvetica, Arial, sans-serif;
  line-height: 1.45;
  word-wrap: break-word;
}

/* General & 'Reset' Stuff */


.container {
  width: 980px;
  margin: 0 auto;
}

section {
  display: block;
  margin: 0;
}

h1, h2, h3, h4, h5, h6 {
  margin: 0;
}

/* Header, <header>
   header   - container
   h1       - project name
   h2       - project description
*/

#header {
  color: #FFF;
  background: #68217a;
  position:relative;
}
#hangcloud {
    width: 190px;
    height: 160px;
    background: url("../images/bannerart03.png");
    position: absolute;
    top: 0;
    right: -30px;
}
h1, h2 {
  font-family: "Segoe UI Light", "Segoe UI", Helvetica, Arial, sans-serif;
  line-height: 1;
  margin: 0 18px;
  padding: 0;
}
#header h1 {
  font-size: 3.4em;
  padding-top: 18px;
  font-weight: normal;
  margin-left: 15px;
}

#header h2 {
  font-size: 1.5em;
  margin-top: 10px;
  padding-bottom: 18px;
  font-weight: normal;
}


#main_content {
  width: 100%;
  display: flex;
  flex-direction: row;
}


h1, h2, h3, h4, h5, h6 {
  font-weight: bolder;
}

#main_content h1 {
  font-size: 1.8em;
  margin-top: 34px;
}

    #main_content h1:first-child {
        margin-top: 30px;
    }

#main_content h2 {
  font-size: 1.4em;
  font-weight: bold;
}
p, ul {
    margin: 11px 18px;
}

#main_content a {
    color: #06C;
    text-decoration: none;
}
ul {
        margin-top: 13px;
    margin-left: 18px;
    padding-left: 0;
}
    ul li {
        margin-left: 18px;
        padding-left: 0;
    }
#lpanel {
    width: 620px;
    float: left;
}
#rpanel ul {
    list-style-type: none;
    width: 300px;
}
    #rpanel ul li {
        line-height: 1.8em;
    }
#rpanel {
    background: #e7e7e7;
    width: 360px;
        float: right;
}

#rpanel div {
  width: 300px;
}
```

*HelloWorld/HelloWorld.sln*

```
﻿
Microsoft Visual Studio Solution File, Format Version 12.00
# Visual Studio 15
VisualStudioVersion = 15.0.26430.13
MinimumVisualStudioVersion = 10.0.40219.1
Project("{FAE04EC0-301F-11D3-BF4B-00C04F79EFBC}") = "HelloWorld", "HelloWorld\HelloWorld.csproj", "{08CD5955-070B-40E6-A4CF-93731F0AFA1C}"
EndProject
Global
	GlobalSection(SolutionConfigurationPlatforms) = preSolution
		Debug|Any CPU = Debug|Any CPU
		Release|Any CPU = Release|Any CPU
	EndGlobalSection
	GlobalSection(ProjectConfigurationPlatforms) = postSolution
		{08CD5955-070B-40E6-A4CF-93731F0AFA1C}.Debug|Any CPU.ActiveCfg = Debug|Any CPU
		{08CD5955-070B-40E6-A4CF-93731F0AFA1C}.Debug|Any CPU.Build.0 = Debug|Any CPU
		{08CD5955-070B-40E6-A4CF-93731F0AFA1C}.Release|Any CPU.ActiveCfg = Release|Any CPU
		{08CD5955-070B-40E6-A4CF-93731F0AFA1C}.Release|Any CPU.Build.0 = Release|Any CPU
	EndGlobalSection
	GlobalSection(SolutionProperties) = preSolution
		HideSolutionNode = FALSE
	EndGlobalSection
EndGlobal
```
