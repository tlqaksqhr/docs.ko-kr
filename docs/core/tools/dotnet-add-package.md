---
title: dotnet add package 명령 - .NET Core CLI
description: ‘dotnet add package’ 명령은 NuGet 패키지 참조를 프로젝트에 추가하는 편리한 옵션을 제공합니다.
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: 31dda9dbb101238b3a33d8b0d9a17765744480e0
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696301"
---
# <a name="dotnet-add-package"></a>dotnet add package

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet add package` - 패키지 참조를 프로젝트 파일에 추가합니다.

## <a name="synopsis"></a>개요

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-h|--help] [-f|--framework] [-n|--no-restore] [--package-directory] [-s|--source] [-v|--version]`

## <a name="description"></a>설명

`dotnet add package` 명령은 패키지 참조를 프로젝트 파일에 추가하는 편리한 옵션을 제공합니다. 명령을 실행한 후 패키지가 프로젝트의 프레임워크와 호환되는지 확인하는 호환성 검사가 있습니다. 검사를 통과하면 `<PackageReference>` 요소가 프로젝트 파일에 추가되고 [dotnet restore](dotnet-restore.md)가 실행됩니다.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

예를 들어 `Newtonsoft.Json`를 *ToDo.csproj*에 추가하면 다음 예제와 유사한 출력이 생성됩니다.

```console
  Writing C:\Users\mairaw\AppData\Local\Temp\tmp95A8.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'C:\projects\ToDo\ToDo.csproj'.
log  : Restoring packages for C:\projects\ToDo\ToDo.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 235ms
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'C:\projects\ToDo\ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '10.0.3' added to file 'C:\projects\ToDo\ToDo.csproj'.
```

이제 *ToDo.csproj* 파일에 참조되는 패키지에 대한 [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) 요소가 포함됩니다.

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

## <a name="arguments"></a>인수

`PROJECT`

프로젝트 파일을 지정합니다. 지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다.

`PACKAGE_NAME`

추가할 패키지 참조입니다.

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.

`-f|--framework <FRAMEWORK>`

특정 [프레임워크](../../standard/frameworks.md)를 대상으로 하는 경우에만 패키지 참조를 추가합니다.

`-n|--no-restore`

복원 미리 보기 및 호환성 검사를 수행하지 않고 패키지 참조를 추가합니다.

`--package-directory <PACKAGE_DIRECTORY>`

지정된 디렉터리에 패키지를 복원합니다.

`-s|--source <SOURCE>`

복원 작업 중 특정 NuGet 패키지 소스를 사용합니다.

`-v|--version <VERSION>`

패키지의 버전입니다.

## <a name="examples"></a>예제

`Newtonsoft.Json` NuGet 패키지를 프로젝트에 추가합니다.

`dotnet add package Newtonsoft.Json`

특정 버전의 패키지를 프로젝트에 추가합니다.

`dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0`

특정 NuGet 소스를 사용하여 패키지를 추가합니다.

`dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json`
