---
title: Azure 컨테이너 서비스 (즉, Kubernetes)에 Windows 컨테이너를 배포 하는 경우
description: Azure 클라우드 및 Windows 컨테이너와 기존.NET 응용 프로그램을 최신식 | Azure 컨테이너 서비스 (즉, Kubernetes)에 Windows 컨테이너를 배포 하는 경우
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: b7f106e2b79a2c6bb24733debf7f4828505d66a6
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
ms.locfileid: "33958173"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Azure 컨테이너 서비스 (즉, Kubernetes)에 Windows 컨테이너를 배포 하는 경우

Azure 컨테이너 서비스를 Azure에 맞게 인기 있는 오픈 소스 도구 및 기술 구성을 최적화합니다. 사용자 컨테이너 및 응용 프로그램 구성에 대 한 이식성을 제공 하는 열린 솔루션 가져오기 Orchestrator 도구, 호스트, 수 및 크기를 선택 합니다. Azure 컨테이너 서비스를 인프라를 처리합니다.

Kubernetes, docker는 Docker Swarm 또는 DC/OS와 같은 오픈 소스 orchestrators와 이미 작업 하는 경우에 기존 관리 명시할 컨테이너 작업을 클라우드로 이동할 수를 변경할 필요가 없습니다. 익숙한 이미 응용 프로그램 관리 도구를 사용 하 고 사용자가 선택한 orchestrator에 대 한 표준 API 끝점을 통해 연결 합니다.

이러한 모든 orchestrators은 완성도 높은 환경, Linux Docker 컨테이너를 사용 하는 하지만 Windows 컨테이너에 대 한 미리 보기 상태에만 포함 될 수 있습니다.

예를 들어 Kubernetes, 컨테이너에 대 한 지원은 Windows 컨테이너 Kubernetes에 사용 하 여 네이티브 (첫 번째 클래스 시민) (초기 2018 현재 ACS에서 미리 보기)에 효과적입니다.

하지만 중요 참고:의 진화 하 고 "더 많은 PaaS" Kubernetes에 대 한 ACS (Azure 컨테이너 서비스)의 버전은 AKS (Azure Kubernetes 서비스), Windows 컨테이너는 여전히 Q2 2018 기준으로 지원 되지 않지만 곧 지원 될 예정입니다.

>[!div class="step-by-step"]
[이전](when-to-deploy-windows-containers-to-service-fabric.md)
[다음](choosing-azure-compute-options-for-container-based-applications.md)
