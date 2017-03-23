---
title: "dotnet-restore 명령 | Microsoft 문서"
description: "dotnet restore 명령을 사용하여 종속성 및 프로젝트 관련 도구를 복원하는 방법을 알아봅니다."
keywords: "dotnet-restore, CLI, CLI 명령, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fd7a5769-afbe-4838-bbaf-3ae0cfcbb914
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: a55cd932045a59f08146dff367a87eb6fe61f6e5
ms.lasthandoff: 03/07/2017

---

#<a name="dotnet-restore"></a>dotnet-restore

## <a name="name"></a>이름

`dotnet-restore` - 프로젝트의 종속성 및 도구를 복원합니다.

## <a name="synopsis"></a>개요

```
dotnet restore [root] [-s|--source] [-r|--runtime] [--packages] [--disable-parallel] [--configfile] [--no-cache] [--ignore-failed-sources] [--no-dependencies] [-v|--verbosity]
dotnet restore [-h|--help]
```

## <a name="description"></a>설명

`dotnet restore` 명령은 NuGet을 사용하여 프로젝트 파일에 지정된 종속성 및 프로젝트 관련 도구를 복원합니다. 기본적으로 종속성 및 도구의 복원은 병렬로 수행됩니다.

종속성을 복원하려면 NuGet에 패키지가 있는 피드가 필요합니다. 일반적으로 피드는 NuGet.config 구성 파일을 통해 제공되며, 기본적으로 CLI 도구를 설치할 때 제공됩니다. 프로젝트 디렉터리에 고유한 NuGet.config 파일을 만들어 더 많은 피드를 지정할 수 있습니다. 명령 프롬프트에서 호출당 피드를 지정할 수도 있습니다. 

종속성의 경우 복원 작업 중 `--packages` 인수를 사용하여 복원된 패키지가 배치될 위치를 지정할 수 있습니다. 지정하지 않으면 기본 NuGet 패키지 캐시가 사용됩니다. 이 캐시는 모든 운영 체제에서 사용자의 홈 디렉터리(예: Linux의 경우 */home/user1* 또는 Windows의 경우 *C:\Users\user1*)에 있는 `.nuget/packages` 디렉터리에 있습니다.

프로젝트 관련 도구의 경우 `dotnet restore`는 먼저 도구가 압축된 패키지를 복원한 다음 프로젝트 파일에 지정된 대로 도구의 종속성을 계속 복원합니다.

## <a name="options"></a>옵션

`root` 
    
프로젝트 파일을 복원하는 선택적 경로입니다. 

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.

`-s|--source <SOURCE>`

복원 작업 중 사용할 NuGet 패키지 소스를 지정합니다. 이 소스는 NuGet.config 파일에 지정된 모든 소스를 재정의합니다. 이 옵션을 여러 번 지정하여 여러 소스를 제공할 수 있습니다.

`--packages <PACKAGES_DIRECTORY]`

복원된 패키지를 배치할 디렉터리를 지정합니다. 

`--disable-parallel`

여러 프로젝트를 병렬로 복원을 사용하지 않도록 설정합니다. 

`--configfile <FILE>`

복원 작업에 사용할 NuGet 구성 파일(NuGet.config)입니다.

`--no-cache`

패키지 및 HTTP 요청을 캐시하지 하도록 지정합니다.

` --ignore-failed-sources`

버전 요구 사항을 충족하는 패키지가 있는 경우 실패한 소스에 대해서만 경고합니다.

`--no-dependencies`

P2P 참조를 사용하여 프로젝트를 복원할 경우 참조를 복원하지 말고 루트 프로젝트만 복원하세요.

`--verbosity <LEVEL>`

출력에 세부 정보를 표시합니다. 수준은 `normal`, `quiet` 또는 `detailed`입니다.

## <a name="examples"></a>예제

현재 디렉터리에 있는 프로젝트에 대한 종속성 및 도구를 복원합니다.

`dotnet restore` 

지정된 경로에 있는 `app1` 프로젝트에 대한 종속성 및 도구를 복원합니다.

`dotnet restore ~/projects/app1/app1.csproj`
    
대체 소스로 제공된 파일 경로를 사용하여 현재 디렉터리에 있는 프로젝트에 대한 종속성 및 도구를 복원합니다.

`dotnet restore -f c:\packages\mypackages` 

대체 소스로 제공된 두 개의 파일 경로를 사용하여 현재 디렉터리에 있는 프로젝트에 대한 종속성 및 도구를 복원합니다.

`dotnet restore -f c:\packages\mypackages -f c:\packages\myotherpackages` 

현재 디렉터리에 있는 프로젝트에 대한 종속성 및 도구를 복원하고 오류만 출력에 표시합니다.

`dotnet restore --verbosity Error`

