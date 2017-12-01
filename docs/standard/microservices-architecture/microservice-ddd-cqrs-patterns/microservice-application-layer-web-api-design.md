---
title: "마이크로 서비스 응용 프로그램 계층 및 Web API 디자인"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 마이크로 서비스 응용 프로그램 계층 및 Web API 디자인"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7509b470a30005dd48fa88eefa91f7ed241e4e09
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="designing-the-microservice-application-layer-and-web-api"></a>마이크로 서비스 응용 프로그램 계층 및 Web API 디자인

## <a name="using-solid-principles-and-dependency-injection"></a>단색 원칙 및 종속성 주입을 사용 하 여

단색 원칙은 현대적이 고 필수적인 같은 응용 프로그램 DDD 패턴과 마이크로 서비스를 개발에 사용할 중요 기술입니다. 단색는 머리글자어로 해당 5 개 그룹 원칙은:

-   단일 책임 원칙

-   열기/닫기 원칙

-   Liskov 대체 원칙

-   반전 분리 원칙

-   종속성 반전 원칙

솔리드 응용 프로그램 또는 마이크로 서비스 내부 계층을 디자인 하는 방법에 대 한 및 이들 간의 종속성을 분리 하는 방법에 대 한 자세한입니다. 도메인에 있지만 응용 프로그램의 기술적 설계에는 관련 되지 않았습니다. 최종 원칙 종속성 Inversion (DI) 원칙을 사용 하면 분리 된 DDD 계층을 더 잘 구현 수 있는, 계층의 나머지 부분에서 인프라 계층을 분리 하기 위한 수 있습니다.

DI는 종속성 반전 원칙을 구현 하는 한 가지 방법은 됩니다. 이 개체 및 개체 종속성 간의 느슨한 결합을 실현을 위한 기술입니다. 대신 직접 공동 작업자를 인스턴스화하거나 정적 참조를 사용 하 여, 해당 작업을 수행 하는 데 필요한 클래스는 개체는에 제공 (또는 "에 삽입")는 클래스입니다. 대부분의 경우 클래스 명시적 종속 관계 원칙에 따라 수 있으므로 해당 생성자를 통해 해당 종속성을 선언 합니다. DI은 일반적으로 Inversion of Control IoC ()는 특정 컨테이너 기반으로 합니다. ASP.NET Core 간단한 기본 제공 IoC 컨테이너를 제공 하지만 Autofac 또는 Ninject 같은 즐겨 찾는 IoC 컨테이너를 사용할 수도 있습니다.

단색 원칙을 따르면를 작은 하 고, 잘 구성 된 테스트를 쉽게 거친 자연스럽 게 클래스는 경향이 있습니다. 하지만 너무 많은 종속성은 클래스에 삽입 되는 경우 어떻게 알 수 있습니다. 생성자를 통해 DI를 사용 하는 경우 생성자에 대 한 매개 변수 개수 확인만 하 여 점을 감지할 쉽게 됩니다. 너무 많은 종속성이 있는 경우이 일반적으로 기호 (한 [냄새 코드](http://deviq.com/code-smells/)) 클래스를 너무 많이 수행 하 고 아마도 단일 책임 원칙을 위반 합니다.

걸리는 자세히 단색을 포함 하는 다른 지침입니다. 따라서이 가이드에 다음이 항목 중 최소 지식이 포함 해야 합니다.

#### <a name="additional-resources"></a>추가 리소스

-   **단색: 기본 OOP 원칙**
    [*http://deviq.com/solid/*](http://deviq.com/solid/%20)

-   **컨트롤 컨테이너 및 종속성 주입 패턴의 반전**
    [*https://martinfowler.com/articles/injection.html*](https://martinfowler.com/articles/injection.html)

-   **Steve Smith 합니다. 새 작업은**
    [*http://ardalis.com/new-is-glue*](http://ardalis.com/new-is-glue)


>[!div class="step-by-step"]
[이전] (nosql-데이터베이스-지 속성-infrastructure.md) [다음] (microservice-application-layer-implementation-web-api.md)
