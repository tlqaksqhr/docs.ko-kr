---
title: Docker 앱을 위한 개발 환경
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기
ms.prod: .net
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c164b94572a8fde58124acaa14d47da574a19383
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="development-environment-for-docker-apps"></a>Docker 앱을 위한 개발 환경

## <a name="development-tools-choices-ide-or-editor"></a>개발 도구 선택: IDE 또는 편집기

관계 없이 완전 하 고 강력한 IDE 또는 편집기를 간단 하 고 agile 선호 하는 경우 Microsoft에서는 Docker 응용 프로그램 개발에 있어 거둘 수 있습니다.

### <a name="visual-studio-code-and-docker-cli-cross-platform-tools-for-mac-linux-and-windows"></a>Visual Studio Code 및 Docker CLI (Mac, Linux 및 Windows 용 플랫폼 간 도구)

모든 개발 언어를 지 원하는 플랫폼 간을 간단 하 고 편집기를 선호 하는 경우에 Visual Studio Code 및 Docker CLI를 사용할 수 있습니다. 이러한 제품은 개발자 워크플로 최적화 하기 위한 중요 한 단순 하면서도 강력한 환경을 제공 합니다. "Docker에 대 한 Mac" 또는 "Docker에 대 한 Windows" (개발 환경)를 설치 하 여 Docker 개발자가 Windows 또는 Linux (런타임 환경)를 둘 다에 대 한 앱을 빌드할 수 단일 Docker CLI를 사용할 수 있습니다. 또한 Visual Studio Code 편집기에서 Docker 명령을 실행 하려면 Dockerfile 및 바로 가기 작업에 대 한 intellisense 기능을 갖춘 Docke에 대 한 확장을 지원 합니다.

> [!NOTE]
> Visual Studio 코드를 다운로드 하려면로 이동 <https://code.visualstudio.com/download>합니다.

Mac 및 Windows 용 Docker을 다운로드 하려면로 이동 <http://www.docker.com/products/docker>합니다.

### <a name="visual-studio-with-docker-tools"></a>Docker 도구와 visual Studio

Visual Studio 2015를 사용 하는 경우 "Visual Studio 용 Docker 도구입니다." 추가 기능 도구를 설치할 수 있습니다. Visual Studio 2017 년에 대 한 Docker 도구 제공 내장 이미 됩니다. 두 경우 모두 개발할 수 있습니다 실행 하 고 선택한 Docker 환경에서 직접 응용 프로그램의 유효성을 검사 합니다. F 5를 눌러 응용 프로그램 (단일 컨테이너 또는 여러 컨테이너)는 Docker에 직접 디버깅을 호스트 하거나 Ctrl + f 5를 편집 하 여 컨테이너를 다시 작성 하지 않고도 앱을 새로 고칩니다. 이 Linux 또는 Windows 용 Docker 컨테이너를 만들고 Windows 개발자를 위한 가장 간단한 효율적이 고 좋습니다.

> [!NOTE]
> Visual Studio 용 Docker 도구를 다운로드 하려면로 이동 <https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4>합니다.

## <a name="language-and-framework-choices"></a>언어 및 프레임 워크 선택

Docker 응용 프로그램 및 대부분의 언어와 Microsoft 도구를 개발할 수 있습니다. 다음은 초기 목록을 하지만에 제한 되지 않습니다.

-   .NET core 및 ASP.NET 코어

-   Node.js

-   Golang

-   Java

-   Ruby

-   Python

기본적으로, Linux 또는 Windows에서 Docker에서 지 원하는 다른 최신 언어를 사용할 수 있습니다.


>[!div class="step-by-step"]
[이전] (오케스트레이션-높은-확장성-availability.md) [다음] (docker-앱-내부-루프-workflow.md)
