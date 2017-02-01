---
title: ".NET Core 명령줄을 사용하여 프로젝트 구성 및 테스트(SDK Preview 4) | Microsoft 문서"
description: ".NET Core 명령줄을 사용하여 프로젝트 구성 및 테스트(SDK Preview 4)"
keywords: .NET, .NET Core
author: cartermp
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 52ff1be3-d92e-4477-9c84-8c1771e87ab5
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: f3d5ebbac45726e320e5b886dbb6b81259bea36c

---

# <a name="organizing-and-testing-projects-with-the-net-core-command-line-sdk-preview-4"></a>.NET Core 명령줄을 사용하여 프로젝트 구성 및 테스트(SDK Preview 4)

> [!WARNING]
> 이 항목은 Visual Studio 2017 RC - .NET Core Tools Preview 4에 적용됩니다. .NET Core Tools Preview 2 버전의 경우 [명령줄을 사용하여 Windows/Linux/macOS에서 .NET Core 시작](../../tutorials/using-with-xplat-cli.md) 항목을 참조하세요.

이 자습서에서는 [명령줄을 사용하여 Windows/Linux/macOS에서 .NET Core 시작(SDK Preview 4)](./using-with-xplat-cli-msbuild.md)에 따라 간단한 "hello world" 시나리오 이상의 방법을 보여 주며, 잘 구성된 고급 응용 프로그램을 위한 방법을 안내합니다.

## <a name="using-folders-to-organize-code"></a>폴더를 사용하여 코드 구성

작업할 몇 가지 새로운 형식을 도입하려 한다고 가정해 보겠습니다.  이렇게 하려면 파일을 더 추가하고 `Program.cs` 파일에 포함할 수 있는 네임스페이스를 부여하면 됩니다.

```
/MyProject
|__Program.cs
|__AccountInformation.cs
|__MonthlyReportRecords.cs
|__MyProject.csproj
```

프로젝트의 크기가 비교적 작은 경우에는 이 방법이 매우 효과적입니다.  그러나 다양한 데이터 형식 및 여러 레이어가 포함된 더 큰 앱이 있는 경우 항목을 논리적으로 구성해야 할 수 있습니다. 여기에서 폴더를 생각할 수 있습니다.  이 가이드에서 다루는 [NewTypes 샘플 프로젝트](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/NewTypesMsBuild)를 따를 수도 있고, 자신의 파일과 폴더를 만들 수도 있습니다.

시작하려면 프로젝트의 루트 아래에 새 폴더를 만듭니다. `/Model`이 여기서 선택되었습니다.

```
/NewTypes
|__/Model
|__Program.cs
|__NewTypes.csproj
```

이제 몇 가지 새로운 형식을 폴더에 추가합니다.

```
/NewTypes
|__/Model
   |__AccountInformation.cs
   |__MonthlyReportRecords.cs
|__Program.cs
|__NewTypes.csproj
```

이제 마치 이들이 동일한 디렉터리의 파일인 것처럼, `Program.cs`에 포함할 수 있도록 모든 파일에 동일한 네임스페이스를 부여합니다.

### <a name="example-pet-types"></a>예제: Pet 형식

이 예제에서는 새로운 두 형식 `Dog` 및 `Cat`을 만들고 인터페이스 `IPet`을 구현합니다.

폴더 구조:

```
/NewTypes
|__/Pets
   |__Dog.cs
   |__Cat.cs
   |__IPet.cs
|__Program.cs
|__NewTypes.csproj
```

`IPet.cs`:
```csharp
using System;

namespace Pets
{
    public interface IPet
    {
        string TalkToOwner();
    }
}
```

`Dog.cs`:
```csharp
using System;

namespace Pets
{
    public class Dog : IPet
    {
        public string TalkToOwner() => "Woof!";
    }
}
```

`Cat.cs`:
```csharp
using System;

namespace Pets
{
    public class Cat : IPet
    {
        public string TalkToOwner() => "Meow!";
    }
}
```

`Program.cs`:
```csharp
using System;
using Pets;
using System.Collections.Generic;

namespace ConsoleApplication
{
    public class Program
    {
        public static void Main(string[] args)
        {
            List<IPet> pets = new List<IPet>
            {
                new Dog(),
                new Cat()  
            };
            
            foreach (var pet in pets)
            {
                Console.WriteLine(pet.TalkToOwner());
            }
        }
    }
}
```

`NewTypes.csproj`:
```xml
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />
  
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.0</TargetFramework>
  </PropertyGroup>

  <ItemGroup>
    <Compile Include="**\*.cs" />
    <EmbeddedResource Include="**\*.resx" />
  </ItemGroup>

  <ItemGroup>
    <PackageReference Include="Microsoft.NETCore.App">
      <Version>1.0.1</Version>
    </PackageReference>
    <PackageReference Include="Microsoft.NET.Sdk">
      <Version>1.0.0-alpha-20161104-2</Version>
      <PrivateAssets>All</PrivateAssets>
    </PackageReference>
  </ItemGroup>
  
  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
</Project>
```

이를 실행하면 다음이 가능합니다.

```
$ dotnet restore
$ dotnet run
Woof!
Meow!
```

새로운 pet 형식을 추가하여(예: `Bird`) 이 프로젝트를 확장할 수 있습니다.

