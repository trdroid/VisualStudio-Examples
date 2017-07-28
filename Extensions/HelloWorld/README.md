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

On selecting the manifest file ...

![](_misc/Selecting%20manifest%20file.PNG)

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

### Adding a User Control

Right click on the project and select Add -> User Control

![](_misc/Adding%20a%20User%20Control.PNG)

### Selecting a Command

![](_misc/Adding%20a%20new%20Command.PNG)

### Files created on selecting a Command

![](_misc/After%20adding%20a%20new%20command.PNG)

### Contents Added

![](_misc/New%20Contents%20Added.PNG)

*HelloWorld\HelloWorld\Resources\HelloWorldCommand.png*

![](HelloWorld/Resources/HelloWorldCommand.png)

*HelloWorld\HelloWorld\Resources\HelloWorldCommandPackage.ico*

![](_misc/HelloWorldCommandPackage%20icon%20image.PNG)

*HelloWorld\HelloWorld\HelloWorldCommand.cs*

```cs
﻿//------------------------------------------------------------------------------
// <copyright file="HelloWorldCommand.cs" company="Company">
//     Copyright (c) Company.  All rights reserved.
// </copyright>
//------------------------------------------------------------------------------

using System;
using System.ComponentModel.Design;
using System.Globalization;
using Microsoft.VisualStudio.Shell;
using Microsoft.VisualStudio.Shell.Interop;

namespace HelloWorld
{
    /// <summary>
    /// Command handler
    /// </summary>
    internal sealed class HelloWorldCommand
    {
        /// <summary>
        /// Command ID.
        /// </summary>
        public const int CommandId = 0x0100;

        /// <summary>
        /// Command menu group (command set GUID).
        /// </summary>
        public static readonly Guid CommandSet = new Guid("58ba7c22-5d1d-4602-a33b-09fad84141d8");

        /// <summary>
        /// VS Package that provides this command, not null.
        /// </summary>
        private readonly Package package;

        /// <summary>
        /// Initializes a new instance of the <see cref="HelloWorldCommand"/> class.
        /// Adds our command handlers for menu (commands must exist in the command table file)
        /// </summary>
        /// <param name="package">Owner package, not null.</param>
        private HelloWorldCommand(Package package)
        {
            if (package == null)
            {
                throw new ArgumentNullException("package");
            }

            this.package = package;

            OleMenuCommandService commandService = this.ServiceProvider.GetService(typeof(IMenuCommandService)) as OleMenuCommandService;
            if (commandService != null)
            {
                var menuCommandID = new CommandID(CommandSet, CommandId);
                var menuItem = new MenuCommand(this.MenuItemCallback, menuCommandID);
                commandService.AddCommand(menuItem);
            }
        }

        /// <summary>
        /// Gets the instance of the command.
        /// </summary>
        public static HelloWorldCommand Instance
        {
            get;
            private set;
        }

        /// <summary>
        /// Gets the service provider from the owner package.
        /// </summary>
        private IServiceProvider ServiceProvider
        {
            get
            {
                return this.package;
            }
        }

        /// <summary>
        /// Initializes the singleton instance of the command.
        /// </summary>
        /// <param name="package">Owner package, not null.</param>
        public static void Initialize(Package package)
        {
            Instance = new HelloWorldCommand(package);
        }

        /// <summary>
        /// This function is the callback used to execute the command when the menu item is clicked.
        /// See the constructor to see how the menu item is associated with this function using
        /// OleMenuCommandService service and MenuCommand class.
        /// </summary>
        /// <param name="sender">Event sender.</param>
        /// <param name="e">Event args.</param>
        private void MenuItemCallback(object sender, EventArgs e)
        {
            string message = string.Format(CultureInfo.CurrentCulture, "Inside {0}.MenuItemCallback()", this.GetType().FullName);
            string title = "HelloWorldCommand";

            // Show a message box to prove we were here
            VsShellUtilities.ShowMessageBox(
                this.ServiceProvider,
                message,
                title,
                OLEMSGICON.OLEMSGICON_INFO,
                OLEMSGBUTTON.OLEMSGBUTTON_OK,
                OLEMSGDEFBUTTON.OLEMSGDEFBUTTON_FIRST);
        }
    }
}
```

