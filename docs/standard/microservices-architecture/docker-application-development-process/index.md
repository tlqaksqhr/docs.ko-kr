---
title: "Docker 기반 응용 프로그램에 대한 개발 프로세스"
description: "컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | Docker 기반 응용 프로그램에 대한 개발 프로세스"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.translationtype: HT
ms.sourcegitcommit: 9bb64ea7199f5699ff166d1affb7f8126dcc6612
ms.openlocfilehash: f4c241f463ff1270037c7d66ba39409ca5d9e728
ms.contentlocale: ko-kr
ms.lasthandoff: 09/05/2017

---
# <a name="development-process-for-docker-based-applications"></a>Docker 기반 응용 프로그램에 대한 개발 프로세스

*Visual Studio 및 Visual Studio Tools for Docker에 중점을 둔 IDE 또는 Docker CLI 및 Visual Studio Code에 중점을 둔 CLI/편집기 중 원하는 방식으로 컨테이너화된 .NET 응용 프로그램을 개발하세요.*

## <a name="development-environment-for-docker-apps"></a>Docker 앱을 위한 개발 환경

### <a name="development-tool-choices-ide-or-editor"></a>개발 도구 선택: IDE 또는 편집기

완전하고 강력한 IDE를 선호하든지 아니면 간단하고 민첩한 편집기를 선호하든지 상관없이 Microsoft는 Docker 응용 프로그램을 개발하는 데 사용할 수 있는 도구를 제공합니다.

**Visual Studio Tools for Docker**. Visual Studio 2015를 사용할 경우 [Visual Studio Tools for Docker](https://marketplace.visualstudio.com/items?itemName=MicrosoftCloudExplorer.VisualStudioToolsforDocker-Preview) 추가 기능을 설치할 수 있습니다. Visual Studio 2017을 사용할 경우 Docker용 도구가 이미 기본 제공되어 있습니다. 두 경우 모두 Docker용 도구를 통해 대상 Docker 환경에서 직접 응용 프로그램을 개발하고 실행할 수 있으며, 응용 프로그램의 유효성을 검사할 수 있습니다. F5 키를 눌러 응용 프로그램(단일 컨테이너 또는 여러 컨테이너)을 Docker 호스트에 직접 실행 및 디버그하거나, Ctrl+F5를 눌러 컨테이너를 다시 빌드하지 않고도 응용 프로그램을 편집 및 새로 고칠 수 있습니다. 이는 Linux 또는 Windows용 Docker 컨테이너를 대상으로 하는 Windows 개발자를 위한 가장 간단하고 강력한 옵션입니다.

**Visual Studio Code 및 Docker CLI**. 개발 언어를 지원하는 간단한 플랫폼 간 편집기를 선호하는 경우 Microsoft VS Code(Visual Studio Code) 및 Docker CLI를 사용할 수 있습니다. 이는 Mac, Linux 및 Windows에 대한 플랫폼 간 개발 접근법입니다.

이러한 제품은 간단하지만 강력한 환경을 제공하여 개발자 워크플로를 간소화합니다. [Docker CE(Community Edition)](https://www.docker.com/community-edition) 도구를 설치하면 단일 Docker CLI를 사용하여 Windows용 앱과 Linux용 앱을 모두 빌드할 수 있습니다. 또한 Visual Studio Code는 Dockerfile용 IntelliSense와 같은 Docker용 확장을 지원하고 편집기에서 Docker 명령을 실행하는 바로 가기 작업도 지원합니다.

### <a name="additional-resources"></a>추가 리소스

-   **Visual Studio Tools for Docker**
    [*https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4*](https://visualstudiogallery.msdn.microsoft.com/0f5b2caa-ea00-41c8-b8a2-058c7da0b3e4)

-   **Visual Studio Code**. 공식 사이트입니다.
    [*https://code.visualstudio.com/download*](https://code.visualstudio.com/download)

-   **Mac 및 Windows용 Docker CE(Community Edition)**
    [*https://www.docker.com/community-editions*](https://www.docker.com/community-edition)

## <a name="net-languages-and-frameworks-for-docker-containers"></a>Docker 컨테이너를 위한 .NET 언어 및 프레임워크

이 가이드의 이전 섹션에서 언급했듯이 Docker 컨테이너화된 .NET 응용 프로그램을 개발할 때 .NET Framework, .NET Core 또는 오픈 소스 Mono 프로젝트를 사용할 수 있습니다. Linux 또는 Windows 컨테이너를 대상으로 할 때 사용 중인 .NET Framework에 따라 C\#, F\# 또는 Visual Basic으로 개발할 수 있습니다. .NET 언어에 대한 자세한 내용은 블로그 게시물, [The .NET Language Strategy](https://blogs.msdn.microsoft.com/dotnet/2017/02/01/the-net-language-strategy/)(.NET 언어 전략)를 참조하세요.


>[!div class="step-by-step"]
[이전](../architect-microservice-container-applications/using-azure-service-fabric.md) [다음](docker-app-development-workflow.md)

