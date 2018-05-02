---
title: 공식 .NET Docker 이미지
description: 컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 공식 .NET Docker 이미지
keywords: Docker, 마이크로 서비스, ASP.NET, 컨테이너
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: adbe63a2d2f93819b5b29c6dd8d8089cd35ad2f3
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="official-net-docker-images"></a>공식 .NET Docker 이미지

공식 .NET Docker 이미지는 Microsoft에서 만들고 최적화된 Docker 이미지입니다. 이러한 이미지는 [Docker 허브](https://hub.docker.com/u/microsoft/)의 Microsoft 리포지토리에서 공개적으로 사용할 수 있습니다. 각 리포지토리는 .NET 버전 및 OS와 버전(Linux Debian, Linux Alpine, Windows Nano Server, Windows Server Core 등)에 따라 여러 이미지를 포함할 수 있습니다.

.NET 리포지토리에 대한 Microsoft의 비전은 세분화되고 집중된 리포지토리를 제공하는 것입니다. 여기서 리포지토리는 특정 시나리오나 워크로드를 나타냅니다. 예를 들어 컨테이너를 빠르게 시작할 수 있도록 해당 ASP.NET Core 이미지가 추가 최적화를 제공하기 때문에 [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) 이미지는 Docker에서 ASP.NET Core를 사용할 때 사용됩니다.

반면에 .NET Core 이미지(microsoft/dotnet)는 .NET Core를 기반으로 하는 콘솔 앱을 위한 것입니다. 예를 들어 일괄 처리 프로세스, Azure WebJobs 및 기타 콘솔 시나리오는 .NET Core를 사용해야 합니다. 해당 이미지는 ASP.NET Core 스택을 포함하지 않으므로 더 작은 컨테이너 이미지가 생성됩니다.

이미지 리포지토리 대부분은 특정 프레임워크 버전뿐만 아니라 OS(Linux 배포 또는 Windows 버전)를 선택하는 데 도움이 되는 광범위한 태그 지정을 제공합니다.

Microsoft에서 제공하는 공식 .NET Docker 이미지에 대한 자세한 내용은 [.NET Docker 이미지 요약](https://aka.ms/dotnetdockerimages)을 참조하세요.

## <a name="net-core-and-docker-image-optimizations-for-development-versus-production"></a>개발 및 프로덕션을 위한 .NET Core 및 Docker 이미지 최적화

Microsoft에서는 개발자를 위한 Docker 이미지를 빌드할 때 다음과 같은 주요 시나리오를 중점적으로 고려했습니다.

-   .NET Core 앱을 *개발*하고 빌드하는 데 사용되는 이미지

-   .NET Core 앱을 *실행*하는 데 사용되는 이미지

여러 이미지인 이유는 무엇인가요? 컨테이너화된 응용 프로그램을 개발, 빌드 및 실행할 때 일반적으로 다양한 우선 순위가 있습니다. Microsoft에서는 이러한 별도 작업에 다른 이미지를 제공하여 앱을 개발하고, 빌드하고, 배포하는 별도 프로세스를 최적화할 수 있습니다.

### <a name="during-development-and-build"></a>개발 및 빌드 중

개발 중에 중요한 점은 변경 내용을 반복하는 신속성 및 변경 내용을 디버깅하는 기능입니다. 이미지의 크기는 코드를 변경하고 변경 내용을 신속하게 확인하는 기능만큼 중요하지 않습니다. 일부 도구 및 "빌드 에이전트 컨테이너"는 개발 및 빌드 프로세스 중에 개발 ASP.NET Core 이미지(microsoft/aspnetcore-build)를 사용합니다. Docker 컨테이너 안에 빌드하는 경우 중요한 측면은 앱을 컴파일하기 위해 필요한 요소입니다. 여기에는 컴파일러 및 다른 .NET 종속성 외에도 npm, Gulp 및 Bower와 같은 웹 개발 종속성이 포함됩니다.

이러한 형식의 빌드 이미지가 중요한 이유는 무엇인가요? 프로덕션에 이 이미지를 배포하지 않습니다. 대신 프로덕션 이미지에 배치하는 콘텐츠를 빌드하는 데 사용되는 이미지입니다. 이 이미지는 CI(연속 통합) 환경 또는 빌드 환경에서 사용됩니다. 예를 들어 모든 응용 프로그램 종속성을 빌드 에이전트 호스트(예: VM)에 직접 설치하는 대신 빌드 에이전트는 응용 프로그램을 빌드하는 데 필요한 모든 종속성을 사용하여 .NET Core 빌드 이미지를 인스턴스화합니다. 빌드 에이전트는 이 Docker 이미지를 실행하는 방법만 알고 있으면 됩니다. 그러면 CI 환경을 간소화하고 더 예측 가능하게 합니다.

### <a name="in-production"></a>프로덕션 내

프로덕션에서 중요한 점은 프로덕션 .NET Core 이미지를 기반으로 컨테이너를 배포하고 시작할 수 있는 신속성입니다. 따라서 네트워크를 통해 Docker 레지스트리에서 Docker 호스트로 빠르게 이동할 수 있도록 [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/)에 기반한 런타임 전용 이미지는 소규모입니다. 콘텐츠를 실행할 준비가 되면 컨테이너 시작부터 결과 처리까지 가장 빠른 시간에 수행할 수 있습니다. Docker 모델에서 빌드 컨테이너를 사용할 때 dotnet 빌드 또는 dotnet 게시를 실행하므로 C\# 코드로 컴파일할 필요가 없습니다.

이 최적화된 이미지에 응용 프로그램을 실행하는 데 필요한 이진 파일 및 기타 콘텐츠를 배치합니다. 예를 들어 dotnet 게시에서 만든 콘텐츠에는 컴파일된 .NET 이진 파일, 이미지, .js 및 .css 파일만이 포함됩니다. 시간이 지남에 따라 미리 JIT 컴파일된 패키지를 포함하는 이미지가 표시됩니다.

여러 버전의 .NET Core 및 ASP.NET Core 이미지가 있지만 기본 계층을 비롯하여 모두 하나 이상의 계층을 공유합니다. 따라서 이미지를 저장하는 데 필요한 디스크 공간의 크기는 작고 사용자 지정 이미지와 해당 기본 이미지 간의 델타로만 구성됩니다. 결과적으로 레지스트리에서 이미지를 빠르게 끌어옵니다.

Docker 허브에서 .NET 이미지 리포지토리를 탐색하는 경우 태그로 분류되거나 표시된 여러 이미지 버전을 찾을 수 있습니다. 이러한 태그를 통해 다음 표와 같이 필요한 버전에 따라 사용할 항목을 결정할 수 있습니다.

-   microsoft/**aspnetcore:2.0**

        ASP.NET Core, with runtime only and ASP.NET Core optimizations, on Linux and Windows (multi-arch)

-   microsoft/**aspnetcore-build:2.0**

        ASP.NET Core, with SDKs included, on Linux and Windows (multi-arch)


>[!div class="step-by-step"]
[이전](net-container-os-targets.md) [다음](../architect-microservice-container-applications/index.md)