*HelloWorld\HelloWorld\HelloWorldCommandPackage.cs*

```cs
﻿//------------------------------------------------------------------------------
// <copyright file="HelloWorldCommandPackage.cs" company="Company">
//     Copyright (c) Company.  All rights reserved.
// </copyright>
//------------------------------------------------------------------------------

using System;
using System.ComponentModel.Design;
using System.Diagnostics;
using System.Diagnostics.CodeAnalysis;
using System.Globalization;
using System.Runtime.InteropServices;
using Microsoft.VisualStudio;
using Microsoft.VisualStudio.OLE.Interop;
using Microsoft.VisualStudio.Shell;
using Microsoft.VisualStudio.Shell.Interop;
using Microsoft.Win32;

namespace HelloWorld
{
    /// <summary>
    /// This is the class that implements the package exposed by this assembly.
    /// </summary>
    /// <remarks>
    /// <para>
    /// The minimum requirement for a class to be considered a valid package for Visual Studio
    /// is to implement the IVsPackage interface and register itself with the shell.
    /// This package uses the helper classes defined inside the Managed Package Framework (MPF)
    /// to do it: it derives from the Package class that provides the implementation of the
    /// IVsPackage interface and uses the registration attributes defined in the framework to
    /// register itself and its components with the shell. These attributes tell the pkgdef creation
    /// utility what data to put into .pkgdef file.
    /// </para>
    /// <para>
    /// To get loaded into VS, the package must be referred by &lt;Asset Type="Microsoft.VisualStudio.VsPackage" ...&gt; in .vsixmanifest file.
    /// </para>
    /// </remarks>
    [PackageRegistration(UseManagedResourcesOnly = true)]
    [InstalledProductRegistration("#110", "#112", "1.0", IconResourceID = 400)] // Info on this package for Help/About
    [ProvideMenuResource("Menus.ctmenu", 1)]
    [Guid(HelloWorldCommandPackage.PackageGuidString)]
    [SuppressMessage("StyleCop.CSharp.DocumentationRules", "SA1650:ElementDocumentationMustBeSpelledCorrectly", Justification = "pkgdef, VS and vsixmanifest are valid VS terms")]
    public sealed class HelloWorldCommandPackage : Package
    {
        /// <summary>
        /// HelloWorldCommandPackage GUID string.
        /// </summary>
        public const string PackageGuidString = "654c1c5e-2ff5-482b-9a82-f7faf891286f";

        /// <summary>
        /// Initializes a new instance of the <see cref="HelloWorldCommand"/> class.
        /// </summary>
        public HelloWorldCommandPackage()
        {
            // Inside this method you can place any initialization code that does not require
            // any Visual Studio service because at this point the package object is created but
            // not sited yet inside Visual Studio environment. The place to do all the other
            // initialization is the Initialize method.
        }

        #region Package Members

        /// <summary>
        /// Initialization of the package; this method is called right after the package is sited, so this is the place
        /// where you can put all the initialization code that rely on services provided by VisualStudio.
        /// </summary>
        protected override void Initialize()
        {
            HelloWorldCommand.Initialize(this);
            base.Initialize();
        }

        #endregion
    }
}
```

*HelloWorld\HelloWorld\HelloWorldCommandPackage.vsct*

