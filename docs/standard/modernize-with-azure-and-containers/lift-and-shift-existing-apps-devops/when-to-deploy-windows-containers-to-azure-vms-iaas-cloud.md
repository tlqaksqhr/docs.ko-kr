---
title: Azure Vm (IaaS 클라우드)에 Windows 컨테이너를 배포 하는 경우
description: 컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | Azure Vm (IaaS 클라우드)에 Windows 컨테이너를 배포 하는 경우
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.prod: .net
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d1a9f0593b4b84cbe25da9e4164f4ecbe8513831
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="when-to-deploy-windows-containers-to-azure-vms-iaas-cloud"></a>Azure Vm (IaaS 클라우드)에 Windows 컨테이너를 배포 하는 경우

또한 Windows 컨테이너를 사용 하는 경우에 조직에서 Azure Vm을 사용 하는, 하는 경우 여전히 IaaS 처리입니다. 부하 분산 된 인프라의 여러 Vm에 배포 해야 할 때 확장성이 높은 응용 프로그램에 대 한 인프라 작업, VM OS 패치 및 인프라 복잡성 해당 다루는 것입니다. Azure VM에서 Windows 컨테이너를 사용 하기 위한 주요 시나리오입니다.

-   **개발/테스트 환경**: 클라우드에서 A VM은 개발 및 테스트 클라우드에서 하는 데 적합 합니다. 신속 하 게 만들 하거나 필요에 따라 환경을 중지할 수 있습니다.

-   **소형 및 중간 규모의 확장성 요구**: 프로덕션 환경에 대 한 Vm 몇 번만 해야 하는 시나리오에서 적은 수의 Vm 관리 저렴 한 때까지 수 orchestrators 같은 고급 PaaS 환경으로 이동할 수 있습니다.

-   **프로덕션 환경에 기존 배포 도구**: Vm 또는 완전 복구 서버 (예: Puppet 또는 유사한 도구)를 복잡 한 배포 하는 도구에 투자를 온-프레미스 환경에서 이동 될 수 있습니다. 프로덕션 환경 배포 절차의 변경을 최소화 하면서 클라우드로 이동, 이러한 도구를 사용 하 여 Azure Vm에 배포할 계속 수 있습니다. 그러나 배포의 단위로 배포 환경을 개선 하기 위해 Windows 컨테이너를 사용 합니다.

>[!div class="step-by-step"]
[이전](when-to-deploy-windows-containers-in-your-on-premises-iaas-vm-infrastructure.md)
[다음](when-to-deploy-windows-containers-to-service-fabric.md)
