---
title: "EShopOnContainers에서 DDD 마이크로 서비스에 적용 CQRS 및 CQS 방법"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | EShopOnContainers에서 DDD 마이크로 서비스에 적용 CQRS 및 CQS 방법"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: a2c4429a75ca47d4fbcde868b95e76bc65ea2bef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="applying-cqrs-and-cqs-approaches-in-a-ddd-microservice-in-eshoponcontainers"></a>EShopOnContainers에서 DDD 마이크로 서비스에 적용 CQRS 및 CQS 방법

EShopOnContainers 참조 응용 프로그램에서 주문 마이크로 서비스의 디자인 원칙 CQRS 기반으로 합니다. 그러나 방금 쿼리 명령에서 분리 되 고 동일한 데이터베이스를 사용 하 여 두 가지 동작 모두에 대 한 가장 간단한 접근 방식을 사용 합니다.

이러한 패턴 및 여기에서 중요 한 점은의 핵심은 쿼리 idempotent 않는다는: 해당 시스템의 상태는 시스템을 쿼리 하는 몇 번 변경 되지 않으므로 관계 없이 있습니다 사용 하 여 트랜잭션 논리 "쓰기" 보다 다른 "읽기" 데이터 모델 정렬 microservices 동일한 데이터베이스를 사용 하는 있지만 도메인 모델입니다. 따라서 간단한 CQRS 접근 방법입니다.

반면에 명령, 트랜잭션 및 데이터 업데이트를 트리거하는 시스템의 상태를 변경 합니다. 명령, 때는 주의 해야 복잡성 및 비즈니스 규칙 끊임없이 변화를 처리 합니다. 이것은 where DDD 기술을 더 잘 모델링 된 시스템에 적용 하려는 합니다.

이 가이드에서 제시 DDD 패턴 보편적으로 적용할 수 없습니다. 이러한 디자인에 대 한 제약 조건을 소개합니다. 이러한 제약 조건을 특히 명령 및 시스템 상태를 수정 하는 다른 코드에서 시간에 따라 더 높은 품질 같은 이점을 제공 합니다. 그러나 이러한 제약 조건을 읽고 데이터를 쿼리 하기 위해 더 적은 이점의 복잡성을 추가 합니다.

이러한 패턴 중 하나는 이후 섹션에서 더 검사 하는 집계 패턴입니다. 짧게 집계 패턴에 많은 도메인 개체를 처리 도메인에서 해당 관계의 결과로 단일 단위입니다. 수 하지 항상 이점을 얻을 수 있습니다; 쿼리에서이 패턴에서 이 쿼리 논리의 복잡성을 증가할 수 있습니다. 읽기 전용 쿼리에 대 한 단일 집계로 여러 개체를 처리 하는 방법의 장점은 발생 하지 않습니다. 만 복잡성을 가져옵니다.

그림 9-2와 같이,이 가이드는 (즉, 대로 명령을 사용 하 여 트리거) 프로그램 마이크로 서비스의 트랜잭션/업데이트 영역에만 DDD 패턴을 사용 하 여 제안 합니다. 보다 간단한 방법은 따르면 쿼리와 CQRS 방식을 따릅니다 명령에서 분리 해야 합니다.

"쿼리"쪽을 구현 하기 위한 EF 코어, AutoMapper 프로젝션, 저장된 프로시저, 뷰, 구체화 된 뷰 또는 마이크로 ORM와 같은 완전 한 ORM 프로그램에서 여러 방법 중에서 선택할 수 있습니다.

ORM 같은 및 eShopOnContainers (구체적으로 정렬 마이크로 서비스)는 마이크로 사용 하 여 직접 쿼리를 구현 하도록 선택 했으므로이 가이드에서 [Dapper](https://github.com/StackExchange/dapper-dot-net)합니다. 이렇게 하면 매우 적은 양의 오버 헤드는 밝은 프레임 워크 덕분에 최상의 성능을 위해서는 SQL 문을 기반으로 모든 쿼리를 구현할 수 있습니다.

이 방법을 사용 하면 모델에 엔터티는 SQL 데이터베이스에 유지 하는 방법에 영향을 주는 모든 업데이트에는 해야 Dapper 또는 쿼리를 별도 다른 모든 (비 EF) 방법을 사용 하는 SQL 쿼리를 별도 업데이트 note 합니다.

## <a name="cqrs-and-ddd-patterns-are-not-top-level-architectures"></a>CQRS 및 DDD 패턴은 최상위 아키텍처 아닙니다.

해당 CQRS, 대부분 DDD 패턴 (예: DDD 레이어 또는 집계를 사용 하 여 도메인 모델) 이해 해야 하는 아키텍처 스타일 아니라만 아키텍처 패턴. Microservices, SOA 및 이벤트 기반 아키텍처 (EDA)은 아키텍처 스타일의 예입니다. 개체 설명 시스템 많은 microservices 등의 여러 구성 요소입니다. CQRS 및 DDD 패턴을 단일 시스템 또는 구성 요소; 내부 항목에 대해 설명 이 경우, 한 마이크로 서비스 내 항목 합계입니다.

서로 다른 제한 된 컨텍스트 (BCs) 서로 다른 패턴을 사용 됩니다. 서로 다른 책임 있고 다양 한 솔루션으로 인해입니다. 것이 실패 하면 모든 범위는 같은 패턴을 강제 적용 하는 강조 합니다. CQRS 및 DDD 패턴을 모든 위치에서 사용 하지 마십시오. 많은 하위 시스템, BCs, 또는 microservices 더 간단 하 고 단순 CRUD 서비스를 사용 하 여 또는 다른 방식을 사용 하 여 보다 쉽게 구현할 수 있습니다.

하나의 응용 프로그램 아키텍처 없는: 시스템 또는 종단 간 응용 프로그램의 아키텍처 디자인 하는 (예: microservices 아키텍처). 그러나 각 경계가 지정 된 컨텍스트 또는 해당 응용 프로그램 내의 마이크로 서비스의 디자인 자체 장단점 및 아키텍처 패턴 수준에서 내부 디자인 관련 결정을 반영합니다. 동일한 아키텍처 패턴 CQRS 또는 DDD 같은 everywhere 적용 하지 마십시오.

####  <a name="additional-resources"></a>추가 리소스

-   **Martin Fowler. CQRS**
    [*https://martinfowler.com/bliki/CQRS.html*](https://martinfowler.com/bliki/CQRS.html)

-   **Greg Young 합니다. CQS vs입니다. CQRS**
    [*http://codebetter.com/gregyoung/2009/08/13/command-query-separation/*](http://codebetter.com/gregyoung/2009/08/13/command-query-separation/)

-   **Greg Young 합니다. CQRS 문서**
    [*https://cqrs.files.wordpress.com/2010/11/cqrs\_documents.pdf*](https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf)

-   **Greg Young 합니다. CQRS 작업 기반된 Ui 및 이벤트 소싱**
    [*http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/*](http://codebetter.com/gregyoung/2010/02/16/cqrs-task-based-uis-event-sourcing-agh/)

-   **Udi Dahan 합니다. CQRS 설명이 명확해졌습니다**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)

-   **CQRS**
    [*http://udidahan.com/2009/12/09/clarified-cqrs/*](http://udidahan.com/2009/12/09/clarified-cqrs/)

-   **이벤트 소싱 (ES)**
    [*http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/*](http://codebetter.com/gregyoung/2010/02/20/why-use-event-sourcing/)


>[!div class="step-by-step"]
[이전] [다음] (cqrs 마이크로 서비스 reads.md) (apply-simplified-microservice-cqrs-ddd-patterns.md)