```xml
﻿<?xml version="1.0" encoding="utf-8"?>
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema">

  <!--  This is the file that defines the actual layout and type of the commands.
        It is divided in different sections (e.g. command definition, command
        placement, ...), with each defining a specific set of properties.
        See the comment before each section for more details about how to
        use it. -->

  <!--  The VSCT compiler (the tool that translates this file into the binary
        format that VisualStudio will consume) has the ability to run a preprocessor
        on the vsct file; this preprocessor is (usually) the C++ preprocessor, so
        it is possible to define includes and macros with the same syntax used
        in C++ files. Using this ability of the compiler here, we include some files
        defining some of the constants that we will use inside the file. -->

  <!--This is the file that defines the IDs for all the commands exposed by VisualStudio. -->
  <Extern href="stdidcmd.h"/>

  <!--This header contains the command ids for the menus provided by the shell. -->
  <Extern href="vsshlids.h"/>

  <!--The Commands section is where commands, menus, and menu groups are defined.
      This section uses a Guid to identify the package that provides the command defined inside it. -->
  <Commands package="guidHelloWorldCommandPackage">
    <!-- Inside this section we have different sub-sections: one for the menus, another
    for the menu groups, one for the buttons (the actual commands), one for the combos
    and the last one for the bitmaps used. Each element is identified by a command id that
    is a unique pair of guid and numeric identifier; the guid part of the identifier is usually
    called "command set" and is used to group different command inside a logically related
    group; your package should define its own command set in order to avoid collisions
    with command ids defined by other packages. -->

    <!-- In this section you can define new menu groups. A menu group is a container for
         other menus or buttons (commands); from a visual point of view you can see the
         group as the part of a menu contained between two lines. The parent of a group
         must be a menu. -->
    <Groups>
      <Group guid="guidHelloWorldCommandPackageCmdSet" id="MyMenuGroup" priority="0x0600">
        <Parent guid="guidSHLMainMenu" id="IDM_VS_MENU_TOOLS"/>
      </Group>
    </Groups>

    <!--Buttons section. -->
    <!--This section defines the elements the user can interact with, like a menu command or a button
        or combo box in a toolbar. -->
    <Buttons>
      <!--To define a menu group you have to specify its ID, the parent menu and its display priority.
          The command is visible and enabled by default. If you need to change the visibility, status, etc, you can use
          the CommandFlag node.
          You can add more than one CommandFlag node e.g.:
              <CommandFlag>DefaultInvisible</CommandFlag>
              <CommandFlag>DynamicVisibility</CommandFlag>
          If you do not want an image next to your command, remove the Icon node /> -->
      <Button guid="guidHelloWorldCommandPackageCmdSet" id="HelloWorldCommandId" priority="0x0100" type="Button">
        <Parent guid="guidHelloWorldCommandPackageCmdSet" id="MyMenuGroup" />
        <Icon guid="guidImages" id="bmpPic1" />
        <Strings>
          <ButtonText>Invoke HelloWorldCommand</ButtonText>
        </Strings>
      </Button>
    </Buttons>

    <!--The bitmaps section is used to define the bitmaps that are used for the commands.-->
    <Bitmaps>
      <!--  The bitmap id is defined in a way that is a little bit different from the others:
            the declaration starts with a guid for the bitmap strip, then there is the resource id of the
            bitmap strip containing the bitmaps and then there are the numeric ids of the elements used
            inside a button definition. An important aspect of this declaration is that the element id
            must be the actual index (1-based) of the bitmap inside the bitmap strip. -->
      <Bitmap guid="guidImages" href="Resources\HelloWorldCommand.png" usedList="bmpPic1, bmpPic2, bmpPicSearch, bmpPicX, bmpPicArrows, bmpPicStrikethrough"/>
    </Bitmaps>
  </Commands>

  <Symbols>
    <!-- This is the package guid. -->
    <GuidSymbol name="guidHelloWorldCommandPackage" value="{654c1c5e-2ff5-482b-9a82-f7faf891286f}" />

    <!-- This is the guid used to group the menu commands together -->
    <GuidSymbol name="guidHelloWorldCommandPackageCmdSet" value="{58ba7c22-5d1d-4602-a33b-09fad84141d8}">
      <IDSymbol name="MyMenuGroup" value="0x1020" />
      <IDSymbol name="HelloWorldCommandId" value="0x0100" />
    </GuidSymbol>

    <GuidSymbol name="guidImages" value="{08435f6c-1f8e-41a7-8328-401134a01e5b}" >
      <IDSymbol name="bmpPic1" value="1" />
      <IDSymbol name="bmpPic2" value="2" />
      <IDSymbol name="bmpPicSearch" value="3" />
      <IDSymbol name="bmpPicX" value="4" />
      <IDSymbol name="bmpPicArrows" value="5" />
      <IDSymbol name="bmpPicStrikethrough" value="6" />
    </GuidSymbol>
  </Symbols>
</CommandTable>
```

*HelloWorld\HelloWorld\Key.snk*

*HelloWorld\HelloWorld\packages.config*

