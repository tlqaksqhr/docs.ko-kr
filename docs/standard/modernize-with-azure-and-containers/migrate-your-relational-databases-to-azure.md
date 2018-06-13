---
title: 관계형 데이터베이스를 azure로 마이그레이션
description: 기존.NET 응용 프로그램을 Azure 클라우드 및 Windows 컨테이너를 최신식 | 관계형 데이터베이스를 azure로 마이그레이션
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: fe1bf5820c2306beb380749b34d5a56964e016e4
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2018
ms.locfileid: "33956087"
---
# <a name="migrate-your-relational-databases-to-azure"></a>관계형 데이터베이스를 azure로 마이그레이션

비전: Azure는 가장 포괄적인 데이터베이스 마이그레이션을 제공 합니다.

Azure에서 데이터베이스 서버 (순수 리프트 및 shift) IaaS Vm에 직접 마이그레이션할 수 있습니다 또는 추가 혜택에 대 한 Azure SQL 데이터베이스로 마이그레이션할 수 있습니다. Azure SQL 데이터베이스 관리 되는 인스턴스 및 전체 데이터베이스-as a service (DBaaS) 옵션을 제공 합니다. 그림 3-1 여러 관계형 데이터베이스는 Azure에서 사용할 수 있는 마이그레이션 경로 보여 줍니다.

![Azure에서 데이터베이스 마이그레이션 경로](./media/image3-1.png)

> **그림 3-1.** Azure에서 데이터베이스 마이그레이션 경로

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a>Azure SQL 데이터베이스 관리 되는 인스턴스를 마이그레이션 시기

대부분의 경우 Azure SQL 데이터베이스 관리 되는 인스턴스를 Azure로 데이터를 마이그레이션할 때 고려할 최선의 됩니다. SQL Server 데이터베이스를 마이그레이션하는 응용 프로그램 아키텍처를 변경 하거나 데이터 또는 데이터 액세스 코드를 변경할 필요가 없습니다 100% 보증 거의 해야 하는 경우 Azure SQL 데이터베이스의 관리 되는 인스턴스 기능을 선택 합니다.

Azure SQL 데이터베이스 관리 되는 인스턴스는 표준 Azure SQL 데이터베이스 (단일 데이터베이스 모델)에서 제공 하는 기능 외의 격리 요구 사항 또는 SQL Server 인스턴스 수준 기능에 대 한 추가 요구 사항이 있는 경우 최상의 옵션입니다. 마지막 하나는 가장 PaaS 지향 선택 하지만 기존의 SQL server의 같은 기능을 제공 하지 않습니다. 마이그레이션 frictions 노출 될 수 있습니다.

예를 들어 SQL Server 기능을 인스턴스 수준에 심층 투자 했습니다 하는 조직에서 관리 되는 인스턴스 SQL로 마이그레이션 도움이 되는 경우 인스턴스 수준 SQL Server 기능의 예 SQL 공용 언어 런타임 (CLR) 통합, SQL Server 에이전트, 포함 및 데이터베이스 간 쿼리 합니다. 이러한 기능에 대 한 지원 표준 Azure SQL 데이터베이스 (단일 데이터베이스 모델)에서 사용할 수 없는 경우

조직은 되는 산업에서 작동 하 고 보안을 위해 격리를 유지 해야 하는 SQL 관리 되는 인스턴스 모델 선택에서 향상 될 수 있습니다.

Azure SQL 데이터베이스에서 관리 되는 인스턴스는 다음과 같은 특징이 있습니다.

- Azure 가상 네트워크를 통해 보안 격리

- 응용 프로그램 표면 호환성, 이러한 기능:

  - SQL Server 에이전트 및 SQL Server Profiler

  - 데이터베이스 간 참조와 쿼리를 SQL CLR 복제, 변경 데이터 캡처 (CDC) 및 Service Broker

- 데이터베이스 크기를 최대 35 확장성

- 이러한 기능을 사용 하 여 최소 가동 중지 시간 마이그레이션:

  - Azure 데이터베이스 마이그레이션 서비스

  - 기본 백업 및 복원 및 로그 전달

이러한 기능을 사용 Azure SQL 데이터베이스를 기존 응용 프로그램 데이터베이스를 마이그레이션할 때의 관리 되는 인스턴스 모델 제공 거의 100 %Paas 이점에 SQL Server에 대 한 합니다. 관리 되는 인스턴스는 인스턴스 수준 기능을 사용 하 여 응용 프로그램 디자인을 변경 하지 않고 계속 하면 SQL Server 환경입니다.

