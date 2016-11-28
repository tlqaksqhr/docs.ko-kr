---
title: "dotnet-test 명령 | .NET Core SDK"
description: "`dotnet test` 명령은 지정된 프로젝트에서 단위 테스트를 실행하는 데 사용됩니다."
keywords: "dotnet-test, CLI, CLI 명령, .NET Core"
author: mairaw
manager: wpickett
ms.date: 10/07/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 3a0fa917-eb0a-4d7e-9217-d06e65455675
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: 66c9f949980612f6e21b6d441c004cc09f4eb7d3

---

#<a name="dotnet-test"></a>dotnet-test

## <a name="name"></a>이름

`dotnet-test` - .NET 테스트 드라이버

## <a name="synopsis"></a>개요

`dotnet test [project] [--help] 
    [--settings] [--listTests] [--testCaseFilter] 
    [--testAdapterPath] [--logger] 
    [--configuration] [--output] [--framework] [--diag]
    [--noBuild]`  

## <a name="description"></a>설명

`dotnet test` 명령은 지정된 프로젝트에서 단위 테스트를 실행하는 데 사용됩니다. 단위 테스트는 단위 테스트 프레임워크(예: NUnit 또는 xUnit) 및 해당 단위 테스트 프레임워크에 대한 dotnet Test Runner에 종속되어 있는 클래스 라이브러리 프로젝트입니다. 이러한 프로젝트는 NuGet 패키지로 패키지되고 프로젝트에 대한 일반 종속성으로 복원됩니다.

테스트 프로젝트에서는 Test Runner도 지정해야 합니다. 다음의 예제 프로젝트 파일에서 볼 수 있듯이 일반적인 `<PackageReference>` 요소를 사용하여 지정합니다.

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
  </ItemGroup>

  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
</Project>
```

## <a name="options"></a>옵션

`[project]`
    
테스트 프로젝트에 대한 경로를 지정합니다. 생략하면 현재 디렉터리로 기본 설정됩니다.

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.

`-s | --settings <SETTINGS_FILE>`

테스트를 실행할 때 사용할 설정입니다. 

`-lt | --listTests`

현재 프로젝트에서 검색된 테스트를 모두 나열합니다. 

`-tcf | --testCaseFilter <EXPRESSION>`

지정된 식을 사용하여 현재 프로젝트의 테스트를 필터링합니다. 

`-tap | --testAdapterPath <TEST_ADAPTER_PATH>`

이 테스트 실행에 지정된 경로에서 사용자 지정 테스트 어댑터를 사용합니다. 

`--logger <LOGGER>`

테스트 결과에 대해 로거를 지정합니다. 

`-c|--configuration <Debug|Release>`

빌드할 구성입니다. 기본값은 `Release`입니다. 

`-o|--output [OUTPUT_DIRECTORY]`

실행할 이진 파일을 찾을 디렉터리입니다.

`-f|--framework [FRAMEWORK]`

특정 프레임워크에 대한 테스트 이진 파일을 찾습니다.

`-r|--runtime [RUNTIME_IDENTIFIER]`

지정된 런타임에 대한 테스트 이진 파일을 찾습니다.

`--noBuild` 

텍스트 프로젝트를 실행하기 전에 빌드하지 않습니다. 

`-d | --diag <DIAGNOSTICS_FILE>`

테스트 플랫폼에 대한 진단 모드를 사용하도록 설정하고 지정된 파일에 진단 메시지를 기록합니다. 

## <a name="examples"></a>예제

현재 디렉터리에 있는 프로젝트에서 테스트를 실행합니다.

`dotnet test` 

test1 프로젝트에서 테스트를 실행합니다.

`dotnet test ~/projects/test1/test1.csproj` 

## <a name="see-also"></a>참고 항목

[프레임워크](../../../standard/frameworks.md)

[RID(런타임 식별자) 카탈로그](../../rid-catalog.md)



<!--HONumber=Nov16_HO3-->


