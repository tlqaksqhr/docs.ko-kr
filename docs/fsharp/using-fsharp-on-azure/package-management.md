---
title: "F #을 사용한 패키지 관리를 사용 하 여 Azure에 대 한"
description: "F # Azure 종속성을 관리 하려면 Paket 또는 Nuget 사용"
keywords: "visual f #, f #, 기능 프로그래밍,.NET,.NET Core를 Azure"
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: dd32ef9c-5416-467e-9fa3-c9ee3bb08456
ms.openlocfilehash: d1a807053f5c4c45492f206739922aacdf6d4122
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2018
---
# <a name="package-management-for-f-azure-dependencies"></a>F# Azure 종속성에 대한 패키지 관리

Azure 개발에 대 한 패키지를 가져오는 패키지 관리자를 사용 하는 경우 쉽습니다. 두 옵션은 [Paket](https://fsprojects.github.io/Paket/) 및 [NuGet](https://www.nuget.org/)합니다.

## <a name="using-paket"></a>Paket를 사용 하 여

사용 중인 경우 [Paket](https://fsprojects.github.io/Paket/) 종속성 관리자를 사용 하 여는 `paket.exe` Azure 종속성을 추가 하는 도구입니다. 예:

    > paket add nuget WindowsAzure.Storage

사용 중인 경우 또는 [모노](https://www.mono-project.com/) 플랫폼 간.NET 개발을 위한:

    > mono paket.exe add nuget WindowsAzure.Storage

이렇게 하면 추가 됩니다 `WindowsAzure.Storage` 수정 하면 현재 디렉터리에 프로젝트에 대 한 패키지 종속성 집합에는 `paket.dependencies` 파일을 선택한 패키지를 다운로드 합니다. 이전에 종속성을 설정 하거나 사용 하는 프로젝트에 종속성 설치를 다른 개발자가 경우 해결 하 고 다음과 같은 로컬 종속성을 설치할 수 있습니다.

    > paket install

또는 모노 개발:

    > mono paket.exe install

다음과 같은 최신 버전으로 모든 패키지 종속 파일을 업데이트할 수 있습니다.

    > paket update

또는 모노 개발:

    > mono paket.exe update

## <a name="using-nuget"></a>Nuget을 사용 하 여

사용 중인 경우 [NuGet](https://www.nuget.org/) 종속성 관리자를 사용 하 여는 `nuget.exe` Azure 종속성을 추가 하는 도구입니다. 예:

    > nuget install WindowsAzure.Storage -ExcludeVersion

또는 모노 개발:

    > mono nuget.exe install WindowsAzure.Storage -ExcludeVersion

이렇게 하면 추가 됩니다 `WindowsAzure.Storage` 를 현재 디렉터리 및 다운로드 패키지에 프로젝트에 대 한 패키지 종속 파일의 집합입니다. 이전에 종속성을 설정 하거나 사용 하는 프로젝트에 종속성 설치를 다른 개발자가 경우 해결 하 고 다음과 같은 로컬 종속성을 설치할 수 있습니다.

    > nuget restore 

또는 모노 개발:

    > mono nuget.exe restore

다음과 같은 최신 버전으로 모든 패키지 종속 파일을 업데이트할 수 있습니다.

    > nuget update

또는 모노 개발:

    > mono nuget.exe update

## <a name="referencing-assemblies"></a>어셈블리 참조

F # 스크립트에 패키지를 사용 하기 위해 사용 하 여 패키지에 포함 된 어셈블리를 참조 해야는 `#r` 지시문입니다. 예:

    > #r "packages/WindowsAzure.Storage/lib/net40/Microsoft.WindowsAzure.Storage.dll"

볼 수 있듯이 DLL과 하지 않을 수 있는 정확 하 게 패키지 이름과 전체 DLL 이름에 상대 경로를 지정 해야 합니다. 경로 프레임 워크 버전 및 패키지 버전 번호가 포함 됩니다. 설치 된 모든 어셈블리를 찾으려면 Windows 명령줄에서 다음과 같이 사용할 수 있습니다.

    > cd packages/WindowsAzure.Storage
    > dir /s/b *.dll

또는 Unix 셸에서 다음과 같은이:

    > find packages/WindowsAzure.Storage -name "*.dll"

이렇게 하면 경로는 설치 된 어셈블리에 있습니다. 여기에서 프레임 워크 버전에 대 한 올바른 경로 선택할 수 있습니다.
