---
title: "일부 오류를 처리 하기 위한 전략"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 일부 오류를 처리 하기 위한 전략"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: ff3bed530b13a9b1822c7cccf5a4d47df6fc6239
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="strategies-for-handling-partial-failure"></a>일부 오류를 처리 하기 위한 전략

부분적인 오류를 처리 하기 위한 전략은 다음과 같습니다.

**비동기 통신 (예를 들어 메시지 기반 통신)를 사용 하 여 내부 microservices 걸쳐**합니다. 항상을 잘못 된 해당 디자인에는 잘못 되었습니다. 중단의 주요 원인 결국 때문에 내부 microservices에서 긴 체인 HTTP에 대 한 동기 호출을 만들지 않도록는 것이 좋습니다. 반대로, 클라이언트 응용 프로그램과 첫 번째 수준의 microservices 또는 세분화 된 API 게이트웨이 간의 통신의 프런트 엔드를 제외 하 고 것이 좋습니다 비동기 (메시지 기반) 통신만 초기 요청을 지 나 한 번만 사용 하도록 / 내부 microservices 걸쳐 응답 주기가 결과적 일관성 및 이벤트 기반 아키텍처 ripple 영향을 최소화 하는 데 도움이 됩니다. 이러한 방법을 사용 더 높은 수준의 자율성 마이크로 서비스를 강제 적용 되 고 따라서 여기서 설명 하는 문제를 방지 합니다.

**재시도 지 수 백오프를 사용 하 여**합니다. 짧은 하지 않으려면이 방법을 사용 하면 및 호출을 수행 하 여 일시적인 오류가 경우 서비스에서 짧은 시간에만 사용할 수 없습니다. 몇 번의 다시 시도 시간입니다. 마이크로 서비스/컨테이너를 클러스터의 다른 노드로 이동할 때 또는 일시적인 네트워크 문제로 인해 발생할 수 있습니다. 그러나 이러한 재시도 없는 경우 제대로 회로 차단기와, 그 수 aggravate ripple 효과 바꾸지 궁극적으로 [서비스 거부 (DoS)](https://en.wikipedia.org/wiki/Denial-of-service_attack)합니다.

**네트워크 제한 시간 까지의 작업**합니다. 일반적으로 클라이언트를 무기한으로 차단 하지 않도록 하 고 응답을 받기 위해 대기 하는 경우 항상 제한 시간을 사용 하도록 설계 되어야 합니다. 시간 제한을 사용 하는 리소스는 되지 하느라 정체 무기한 확인 합니다.

**회로 차단기 패턴을 사용 하 여**합니다. 이 방법에서는 클라이언트 프로세스 실패 한 요청 수를 추적합니다. 오류 비율 즉시 시도가 실패 하는 구성 된 제한 "회로 차단 기가" trips을 초과 하면 합니다. (많은 수의 요청 실패 하는 경우 제시 요청을 보낼 무의미 한 인지 하 고 서비스를 사용할 수 없습니다.) 제한 시간 후 클라이언트 해야 다시 시도 하 고, 새 요청은 성공 하는 경우 회로 차단기를 닫습니다.

**대체 제공**합니다. 이 방법에서는 클라이언트 프로세스에서 캐시 된 데이터 또는 기본값을 반환 하는 등의 요청이 실패할 경우 대체 논리를 수행 합니다. 쿼리에 대 한 적합 한 접근 방식을 이며 업데이트 또는 명령에 대 한 더 복잡 합니다.

**큐 대기 요청 수가 제한**합니다. 클라이언트는 클라이언트 마이크로 서비스를 특정 서비스에 보낼 수 있는 처리 중인 요청 수에 대 한 상한 값을 입력할 수 해야 합니다. 제한에 도달 하면 추가 요청을 만드는 무의미 한 것 이며 재전송 시도 즉시 중단 해야 합니다. 관 구현 측면에서 [Bulkhead 격리](https://github.com/App-vNext/Polly/wiki/Bulkhead) 정책이 요구이 사항을 충족 데 사용할 수 있습니다. 이 방법은와 병렬화 스로틀 [SemaphoreSlim](https://docs.microsoft.com/dotnet/api/system.threading.semaphoreslim?view=netcore-1.1) 구현으로 합니다. 또한는 bulkhead 외부 "queue" 수 있습니다. (예를 들어 때문에 용량 완전 하다 고 판단 되) 실행 하기 전에 초과 부하를 늘리는 사전 있습니다. 이렇게 하면 특정 오류 시나리오에 대 한 응답 회로 차단기는 오류에 대 한 대기 하므로 회로 차단기 될 것 보다 더 빠르게 있습니다. 관 BulkheadPolicy 개체 노출 사용률이 bulkhead 및 큐는 고 오버플로가 제공 이벤트 하므로 수 있습니다 사용할 수도 자동화 된 수평 확장이 진행 하는 데 합니다.

## <a name="additional-resources"></a>추가 리소스

-   **복원 력 패턴**
    [*https://docs.microsoft.com/azure/architecture/patterns/category/resiliency*](https://docs.microsoft.com/azure/architecture/patterns/category/resiliency)

-   **추가 복원 력 및 성능 최적화**
    [*https://msdn.microsoft.com/en-us/library/jj591574.aspx*](https://msdn.microsoft.com/en-us/library/jj591574.aspx)

-   **Bulkhead 합니다.** GitHub 리포지토리 합니다. 관 정책 사용 하 여 구현 합니다. \ \
    [*https://github.com/App-vNext/Polly/wiki/Bulkhead*](https://github.com/App-vNext/Polly/wiki/Bulkhead)

-   **Azure에 대 한 복원 력 있는 응용 프로그램 디자인**
    [*https://docs.microsoft.com/azure/architecture/resiliency/*](https://docs.microsoft.com/azure/architecture/resiliency/)

-   **일시적인 오류 처리**
    <https://docs.microsoft.com/azure/architecture/best-practices/transient-faults>


>[!div class="step-by-step"]
[이전] (핸들-부분-failure.md) [다음] (구현-다시 시도-지 수-backoff.md)
