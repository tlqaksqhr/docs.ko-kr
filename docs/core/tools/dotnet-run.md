---
title: "dotnet-run 명령 | Microsoft 문서"
description: "dotnet-run 명령은 소스 코드에서 응용 프로그램을 실행하는 편리한 옵션을 제공합니다."
keywords: "dotnet-run, CLI, CLI 명령, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 40d4e60f-9900-4a48-b03c-0bae06792d91
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 60bb9160e43788539b0dc6bcf1372bb925e9ba22
ms.lasthandoff: 03/07/2017

---

#<a name="dotnet-run"></a>dotnet-run

## <a name="name"></a>이름 

`dotnet-run` - 명시적 컴파일이나 시작 명령을 사용하지 않고 소스 코드를 '현재 위치'에서 실행합니다.

## <a name="synopsis"></a>개요

```
dotnet run [-c|--configuration] [-f|--framework] [-p|--project] [[--] [application arguments]]
dotnet run [-h|--help]
```

## <a name="description"></a>설명

`dotnet run` 명령은 하나의 명령을 사용하여 소스 코드에서 응용 프로그램을 실행하는 편리한 옵션을 제공합니다. 명령줄에서 빠른 반복 개발에 유용합니다. 명령은 코드를 빌드하는 [ `dotnet build` ](dotnet-build.md) 명령에 따라 달라지므로, 프로젝트를 먼저 복원해야 하는 것처럼 빌드에 대한 요구 사항이 `dotnet run`에 적용됩니다. 

출력 파일은 `bin/<configuration>/<target>`인 기본 위치에 작성됩니다. 예를 들어 `netcoreapp1.0` 응용 프로그램이 있고 `dotnet run`을 실행하는 경우 출력은 `bin/Debug/netcoreapp1.0`에 놓입니다. 필요에 따라 파일을 덮어씁니다. 임시 파일은 `obj` 디렉터리에 놓입니다. 

지정된 프레임워크가 여러 개인 프로젝트의 경우 응용 프로그램을 실행할 프레임워크을 지정하는 데 `--framework` 옵션이 사용되지 않으면 `dotnet run`은 오류를 표시합니다.

`dotnet run` 명령은 빌드된 어셈블리가 아닌 프로젝트의 컨텍스트에서 사용해야 합니다. 이식 가능한 응용 프로그램 DLL을 대신 실행하려는 경우에는 다음 예제와 같이 다른 명령 없이 [dotnet](dotnet.md)을 사용해야 합니다.
 
`dotnet myapp.dll`

`dotnet` 드라이버에 대한 자세한 내용은 [.NET Core 명령줄 도구(CLI)](index.md) 항목을 참조하세요.

응용 프로그램을 실행하기 위해 `dotnet run` 명령은 NuGet 캐시에서 공유 런타임의 외부에 있는 응용 프로그램의 종속성을 확인합니다. 이러한 점에서 프로덕션에서 응용 프로그램을 실행하기 위해 이 명령을 사용하는 것은 권장되지 않습니다. 대신 [ `dotnet publish` ](dotnet-publish.md) 명령을 사용하여 [배포를 만들고](../deploying/index.md) 프로덕션에서 이 배포를 사용해야 합니다. 

## <a name="options"></a>옵션

`--`

실행 중인 응용 프로그램에 대한 인수에서 `dotnet run`에 대한 인수를 구분합니다. 이 인수 다음의 모든 인수가 실행 중인 응용 프로그램에 전달됩니다. 

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.

`-c|--configuration {Debug|Release}`

프로젝트 빌드에 사용할 구성입니다. 기본값은 `Debug`입니다.

`-f|--framework <FRAMEWORK_IDENTIFIER>`

지정된 프레임워크를 사용하여 앱을 빌드하고 실행합니다. 프레임워크는 프로젝트 파일에 지정되어야 합니다.

`-p|--project <PATH>`

실행할 프로젝트 파일의 경로를 지정합니다. [csproj](csproj.md) 파일 또는 [csproj](csproj.md) 파일을 포함하는 디렉터리에 대한 경로일 수 있습니다. 지정하지 않으면 현재 디렉터리로 기본 설정됩니다. 

## <a name="examples"></a>예제

현재 디렉터리에 있는 프로젝트를 실행합니다.

`dotnet run` 

지정된 프로젝트를 실행합니다.

`dotnet run --project /projects/proj1/proj1.csproj`

현재 디렉터리에 있는 프로젝트를 실행합니다. `--` 인수가 사용되었으므로 이 예제의 `--help` 인수는 실행 중인 응용 프로그램에 전달됩니다.

`dotnet run --configuration Release -- --help`
