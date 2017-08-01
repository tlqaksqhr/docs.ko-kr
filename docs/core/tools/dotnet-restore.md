---
title: "dotnet-restore 명령 - .NET Core CLI"
description: "dotnet restore 명령을 사용하여 종속성 및 프로젝트 관련 도구를 복원하는 방법을 알아봅니다."
keywords: "dotnet-restore, CLI, CLI 명령, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/24/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fd7a5769-afbe-4838-bbaf-3ae0cfcbb914
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a9e471bd1d66d68703b025cd3eaa009cb296a9fb
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-restore"></a>dotnet-restore

## <a name="name"></a>이름

`dotnet-restore` - 프로젝트의 종속성 및 도구를 복원합니다.

## <a name="synopsis"></a>개요

`dotnet restore [<ROOT>] [-s|--source] [-r|--runtime] [--packages] [--disable-parallel] [--configfile] [--no-cache] [--ignore-failed-sources] [--no-dependencies] [-v|--verbosity] [-h|--help]`

## <a name="description"></a>설명

`dotnet restore` 명령은 NuGet을 사용하여 프로젝트 파일에 지정된 종속성 및 프로젝트 관련 도구를 복원합니다. 기본적으로 종속성 및 도구의 복원은 병렬로 수행됩니다.

종속성을 복원하려면 NuGet에 패키지가 있는 피드가 필요합니다. 피드는 일반적으로 *NuGet.config* 구성 파일을 통해 제공됩니다. CLI 도구가 설치될 때 기본 구성 파일이 제공됩니다. 프로젝트 디렉터리에 고유한 *NuGet.config* 파일을 만들어 추가 피드를 지정합니다. 또한 명령 프롬프트에서 호출당 추가 피드를 지정합니다. 

종속성의 경우 복원 작업 중 `--packages` 인수를 사용하여 복원된 패키지가 배치될 위치를 지정합니다. 지정하지 않으면 모든 운영 체제에서 사용자의 홈 디렉터리(예: Linux의 경우 */home/user1* 또는 Windows의 경우 *C:\Users\user1*)에 있는 `.nuget/packages` 디렉터리에 있는 기본 NuGet 패키지 캐시가 사용됩니다.

프로젝트 관련 도구의 경우 `dotnet restore`는 먼저 도구가 압축된 패키지를 복원한 다음 프로젝트 파일에 지정된 대로 도구의 종속성을 계속 복원합니다.

`dotnet restore` 명령의 동작은 *Nuget.Config* 파일(있는 경우)에 있는 일부 설정의 영향을 받습니다. 예를 들어 *NuGet.Config*의 `globalPackagesFolder`를 설정하면 복원된 NuGet 패키지가 지정한 폴더에 저장됩니다. `dotnet restore` 명령의 `--packages` 옵션을 지정하는 대신 이 방법을 사용할 수 있습니다. 자세한 내용은 [NuGet.Config 참조](/nuget/schema/nuget-config-file)를 참조하세요.

## <a name="arguments"></a>인수

`ROOT` 
    
프로젝트 파일을 복원하는 선택적 경로입니다.

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.

`-s|--source <SOURCE>`

복원 작업 중 사용할 NuGet 패키지 소스를 지정합니다. 이 소스는 *NuGet.config* 파일에 지정된 모든 소스를 재정의합니다. 이 옵션을 여러 번 지정하여 여러 소스를 제공할 수 있습니다.

`-r|--runtime <RUNTIME_IDENTIFIER>`

패키지 복원의 런타임을 지정합니다. *.csproj* 파일의 `<RuntimeIdentifiers>` 태그에 명시적으로 나열되지 않은 런타임의 패키지를 복원하는 데 사용됩니다. RID(런타임 식별자) 목록은 [RID 카탈로그](../rid-catalog.md)를 참조하세요. 이 옵션을 여러 번 지정하여 여러 RID를 제공합니다.

`--packages <PACKAGES_DIRECTORY>`

복원된 패키지에 대한 디렉터리를 지정합니다. 

`--disable-parallel`

여러 프로젝트를 병렬로 복원을 사용하지 않도록 설정합니다. 

`--configfile <FILE>`

복원 작업에 사용할 NuGet 구성 파일(*NuGet.config*)입니다.

`--no-cache`

패키지 및 HTTP 요청을 캐시하지 하도록 지정합니다.

`--ignore-failed-sources`

버전 요구 사항을 충족하는 패키지가 있는 경우 실패한 소스에 대해서만 경고합니다.

`--no-dependencies`

프로젝트 간(P2P) 참조를 사용하여 프로젝트를 복원할 경우 참조가 아닌 루트 프로젝트를 복원하세요.

`--verbosity <LEVEL>`

명령의 세부 정보 표시 수준을 설정합니다. 허용되는 값은 `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, `diag[nostic]`입니다.

## <a name="examples"></a>예제

현재 디렉터리에 있는 프로젝트에 대한 종속성 및 도구를 복원합니다.

`dotnet restore` 

지정된 경로에 있는 `app1` 프로젝트에 대한 종속성 및 도구를 복원합니다.

`dotnet restore ~/projects/app1/app1.csproj`
    
소스로 제공된 파일 경로를 사용하여 현재 디렉터리에 있는 프로젝트에 대한 종속성 및 도구를 복원합니다.

`dotnet restore -s c:\packages\mypackages` 

소스로 제공된 2개의 파일 경로를 사용하여 현재 디렉터리에 있는 프로젝트에 대한 종속성 및 도구를 복원합니다.

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages` 

현재 디렉터리에 있는 프로젝트에 대한 종속성 및 도구를 복원하고 최소 출력만 표시합니다.

`dotnet restore --verbosity minimal`

