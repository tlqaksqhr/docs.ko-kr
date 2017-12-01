---
title: "클라우드에 대 한 준비 복원 력 있는 서비스를 빌드하십시오. 클라우드의 일시적 오류를 수용 합니다."
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 클라우드에 대 한 준비 복원 력 있는 서비스를 빌드하십시오. 클라우드의 일시적 오류를 수용 합니다."
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 9c21ae37ad2e4fc318eb4b206069db7662bfc5d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud"></a>클라우드에 대 한 준비 복원 력 있는 서비스를 빌드: 클라우드의 일시적 오류를 수용 합니다. 

복원력은 오류를 복구하고 계속 작업을 진행하는 기능입니다. 복구를 사용 하지만 오류를 방지 하 고, 오류가 발생할 수 있는 팩트를 수락 하 고, 다음 가동 중지 시간 또는 데이터 손실 방지 하는 방법에서 응답 하는 방법에 대 한 않습니다. 복원력의 목표는 오류 발생 후 응용 프로그램을 완전히 작동 중인 상태로 되돌리는 것입니다.

응용 프로그램은 여기에 최소한 그 복원 기능, 소프트웨어 기반 모델을이 아니라는 하드웨어 기반 모델을 구현 하는 경우 클라우드 준비가 됩니다. 클라우드 응용 프로그램 확실히 발생 하는 부분 장애를 도입 해야 합니다. 디자인 또는 부분적으로 예상된 부분 실패에 대 한 탄력성을 달성 하려면 응용 프로그램을 리팩터링 해야 합니다. 일시적인 네트워크 중단 및 노드 또는 Vm 클라우드의 충돌 같은 부분적인 오류에 대처 하기 위해 설계 되어야 합니다. Orchestrator 클러스터 내의 다른 노드로 이동 되 고 짝수 컨테이너 응용 프로그램에서 짧은 일시적인 오류가 발생할 수 있습니다.

## <a name="handling-partial-failure"></a>부분 오류 처리

클라우드 기반 응용 프로그램에서 부분 실패는 끊임없이 위험이 있습니다. 예를 들어, 단일 웹 사이트 인스턴스 또는 컨테이너에 실패할 것 또는 사용 불가능 하거나 짧은 시간 동안 응답 하지 않을 수 있습니다. 또는 단일 VM 또는 서버가 중단 될 수 있습니다.

클라이언트와 서비스는 별도 프로세스 이므로 서비스 클라이언트의 요청에 시기 적절 하 게 응답 하지 못할 수 있습니다. 서비스 오버 로드 될 수 있습니다 및 요청에 응답을 늦출 매우 또는 것 단순히 액세스할 수 없는 짧은 시간에 대 한 네트워크 문제 때문입니다.

Azure SQL 데이터베이스에서 데이터베이스를 액세스 하는 단일.NET 응용 프로그램을 예로 들 수 있습니다. Azure SQL 데이터베이스 또는 다른 제 3 자 서비스에 대 한 간단한 응답 하지 않으면 시간 (Azure SQL 데이터베이스는 다른 노드 또는 서버에 이동 될 수 하 고 몇 초 동안 응답 하지 않을 수)는 사용자가 모든 작업을 수행 하려고 하는 경우 응용 프로그램이 중단 될 수 있습니다 및 파일 w 동일한 순간에 예외가 있습니다.

HTTP 서비스를 사용 하는 앱에서 이와 유사한 시나리오가 발생할 수 있습니다. 네트워크 또는 서비스 자체 하지 못할 수도 있습니다는 클라우드에서 짧은, 일시적인 오류 발생 시.

그림 4-9에 표시 된 것 처럼는 복원 력 있는 응용 프로그램 리소스의 일시적 오류를 처리할 수 있도록 응용 프로그램에 제공 하려면 "지 수 백오프 함께 다시 시도"와 같은 기법을 구현 해야 합니다. 또한 응용 프로그램에서 "회로 차단기" 사용 해야 합니다. 회로 차단기는 실제로 장기적인 실패 하는 경우 리소스에 액세스 하려고 하 여 응용 프로그램을 중지 합니다. 회로 차단기를 사용 하 여 응용 프로그램 자체에 서비스 거부가 발생 시킨 방지할 수 있습니다.

![지 수 백오프 함께 다시 시도에서 처리 하는 일부 실패](./media/image9.png)

> **그림 4-9입니다.** 지 수 백오프 함께 다시 시도에서 처리 하는 일부 실패

이러한 기술은 HTTP 리소스와 데이터베이스 리소스에서 사용할 수 있습니다. 그림 4-9에서 응용 프로그램 기반으로 3 계층 아키텍처 및 데이터 계층 수준 (TCP) (HTTP) 서비스 수준에서 이러한 기술은 필요 합니다. (추가 서비스 또는 microservices 없음) 데이터베이스 이외에도 단일 응용 프로그램 계층만을 사용 하는 모놀리식 응용 프로그램, 데이터베이스 연결 수준에서 임시 오류 처리으로 충분 합니다. 이 시나리오에서는 일반적으로 특정 데이터베이스 연결의 구성은 필요 합니다.

를 사용 하는.NET의 버전에 따라 데이터베이스에 액세스 하는 복원 력 있는 통신을 구현할 때 매우 간단 하 게 될 수 있습니다 (예를 들어 [Entity Framework 6 이상](https://msdn.microsoft.com/library/dn456835(v=vs.113).aspx), 구성의 문제만 이기는 데이터베이스 연결)입니다. 또는 같은 추가 라이브러리를 사용 해야 할 수는 [일시적인 오류 처리 응용 프로그램 블록](https://msdn.microsoft.com/library/hh680934(v=pandp.50).aspx) (이전 버전의.NET)에 대해 또는 사용자 고유의 라이브러리를 구현할 수도 있습니다.

.NET에 대 한 권장 사항을 사용 하는 HTTP 재시도 횟수 및 회로 차단기를 구현 하는 경우는 [관](https://github.com/App-vNext/Polly) .NET 4.0,.NET 4.5 및.NET Core를 지 원하는.NET 표준 1.1을 대상으로 하는 라이브러리입니다.

클라우드에서 부분 장애를 처리 하기 위한 전략을 구현 하는 방법을 알아보려면 다음을 참조 합니다.

### <a name="additional-resources"></a>추가 리소스

-   **부분 실패를 처리 하는 복원 력 있는 통신을 구현 합니다.**

    [https://docs.microsoft.com/dotnet/standard/microservices-architecture/implement-resilient-applications/partial-failure-strategies](https://docs.microsoft.com/dotnet/standard/microservices-architecture/implement-resilient-applications/partial-failure-strategies)

-   **Entity Framework 연결 복원 력 및 재시도 논리 (버전 6 이상)**

    [https://msdn.microsoft.com/en-us/library/dn456835 (v=vs.113).aspx](https://msdn.microsoft.com/en-us/library/dn456835(v=vs.113).aspx)

-   **일시적인 오류 처리 응용 프로그램 블록**

<!-- -->

-   [https://msdn.microsoft.com/en-us/library/hh680934 (v=pandp.50).aspx](https://msdn.microsoft.com/en-us/library/hh680934(v=pandp.50).aspx)

-   **복원 력 있는 HTTP 통신에 대 한 관 라이브러리**

    https://github.com/App-vNext/Polly

>[!div class="step-by-step"]
[이전](when-to-deploy-windows-containers-to-azure-container-service-kubernetes.md)
[다음](modernize-your-apps-with-monitoring-and-telemetry.md)
