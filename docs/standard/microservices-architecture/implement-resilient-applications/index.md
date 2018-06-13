---
title: 복원력 있는 응용 프로그램 구현
description: 컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 복원력 있는 응용 프로그램 구현
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 211814eff0f2aaf0cf71a19cfcaaeb44924fb6f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573745"
---
# <a name="implementing-resilient-applications"></a>복원력 있는 응용 프로그램 구현

*마이크로 서비스와 클라우드 기반 응용 프로그램에서는 결국 발생하게 되는 부분 오류를 수용해야 합니다. 부분 오류에 탄력적으로 대처할 수 있도록 응용 프로그램을 디자인해야 합니다.*

복원력은 오류를 복구하고 계속 작업을 진행하는 기능입니다. 이는 오류를 방지하는 기능이 아닌 오류가 발생할 수 있다는 사실을 받아들이고 가동 중지 시간 또는 데이터 손실을 방지할 수 있도록 해당 오류에 응답하는 기능입니다. 복원력의 목표는 오류 발생 후 응용 프로그램을 완전히 작동 중인 상태로 되돌리는 것입니다.

마이크로 서비스 기반 응용 프로그램을 디자인하고 배포하기는 쉽지 않습니다. 그러나 일부 오류가 명확히 발생하는 환경에서 응용 프로그램을 계속 실행하는 작업도 필요합니다. 따라서 응용 프로그램에 복원력이 있어야 합니다. 응용 프로그램은 클라우드에서의 네트워크 중단 또는 노드 또는 VM 충돌과 같은 부분 오류에 대처할 수 있도록 디자인되어야 합니다. 클러스터 내에서 다른 노드로 이동한 마이크로 서비스(컨테이너)도 응용 프로그램에서 일시적 단기 오류를 유발할 수 있습니다.

응용 프로그램의 여러 개별 구성 요소도 상태 모니터링 기능과 통합해야 합니다. 이 장의 지침을 따라 가동 중지 시간 또는 복잡한 클라우드 기반 배포의 일반적인 문제가 발생하는 환경에서도 원활하게 작동하는 응용 프로그램을 만들 수 있습니다.


>[!div class="step-by-step"]
[이전] (../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md) [다음] (handle-partial-failure.md)
