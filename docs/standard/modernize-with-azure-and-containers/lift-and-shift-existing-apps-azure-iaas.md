---
title: "기존 응용 프로그램이 Azure IaaS 이동할"
description: "기존.NET 응용 프로그램을 Azure 클라우드 및 Windows 컨테이너를 현대화 합니다."
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 7f7715bb0ec323874271a7e9ce1c666e23e33b22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="lift-and-shift-existing-apps-azure-iaas"></a>기존 응용 프로그램이 Azure IaaS 이동할

> 비전:으로 하드웨어의 온-프레미스 투자와 총 비용을 줄이고 유지 관리, 네트워킹 단순히를 다시 호스트 하는 클라우드에서 기존 응용 프로그램의 첫 번째 단계입니다.

들어가기 전에 *어떻게* 서비스 (IaaS) 플랫폼으로 Azure 인프라를 기존 응용 프로그램을 마이그레이션하려면 중요 한 이유를 분석 하는 *이유* IaaS에 직접 마이그레이션할 원하는 azure입니다. 기본적으로이 현대화 완성도 수준 시나리오, 현재 온-프레미스 인프라를 사용 하 여 계속 진행 하지 않고 클라우드 Vm을 사용 하 여 시작 것입니다.

다른 분석 점은 *이유* 방금 더 많은 고급 Azure에서 관리 되는 서비스를 추가 하는 대신 순수 IaaS 클라우드로 마이그레이션하는 것이 좋습니다. 경우의 수를 결정 해야 IaaS를 처음에 필요 합니다.

그림 2-1 현대화 완성도 수준의 클라우드 인프라를 갖춘 응용 프로그램을 배치 합니다.

![클라우드 인프라를 갖춘 응용 프로그램을 위치 지정](./media/image2-1.png)

> **그림 2-1입니다.** 클라우드 인프라를 갖춘 응용 프로그램을 위치 지정

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a>기존.NET 웹 응용 프로그램에서는 Azure IaaS 마이그레이션하는 이유 

비용 절감을 달성 하기 위해 초기 IaaS 수준에서도 클라우드로 마이그레이션하는 주요 이유는 합니다. 더 많은 관리 되는 인프라 서비스를 사용 하 여 조직의 하드웨어 유지 관리, 서버 또는 VM 프로 비전 및 배포 및 관리 인프라에 투자를 줄일 수 있습니다.

앱에서 클라우드로 이동 하도록 결정을 내린 후 선택 하는 이유에 IaaS PaaS는 단순히는 같은 더 많은 고급 옵션 대신 IaaS 환경의 주요 이유는 더 익숙할 것입니다. 온-프레미스 환경에서는 현재와 비슷한 환경으로 이동, 가장 빠른 경로 클라우드를 만들어 더 낮은 학습 곡선을 제공 합니다.

그러나 클라우드로 가장 빠른 경로 라인 것은 아닙니다는 클라우드에서 실행 중인 응용 프로그램에서 가장 효과적 권한을 얻게 됩니다. 어떤 조직에서 이미 도입 된 클라우드 DevOps 지원 및 PaaS (클라우드 최적화) 완성도 수준에서 클라우드 마이그레이션 가장 큰 이점을 얻게 됩니다.

또한 되었기 때문에 응용 프로그램을 더 쉽게 최신식 다시 이미에 IaaS 클라우드에서 실행 될 때 나중에 설계 하 분명 하 게 합니다. 부분적 때문에 응용 프로그램 데이터 마이그레이션을 이미 달성 되었습니다. 또한 조직 됩니다가 클라우드에서 작업에 필요한 기술 얻은 하려고 하 교대조에서 "클라우드 문화권"입니다.

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a>PaaS로 대신 IaaS를 마이그레이션 시기

다음 섹션에서는에서는 주로 PaaS 플랫폼 및 서비스에 기반 하는 클라우드 DevOps 지원 응용 프로그램에 설명 합니다. 이러한 응용 프로그램을 클라우드로 마이그레이션하면 대부분 이점을 제공 합니다.

목표는 클라우드에서 기존 응용 프로그램을 이동 하는 단순히, 하는 경우 먼저, Azure 앱 서비스에서 실행 되도록를 대폭 수정 해야 하는 기존 응용 프로그램을 식별 합니다. 이러한 앱에는 첫 번째 후보 이어야 합니다.

그런 다음 원하지 않거나 Windows 컨테이너 및 또는 Azure 서비스 패브릭 또는 Kubernetes 같은 orchestrators로 이동할 수 없습니다, 아직 다음 있으면 일반 Vm (IaaS)를 사용 합니다.

하지만 올바르게 구성, 안전 하 게 유지 하 고, Vm을 유지 해야 한다는 훨씬 더 많은 시간 및 Azure에서 PaaS 서비스를 사용 하는 IT 전문 염두에서에 둬야 합니다. Azure 가상 컴퓨터를 고려 하는 경우 수행 하는 계정으로 패치, 업데이트 및 VM 환경을 관리 하는 데 필요한 지속적인 유지 관리 작업이 있는지 확인 합니다. Azure 가상 컴퓨터 IaaS를입니다.

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a>Azure 마이그레이션을 사용 하 여 분석 하 고 기존 응용 프로그램을 Azure 마이그레이션

