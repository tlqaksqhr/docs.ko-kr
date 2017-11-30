---
title: "일반적인 지침"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 일반적인 지침"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 22dea926e77079e4f543934613ced13a28b2dae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="general-guidance"></a>일반적인 지침

이 섹션에서는.NET Framework 또는.NET Core를 선택 하는 경우에 대 한 요약을 제공 합니다. 에서는 다음 섹션에서는 이러한 선택 항목에 대 한 자세한 정보를 제공 합니다.

컨테이너 화 된 Docker 서버 응용 프로그램에 대 한 Linux 또는 Windows 컨테이너와 함께.NET Core를 사용 해야 경우:

-   플랫폼 간 요구 사항이 있습니다. 예를 들어 Linux와 Windows 컨테이너를 사용 하려면.

-   응용 프로그램 아키텍처 microservices를 기반으로 합니다.

-   비용을 절감 하기 위해 향상 된 밀도 달성 하기 위해 컨테이너 또는 하드웨어 단위당 컨테이너가 더 이상 당 적은 공간만 사용 하 고 컨테이너 빠른 시작 해야 합니다.

즉, 새 컨테이너 화 된.NET 응용 프로그램을 만들 때.NET Core 기본 선택으로 고려해 야 합니다. 다양 한 이점을 있으며 컨테이너 대 한 개념 및 작업 스타일에 가장 적합 합니다.

.NET Core를 사용 하 여 또 다른 이점은 동일한 컴퓨터에서 응용 프로그램에 대 한 병렬.NET 버전을 실행할 수 있습니다. 이 기능은 컨테이너 응용 프로그램에 필요한.NET 버전을 격리 하기 때문에 서버 또는 컨테이너를 사용 하지 않는 Vm에 대 한 더 중요 합니다. (으로 기본 운영 체제와 호환 됩니다.)

Windows 컨테이너와 컨테이너 화 된 Docker 서버 응용 프로그램에 대 한.NET Framework를 사용 해야 경우:

-   응용 프로그램에 현재.NET Framework를 사용 하 여와 Windows에 강력한 의존 합니다.

-   .NET Core에서 지원 되지 않는 Windows Api를 사용 해야 합니다.

-   제 3 자.NET 라이브러리 또는.NET Core를 사용할 수 없는 NuGet 패키지를 사용 해야 합니다.

Docker에서.NET Framework를 사용 하 여 배포 문제를 최소화 하 여 배포 환경을 향상 시킬 수 있습니다. 이 [ *"리프트 및 이동" 시나리오* ](https://aka.ms/liftandshiftwithcontainersebook) containerizing ASP.NET WebForms, MVC 웹 응용 프로그램 또는 WCF (처럼 기존.NET Framework와 함께 원래 개발 된 레거시 응용 프로그램에 대 한 중요 Windows Communication Foundation) 서비스입니다.

### <a name="additional-resources"></a>추가 리소스

-   **전자책: Azure와 Windows 컨테이너와 기존.NET Framework 응용 프로그램을 최신식**
    [*https://aka.ms/liftandshiftwithcontainersebook*](https://aka.ms/liftandshiftwithcontainersebook)

-   **앱 샘플: Windows 컨테이너를 사용 하 여 기존 ASP.NET 웹 응용 프로그램의 현대화**
    [*https://aka.ms/eshopmodernizing*](https://aka.ms/eshopmodernizing)


>[!div class="step-by-step"]
[이전] [다음] (net-코어-컨테이너-scenarios.md) (index.md)