```xml
﻿<?xml version="1.0" encoding="utf-8"?>
<packages>
  <package id="Microsoft.VisualStudio.CoreUtility" version="15.0.26201" targetFramework="net46" />
  <package id="Microsoft.VisualStudio.Imaging" version="15.0.26201" targetFramework="net46" />
  <package id="Microsoft.VisualStudio.OLE.Interop" version="7.10.6070" targetFramework="net46" />
  <package id="Microsoft.VisualStudio.Shell.15.0" version="15.0.26201" targetFramework="net46" />
  <package id="Microsoft.VisualStudio.Shell.Framework" version="15.0.26201" targetFramework="net46" />
  <package id="Microsoft.VisualStudio.Shell.Interop" version="7.10.6071" targetFramework="net46" />
  <package id="Microsoft.VisualStudio.Shell.Interop.10.0" version="10.0.30319" targetFramework="net46" />
  <package id="Microsoft.VisualStudio.Shell.Interop.11.0" version="11.0.61030" targetFramework="net46" />
  <package id="Microsoft.VisualStudio.Shell.Interop.12.0" version="12.0.30110" targetFramework="net46" />
  <package id="Microsoft.VisualStudio.Shell.Interop.8.0" version="8.0.50727" targetFramework="net46" />
  <package id="Microsoft.VisualStudio.Shell.Interop.9.0" version="9.0.30729" targetFramework="net46" />
  <package id="Microsoft.VisualStudio.TextManager.Interop" version="7.10.6070" targetFramework="net46" />
  <package id="Microsoft.VisualStudio.TextManager.Interop.8.0" version="8.0.50727" targetFramework="net46" />
  <package id="Microsoft.VisualStudio.Threading" version="15.0.240" targetFramework="net46" />
  <package id="Microsoft.VisualStudio.Utilities" version="15.0.26201" targetFramework="net46" />
  <package id="Microsoft.VisualStudio.Validation" version="15.0.82" targetFramework="net46" />
  <package id="Microsoft.VSSDK.BuildTools" version="15.0.26201" targetFramework="net46" developmentDependency="true" />
</packages>
```

*HelloWorld\HelloWorld\VSPackage.resx*

