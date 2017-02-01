---
title: ".NET Core CLI 확장성 모델 | Microsoft 문서"
description: ".NET Core CLI 확장성 모델"
keywords: "CLI, 확장성, 사용자 지정 명령, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 11/13/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fffc3400-aeb9-4c07-9fea-83bc8dbdcbf3
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: 7df8b8bd4ae96a344b279a2673906962beaf29a4

---

# <a name="net-core-cli-extensibility-model-tooling-preview-4"></a>.NET Core CLI 확장성 모델(Tooling Preview 4)

> [!WARNING]
> 이 항목은 Visual Studio 2017 RC - .NET Core Tools Preview 4에 적용됩니다. .NET Core Tools Preview 2 버전의 경우 [.NET Core CLI 확장성 모델](../../tools/dotnet-test.md) 항목을 참조하세요.

## <a name="overview"></a>개요
이 문서에서는 CLI 도구를 확장하는 주요 방법 및 각 방법을 구동하는 시나리오에 대해 설명합니다. 도구를 사용하는 방법에 대해 간략하게 설명할 뿐만 아니라 두 종류의 도구를 빌드하는 방법에 대한 간단한 메모를 제공합니다. 

## <a name="how-to-extend-cli-tools"></a>CLI 도구를 확장하는 방법
Preview 4 CLI 도구는 세 가지 주요 방법으로 확장할 수 있습니다.

1. 프로젝트 단위로 NuGet 패키지 사용
2. 사용자 지정 대상을 사용하여 NuGet 패키지 사용  
3. 시스템의 PATH 사용

위에서 간략하게 설명한 세 가지 확장성 메커니즘은 전체를 사용하거나, 하나만 사용하거나, 조합해서 사용할 수 있습니다. 선택하는 방법은 확장을 통해 달성하려는 목표에 따라 크게 달라집니다.

## <a name="per-project-based-extensibility"></a>프로젝트 단위 기반 확장성
프로젝트 단위 도구는 NuGet 패키지로 배포되는 [프레임워크 종속 배포](../deploying/index.md)입니다. 도구는 해당 도구를 참조하고 도구가 복원되는 프로젝트의 컨텍스트에서만 사용할 수 있습니다. 프로젝트 컨텍스트 외부(예: 프로젝트를 포함하는 디렉터리 외부)에서 호출하면 명령을 찾을 수 없기 때문에 실패합니다.

이러한 도구는 빌드 서버에도 완벽한데, 프로젝트 파일 외부의 항목이 필요하지 않기 때문입니다. 빌드 프로세스에서는 빌드하는 프로젝트에 대해 복원을 실행하므로 도구를 사용할 수 있습니다. F#과 같은 언어 프로젝트도 이 범주에 속합니다. 결국 각 프로젝트는 하나의 특정 언어로만 작성할 수 있습니다. 

