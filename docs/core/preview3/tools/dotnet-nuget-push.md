---
title: "dotnet-nuget-push 명령 | Microsoft 문서"
description: "dotnet-nuget-push 명령은 서버에 패키지를 푸시하고 게시합니다."
keywords: "dotnet-nuget-push, CLI, CLI 명령, .NET Core"
author: karann-msft
ms.author: mairaw
ms.date: 11/11/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f54d9adf-94f8-41cc-bb52-42f7ca3be6ff
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: dcc89fd24e23e624c4bcf90a8200b4e655af6dd6

---

#<a name="dotnet-nuget-push"></a>dotnet-nuget-push

[!INCLUDE[preview-warning](../../../includes/warning.md)]

## <a name="name"></a>이름 
`dotnet-nuget-push` - 서버에 패키지를 푸시하고 게시합니다. 

## <a name="synopsis"></a>개요

`dotnet nuget push [<package>] [--help] [--source] [--symbols-source] 
    [--timeout] [--api-key] [--symbol-api-key] [--disable-buffering] [--no-symbols] 
    [--force-english-output] [--config-file] [--verbosity]`

## <a name="description"></a>설명

`dotnet nuget push` 명령은 서버에 패키지를 푸시하고 게시합니다. push 명령은 시스템의 NuGet 구성 파일에 있는 서버 및 자격 증명 정보 또는 구성 파일 체인을 사용합니다. 구성 파일에 대한 자세한 내용은 [NuGet 동작 구성](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior)을 참조하세요. NuGet의 기본 구성은 *%AppData%\NuGet\NuGet.config*(Windows) 또는 *$HOME/.local/share*(Linux/macOS)를 로드한 다음 드라이브의 루트에서 시작되고 현재 디렉터리에서 끝나는 *nuget.config* 또는 *.nuget\nuget.config*를 로드하여 가져올 수 있습니다.

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.  

`-s|--source <SOURCE>`

서버 URL을 지정합니다. 이 옵션은 NuGet 구성 파일에 DefaultPushSource 구성 값이 설정되어 있지 않을 때 필요합니다.

`--symbols-source <SOURCE>`

기호 서버 URL을 지정합니다.

`-t|--timeout <TIMEOUT>`

서버에 푸시하기 위한 제한 시간(초)을 지정합니다. 기본값은 300 초(5 분)입니다. 0을 지정해도 이 기본값으로 설정됩니다.

`-k|--api-key <API_KEY>`

서버에 대한 API 키입니다.

`--symbol-api-key <API_KEY>`

기호 서버에 대한 API 키입니다.

`-d|--disable-buffering`

메모리 사용량을 줄이려면 HTTP(S) 서버로 푸시할 때 버퍼링을 사용하지 않도록 설정합니다.

`-n|--no-symbols`

기호를 푸시하지 않습니다(있는 경우).

`--force-english-output`

기록되는 모든 출력은 영어로 강제로 표시됩니다. 영어가 설정되지 않은 컴퓨터에서 영어 출력이 생성되는 것 뿐 아니라 이 옵션에서 제공하는 플랫폼 간 일관성은 텍스트를 위한 로그를 스크랩하는 자동화된 도구의 유용한 기능입니다.

`--config-file <FILE>`

이 명령에서 특별히 사용되는 NuGet 구성 파일로 표준 구성 파일 검색 및 연결 프로세스에서 찾은 다른 구성 파일을 대체합니다. 절대 경로나 상대 경로일 수 있습니다.
구성 파일에 대한 자세한 내용은 [NuGet 동작 구성](https://docs.microsoft.com/nuget/consume-packages/configuring-nuget-behavior)을 참조하세요. 

`--verbosity <LEVEL>`

출력에 세부 정보를 표시합니다. 수준은 `normal`, `quiet` 또는 `detailed`입니다.

## <a name="examples"></a>예제

기본 푸시 소스에 foo.nupkg를 푸시하여 API 키를 제공합니다.

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a`

사용자 지정 푸시 소스 `http://customsource`에 foo.nupkg를 푸시하여 API 키를 제공합니다.

`dotnet nuget push foo.nupkg -k 4003d786-cc37-4004-bfdf-c4f3e8ef9b3a -s http://customsource/` 

기본 푸시 소스 foo.nupkg를 푸시합니다.

`dotnet nuget push foo.nupkg` 

기본 기호 소스에 foo.symbols.nupkg를 푸시합니다.

`dotnet nuget push foo.symbols.nupkg`

360초 제한 시간을 지정하여 기본 푸시 소스에 foo.nupkg를 푸시합니다.

`dotnet nuget push foo.nupkg --timeout 360`

기본 푸시 소스에 현재 디렉터리에 있는 모든.nupkg 파일을 푸시합니다.

`dotnet nuget push *.nupkg`

사용자 지정 구성 파일 *./config/My.Config*를 지정하여 기본 푸시 소스에 현재 디렉터리에 있는 모든.nupkg 파일을 푸시합니다.

`dotnet nuget push *.nupkg --config-file ./config/My.Config`

기본 푸시 소스에 현재 디렉터리에 있는 모든.nupkg 파일을 최대한 자세하게 푸시합니다.

`dotnet nuget push *.nupkg --verbosity detailed`



<!--HONumber=Jan17_HO3-->