```xml
﻿<?xml version="1.0" encoding="utf-8"?>
<!--
    VS SDK Notes: This resx file contains the resources that will be consumed from your package by Visual Studio.
    For example, Visual Studio will attempt to load resource '400' from this resource stream when it needs to
    load your package's icon. Because Visual Studio will always look in the VSPackage.resources stream first for
    resources it needs, you should put additional resources that Visual Studio will load directly into this resx
    file.

    Resources that you would like to access directly from your package in a strong-typed fashion should be stored
    in Resources.resx or another resx file.
-->
<root>
  <!--
    Microsoft ResX Schema

    Version 2.0

    The primary goals of this format is to allow a simple XML format
    that is mostly human readable. The generation and parsing of the
    various data types are done through the TypeConverter classes
    associated with the data types.

    Example:

    ... ado.net/XML headers & schema ...
    <resheader name="resmimetype">text/microsoft-resx</resheader>
    <resheader name="version">2.0</resheader>
    <resheader name="reader">System.Resources.ResXResourceReader, System.Windows.Forms, ...</resheader>
    <resheader name="writer">System.Resources.ResXResourceWriter, System.Windows.Forms, ...</resheader>
    <data name="Name1"><value>this is my long string</value><comment>this is a comment</comment></data>
    <data name="Color1" type="System.Drawing.Color, System.Drawing">Blue</data>
    <data name="Bitmap1" mimetype="application/x-microsoft.net.object.binary.base64">
        <value>[base64 mime encoded serialized .NET Framework object]</value>
    </data>
    <data name="Icon1" type="System.Drawing.Icon, System.Drawing" mimetype="application/x-microsoft.net.object.bytearray.base64">
        <value>[base64 mime encoded string representing a byte array form of the .NET Framework object]</value>
        <comment>This is a comment</comment>
    </data>

    There are any number of "resheader" rows that contain simple
    name/value pairs.

    Each data row contains a name, and value. The row also contains a
    type or mimetype. Type corresponds to a .NET class that support
    text/value conversion through the TypeConverter architecture.
    Classes that don't support this are serialized and stored with the
    mimetype set.

    The mimetype is used for serialized objects, and tells the
    ResXResourceReader how to depersist the object. This is currently not
    extensible. For a given mimetype the value must be set accordingly:

    Note - application/x-microsoft.net.object.binary.base64 is the format
    that the ResXResourceWriter will generate, however the reader can
    read any of the formats listed below.

    mimetype: application/x-microsoft.net.object.binary.base64
    value   : The object must be serialized with
            : System.Runtime.Serialization.Formatters.Binary.BinaryFormatter
            : and then encoded with base64 encoding.

    mimetype: application/x-microsoft.net.object.soap.base64
    value   : The object must be serialized with
            : System.Runtime.Serialization.Formatters.Soap.SoapFormatter
            : and then encoded with base64 encoding.

    mimetype: application/x-microsoft.net.object.bytearray.base64
    value   : The object must be serialized into a byte array
            : using a System.ComponentModel.TypeConverter
            : and then encoded with base64 encoding.
    -->
  <xsd:schema id="root" xmlns="" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
    <xsd:import namespace="http://www.w3.org/XML/1998/namespace" />
    <xsd:element name="root" msdata:IsDataSet="true">
      <xsd:complexType>
        <xsd:choice maxOccurs="unbounded">
          <xsd:element name="metadata">
            <xsd:complexType>
              <xsd:sequence>
                <xsd:element name="value" type="xsd:string" minOccurs="0" />
              </xsd:sequence>
              <xsd:attribute name="name" use="required" type="xsd:string" />
              <xsd:attribute name="type" type="xsd:string" />
              <xsd:attribute name="mimetype" type="xsd:string" />
              <xsd:attribute ref="xml:space" />
            </xsd:complexType>
          </xsd:element>
          <xsd:element name="assembly">
            <xsd:complexType>
              <xsd:attribute name="alias" type="xsd:string" />
              <xsd:attribute name="name" type="xsd:string" />
            </xsd:complexType>
          </xsd:element>
          <xsd:element name="data">
            <xsd:complexType>
              <xsd:sequence>
                <xsd:element name="value" type="xsd:string" minOccurs="0" msdata:Ordinal="1" />
                <xsd:element name="comment" type="xsd:string" minOccurs="0" msdata:Ordinal="2" />
              </xsd:sequence>
              <xsd:attribute name="name" type="xsd:string" use="required" msdata:Ordinal="1" />
              <xsd:attribute name="type" type="xsd:string" msdata:Ordinal="3" />
              <xsd:attribute name="mimetype" type="xsd:string" msdata:Ordinal="4" />
              <xsd:attribute ref="xml:space" />
            </xsd:complexType>
          </xsd:element>
          <xsd:element name="resheader">
            <xsd:complexType>
              <xsd:sequence>
                <xsd:element name="value" type="xsd:string" minOccurs="0" msdata:Ordinal="1" />
              </xsd:sequence>
              <xsd:attribute name="name" type="xsd:string" use="required" />
            </xsd:complexType>
          </xsd:element>
        </xsd:choice>
      </xsd:complexType>
    </xsd:element>
  </xsd:schema>
  <resheader name="resmimetype">
    <value>text/microsoft-resx</value>
  </resheader>
  <resheader name="version">
    <value>2.0</value>
  </resheader>
  <resheader name="reader">
    <value>System.Resources.ResXResourceReader, System.Windows.Forms, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089</value>
  </resheader>
  <resheader name="writer">
    <value>System.Resources.ResXResourceWriter, System.Windows.Forms, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089</value>
  </resheader>
  <assembly alias="System.Windows.Forms" name="System.Windows.Forms, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
  <data name="110" xml:space="preserve">
    <value>HelloWorldCommand Extension</value>
  </data>
  <data name="112" xml:space="preserve">
    <value>HelloWorldCommand Visual Studio Extension Detailed Info</value>
  </data>
  <data name="400" type="System.Resources.ResXFileRef, System.Windows.Forms">
    <value>Resources\HelloWorldCommandPackage.ico;System.Drawing.Icon, System.Drawing, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b03f5f7f11d50a3a</value>
  </data>
</root>
```









