---
title: "Azure 컨테이너 서비스 (즉, Kubernetes)에 Windows 컨테이너를 배포 하는 경우"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | Azure 컨테이너 서비스 (즉, Kubernetes)에 Windows 컨테이너를 배포 하는 경우"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: f5ba7aa2cf14e7ca9f3a1f3eb12bbe236dca7e97
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Azure 컨테이너 서비스 (즉, Kubernetes)에 Windows 컨테이너를 배포 하는 경우

Azure 컨테이너 서비스를 Azure에 맞게 인기 있는 오픈 소스 도구 및 기술 구성을 최적화합니다. 사용자 컨테이너 및 응용 프로그램 구성에 대 한 이식성을 제공 하는 열린 솔루션 가져오기 Orchestrator 도구, 호스트, 수 및 크기를 선택 합니다. Azure 컨테이너 서비스를 인프라를 처리합니다.

Kubernetes, docker는 Docker Swarm 또는 DC/OS와 같은 오픈 소스 orchestrators와 이미 작업 하는 경우에 기존 관리 명시할 컨테이너 작업을 클라우드로 이동할 수를 변경할 필요가 없습니다. 이미 익숙한, 사용자가 선택한 orchestrator에 대 한 표준 API 끝점을 통해 연결 하는 응용 프로그램 관리 도구를 사용 합니다.

사용 하는 것 이지만, Linux Docker 컨테이너도 지원 Windows 컨테이너 2017 (이전와 최근 orchestrator에 따라)의으로 하는 경우 이러한 모든 orchestrators 완성도 높은 환경을 결정 됩니다.

예를 들어 Kubernetes, 컨테이너에 대 한 지원은 Windows 컨테이너 Kubernetes에 사용 하 여 네이티브 (첫 번째 클래스 시민) 매우 효과적이 고 신뢰할 수 있는 이기도 (미리 보기 될 때까지 초기 대체 2017).

>[!div class="step-by-step"]
[이전](when-to-deploy-windows-containers-to-service-fabric.md)
[다음](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
