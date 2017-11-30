---
title: "서비스 패브릭에 Windows 컨테이너를 배포 하는 경우"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 서비스 패브릭에 Windows 컨테이너를 배포 하는 경우"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 21b6c348991e07dac7dbc9d327b63fa88a588ba4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="when-to-deploy-windows-containers-to-service-fabric"></a>서비스 패브릭에 Windows 컨테이너를 배포 하는 경우

Windows 컨테이너를 기반으로 하는 응용 프로그램 더욱 해소 IaaS Vm에서 다른 페이지로 이동 하는 플랫폼을 사용 하 여 신속 하 게 할 수 있습니다. 자동화 된 향상 된 확장성 및 높은 확장성, 이므로 배포의 경우 전체 관리 경험을 크게 향상 된 기능을 위해 업그레이드 하는 작업, 버전 관리, 롤백 및 상태 모니터링. Orchestrator는 Microsoft Azure 클라우드 뿐만 아니라 온-프레미스, 또는 사설 클라우드에서 다른 클라우드에도 사용할 수 있는 Azure 서비스 패브릭와 이러한 목표를 달성할 수 있습니다.

대부분의 조직에서는 아니며 해지 되며 두 가지 이유로 컨테이너에 모놀리식 기존 응용 프로그램을 이동 합니다.

-   비용된 절감, 통합 및 기존 하드웨어 또는 더 높은 밀도에서 실행 중인 응용 프로그램에서 제거 되었기 때문입니다.

-   개발 및 운영 간의 일관 된 배포 계약입니다.

비용 절감을 추진 하는 것은 이해할 수 있도록와 가능성이 모든 조직 목표를 추적 됩니다. 일관 된 배포를 평가 하려면 어렵습니다 이지만 중요로 동일 하 게 합니다. 일관 된 배포 계약 코드 개발자 자유롭게, 적합 한 기술을 사용 하 여 선택할 수는 운영 팀을 배포 하 고 응용 프로그램을 관리 하는 단일 방법을 가져옵니다 의미 합니다. 본이 계약의 많은 다른 기술의 복잡 한 처리 작업이 필요 하거나 개발자가 특정 기술만 사용할 강제 불편을 완화 합니다. 기본적으로, 각 응용 프로그램은 자체 포함된 배포 이미지에서 컨테이너 화 된 합니다.

일부 조직에서는 현대화 microservices (클라우드 액세스에 최적화 된 / 클라우드 네이티브 응용 프로그램)를 추가 하 여 계속 합니다. 대부분의 조직에서는 여기 (클라우드 DevOps 지원)를 중지 합니다. 그림 4-8과 같이 이러한 조직에 필요 하지 수 있으므로 microservices 아키텍처 이동 하지 않습니다. 어떤 경우 든, 이미 받게는 컨테이너 및 서비스 패브릭을 사용 하 여 배포를 포함 하는 제공 전체 관리 환경을 업그레이드 하는 이점, 버전 관리, 롤백 및 상태 모니터링.

> ![이동할 서비스 패브릭 응용 프로그램](./media/image8.png)
>
> **그림 4-8입니다.** 이동할 서비스 패브릭 응용 프로그램

서비스 패브릭을 기존 코드를 다시 사용 및 단순히 이동 하는 주요 방법은입니다. 따라서 Windows 컨테이너를 사용 하 여 현재.NET Framework 응용 프로그램을 마이그레이션하고 서비스 패브릭에 배포할 수 있습니다. 쉽게 이동 현대화, 결국 새 microservices를 추가 하 여 보관할 수 수 있습니다.

서비스 패브릭 다른 orchestrators을 비교할 때에 서비스 패브릭은 Windows 기반 응용 프로그램 및 서비스 실행에 매우 성숙한 강조 표시 해야 합니다. Windows 기반 서비스 및 응용 프로그램, Microsoft에서 1 단계, 중요 한 제품을 포함 하 여 연도 대 한 서비스 패브릭을 실행 합니다. Windows 컨테이너 (2017 년 5 월)에 대 한 일반 공급을 첫 번째 orchestrator 이었습니다. Kubernetes, DC/OS 및 docker는 Docker Swarm와 같은 다른 컨테이너는 Windows Fabric 서비스 기반 응용 프로그램 및 Windows 컨테이너 보다 덜 성숙한 하지만 Linux에서 더 성숙한입니다.

서비스 패브릭의 최종 목표는 microservices 접근 방식을 사용 하 여 응용 프로그램을 구축의 복잡성을 줄이는 것입니다. 결국 하려는 응용 프로그램, 비용이 많이 드는 재설계 방지 하기 위해 특정 수입니다. 작은 항목부터 시작, 필요할 때의 크기를 조정, 서비스 사용 안 함, 새로운 서비스를을 추가한 고객이 사용 하는 응용 프로그램을 개선 합니다. 회원님의 대부분의 개발자가 보다 쉽게 수행할 microservices 수행할 수 있도록 해결 해야 할에 아직 다른 많은 문제가 있습니다. 현재 방금 아니며 해지 하 고는 Windows 컨테이너 응용 프로그램을 이동 하지만 microservices 나중에 따라 컨테이너에 추가 하는 방법에 대 한 하려고 하는 경우 서비스 패브릭 부분은입니다.

>[!div class="step-by-step"]
[이전](when-to-deploy-windows-containers-to-azure-vms-iaas-cloud.md)
[다음](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
