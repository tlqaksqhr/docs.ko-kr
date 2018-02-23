---
title: "일반 지침"
description: "컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 일반 지침"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: fa58d1d81b2d1523baf123d4963db2ca00fee15d
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="general-guidance"></a>일반 지침

이 섹션에서는 .NET Framework 또는.NET Core를 선택하는 경우에 대해 요약합니다. 이 선택에 대한 더 자세한 내용은 다음 섹션에서 설명합니다.

다음과 같은 상황에서는 컨테이너화된 Dockeer 서버 응용 프로그램에 대해 .NET Core를 Linux 또는 Windows Containers에 사용해야 합니다.

-   플랫폼 간 요구 사항이 있습니다. 예를 들어 Linux와 Windows 컨테이너를 모두 사용하려 합니다.

-   응용 프로그램 아키텍처가 마이크로 서비스를 기반으로 합니다.

-   비용을 낮추기 위해 하드웨어당 밀도를 높이거나 또는 더 많은 컨테이너를 달성하려는 경우 컨테이너당 공간을 줄이고 더 빠르게 컨테이너를 시작해야 합니다.

즉 컨테이너화된 새 .NET 응용 프로그램을 만들 때는 .NET Core를 기본 선택으로 고려해야 합니다. 여러 장점이 있고 컨테이너 개념과 작업 스타일에 가장 잘 맞습니다.

.NET Core를 사용하면 같은 머신 안에서 응용 프로그램에 대해 .NET 버전을 함께 실행한다는 또 다른 장점이 있습니다. 이러한 장점은 컨테이너가 앱이 필요한 .NET 버전을 격리하기 때문에 컨테이너를 사용하지 않는 서버나 VM에서 특히 중요합니다 (기본 OS와 호환되는 한).

다음과 같은 상황에서는 컨테이너화된 Dockeer 서버 응용 프로그램에 대해 .NET Framework를 Windows Containers에 사용해야 합니다.

-   응용 프로그램에서 현재 .NET Framework를 사용하며 Windows에 대한 의존도가 높습니다.

-   .NET Core에서 지원되지 않는 Windows API를 사용해야 합니다.

-   .NET Core에 사용할 수 없는 타사 .NET 라이브러리 또는 NuGet 패키지를 사용해야 합니다.

Docker에서 .NET Framework를 사용하면 배포 문제 최소화를 통해 배포 환경을 개선할 수 있습니다. 이러한 [*"이동 편의" 시나리오*](https://aka.ms/liftandshiftwithcontainersebook)는 ASP.NET WebForms, MVC 웹앱 또는 WCF(Windows Communication Foundation) 서비스 같은 기존 .NET Framework로 개발된 레거시 응용 프로그램을 컨테이너화하는 데 중요합니다.

### <a name="additional-resources"></a>추가 리소스

-   **전자책: Azure 및 Windows Containers를 통한 기존 .NET Framework 응용 프로그램 현대화**
    [*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)

-   **앱 샘플: Windows Containers를 통한 레거시 ASP.NET 웹 앱 현대화**
    [*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)


>[!div class="step-by-step"]
[이전] (index.md) [다음] (net-core-container-scenarios.md)
