---
title: "Visual Studio를 사용한 .NET Core 앱 배포 | Microsoft Docs"
description: "Visual Studio를 사용한 .NET Core 앱 배포에 대해 알아봅니다."
keywords: ".NET, .NET Core, .NET Core 배포"
author: rpetrusha
ms.author: ronpet
ms.date: 04/18/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 01049a21-fd50-4419-9ab2-0e4a2e091050
ms.translationtype: Human Translation
ms.sourcegitcommit: 3ffe3909902659a22cb25bac6dc5aaa4f5b9fde2
ms.openlocfilehash: c6fe1813f0d09207c6730fc5dce682647e25eb03
ms.contentlocale: ko-kr
ms.lasthandoff: 05/13/2017

---

# <a name="deploying-net-core-apps-with-visual-studio"></a>Visual Studio를 사용하여 .NET Core 앱 배포

.NET Core 응용 프로그램은 응용 프로그램 이진을 포함하지만 대상 시스템에 .NET Core가 있는지 여부에 따라 달라지는 *프레임워크 종속 배포* 또는 응용 프로그램과 .NET Core 이진을 모두 포함하는 *자체 포함 배포*로 배포할 수 있습니다. .NET Core 응용 프로그램 배포 개요는 [.NET Core 응용 프로그램 배포](index.md)를 참조하세요.

다음 섹션에서는 Microsoft Visual Studio를 사용하여 다음과 같은 종류의 배포를 만드는 방법을 보여 줍니다.

- 프레임워크 종속 배포
- 타사 종속성이 있는 프레임워크 종속 배포
- 자체 포함 배포
- 타사 종속성이 있는 자체 포함 배포