관리 되는 인스턴스는 현재 SQL Server를 사용 하 고 클라우드에서 네트워크 보안에는 유연성 필요 엔터프라이즈의 경우 가장 적합 한 때문일 수 있습니다. SQL 데이터베이스에 대 한 개인 가상 네트워크를 것 같습니다.

## <a name="when-to-migrate-to-azure-sql-database"></a>Azure SQL 데이터베이스로 마이그레이션 시기

앞서 언급 했 듯이 표준 Azure SQL 데이터베이스는 완전히 관리 되는, 관계형 DBaaS 합니다. SQL 데이터베이스는 전 세계 38 데이터 센터 간에 수백만 프로덕션 데이터베이스의 현재 관리합니다. 광범위 한 응용 프로그램 및 구동 세계적인 규모에 고급 데이터 처리를 필요로 하는 데이터를 가장 많이 사용, 중요 한 응용 프로그램을 간단 하 게 트랜잭션 데이터를 관리 하에서 작업을 지원 합니다.

해당 전체 PaaS 기능 때문에 더 잘 가격-궁극적으로 비용을 절감 하 고-없습니다 추가 인스턴스 기능과 그 사용 하 여 기본, 표준 SQL 데이터베이스 응용 프로그램이 있는 경우 프로그램 "기본적으로 선택"으로 표준 Azure SQL 데이터베이스를 이동 해야 합니다. SQL CLR 통합, SQL Server 에이전트 및 데이터베이스 간 쿼리 같은 SQL Server 기능 표준 Azure SQL 데이터베이스에서 지원 되지 않습니다. 이러한 기능은 Azure SQL 데이터베이스 관리 되는 인스턴스 모델에만 사용할 수 있습니다.

Azure SQL 데이터베이스는 응용 프로그램 개발자에 만들어지는 지능형 클라우드 데이터베이스 서비스입니다. 즉시, 다중 테 넌 트 앱을 효율적으로 제공할 수 있도록 가동 중지 시간 없이 크기가 조정 되는 유일한 클라우드 데이터베이스 서비스 이기도 합니다. 궁극적으로, Azure SQL 데이터베이스 혁신을 하는 데 시간이 더 오래 유지 및 시장 출시 시간을 가속화 합니다. 보안 응용 프로그램을 빌드하고 언어 및 선호 하는 플랫폼을 사용 하 여 SQL 데이터베이스 연결 수 있습니다.

Azure SQL 데이터베이스는 다음과 같은 이점을 제공합니다.

- 학습 및 응용 프로그램에 맞게 조정 하는 기본 제공 지능 (기계 학습)

- 요청 시 데이터베이스 프로 비전

- 모든 작업에 대 한 제품의 범위

- 99.99% 가용성 SLA, 0 개 유지 관리

- 데이터 보호를 위한 지리적 복제 및 복원 서비스

- Azure SQL 데이터베이스 지정 시간 복원 기능

- SQL Server 2016에서는 하이브리드 및 마이그레이션을 포함 하 여 호환성

표준 Azure SQL 데이터베이스 보다에 더 가까운 PaaS Azure SQL 데이터베이스 관리 되는 인스턴스. 관리 되는 클라우드에서 많은 혜택을 얻게 됩니다 때문에 표준 Azure SQL 데이터베이스를 선호 합니다. 그러나 Azure SQL 데이터베이스 일반에서 몇 가지 주요 차이점이 있으며 온-프레미스 SQL Server 인스턴스. 기존 응용 프로그램의 데이터베이스 요구 사항 및 enterprise 요구 사항 및 정책에 따라 아닐 적합 하 고 클라우드로 마이그레이션을 계획할 때.

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a>VM (IaaS)에 원래 RDBMS 프로그램을 이동 하는 경우

마이그레이션 옵션 중 하나 원래 관계형 데이터베이스 관리 시스템 RDBMS (), Oracle, IBM DB2, MySQL, PostgreSQL 또는 SQL Server를 포함 하 여 Azure VM에서 실행 중인 유사한 서버를 이동 하는 것입니다. 마이그레이션해야 하는 가장 빠른 클라우드 최소한의 변경 또는 전혀 변경으로 전혀 기존 응용 프로그램의 경우 IaaS 클라우드에서로 직접 마이그레이션을 상당히 많은 옵션을 수 있습니다. 클라우드의 모든 이점을 활용 하는 가장 좋은 방법은 하지 않을 수 있지만 가장 빠른 초기 경로 때문일 합니다.

현재 Microsoft Azure 지원 최대 [331 다른 데이터베이스 서버의](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/category/databases?page=1&subcategories=databases-all) IaaS Vm으로 배포 합니다. 여기에 SQL Server, Oracle, MySQL, PostgreSQL, 및 IBM DB2와 같은 인기 있는 RDBMS MongoDB, Cassandra, DataStax, MariaDB, 및 Cloudera와 같은 다른 많은 NoSQL 데이터베이스 포함 됩니다.

