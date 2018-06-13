---
title: dotnet new에 대한 사용자 지정 템플릿
description: 모든 형식의 .NET 프로젝트 또는 파일에 대한 사용자 지정 템플릿을 알아봅니다.
author: guardrex
ms.author: mairaw
ms.date: 08/11/2017
ms.openlocfilehash: fe888d0bfeeb51d77b73ec481b93fec9b40aa6ad
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33217323"
---
# <a name="custom-templates-for-dotnet-new"></a>dotnet new에 대한 사용자 지정 템플릿

[.NET Core SDK](https://www.microsoft.com/net/download/core)에는 [`dotnet new` 명령](dotnet-new.md)과 함께 사용할 많은 템플릿이 미리 설치되어 제공됩니다. .NET Core 2.0부터 앱, 서비스, 도구 또는 클래스 라이브러리와 같은 모든 형식의 프로젝트에 대한 사용자 지정 템플릿을 만들 수 있습니다. 구성 파일과 같이 하나 이상의 종속 파일을 출력하는 템플릿도 만들 수 있습니다.

NuGet *nupkg* 파일을 직접 참조하거나 템플릿이 포함된 파일 시스템 디렉터리를 지정하여 NuGet 피드의 NuGet 패키지에서 사용자 지정 템플릿을 설치할 수 있습니다. 템플릿 엔진은 값을 바꾸고, 파일과 파일 지역을 포함 및 제외하고, 서식이 사용될 때 사용자 지정 처리 작업을 실행할 수 있는 기능을 제공합니다.

템플릿 엔진은 오픈 소스이며 온라인 코드 리포지토리는 GitHub의 [dotnet/templating](https://github.com/dotnet/templating/)에 있습니다. 템플릿 샘플을 보려면 [dotnet/dotnet-template-samples](https://github.com/dotnet/dotnet-template-samples) 리포지토리를 참조하세요. 타사 템플릿을 포함한 추가 템플릿은 GitHub의 [Available templates for dotnet new](https://github.com/dotnet/templating/wiki/Available-templates-for-dotnet-new)(dotnet new에 대한 사용 가능한 템플릿)에서 찾을 수 있습니다. 사용자 지정 템플릿을 만들고 사용하는 방법에 대한 자세한 내용은 [How to create your own templates for dotnet new](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/)(dotnet new에 대한 사용자 지정 템플릿을 만드는 방법) 및 [dotnet/templating GitHub repo Wiki](https://github.com/dotnet/templating/wiki)(dotnet/templating GitHub 리포지토리 Wiki)를 참조하세요.

연습을 수행하고 템플릿을 만들려면 [dotnet new에 대한 사용자 지정 템플릿 만들기](~/docs/core/tutorials/create-custom-template.md) 자습서를 참조하세요.

## <a name="configuration"></a>구성

템플릿은 다음 구성 요소로 구성됩니다.

- 소스 파일 및 폴더
- 구성 파일(*template.json*)

### <a name="source-files-and-folders"></a>소스 파일 및 폴더

소스 파일 및 폴더에는 `dotnet new <TEMPLATE>` 명령이 실행될 때 템플릿 엔진에서 사용하려는 모든 파일 및 폴더가 포함됩니다. 템플릿 엔진은 프로젝트를 생성하는 데 *실행 가능한 프로젝트*를 소스 코드로 사용하도록 디자인되어 있습니다. 여기에는 여러 가지 이점이 있습니다.

- 템플릿 엔진에서는 특수 토큰을 프로젝트의 소스 코드에 삽입할 필요가 없습니다.
- 코드 파일은 특수 파일이 아니고 템플릿 엔진 작업을 수행하는 방식으로 수정되지도 않습니다. 따라서 일반적으로 프로젝트 작업을 할 때 사용하는 도구로 템플릿 콘텐츠를 처리할 수 있습니다.
- 다른 프로젝트를 처리하는 것처럼 템플릿 프로젝트를 빌드, 실행 및 디버그합니다.
- *template.json* 구성 파일을 프로젝트에 추가하면 기존 프로젝트에서 템플릿을 빠르게 만들 수 있습니다.

템플릿에 저장되는 파일과 폴더는 .NET Core 또는 .NET Framework 솔루션과 같은 공식 .NET 프로젝트 형식으로 제한되지 않습니다. 템플릿 엔진에서 출력에 대한 파일(예: 구성 파일 또는 솔루션 파일)을 하나만 생성하는 경우에도 소스 파일 및 폴더는 템플릿을 사용할 때 만들려는 콘텐츠로 구성될 수 있습니다. 예를 들어 *web.config* 소스 파일이 포함되고 템플릿을 사용할 때 프로젝트에 대한 수정된 *web.config* 파일을 만드는 템플릿을 만들 수 있습니다. 소스 파일의 수정 사항은 *template.json* 구성 파일에서 제공한 논리와 설정 및 `dotnet new <TEMPLATE>` 명령에 대한 옵션으로 전달된 사용자 제공 값을 기반으로 합니다.

### <a name="templatejson"></a>template.json

*template.json* 파일은 템플릿 루트 디렉터리의 *.template.config* 폴더에 배치됩니다. 이 파일은 템플릿 엔진에 구성 정보를 제공합니다. 기능 템플릿을 충분히 만들 수 있는 최소 구성으로 다음 표에 나와 있는 멤버가 필요합니다.

| 멤버            | 형식          | 설명 |
| ----------------- | ------------- | ----------- |
| `$schema`         | URI           | *template.json* 파일에 대한 JSON 스키마. 스키마 지정 시 JSON 스키마가 JSON 편집 기능을 구현하도록 지원하는 편집기. 예를 들어 [Visual Studio Code](https://code.visualstudio.com/)에서는 이 멤버가 IntelliSense를 구현해야 합니다. `http://json.schemastore.org/template` 값을 사용하세요. |
| `author`          | string        | 템플릿 작성자. |
| `classifications` | array(string) | 사용자가 템플릿 검색 시 템플릿을 찾는 데 사용할 수 있는 0개 이상의 템플릿 특성. <code>dotnet new -l&#124;--list</code> 명령을 사용하여 생성된 템플릿 목록에 템플릿이 나타날 때 *태그* 열에 분류도 표시됩니다. |
| `identity`        | string        | 이 템플릿의 공유한 이름. |
| `name`            | string        | 사용자에게 표시되어야 하는 템플릿의 이름. |
| `shortName`       | string        | 템플릿 이름이 GUI를 통해 선택되는 것이 아니라 사용자에 의해 지정되는 환경에 적용되는 템플릿을 선택하기 위한 기본 약어. 예를 들어 명령 프롬프트에서 템플릿과 CLI 명령을 함께 사용할 경우 짧은 이름이 유용합니다. |

#### <a name="example"></a>예제:

```json
{
  "$schema": "http://json.schemastore.org/template",
  "author": "Catalina Garcia",
  "classifications": [ "Common", "Console" ],
  "identity": "GarciaSoftware.ConsoleTemplate.CSharp",
  "name": "Garcia Software Console Application",
  "shortName": "garciaconsole"
}
```

*template.json* 파일에 대한 전체 스키마는 [JSON Schema Store](http://json.schemastore.org/template)(JSON 스키마 저장소)에서 찾을 수 있습니다.

## <a name="net-default-templates"></a>.NET 기본 템플릿

[.NET Core SDK](https://www.microsoft.com/net/download/core)를 설치할 때 콘솔 앱, 클래스 라이브러리, 단위 테스트 프로젝트, ASP.NET Core 앱([Angular](https://angular.io/) 및 [React](https://facebook.github.io/react/) 프로젝트 포함) 및 구성 파일을 비롯한 프로젝트 및 파일을 만들 수 있는 12개 이상의 기본 제공 템플릿이 제공됩니다. 기본 제공 템플릿을 나열하려면 `dotnet new` 명령을 `-l|--list` 옵션과 함께 실행합니다.

```console
dotnet new -l
```

## <a name="packing-a-template-into-a-nuget-package-nupkg-file"></a>템플릿을 NuGet 패키지(nupkg 파일)로 압축

현재 사용자 지정 템플릿은 Windows에서 [nuget.exe](https://dist.nuget.org/win-x86-commandline/latest/nuget.exe)([dotnet pack](dotnet-pack.md)이 아님)를 사용하여 압축됩니다. 플랫폼 간 패키징의 경우 [NuGetizer 3000](https://github.com/NuGet/Home/wiki/NuGetizer-3000)을 사용하는 것이 좋습니다.

프로젝트 폴더의 콘텐츠는 *.template.config/template.json* 파일과 함께 *content* 폴더에 배치됩니다. *content* 폴더 옆에 패키지 콘텐츠를 설명하고 NuGet 패키지를 만드는 프로세스를 적용하는 XML 매니페스트 파일인 [*nuspec* 파일](/nuget/create-packages/creating-a-package)을 추가합니다. *nuspec* 파일의 **\<packageTypes>** 요소 내부에는 **\<packageType>** 요소와 `Template`의 `name` 특성 값이 포함됩니다. *content* 폴더와 *nuspec* 파일은 동일한 디렉터리에 있어야 합니다. 표에서는 템플릿을 NuGet 패키지로 생성하는 데 필요한 최소 *nuspec* 파일 요소를 보여 줍니다.

| 요소            | 형식   | 설명 |
| ------------------ | ------ | ----------- |
| **\<authors>**     | string | nuget.org에서 프로필 이름과 일치하는, 쉼표로 구분된 패키지 작성자 목록입니다. 작성자는 nuget.org의 NuGet 갤러리에 표시되고 동일한 작성자가 패키지를 상호 참조하는 데 사용됩니다. |
| **\<description>** | string | UI 표시를 위한 패키지에 대한 자세한 설명입니다. |
| **\<id>**          | string | nuget.org 또는 무엇이든 패키지가 상주하는 갤러리에서 고유해야 하는 대/소문자를 구분하지 않는 패키지 식별자입니다. ID는 URL에 유효하지 않은 공백이나 문자를 포함할 수 없고 일반적으로 .NET 네임스페이스 규칙을 따릅니다. 자세한 내용은 [고유한 패키지 식별자 선택 및 버전 번호 설정](/nuget/create-packages/creating-a-package#choosing-a-unique-package-identifier-and-setting-the-version-number)을 참조하세요. |
| **\<packageType>** | string | **\<metadata>** 요소 중 **\<packageTypes>** 요소 내부에 이 요소를 삽입합니다. **\<packageType>** 요소의 `name` 특성을 `Template`으로 설정합니다. |
| **\<version>**     | string | major.minor.patch 패턴을 따르는 패키지 버전입니다. 버전 번호는 [시험판 버전](/nuget/create-packages/prerelease-packages#semantic-versioning) 항목의 설명대로 시험판 접미사를 포함할 수 있습니다. |

전체 *nuspec* 파일 스키마는 [.nuspec reference](/nuget/schema/nuspec)(.nuspec 참조)를 참조하세요. 템플릿에 대한 예제 *nuspec* 파일은 [dotnet new에 대한 사용자 지정 템플릿 만들기](~/docs/core/tutorials/create-custom-template.md) 자습서에 나타납니다.

`nuget pack <PATH_TO_NUSPEC_FILE>` 명령을 사용하여 [패키지를 만듭니다](/nuget/create-packages/creating-a-package#creating-the-package).

## <a name="installing-a-template"></a>템플릿 설치

*nupkg* 파일을 직접 참조하거나 템플릿 구성이 포함된 파일 시스템 디렉터리를 지정하여 NuGet 피드의 NuGet 패키지에서 사용자 지정 템플릿을 설치합니다. `-i|--install` 옵션을 [dotnet new](dotnet-new.md) 명령과 함께 사용합니다.

### <a name="to-install-a-template-from-a-nuget-package-stored-at-nugetorg"></a>nuget.org에 저장된 NuGet 패키지에서 템플릿을 설치하려면

```console
dotnet new -i <NUGET_PACKAGE_ID>
```

### <a name="to-install-a-template-from-a-local-nupkg-file"></a>로컬 nupkg 파일에서 템플릿을 설치하려면

```console
dotnet new -i <PATH_TO_NUPKG_FILE>
```

### <a name="to-install-a-template-from-a-file-system-directory"></a>파일 시스템 디렉터리에서 템플릿을 설치하려면

`FILE_SYSTEM_DIRECTORY`는 프로젝트 및 *.template.config* 폴더가 포함된 프로젝트 폴더입니다.

```console
dotnet new -i <FILE_SYSTEM_DIRECTORY>
```

## <a name="uninstalling-a-template"></a>템플릿 제거

`id`를 통해 NuGet 패키지를 참조하거나 템플릿 구성이 포함된 파일 시스템 디렉터리를 지정하여 사용자 지정 템플릿을 제거합니다. `-u|--uninstall` 설치 옵션을 [dotnet new](dotnet-new.md) 명령과 함께 사용합니다.

### <a name="to-uninstall-a-template-from-a-nuget-package-stored-at-nugetorg"></a>nuget.org에 저장된 NuGet 패키지에서 템플릿을 제거하려면

```console
dotnet new -u <NUGET_PACKAGE_ID>
```

### <a name="to-uninstall-a-template-from-a-local-nupkg-file"></a>로컬 nupkg 파일에서 템플릿을 제거하려면

템플릿을 제거하려는 경우 *nupkg* 파일의 경로를 사용하지 마세요. *`dotnet new -u <PATH_TO_NUPKG_FILE>`을 사용하여 템플릿을 제거하는 시도가 실패합니다.* `id`를 통해 패키지를 참조합니다.

```console
dotnet new -u <NUGET_PACKAGE_ID>
```

### <a name="to-uninstall-a-template-from-a-file-system-directory"></a>파일 시스템 디렉터리에서 템플릿을 제거하려면

`FILE_SYSTEM_DIRECTORY`는 프로젝트 및 *.template.config* 폴더가 포함된 프로젝트 폴더입니다.

```console
dotnet new -u <FILE_SYSTEM_DIRECTORY>
```

## <a name="create-a-project-using-a-custom-template"></a>사용자 지정 템플릿을 사용하여 프로젝트 만들기

템플릿이 설치된 후 다른 미리 설치된 템플릿을 사용하는 것처럼 `dotnet new <TEMPLATE>` 명령을 실행하여 템플릿을 사용합니다. 템플릿 설정에서 구성한 템플릿 관련 옵션을 포함하여 `dotnet new` 명령에 대한 [옵션](dotnet-new.md#options)을 지정할 수도 있습니다. 템플릿의 짧은 이름을 직접 명령에 제공합니다.

```console
dotnet new <TEMPLATE>
```

## <a name="see-also"></a>참고 항목

[dotnet new에 대한 사용자 지정 템플릿(자습서)](../tutorials/create-custom-template.md)  
[dotnet/templating GitHub repo Wiki](https://github.com/dotnet/templating/wiki)(dotnet/templating GitHub 리포지토리 Wiki)  
[dotnet/dotnet-template-samples GitHub repo](https://github.com/dotnet/dotnet-template-samples)(dotnet/dotnet-template-samples GitHub 리포지토리)  
[How to create your own templates for dotnet new](https://blogs.msdn.microsoft.com/dotnet/2017/04/02/how-to-create-your-own-templates-for-dotnet-new/)(dotnet new에 대한 사용자 지정 템플릿을 만드는 방법)  
[*template.json* JSON 스키마 저장소에 대 한 스키마](http://json.schemastore.org/template)  