Visual Studio를 사용하여 .NET Core 응용 프로그램을 개발하는 방법에 대한 자세한 내용은 [Windows의 .NET Core에 대한 필수 조건](../windows-prerequisites.md#prerequisites-with-visual-studio-2017)을 참조하세요.

## <a name="framework-dependent-deployment"></a>프레임워크 종속 배포

타사 종속성이 없는 프레임워크 종속 배포에는 앱의 빌드, 테스트 및 게시만 포함됩니다. C#으로 작성된 간단한 예제에서는 이 프로세스를 보여 줍니다.  

1. 프로젝트를 만듭니다.

   **파일** > **새로 만들기** > **프로젝트**를 선택합니다. **새 프로젝트** 대화 상자의 **설치됨** 프로젝트 형식 창에서 **.NET Core**를 선택한 다음 가운데 창에서 **콘솔 앱(.NET Core)** 템플릿을 선택합니다. **이름** 텍스트 상자에 "FDD" 등의 프로젝트 이름을 입력합니다. **확인** 단추를 선택합니다.

1. 응용 프로그램의 소스 코드를 추가합니다.

   편집기에서 *Program.cs* 파일을 열고 자동 생성된 코드를 다음 코드로 바꿉니다. 텍스트를 입력하라는 메시지가 표시된 다음 사용자가 입력한 개별 단어가 표시됩니다. 정규식 `\w+`를 사용하여 입력 테스트의 단어를 구분합니다.

   [!code-cs[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]

1. 앱의 디버그 빌드를 만듭니다.

   **빌드** > **솔루션 빌드**를 선택합니다. **디버그** > **디버깅 시작**을 선택하여 응용 프로그램의 디버그 빌드를 컴파일하고 실행할 수도 있습니다.

1. 앱을 배포합니다.

   프로그램을 디버그하고 테스트한 후에는 앱과 함께 배포할 파일을 만듭니다. Visual Studio에서 게시하려면 다음을 수행합니다.

      1. 도구 모음에서 솔루션 구성을 **디버그**에서 **릴리스**로 변경하여 앱의 릴리스(디버그 아님) 버전을 빌드합니다.

      1. **솔루션 탐색기**에서 프로젝트(솔루션 아님)를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다.

      1. **게시** 탭에서 **게시**를 선택합니다. Visual Studio에서 응용 프로그램을 구성하는 파일을 로컬 파일 시스템에 작성합니다.

      1. 이제 **게시** 탭에 단일 프로필 **FolderProfile**이 표시됩니다. 프로필의 구성 설정이 탭의 **요약** 섹션에 표시됩니다.

   결과 파일은 프로젝트 *.\bin\release* 하위 디렉터리의 하위 디렉터리에 있는 `PublishOutput`이라는 디렉터리에 배치됩니다.

게시 프로세스에서는 응용 프로그램의 파일과 함께 앱에 대한 디버깅 정보를 포함하는 프로그램 데이터베이스(.pdb) 파일을 내보냅니다. 이 파일은 주로 예외 디버그에 유용합니다. 응용 프로그램 파일과 함께 패키지하지 않도록 선택할 수 있습니다. 하지만 앱의 릴리스 빌드를 디버그하려는 경우 파일을 저장해야 합니다.

응용 프로그램 파일의 전체 집합을 원하는 방식으로 배포합니다. 예를 들어 Zip 파일로 패키지하거나, 간단한 `copy` 명령을 사용하거나, 선택한 설치 패키지와 함께 배포할 수 있습니다. 설치되고 나면 사용자가 `dotnet` 명령을 사용하고 `dotnet fdd.dll` 등의 응용 프로그램 파일 이름을 제공하여 응용 프로그램을 실행할 수 있습니다.

설치 관리자는 응용 프로그램 이진 외에도 공유 프레임워크 설치 관리자를 번들로 제공하거나 응용 프로그램 설치의 일부로 필수 조건을 확인해야 합니다.  공유 프레임워크 설치는 시스템 수준이므로 관리자/루트 액세스 권한이 필요합니다.

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a>타사 종속성이 있는 프레임워크 종속 배포

하나 이상의 타사 종속성이 있는 프레임워크 종속 배포를 배포하려면 프로젝트에서 모든 종속성을 사용할 수 있어야 합니다. 다음 추가 단계를 수행해야 앱을 빌드할 수 있습니다.

1. **NuGet 패키지 관리자**를 사용하여 NuGet 패키지에 대한 참조를 프로젝트에 추가하고, 시스템에서 패키지를 사용할 수 없는 경우 패키지를 설치합니다. 패키지 관리자를 열려면 **도구** > **NuGet 패키지 관리자** > **솔루션용 NuGet 패키지 관리**를 선택합니다.

1. `Newtonsoft.Json`이 시스템에 설치되어 있는지 확인하고, 설치되지 않은 경우 설치합니다. **설치됨** 탭에 시스템에 설치된 NuGet 패키지가 표시됩니다. `Newtonsoft.Json`이 탭에 표시되지 않는 경우 **찾아보기** 탭을 선택하고 검색 상자에 "Newtonsoft.Json"을 입력합니다. `Newtonsoft.Json`을 선택하고 오른쪽 창에서 해당 프로젝트를 선택한 후 **설치**를 선택합니다.

1. `Newtonsoft.Json`이 시스템에 이미 설치되어 있는 경우 **솔루션용 패키지 관리** 탭의 오른쪽 창에서 해당 프로젝트를 선택하여 프로젝트에 추가합니다.

타사 종속성이 있는 프레임워크 종속 배포는 타사 종속성만큼만 이식 가능합니다. 예를 들어 타사 라이브러리에서 macOS를 지원하는 경우 Windows 시스템에 앱을 이식할 수 없습니다. 이러한 현상은 타사 종속성 자체가 네이티브 코드에 종속된 경우에 발생합니다. 관련된 좋은 예로 [libuv](https://github.com/libuv/libuv)에 대한 기본 종속성이 필요한 [Kestrel 서버](http://docs.microsoft.com/aspnet/core/fundamentals/servers/kestrel)가 있습니다. 이런 종류의 타사 종속성이 있는 응용 프로그램에 대해 FDD를 만들면 게시된 출력에는 기본 종속성에서 지원하고 NuGet 패키지에 있는 각 [RID(런타임 식별자)](../rid-catalog.md#what-are-rids)에 대한 폴더가 포함됩니다.

## <a name="simpleSelf"></a> 타사 종속성이 없는 자체 포함 배포

타사 종속성이 없는 자체 포함 배포에는 프로젝트 만들기, *csproj* 파일 수정, 앱 빌드, 테스트 및 게시가 포함됩니다. C#으로 작성된 간단한 예제에서는 이 프로세스를 보여 줍니다. 

1. 프로젝트를 만듭니다.

   **파일** > **새로 만들기** > **프로젝트**를 선택합니다. **새 프로젝트 추가** 대화 상자의 **설치됨** 프로젝트 형식 창에서 **.NET Core**를 선택한 다음 가운데 창에서 **콘솔 앱(.NET Core)** 템플릿을 선택합니다. **이름** 텍스트 상자에 "SCD" 등의 프로젝트 이름을 입력하고 **확인** 단추를 선택합니다.

1. 응용 프로그램의 소스 코드를 추가합니다.

   편집기에서 *Program.cs* 파일을 열고 자동 생성된 코드를 다음 코드로 바꿉니다. 텍스트를 입력하라는 메시지가 표시된 다음 사용자가 입력한 개별 단어가 표시됩니다. 정규식 `\w+`를 사용하여 입력 테스트의 단어를 구분합니다.

   [!code-cs[deployment#1](../../../samples/snippets/core/deploying/deployment-example.cs)]

1. 앱의 대상 플랫폼을 정의합니다.

   1. **솔루션 탐색기**에서 해당 프로젝트(솔루션 아님)를 마우스 오른쪽 단추로 클릭하고 **SCD.csproj 편집**을 선택합니다.

   1. *csproj* 파일의 `<PropertyGroup>` 섹션에서 앱의 대상 플랫폼을 정의하는 `<RuntimeIdentifiers>` 태그를 만들고 각 대상 플랫폼의 RID(런타임 식별자)를 지정합니다. RID를 구분하려면 세미콜론도 추가해야 합니다. 런타임 식별자 목록은 [런타임 식별자 카탈로그](../rid-catalog.md)를 참조하세요. 

   예를 들어 다음 예에서는 앱이 64비트 Windows 10 운영 체제 및 64비트 OS X 버전 10.11 운영 체제에서 실행됨을 나타냅니다.

```xml
<PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
</PropertyGroup>
```
   `<RuntimeIdentifiers>` 요소는 *csproj* 파일에 있는 `<PropertyGroup>`으로 이동할 수 있습니다. 전체 샘플 *csproj* 파일은 이 섹션의 뒷부분에 나옵니다.

1. 앱의 디버그 빌드를 만듭니다.

   **빌드** > **솔루션 빌드**를 선택합니다. **디버그** > **디버깅 시작**을 선택하여 응용 프로그램의 디버그 빌드를 컴파일하고 실행할 수도 있습니다.

1. 앱을 게시합니다.

   프로그램을 디버그하고 테스트한 후에는 각 대상 플랫폼에 대해 앱과 함께 배포할 파일을 만듭니다.

   Visual Studio에서 앱을 게시하려면 다음을 수행합니다.

      1. 도구 모음에서 솔루션 구성을 **디버그**에서 **릴리스**로 변경하여 앱의 릴리스(디버그 아님) 버전을 빌드합니다.

      1. **솔루션 탐색기**에서 프로젝트(솔루션 아님)를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다. 

      1. **게시** 탭에서 **게시**를 선택합니다. Visual Studio에서 응용 프로그램을 구성하는 파일을 로컬 파일 시스템에 작성합니다.

      1. 이제 **게시** 탭에 단일 프로필 **FolderProfile**이 표시됩니다. 프로필의 구성 설정이 탭의 **요약** 섹션에 표시됩니다. **대상 런타임**은 게시된 런타임을 식별하고, **대상 위치**는 자체 포함 배포의 파일이 작성된 위치를 식별합니다.

      1. Visual Studio는 기본적으로 게시된 모든 파일을 단일 디렉터리에 작성합니다. 편의상, 각 대상 런타임에 대해 별도 프로필을 만들고 게시된 파일을 플랫폼별 디렉터리에 배치하는 것이 좋습니다. 이렇게 하려면 각 대상 플랫폼에 대해 별도 게시 프로필을 만들어야 합니다. 따라서 이제 다음을 수행하여 각 플랫폼용 응용 프로그램을 다시 빌드합니다.

         1. **게시** 대화 상자에서 **새 프로필 만들기**를 선택합니다.

         1. **게시 대상 선택** 대화 상자에서 **폴더 선택** 위치를 *bin\Release\PublishOutput\win10-x64*로 변경합니다. **확인**을 선택합니다.

         1. 프로필 목록에서 새 프로필(**FolderProfile1**)을 선택하고, **대상 런타임**이 `win10-x64`인지 확인합니다. 아닌 경우 **설정**을 선택합니다. **프로필 설정** 대화 상자에서 **대상 런타임**을 `win10-x64`로 변경하고 **저장**을 선택합니다. 그렇지 않으면 **취소**를 선택합니다.

         1. **게시**를 선택하여 64비트 Windows 10 플랫폼용 앱을 게시합니다.

         1. 앞의 단계를 다시 수행하여 `osx.10.11-x64` 플랫폼용 프로필을 만듭니다. **대상 위치**는 *bin\Release\PublishOutput\osx.10.11-x64*이고, **대상 런타임**은 `osx.10.11-x64`입니다. Visual Studio에서 이 프로필에 할당하는 이름은 **FolderProfile2**입니다.

      각 대상 위치에는 앱을 시작하는 데 필요한 전체 파일 집합(앱 파일 및 모든 .NET Core 파일)이 포함됩니다.

게시 프로세스에서는 응용 프로그램의 파일과 함께 앱에 대한 디버깅 정보를 포함하는 프로그램 데이터베이스(.pdb) 파일을 내보냅니다. 이 파일은 주로 예외 디버그에 유용합니다. 응용 프로그램 파일과 함께 패키지하지 않도록 선택할 수 있습니다. 하지만 앱의 릴리스 빌드를 디버그하려는 경우 파일을 저장해야 합니다.

게시된 파일을 원하는 방식으로 배포합니다. 예를 들어 Zip 파일로 패키지하거나, 간단한 `copy` 명령을 사용하거나, 선택한 설치 패키지와 함께 배포할 수 있습니다.

다음은 이 프로젝트에 대한 전체 *csproj* 파일입니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

## <a name="self-contained-deployment-with-third-party-dependencies"></a>타사 종속성이 있는 자체 포함 배포

하나 이상의 타사 종속성이 있는 자체 포함 배포에는 종속성 추가가 포함됩니다. 다음 추가 단계를 수행해야 앱을 빌드할 수 있습니다.

1. **NuGet 패키지 관리자**를 사용하여 NuGet 패키지에 대한 참조를 프로젝트에 추가하고, 시스템에서 패키지를 사용할 수 없는 경우 패키지를 설치합니다. 패키지 관리자를 열려면 **도구** > **NuGet 패키지 관리자** > **솔루션용 NuGet 패키지 관리**를 선택합니다.

1. `Newtonsoft.Json`이 시스템에 설치되어 있는지 확인하고, 설치되지 않은 경우 설치합니다. **설치됨** 탭에 시스템에 설치된 NuGet 패키지가 표시됩니다. `Newtonsoft.Json`이 탭에 표시되지 않는 경우 **찾아보기** 탭을 선택하고 검색 상자에 "Newtonsoft.Json"을 입력합니다. `Newtonsoft.Json`을 선택하고 오른쪽 창에서 해당 프로젝트를 선택한 후 **설치**를 선택합니다.

1. `Newtonsoft.Json`이 시스템에 이미 설치되어 있는 경우 **솔루션용 패키지 관리** 탭의 오른쪽 창에서 해당 프로젝트를 선택하여 프로젝트에 추가합니다.

다음은 이 프로젝트에 대한 전체 *csproj* 파일입니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp1.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

응용 프로그램을 배포하면 앱에서 사용된 타사 종속성도 응용 프로그램 파일에 포함됩니다. 타사 라이브러리는 앱이 실행되는 시스템에 없어도 됩니다.

타사 라이브러리가 있는 자체 포함 배포는 해당 라이브러리에서 지원하는 플랫폼에만 배포할 수 있습니다. 이 배포는 기본 종속성과 함께 타사 종속성이 있는 프레임워크 종속 배포와 유사하며, 이전에 설치되지 않은 경우 대상 플랫폼에는 기본 종속성이 없습니다.

# <a name="see-also"></a>참고 항목
[.NET Core 응용 프로그램 배포](index.md)   
[.NET Core RID(런타임 식별자) 카탈로그](../rid-catalog.md)   