## <a name="testing-your-console-app"></a>콘솔 앱 테스트

어떤 지점에 도달하면 프로젝트를 테스트해야 할 수 있습니다.  이 경우 다음 방법을 사용할 수 있습니다.

1. 기존 프로젝트의 모든 소스를 새로운 `src` 폴더로 이동합니다.

   ```
   /Project
   |__/src
   ```

2. `/test` 디렉터리를 만든 다음 `cd`를 사용하여 만든 디렉터리로 이동합니다.

   ```
   /Project
   |__/src
   |__/test
   ```

3. `dotnet new -t Xunittest` 명령으로 디렉터리를 초기화합니다. 여기에서는 Xunit을 가정하지만 `Xunittest`를 `Mstest`로 대체하여 MS 테스트를 사용할 수도 있습니다.
   
### <a name="example-extending-the-newtypes-project"></a>예제: NewTypes 프로젝트 확장

프로젝트 시스템이 준비되었으므로 이제 테스트 프로젝트를 만들고 테스트 작성을 시작할 수 있습니다. 여기서부터 이 가이드는 [샘플 Types 프로젝트](https://github.com/dotnet/docs/tree/master/samples/core/console-apps/NewTypesMsBuild)를 사용하고 확장합니다. 또한 [Xunit](https://xunit.github.io/) 테스트 프레임워크를 사용합니다. 이 가이드의 과정을 따라 해도 되고, 테스트와 함께 고유한 다중 프로젝트 시스템을 만들어도 됩니다.

전체 프로젝트 구조는 다음과 같습니다.

```
/NewTypes
|__/src
   |__/NewTypes
      |__/Pets
         |__Dog.cs
         |__Cat.cs
         |__IPet.cs
      |__Program.cs
      |__NewTypes.csproj
|__/test
   |__NewTypesTests
      |__PetTests.cs
      |__NewTypesTests.csproj
```

테스트 프로젝트에 있는지 확인해야 할 두 가지가 있습니다.

1. 다음이 포함된 올바른 `NewTypesTests.csproj` 파일

   * 다음에 대한 참조:`xunit`
   * 다음에 대한 참조:`dotnet-test-xunit`
   * 테스트 중인 코드에 해당하는 네임스페이스에 대한 참조

   이 파일은 `NewTypesTests` 디렉터리의 명령줄에서 `dotnet new -t Xunittest`를 간단히 수행한 다음 `NewTypes` 프로젝트에 프로젝트 참조를 추가하여 작성할 수 있습니다.

    `NewTypesTests/NewTypesTests.csproj`:
    ```xml
    <Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
      <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />

      <PropertyGroup>
        <OutputType>Exe</OutputType>
        <TargetFramework>netcoreapp1.0</TargetFramework>
      </PropertyGroup>

      <ItemGroup>
        <Compile Include="**\*.cs" />
        <EmbeddedResource Include="**\*.resx" />
      </ItemGroup>

      <ItemGroup>
        <PackageReference Include="Microsoft.NETCore.App">
          <Version>1.0.1</Version>
        </PackageReference>
        <PackageReference Include="Microsoft.NET.Sdk">
          <Version>1.0.0-alpha-20161104-2</Version>
          <PrivateAssets>All</PrivateAssets>
        </PackageReference>
        <PackageReference Include="Microsoft.NET.Test.Sdk">
          <Version>15.0.0-preview-20161024-02</Version>
        </PackageReference>
        <PackageReference Include="xunit">
          <Version>2.2.0-beta3-build3402</Version>
        </PackageReference>
        <PackageReference Include="xunit.runner.visualstudio">
          <Version>2.2.0-beta4-build1188</Version>
        </PackageReference>
        <ProjectReference Include="../../src/NewTypes/NewTypes.csproj"/>
      </ItemGroup>

      <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
    </Project>
    ```

2. Xunit 테스트 클래스

    `PetTests.cs`: 
    ```csharp
    using System;
    using Xunit;
    using Pets;
    public class PetTests
    {
        [Fact]
        public void DogTalkToOwnerTest()
        {
            string expected = "Woof!";
            string actual = new Dog().TalkToOwner();
            
            Assert.Equal(expected, actual);
        }
        
        [Fact]
        public void CatTalkToOwnerTest()
        {
            string expected = "Meow!";
            string actual = new Cat().TalkToOwner();
            
            Assert.Equal(expected, actual);
        }
    }
    ```
   
이제 테스트를 실행할 수 있습니다!  [`dotnet test`](../tools/dotnet-test.md) 명령은 프로젝트에 지정된 Test Runner를 실행합니다. 최상위 디렉터리에서 시작해야 합니다.
 
```
$ cd test/NewTypesTests
$ dotnet restore
$ dotnet test
```
 
출력은 다음과 같습니다.
 
```
xUnit.net .NET CLI test runner (64-bit win10-x64)
  Discovering: NewTypesTests
  Discovered:  NewTypesTests
  Starting:    NewTypesTests
  Finished:    NewTypesTests
=== TEST EXECUTION SUMMARY ===
   NewTypesTests  Total: 2, Errors: 0, Failed: 0, Skipped: 0, Time: 0.144s
SUMMARY: Total: 1 targets, Passed: 1, Failed: 0.
```



<!--HONumber=Jan17_HO3-->