마지막으로 이 확장성 모델에서는 프로젝트의 빌드된 출력에 액세스해야 하는 도구를 만들 수 있습니다. 예를 들어 [ASP.NET](https://www.asp.net/) MVC 응용 프로그램의 다양한 Razor 보기 도구는 이 범주에 속합니다. 

### <a name="consuming-per-project-tools"></a>프로젝트 단위 도구 사용
이러한 도구를 사용하려면 사용할 도구 각각에 대한 `<DotNetCliToolReference>` 요소를 프로젝트 파일에 추가해야 합니다. `<DotNetCliToolReference>` 요소 내에서는 도구가 상주하는 패키지를 참조하고 필요한 버전을 지정합니다. `dotnet restore`를 실행하면 도구 및 해당 종속성이 복원됩니다. 

프로젝트의 빌드 출력을 로드하여 실행해야 하는 도구의 경우 일반적으로 프로젝트 파일의 일반 종속성 아래에 나열되는 다른 종속성이 있습니다. CLI의 Preview 4 버전에서는 빌드 엔진으로 MSBuild를 사용하기 때문에 전반적인 빌드 프로세스에서 포함될 수 있는 방식으로 이러한 도구 부분을 사용자 지정 MSBuild 대상 및 작업으로 작성하는 것이 좋습니다. 또한 빌드를 통해 생성된 데이터를 모두 쉽게 가져올 수 있습니다(예: 출력 파일 위치, 빌드 중인 현재 구성 등). Preview 4에서 이 정보는 모두 어떤 대상에서도 읽을 수 있는 MSBuild 속성 집합이 됩니다. 이 문서의 뒷부분에 나오는 NuGet을 사용하여 사용자 지정 대상을 추가하는 방법을 살펴보겠습니다. 

간단한 도구를 추가하는 예제를 검토해 보겠습니다. 간단한 프로젝트에 도구만 추가합니다. 다음은 NuGet 패키지에서 지정된 API를 검색할 수 있는 `dotnet-api-search`라는 예제 명령이 지정된 경우 해당 도구를 사용하는 콘솔 응용 프로그램의 프로젝트 파일입니다.


```xml
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1/TargetFramework>
    <VersionPrefix>1.0.0</VersionPrefix>
  </PropertyGroup>
  <ItemGroup>
    <Compile Include="**\*.cs" />
    <EmbeddedResource Include="**\*.resx" />
  </ItemGroup>
  <ItemGroup>
    <PackageReference Include="Microsoft.NETCore.App">
      <Version>1.1.0</Version>
    </PackageReference>
    <PackageReference Include="Microsoft.NET.Sdk">
      <Version>1.0.0-alpha-20161102-2</Version>
      <PrivateAssets>All</PrivateAssets>
    </PackageReference>
  </ItemGroup>

  <!-- The tools reference -->
  <ItemGroup>
    <DotNetCliToolReference Include="dotnet-api-search">
      <Version></Version>
    </DotNetCliToolReference>
  </ItemGroup>

  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
</Project>
```

`<DotNetCliToolReference>` 요소는 `<PackageReference>` 요소와 비슷한 방식으로 구성됩니다. 이 노드에는 도구와 최소 버전을 포함하는 패키지의 패키지 ID가 필요합니다. 

### <a name="building-tools"></a>도구 빌드
앞에서 설명한 대로 도구는 단순히 이식 가능한 콘솔 응용 프로그램입니다. 모든 콘솔 응용 프로그램을 빌드하는 것처럼 도구도 빌드합니다. 도구를 빌드한 후에는 [`dotnet pack`](dotnet-pack.md) 명령을 사용하여 코드, 종속성에 대한 정보 등을 포함하는 NuGet 패키지(nupkg)를 만듭니다. 패키지 이름은 작성자가 원하는 대로 지정할 수 있지만 응용 프로그램 내부 실제 도구 이진은 `dotnet-<command>`의 규칙을 준수해야 `dotnet`을 호출할 수 있습니다. 

Preview 4 비트에서 `dotnet pack` 명령은 도구를 실행하는 데 필요한 `runtimeconfig.json` 파일을 압축하지 않습니다. 이 파일을 패키징하는 방법에는 두 가지 옵션이 있습니다.

1. `nuspec` 파일을 만들고 Preview 4 CLI에서 새로 제공되는 `dotnet nuget pack` 명령을 사용하여 파일 포함
2. 프로젝트 파일의 `<ItemGroup>`에서 새로운 `<Content>` 요소를 사용하여 파일을 수동으로 포함

nuspec 파일을 사용하는 것은 이 문서의 범위를 벗어나지만 [공식 NuGet 문서](https://docs.microsoft.com/nuget/create-packages/creating-a-package#the-role-and-structure-of-the-nuspec-file)에서 유용한 정보를 다양하게 확인할 수 있습니다. 두 번째 방식을 선택하는 경우 `csproj` 파일 예제와 아래와 같이 구성하는 방식을 확인할 수 있습니다.

```xml
  <ItemGroup>
    <Content Include="$(OutputPath)\*.runtimeconfig.json">
      <Pack>true</Pack>
      <PackagePath>lib\$(TargetFramework)</PackagePath>
    </Content>
  </ItemGroup>
```

이 `<ItemGroup>`은 `dotnet pack` 명령을 사용하여 빌드 출력 디렉터리(`$(OutputPath)` 변수에 지정됨)에서 임의의 `runtimeconfig.json` 파일을 압축한 다음 빌드된 대상 프레임워크에 대한 `lib` 폴더로 배치합니다. 빌드된 대상 프레임워크는 MSBuild 속성을 사용하여 출력 경로로 비슷하게 지정됩니다. 이렇게 설정되면 그 결과로 도구 nupkg 파일에 도구 실행에 필요한 모든 항목이 포함됩니다.

도구는 이식 가능한 응용 프로그램이므로 도구 사용자가 도구를 실행하려면 도구가 빌드된 버전의 .NET Core 라이브러리가 있어야 합니다. 도구에서 사용하고 .NET Core 라이브러리 내에서 포함되지 않은 다른 모든 종속성은 NuGet 캐시에서 복원되고 배치됩니다. 따라서 전체 도구는 .NET Core 라이브러리의 어셈블리뿐만 아니라 NuGet 캐시의 어셈블리를 사용하여 실행됩니다. 

이러한 종류의 도구에는 해당 도구를 사용하는 프로젝트의 종속성 그래프와 완전히 구분되는 종속성 그래프가 있습니다. 복원 프로세스에서는 먼저 프로젝트의 종속성을 복원한 다음 각 도구 및 해당 종속성을 복원합니다. 

보다 풍부한 예제 및 다양한 조합은 [.NET Core CLI 리포지토리](https://github.com/dotnet/cli/tree/rel/1.0.0-preview2/TestAssets/TestProjects)에서 확인할 수 있습니다. 동일한 리포지토리에서 [사용된 도구의 구현](https://github.com/dotnet/cli/tree/rel/1.0.0-preview2/TestAssets/TestPackages)도 확인할 수 있습니다. 

### <a name="custom-targets"></a>사용자 지정 대상
NuGet에서는 현재 잠시 동안 사용자 지정 MSBuild 대상 및 속성 파일을 패키지할 수 있으며, [NuGet 설명서 사이트](https://docs.microsoft.com/nuget/create-packages/creating-a-package#including-msbuild-props-and-targets-in-a-package)에서 이에 대한 공식 설명서를 확인할 수 있습니다. CLI에서 MSBuild를 사용하는 것으로 변환됨에 따라 확장성에 대한 동일한 메커니즘이 .NET Core 프로젝트에 적용됩니다. 빌드 프로세스를 확장하거나 빌드 프로세스에서 생성된 파일과 같은 아티팩트에 액세스하거나 빌드 호출 시 구성을 검사하려는 경우 이 유형의 확장성을 사용하게 됩니다. 

참조를 위해 아래 샘플 대상의 프로젝트 파일이 표시됩니다. 다음은 패키지할 항목을 지정하라는 `dotnet pack` 명령에 대해 새로운 `csproj` 구문을 사용하여 대상 파일과 어셈블리를 패키지 내부의 `build` 폴더에 배치하는 방법을 보여 줍니다. 아래의 `<ItemGroup>`에는 "dotnet 팩 지침"으로 설정된 `Label` 속성이 있습니다. 

```xml
<Project ToolsVersion="15.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <Import Project="$(MSBuildExtensionsPath)\$(MSBuildToolsVersion)\Microsoft.Common.props" />
  <PropertyGroup>
    <Description>Sample Packer</Description>
    <VersionPrefix>0.1.0-preview</VersionPrefix>
    <TargetFramework>netstandard1.3</TargetFramework>
    <DebugType>portable</DebugType>
    <AssemblyName>SampleTargets.PackerTarget</AssemblyName>
  </PropertyGroup>
  <ItemGroup>
    <Compile Include="**\*.cs" Exclude="bin\**;obj\**;**\*.xproj;packages\**" />
    <EmbeddedResource Include="**\*.resx" Exclude="bin\**;obj\**;**\*.xproj;packages\**" />
    <EmbeddedResource Include="Resources\Pkg\dist-template.xml;compiler\resources\**\*" Exclude="bin\**;obj\**;**\*.xproj;packages\**" />
  </ItemGroup>
  <ItemGroup>
    <None Include="build\SampleTargets.PackerTarget.targets" />
  </ItemGroup>
  <ItemGroup Label="dotent pack instructions">
    <Content Include="build\*.targets;$(OutputPath)\*.dll;$(OutputPath)\*.json">
      <Pack>true</Pack>
      <PackagePath>build\</PackagePath>
    </Content>
  </ItemGroup>
  <ItemGroup>
    <PackageReference Include="Microsoft.NET.Sdk">
      <Version>1.0.0-alpha-20161029-1</Version>
      <PrivateAssets>All</PrivateAssets>
    </PackageReference>
    <PackageReference Include="Microsoft.Extensions.DependencyModel">
      <Version>1.0.1-beta-000933</Version>
    </PackageReference>
    <PackageReference Include="Microsoft.Build.Framework">
      <Version>0.1.0-preview-00028-160627</Version>
    </PackageReference>
    <PackageReference Include="Microsoft.Build.Utilities.Core">
      <Version>0.1.0-preview-00028-160627</Version>
    </PackageReference>
    <PackageReference Include="Newtonsoft.Json">
      <Version>9.0.1</Version>
    </PackageReference>
  </ItemGroup>
  <ItemGroup Condition=" '$(TargetFramework)' == 'netstandard1.3' ">
    <PackageReference Include="NETStandard.Library">
      <Version>1.6.0</Version>
    </PackageReference>
  </ItemGroup>
  <ItemGroup />
  <PropertyGroup Condition=" '$(TargetFramework)' == 'netstandard1.3' ">
    <DefineConstants>$(DefineConstants);NETSTANDARD1_3</DefineConstants>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)' == 'Release' ">
    <DefineConstants>$(DefineConstants);RELEASE</DefineConstants>
  </PropertyGroup>
  <Import Project="$(MSBuildToolsPath)\Microsoft.CSharp.targets" />
</Project>
```

사용자 지정 대상을 사용하는 작업은 확장되고 있는 프로젝트 내부 버전과 패키지를 가리키는 `<PackageReference>`를 제공함으로써 수행됩니다. 도구와 달리 사용자 지정 대상 패키지는 사용하는 프로젝트의 종속성 종료 항목에 포함됩니다. 

사용자 지정 대상을 사용하는 작업은 구성하는 방법에 따라 전적으로 달라집니다. 일반적인 MSBuild 대상이므로 지정된 대상에 따라 달라지고, 다른 대상 이후에 실행할 수 있으며 `dotnet msbuild /t:<target-name>` 명령을 사용하여 수동으로 호출할 수도 있습니다. 

그러나 사용자에게 더 나은 사용자 환경을 제공 하려는 경우 프로젝트별 도구 및 사용자 지정 대상을 결합할 수 있습니다. 이 시나리오에서 프로젝트별 도구는 기본적으로 매개 변수가 필요한 항목은 허용하고, 대상을 실행할 필수 `dotnet msbuild` 호출로 변환합니다. 이러한 종류의 시너지 효과는 [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer) 프로젝트의 [MVP Summit 2016 Hackathon 샘플](https://github.com/dotnet/MVPSummitHackathon2016) 리포지토리에서 확인할 수 있습니다. 

### <a name="path-based-extensibility"></a>PATH 기반 확장성
일반적으로 PATH 기반 확장성은 개념적으로 둘 이상의 프로젝트를 포함하는 도구가 필요한 개발 컴퓨터에 사용됩니다. 이 확장 메커니즘의 주요 단점은 도구가 있는 컴퓨터에 연결되어 있다는 점입니다. 따라서 다른 컴퓨터에서 필요한 경우에는 배포해야 합니다.

CLI 도구 집합 확장성의 이 패턴은 매우 간단합니다. [.NET Core CLI 개요](index.md)에서 설명한 대로 `dotnet` 드라이버는 `dotnet-<command>` 규칙에 따라 명명된 모든 명령을 실행할 수 있습니다. 기본 해결 논리에서는 여러 위치를 먼저 검색하고 마지막으로 시스템 PATH를 검색합니다. 요청한 명령이 시스템 PATH에 있고 호출할 수 있는 이진인 경우 `dotnet` 드라이버에서 호출합니다. 

이진은 운영 체제에서 실행할 수 있는 거의 모든 항목이 될 수 있습니다. Unix 시스템에서는 `chmod +x`를 통해 실행 비트를 설정하는 모든 항목을 의미하고, Windows에서는 Windows가 실행 방법을 알고 있는 모든 항목을 의미합니다. 

예를 들어 `dotnet clean` 명령의 매우 간단한 구현을 살펴보겠습니다. `bash`를 사용하여 이 명령을 구현합니다. 이 명령은 현재 디렉터리에서 `bin/` 및 `obj/` 디렉터리를 삭제하기만 합니다. `--lock` 인수가 전달되면 `project.lock.json` 파일도 삭제합니다. 전체 명령은 다음과 같습니다. 

```bash
#!/bin/bash

# Delete the bin and obj dirs
rm -rf bin/ obj/

LOCK_FILE=$1
if [[ "$LOCK_FILE" = "--lock" ]]; then
    rm project.lock.json
fi


echo "Cleaning complete..."
```

MacOS에서는 이 스크립트를 `dotnet-clean`으로 저장하고 `chmod +x dotnet-clean`을 사용하여 실행 파일 비트를 설정할 수 있습니다. 그런 다음 `ln -s dotnet-clean /usr/local/bin/` 명령을 사용하여 `/usr/local/bin`에 바로 가기 링크를 만들 수 있습니다. 그러면 `dotnet clean` 구문을 사용하여 정리 명령을 호출할 수 있습니다. 앱을 만들고 해당 앱에서 `dotnet build`를 실행한 다음 `dotnet clean`을 실행하여 테스트할 수 있습니다. 

## <a name="conclusion"></a>결론
.NET Core CLI 도구는 세 가지 주요 확장 포인트를 허용합니다. 프로젝트 단위 도구는 프로젝트의 컨텍스트 내에 포함되지만 복원을 통해 간편한 설치를 허용합니다. 사용자 지정 대상을 사용하면 사용자 지정 작업을 사용하여 빌드 프로세스를 쉽게 확장할 수 있습니다. PATH 기반 도구는 단일 컴퓨터에서 사용할 수 있는 일반적인 프로젝트 간 도구에 적합합니다. 




<!--HONumber=Jan17_HO3-->