클라우드로 마이그레이션의 필요가 어려울 수 있습니다. 하지만 대부분의 조직에는 환경 및 응용 프로그램, 작업, 및 데이터 간의 긴밀 하 게 상호 종속 관계에 대 한 심층 파악-시작 하는 데 어려움 합니다. 해당 표시 하지 않고 앞으로 경로 계획 하기 어려울 수 있습니다. 성공적인 마이그레이션에는 데 필요한 작업에 세부 정보 없이 조직 내에서 오른쪽의 대화를 사용할 수 없습니다. 비용 이점에 대해 충분히 알 수 없는 또는 여부 작업 방금 리프트 및-시프트 하거나 수를 성공적으로 마이그레이션하려면 상당한 재작업 해야 합니다. 대부분의 조직에서는 원하는 대로 당연 합니다.

[Azure 마이그레이션](https://aka.ms/azuremigrate) 지침, 통찰력, 및 Azure로 마이그레이션에 도움을 주는 데 필요한 메커니즘을 제공 하는 새로운 서비스입니다. Azure 마이그레이션 작업을 제공합니다.

-   검색 및 온-프레미스 가상 컴퓨터에 대 한 평가

-   다중 계층 응용 프로그램의 높은 정확도 검색에 기본 제공 된 종속성 매핑

-   Azure 가상 컴퓨터에 지능형 적정

-   보고를 사용 하며 잠재적인 문제에 대 한 지침이 호환성

-   데이터베이스 검색 및 마이그레이션에 대 한 Azure 데이터베이스 관리 서비스와 통합

Azure 마이그레이션 작업 마이그레이션할 비즈니스에 미치는 영향을 최소화 하면서 Azure에서 예상 대로 실행할 수 있는 확신을 줍니다. 적절 한 도구와 지침 최대 해당 중요 한 성능 보장 하는 동안 투자 수익률을 얻을 수 있습니다 및 안정성 요구 사항을 충족 합니다.

그림 2-2 Azure 마이그레이션에서 수행 하는 모든 서버 및 응용 프로그램 연결에 대 한 기본 제공 종속성 매핑을 보여 줍니다.

![클라우드 인프라를 갖춘 응용 프로그램을 위치 지정](./media/image2-2.png)

> **그림 2-2입니다.** 클라우드 인프라를 갖춘 응용 프로그램을 위치 지정

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a>Azure Site Recovery를 사용 하 여 기존 Vm을 Azure Vm에 마이그레이션

끝에 끝의 일환으로 [Azure 마이그레이션](https://aka.ms/azuremigrate), [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) Azure의 Vm에 웹 앱을 쉽게 마이그레이션할 수는 데 사용할 수 있는 도구입니다. 보조 온-프레미스 위치에 복제 또는 온-프레미스 Vm 및 물리적 서버를 Azure에 복제 사이트 복구를 사용할 수 있습니다. 온-프레미스에서 지원 되는 Azure VM에서 실행 되는 작업에도 복제할 수 있습니다 *Hyper-v* VM의는 *VMware* VM을 Windows 또는 Linux 물리적 서버입니다. Azure로의 복제를 보조 데이터 센터를 유지 관리 하 고 비용을 제거 합니다.

사이트 복구에도 부분적으로 하이브리드 환경에 맞게 이루어집니다 온-프레미스와 Azure에 의해서도 영향을 받습니다. 사이트 복구 Vm에서 실행 되는 앱을 유지 하 여 비즈니스 연속성을 보장 하는 데 도움이 됩니다 및 온-프레미스 물리적 서버를 사용할 수 있는 사이트 작동이 중지 된 경우. 복제를 지속적으로 사용할 수 있는 보조 위치에서 기본 사이트를 사용할 수 없는 경우 Vm 및 물리적 서버에서 실행 되는 작업. 작업을 다시 실행 하 고 위쪽 인 경우 기본 사이트를 복구 합니다.

그림 2-3 Azure Site Recovery를 사용 하 여 여러 VM 마이그레이션의 실행을 보여 줍니다.

![클라우드 인프라를 갖춘 응용 프로그램을 위치 지정](./media/image2-3.png)

> **그림 2-3입니다.** 클라우드 인프라를 갖춘 응용 프로그램을 위치 지정

### <a name="additional-resources"></a>추가 리소스

-   **Azure 마이그레이션 데이터 시트**

    [https://aka.ms/azuremigration\_데이터 시트](https://aka.ms/azuremigration\_datasheet)

-   **Azure 마이그레이션**

    [http://azuremigrationcenter.com/](http://azuremigrationcenter.com/)

-   **사이트 복구를 사용 하 여 Azure로 마이그레이션**

    [https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure](https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure)

-   **Azure Site Recovery 서비스 개요**

    [https://docs.microsoft.com/azure/site-recovery/site-recovery-overview](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview)

-   **Azure Vm에는 AWS의 마이그레이션 Vm**

    [https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure](https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure)

>[!div class="step-by-step"]
[이전](index.md)
[다음](migrate-your-relational-databases-to-azure.md)