> [!NOTE]
> 이동 되지만 Azure VM에 프로그램 RDBMS에는 (있기 때문에 IaaS)에서 클라우드로 데이터를 마이그레이션할 수는 가장 빠른 방법은 있을 수 있으며,이 방법은 (데이터베이스 관리자 및 IT 전문가) IT 팀에 많은 투자를 해야 합니다. 엔터프라이즈 팀을 설정 하 고 고가용성, 재해 복구 및 SQL Server에 대 한 패치를 관리 해야 합니다. 이 컨텍스트에 모든 관리 권한 사용 하 여 사용자 지정 된 환경도 필요합니다.

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a>VM (IaaS)으로 SQL Server로 마이그레이션 시기

몇 가지 계속 해야 하는 경우 SQL server 일반 VM으로 마이그레이션할 수 있습니다. 예제 시나리오는 SQL Server Reporting Services를 사용 해야 합니다. 대부분의 경우에서 하지만 Azure SQL 데이터베이스 관리 되는 인스턴스 제공할 수 있습니다는 SQL Server VM로의 마이그레이션을 시도 하면 마지막 수단 이어야 합니다. 온-프레미스 SQL server에서 마이그레이션하는 데 필요한 모든 것입니다.

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a>관계형 데이터베이스를 Azure로 데이터베이스 마이그레이션 Azure 서비스를 사용 하 여 

Azure SQL 데이터베이스, Azure SQL 데이터베이스 관리 되는 인스턴스 또는 Azure VM에서 SQL Server 대상 데이터베이스 인지를 Azure에 SQL Server, Oracle, MySQL 등 관계형 데이터베이스를 마이그레이션하려면 Azure 데이터베이스 마이그레이션 서비스를 사용할 수 있습니다.

자동화 된 워크플로 평가 보고를 사용 하면 데이터베이스를 마이그레이션하기 전에 확인 하는 데 필요한 변경을 안내 합니다. 준비 되 면 서비스 Azure를 원본 데이터베이스를 마이그레이션합니다.

원래 RDBMS를 변경할 때마다 다시 테스트 해야 합니다. SQL 한 문장이 나 테스트 결과 따라 응용 프로그램의 개체-관계형 매핑 (ORM) 코드를 변경 하려면 할 수 있습니다.

다른 데이터베이스 (예를 들어 IBM DB2) 있고 리프트 및 shift 방법을 선택할 수 있습니다 계속 하 시겠습니까 해당 데이터베이스를 사용 하 여 azure에서 IaaS Vm으로 더 복잡 한 데이터 마이그레이션을 수행 하려는 경우가 아니면 합니다. 더 복잡 한 데이터 마이그레이션 새 스키마 및 다른 프로그래밍 라이브러리와 다른 데이터베이스 형식으로 마이그레이션하는 경우 때문에 추가 작업이 필요 합니다.

Azure 데이터베이스 마이그레이션 서비스를 사용 하 여 데이터베이스를 마이그레이션하는 방법에 자세한 내용은 [Azure SQL 데이터베이스 관리 되는 인스턴스 및 Azure 데이터베이스 마이그레이션 서비스 빠르게 클라우드로 가져올](https://channel9.msdn.com/Events/Build/2017/P4008)합니다.

## <a name="additional-resources"></a>추가 자료

- **클라우드 SQL Server 옵션 선택: Azure SQL 데이터베이스 (PaaS) 또는 Azure VM (IaaS)에서 SQL Server**

    [https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas](https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas)

- **Azure SQL DB 관리 되는 인스턴스 및 데이터베이스 마이그레이션 서비스 빠르게 클라우드로 가져오기**

    [https://channel9.msdn.com/Events/Build/2017/P4008](https://channel9.msdn.com/Events/Build/2017/P4008)

- **클라우드의 SQL 데이터베이스에 SQL Server 데이터베이스 마이그레이션**

    [https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate](https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate)

- **Azure SQL Database**

    [https://azure.microsoft.com/services/sql-database/?v=16.50](https://azure.microsoft.com/services/sql-database/?v=16.50)

- **가상 컴퓨터에서 SQL Server**

    [https://azure.microsoft.com/services/virtual-machines/sql-server/](https://azure.microsoft.com/services/virtual-machines/sql-server/)

>[!div class="step-by-step"]
[이전](lift-and-shift-existing-apps-azure-iaas.md)
[다음](modernize-existing-apps-to-cloud-optimized/index.md)