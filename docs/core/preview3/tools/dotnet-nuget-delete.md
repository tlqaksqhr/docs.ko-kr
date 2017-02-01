---
title: "dotnet-nuget-delete 명령 | Microsoft 문서"
description: "dotnet-nuget-delete 명령은 서버에서 패키지를 삭제하거나 목록에서 제거합니다."
keywords: "dotnet-nuget-delete, CLI, CLI 명령, .NET Core"
author: karann-msft
ms.author: mairaw
ms.date: 11/11/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 6ddffde4-c789-4e90-990e-d35f6a6565d4
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: 787b1427b1064943570cbc361042ab2f20d11088

---

#<a name="dotnet-nuget-delete"></a>dotnet-nuget-delete

[!INCLUDE[preview-warning](../../../includes/warning.md)]

## <a name="name"></a>이름 
`dotnet-nuget-delete` - 서버에서 패키지를 삭제하거나 목록에서 제거합니다. 

## <a name="synopsis"></a>개요

`dotnet nuget delete [<package_name> <package_version>] 
    [--help] [--source] [--non-interactive] 
    [--api-key] [--force-english-output] [--verbosity] [--config-file]`

## <a name="description"></a>설명

`dotnet nuget delete` 명령은 패키지를 삭제하거나 목록에서 제거합니다. NuGet.org의 경우 작업을 통해 패키지가 목록에서 제거됩니다.

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.  

`-s|--source <SOURCE>`

서버 URL을 지정합니다. nuget.org에 대해 지원되는 URL에는 `http://www.nuget.org`, `http://www.nuget.org/api/v3` 및 `http://www.nuget.org/api/v2/package`가 포함됩니다. 개인용 피드의 경우 호스트 이름(예: `%hostname%/api/v3`)을 대체합니다.

`--non-interactive`

사용자 입력 또는 확인에 대한 메시지를 표시하지 않습니다.

`-k|--api-key <API_KEY>`

서버에 대한 API 키입니다.

`--force-english-output`

명령줄 출력이 영어로 강제로 표시됩니다.

`--verbosity <LEVEL>`

출력에 세부 정보를 표시합니다. 수준은 `normal`, `quiet` 또는 `detailed`입니다.

`--config-file <FILE>`

이 명령에서 특별히 사용되는 NuGet 구성 파일로 표준 구성 파일 검색 및 연결 프로세스에서 찾은 다른 구성 파일을 대체합니다. 절대 경로나 상대 경로일 수 있습니다.
구성 파일에 대한 자세한 내용은 [NuGet 동작 구성](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior)을 참조하세요.

## <a name="examples"></a>예제

MyPackage 패키지 버전 1.0 삭제:

`dotnet nuget delete MyPackage 1.0` 

사용자에게 자격 증명 또는 기타 입력을 위한 메시지를 표시하지 않고 MyPackage 패키지 버전 1.0 삭제:

`dotnet nuget delete MyPackage 1.0 --non-interactive`

사용자 지정 구성 파일 *./config/My.Config*를 지정하여 MyPackage 패키지의 버전 1.0 삭제 :

`dotnet nuget delete MyPackage 1.0 --config-file ./config/My.Config`

매우 자세하게 MyPackage, 패키지 버전 1.0 삭제:

`dotnet nuget delete MyPackage 1.0 --verbosity detailed`



<!--HONumber=Jan17_HO3-->


