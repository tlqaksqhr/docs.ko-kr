---
title: "공식.NET Docker 이미지"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 공식.NET Docker 이미지"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 6f14bd0cf55a552f3881d755ebe7389f000975d8
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="official-net-docker-images"></a>공식.NET Docker 이미지

공식.NET Docker 이미지는 Docker 이미지 작성 및 Microsoft에서 최적화 합니다. Microsoft 저장소에서 공개적으로 사용할 수 있는 [Docker 허브](https://hub.docker.com/u/microsoft/)합니다. 각 저장소.NET 버전에 따라 및 운영 체제와 버전 (Linux Debian, Alpine Linux, Windows Nano Server, Windows Server Core 등)에 따라 여러 이미지를 포함할 수 있습니다.

.NET 저장소에 대 한 Microsoft의 비전은 세분화 된 이어서 초점을 맞추고 리포지토리 여기서 리포지토리는 특정 시나리오 나 작업입니다. 예를 들어,는 [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) ASP.NET Core 이미지 추가 최적화 하므로 컨테이너를 제공 하기 때문에 Docker에 ASP.NET Core를 사용 하 여 빠르게 시작할 수 때 이미지를 사용 해야 합니다.

반면에 기반으로.NET Core 콘솔 앱 용.NET Core 이미지 (microsoft/dotnet) 사용 됩니다. 예를 들어 일괄 처리, Azure WebJobs 및 기타 콘솔 시나리오.NET Core를 사용 해야 합니다. 이러한 이미지는 더 작은 컨테이너 이미지에는 ASP.NET Core 스택을 포함 하지 않습니다.

대부분 이미지 리포지토리 뿐 아니라 특정 프레임 워크 버전을 선택할 수 있도록 하는 데도 OS (Linux 배포판 또는 Windows 버전)를 선택 합니다. 광범위 한 태그를 제공 합니다.

Microsoft에서 제공 하는 공식.NET Docker 이미지에 대 한 자세한 내용은 참조는 [.NET Docker Images 요약](https://aka.ms/dotnetdockerimages)합니다.

## <a name="net-core-and-docker-image-optimizations-for-development-versus-production"></a>개발 및 프로덕션에 대 한.NET core 및 Docker 이미지 최적화

개발자를 위한 Docker 이미지를 만들 때 Microsoft는 다음과 같은 주요 시나리오에 중점을 두었습니다.

-   에 사용 되는 이미지 *개발* 및.NET Core 응용 프로그램을 빌드합니다.

-   에 사용 되는 이미지 *실행* .NET Core 응용 프로그램입니다.

이유의 여러 이미지? 개발, 빌드 및 실행 중인 컨테이너 화 된 응용 프로그램을 하는 경우 대개 서로 다른 우선 순위를가지고 있습니다. 이러한 별도 작업에 대 한 서로 다른 이미지를 거쳐 개발, 빌드 및 응용 프로그램 배포의 별도 프로세스 최적화는 데 도움이 됩니다.

### <a name="during-development-and-build"></a>개발 및 빌드 중

개발 하는 동안 중요 한 것은 속도 변경 내용 및 변경 내용을 디버깅 하는 기능을 반복할 수 있습니다. 이미지의 크기 코드를 변경 하 고 신속 하 게 변경 내용을 확인 하는 기능으로 중요 하지 않습니다. 일부 도구 및 "빌드 에이전트 컨테이너" 개발 하는 동안 ASP.NET Core 이미지 (빌드-microsoft/aspnetcore) 개발을 사용 하 고 프로세스를 빌드합니다. Docker 컨테이너 안에 빌드하는 경우 중요 한 측면에 응용 프로그램을 컴파일하는 데 필요한 요소는 있습니다. 여기에 컴파일러 및.NET 종속성 및 npm와 같은 웹 개발 종속성 Gulp, Bower 합니다.

이러한 유형의 빌드 이미지 중요 한 이유는 무엇입니까? 프로덕션 환경에이 이미지를 배포 하지 마십시오. 만으로도 프로덕션 이미지에 배치 하면 콘텐츠를 작성 시 사용 하는 이미지입니다. 이 이미지 (CI) 연속 통합 환경 또는 빌드 환경에서 사용할 수 있도록 합니다. 예를 들어, 빌드 에이전트에서 직접 모든 응용 프로그램 종속성을 수동으로 설치 하는 대신 (예: VM)를 호스트, 응용 프로그램을 빌드하는 데 필요한 모든 종속성이 있는.NET Core 빌드 이미지를 인스턴스화하는 빌드 에이전트입니다. 빌드 에이전트는 이 Docker 이미지를 실행하는 방법만 알고 있으면 됩니다. 이 CI 환경을 간소화 하 고 훨씬 더 예측 가능 합니다.

### <a name="in-production"></a>프로덕션 환경에서

프로덕션 환경에서 중요 한 점은 배포 하 고 프로덕션.NET Core 이미지를 기준으로 하 여 컨테이너를 시작할 수 속도입니다. 따라서 런타임 전용 이미지에 따라 [microsoft/aspnetcore](https://hub.docker.com/r/microsoft/aspnetcore/) 이동할 수 있습니다 신속 하 게 네트워크를 통해 Docker 레지스트리에서 Docker 호스트에 있도록 작습니다. 내용이 실행할 준비가 되었습니다. 결과 처리 하는 컨테이너를 시작에서 가장 빠른 시간을 설정 합니다. Docker 모델에서은 C에서 컴파일에 없어도\# 코드를 여기로 dotnet 빌드를 실행 하거나 dotnet 게시할 때 때 컨테이너를 사용 빌드입니다.

이 최적화 된 이미지의 이진 파일 및 응용 프로그램을 실행 하는 데 필요한 기타 콘텐츠를 넣습니다. 예를 들어 dotnet에서 만들어진 콘텐츠가 게시 컴파일된.NET 바이너리, 이미지,.js, 및.css 파일을 포함 합니다. 시간이 지남에 따라 미리 jit 패키지를 포함 하는 이미지를 볼 수 있습니다.

여러 버전의.NET Core 및 ASP.NET Core 이미지에는 없지만 모두 기본 레이어를 포함 하 여 하나 이상의 레이어를 공유 합니다. 따라서 이미지를 저장 하는 데 필요한 디스크 공간의 크기는 작습니다. 사용자 지정 이미지와 해당 기본 이미지 간의 델타의만 구성 됩니다. 결과 레지스트리에서 이미지를 끌어오려면 빠른 된다는 점입니다.

Docker 허브에서.NET 이미지 저장소를 탐색 하는 경우에 분류 또는 태그로 표시 여러 이미지 버전을 찾을 수 있습니다. 이러한 태그 확인할 결정 하는 다음 표에 것과 같은 필요한 버전에 따라 사용할 수 있습니다.

-   microsoft /**aspnetcore:2.0**

        ASP.NET Core, with runtime only and ASP.NET Core optimizations, on Linux and Windows (multi-arch)

-   microsoft /**aspnetcore-빌드: 2.0**

        ASP.NET Core, with SDKs included, on Linux and Windows (multi-arch)


>[!div class="step-by-step"]
[이전] (net-컨테이너-os-targets.md) [다음] (... /architect-microservice-container-applications/index.md)
