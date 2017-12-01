---
title: "마이크로 서비스의 단순화 된 CQRS 및 DDD 패턴 적용"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 마이크로 서비스의 단순화 된 CQRS 및 DDD 패턴 적용"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 99fd7ce32039742e23f8e01aa4c33cddd7a9f698
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="applying-simplified-cqrs-and-ddd-patterns-in-a-microservice"></a>마이크로 서비스의 단순화 된 CQRS 및 DDD 패턴 적용

CQRS는 데이터 읽기 및 쓰기에 대 한 모델을 구분 하는 아키텍처 패턴입니다. 관련된 용어 [명령 쿼리 분리 (CQS)](https://martinfowler.com/bliki/CommandQuerySeparation.html) 저서인 Bertrand 애 하 여 원래 정의 된 *개체 지향 소프트웨어 생성*합니다. 기본 개념은 급격 하 게 분리 된 두 가지 범주로 시스템의 작업을 나눌 수 있습니다.

-   쿼리합니다. 이러한 결과 반환 하 고 시스템의 상태를 변경 하지 않는 있으며 부작용이 없는 합니다.

-   명령입니다. 이러한 시스템의 상태를 변경 합니다.

CQS는 간단한 개념 — 동일한 개체 내에서 메서드는 쿼리 또는 명령입니다. 각 메서드는 상태를 반환 하거나 상태로 설정 되지만 둘 중 하나를 변경 합니다. 단일 리포지토리 패턴 개체도 CQS 따를 수 있습니다. CQS는 CQRS에 대 한 기본 원칙을 간주할 수 있습니다.

[명령 및 쿼리 책임 분리 (CQRS)](https://martinfowler.com/bliki/CQRS.html) Greg young 도입 하 고 강력한 Udi Dahan 및 다른 사용자에 의해 승격 되었습니다. 에 기반 하는 CQS 원칙을 보다 자세히 설명 되어 있지만 합니다. 명령 및 이벤트에 더한 필요에 따라 비동기 메시지에 따라 패턴을 생각할 수 있습니다. 대부분의 경우 CQRS (업데이트) 쓰기 보다 읽기가 (쿼리)에 대 한 서로 다른 물리적 데이터베이스 것과 같습니다 더 고급 시나리오와 관련이 있습니다. 또한 더 진화 CQRS 시스템을 구현할 수 [이벤트 소싱 (ES)](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/) 업데이트 데이터베이스 이므로에 저장할 수 있습니다 이벤트의 현재 상태 데이터를 저장 하는 대신 도메인 모델입니다. 그러나 이것이;이 가이드에서 사용 하는 방법 방금 명령에서 쿼리를 분리 하면 구성 된 단순한 CQRS 방법을 사용 했습니다.

분리 모양의 CQRS는 또 다른 계층에서 명령 및 쿼리 작업에 한 계층을 그룹화 하 여 수행 됩니다. 각 계층에 데이터 모델이 (참고 말할 모델에서는 다른 데이터베이스를 사용 하지 않을 수도 있음)를 패턴 및 기술 자체 조합을 사용 하 여 만들어집니다. 무엇 보다도 두 계층 내에서 동일한 계층 또는 마이크로 서비스를 (마이크로 서비스 순서) 예제와 같이이 가이드에 사용 될 수 있습니다. 또는 액세스에 최적화 된 고 서로 영향을 주지 않고 개별적으로 확장할 수 있도록 다른 microservices 또는 프로세스에 구현할 수 있습니다.

CQRS를 다른 컨텍스트에서 하나도 읽기/쓰기 작업에 대 한 두 개체를 것을 의미 합니다. 더 많은 고급 CQRS 홍보 자료에 대해 알아볼 수 있습니다는 정규화 되지 않은 읽기 데이터베이스에 있어야 하는 이유가 있습니다. 하지만 사용 하지는 여기에서 방법을 ֲ가 좀더 유연한 쿼리를 집계 같은 DDD 패턴에서 제약 조건으로 쿼리를 제한 하는 대신에 위치 합니다.

서비스의 이러한 종류의 예로 eShopOnContainers 참조 응용 프로그램에서 주문 마이크로 서비스. 이 서비스는 간소화 된 CQRS 접근 방식에 따라 한 마이크로 서비스를 구현 합니다. 사용 하 여 단일 데이터 원본 또는 데이터베이스에 있지만 두 논리 모델을 함께 DDD 패턴 트랜잭션 도메인에 대 한 그림 9-2에 나와 있는 것 처럼 합니다.

![](./media/image2.png)

**그림 9-2**합니다. 간소화 된 CQRS 및 DDD 기반 마이크로 서비스

응용 프로그램 계층 웹 API 자체는 될 수 있습니다. 중요 한 디자인 측면은 명령, 도메인 모델 및 트랜잭션 CQRS 패턴에서 쿼리 및 Viewmodel (특히 클라이언트 응용 프로그램에 대해 생성 된 데이터 모델)은 마이크로 서비스 분할 된입니다. 이 방법은 별개의 제한 사항 및 제약 조건 뒤의 섹션에 설명 된 대로 트랜잭션 및 업데이트에만 의미가 DDD 패턴에서 들어오는 쿼리를 유지 합니다.


>[!div class="step-by-step"]
[이전] [다음] (eshoponcontainers-cqrs-ddd-microservice.md) (index.md)
