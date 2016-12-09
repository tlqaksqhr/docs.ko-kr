---
title: dotnet-nuget-locals command | .NET Core SDK
description: "dotnet-nuget-locals 명령은 http-request 캐시, 임시 캐시 또는 시스템 전체의 글로벌 패키지 폴더와 같은 로컬 NuGet 리소스를 지우거나 목록에 포함합니다."
keywords: "dotnet-nuget-locals, CLI, CLI 명령, .NET Core"
author: karann-msft
ms.author: mairaw
ms.date: 11/15/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8440229e-317e-4dc1-9463-cba5fdb12c3b
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: 08c51ecb4e042254c89f618d6baff1b407af0113

---

#<a name="dotnet-nuget-locals"></a>dotnet-nuget-locals

[!INCLUDE[preview-warning](../../../includes/warning.md)] 

## <a name="name"></a>이름 
`dotnet-nuget-locals` - http-request 캐시, 임시 캐시 또는 시스템 전체의 글로벌 패키지 폴더와 같은 로컬 NuGet 리소스를 지우거나 목록에 포함합니다. 

## <a name="synopsis"></a>개요

`dotnet nuget locals <cache_location> [--clear|--list] [--help] [--force-english-output]`

여기서 `<cache_location>` 값은 `all`, `http-cache`, `packages-cache`, `global-packages` 또는 `temp` 중 하나일 수 있습니다.

## <a name="description"></a>설명

`dotnet nuget locals` 명령은 캐시, 임시 캐시 또는 시스템 전체의 글로벌 패키지 폴더와 같은 로컬 NuGet 리소스를 지우거나 목록에 포함합니다.

## <a name="arguments"></a>인수

`all`

지정된 작업이 모든 캐시 형식 즉, http-request 캐시, 전역 패키지 캐시 및 임시 캐시에 적용되어야 함을 나타냅니다.

`http-cache`

지정된 작업이 http-request 캐시에만 적용되어야 함을 나타냅니다. 다른 캐시 위치는 영향을 받지 않습니다.

`global-packages`

지정된 작업이 전역 패키지 캐시에만 적용되어야 함을 나타냅니다. 다른 캐시 위치는 영향을 받지 않습니다.

`temp`

지정된 작업이 임시 캐시에만 적용되어야 함을 나타냅니다. 다른 캐시 위치는 영향을 받지 않습니다.

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.  

`-c|--clear`

지우기 옵션은 지정된 캐시 유형에 지우기 작업을 수행하는 데 사용됩니다. 캐시 디렉터리의 콘텐츠는 재귀적으로 삭제됩니다. 성공적인 작업을 위해 실행 중인 사용자/그룹에게 캐시 디렉터리의 파일에 대한 사용 권한이 있어야 합니다. 그렇지 않은 경우에는 지우지 않은 파일/폴더가 있음을 나타내는 오류가 표시됩니다.

`-l|--list`

목록 옵션은 지정된 캐시 형식의 위치를 표시하는 데 사용됩니다. 

`--force-english-output`

명령줄 출력이 영어로 강제로 표시됩니다.

## <a name="examples"></a>예제

모든 로컬 캐시 디렉터리의 경로를 표시합니다. 즉 http-cache 디렉터리, 전역 패키지 캐시 디렉터리 및 임시 캐시 디렉터리의 경로가 표시됩니다.

`dotnet nuget locals –l all`

로컬 http-cache 디렉터리의 경로를 표시합니다.

`dotnet nuget locals --list http-cache`

모든 로컬 캐시 디렉터리에 있는 파일을 모두 지웁니다. 즉 http_cache 디렉터리, 전역 패키지 캐시 디렉터리 및 임시 캐시 디렉터리의 파일이 모두 지워집니다.

`dotnet nuget locals --clear all`

로컬 글로벌 패키지 캐시 디렉터리에 있는 모든 파일을 지웁니다.

`dotnet nuget locals -c global-packages`

로컬 임시 캐시 디렉터리에 있는 모든 파일을 지웁니다.

`dotnet nuget locals -c temp`

## <a name="troubleshooting"></a>문제 해결

`dotnet-nuget-locals` 명령을 사용하는 동안 가장 일반적으로 나타나는 문제와 오류에 대한 자세한 내용은 [Managing the NuGet cache](https://docs.nuget.org/ndocs/consume-packages/managing-the-nuget-cache)(NuGet 캐시 관리)를 참조하세요.



<!--HONumber=Nov16_HO3-->


