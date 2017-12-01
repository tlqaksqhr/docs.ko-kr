---
title: "API 게이트웨이 패턴 및 직접 클라이언트 마이크로 서비스 통신"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | API 게이트웨이 패턴 및 직접 클라이언트 마이크로 서비스 통신"
keywords: "Docker, Microservices, ASP.NET, 컨테이너, API 게이트웨이"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/18/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: c8227ec47888c7cf361f34c4c85a09c0666f886e
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2017
---
# <a name="direct-client-to-microservice-communication-versus-the-api-gateway-pattern"></a>API 게이트웨이 패턴 및 직접 클라이언트 마이크로 서비스 통신

Microservices 아키텍처에서는 각 마이크로 서비스 fine‑grained 끝점 (일반적으로)의 집합을 노출합니다. 이 섹션에 설명 된 대로이 팩트가 client‑to‑microservice 통신 하는 영향을 줄 수 있습니다.

## <a name="direct-client-to-microservice-communication"></a>직접 클라이언트 마이크로 서비스 통신

가능한 방법은 직접 클라이언트 마이크로 서비스 통신 아키텍처를 사용 하는 것입니다. 이 방법에서는 클라이언트 응용 프로그램 요청을 만들 수는 microservices 중 일부에 직접 그림 4-12에 나와 있는 것 처럼 합니다.

![](./media/image12.png)

**그림 4-12**합니다. 직접 클라이언트 마이크로 서비스 통신 아키텍처를 사용 하 여

이 방식을 사용 합니다. 각 마이크로 서비스에는 공용 끝점을 각 마이크로 서비스에 대 한 다른 TCP 포트를 경우도 있습니다. 특정 서비스에 대 한 URL의 예는 Azure에서 다음 URL을 수 있습니다.

<http://eshoponcontainers.westus.cloudapp.azure.com:88 />

URL은 클러스터에서 사용한 부하 분산 장치에 매핑되는 클러스터에 따라 프로덕션 환경에는 다시 요청을 분산는 microservices 합니다. 프로덕션 환경에서와 같은 응용 프로그램 배달 컨트롤러 (ADC)를 사용할 수 있습니다 [Azure 응용 프로그램 게이트웨이](https://docs.microsoft.com/azure/application-gateway/application-gateway-introduction) 프로그램 microservices와 인터넷 사이입니다. 이 뿐만 아니라 부하 분산을 수행 하지만 SSL 종료를 제공 하 여 서비스를 보호 하는 투명 한 계층으로 작동 합니다. CPU를 많이 사용 SSL 종료 및 Azure 응용 프로그램 게이트웨이를 다른 라우팅 의무를 오프 로드 하 여 호스트 부하 향상 됩니다. 어떤 경우 든, 부하 분산 장치 및 ADC는 논리적 응용 프로그램 아키텍처 관점에서 투명 하 합니다.

직접 클라이언트 마이크로 서비스 통신 아키텍처 충분 작은 마이크로 서비스 기반 응용 프로그램에 대 한 클라이언트 응용 프로그램은 ASP.NET MVC 응용 프로그램 같은 서버 쪽 웹 응용 프로그램 하는 경우에 특히 수 있습니다. 그러나 대규모 또는 복잡 한 마이크로 서비스 기반 응용 프로그램 (예: 마이크로 서비스 형식의 수십을 처리 하는 경우), 빌드 및 클라이언트 앱이 원격 모바일 앱 또는 웹 응용 프로그램 SPA 하는 경우에 특히 해당 접근 몇 가지 문제를 향하도록 합니다.

Microservices에 따라 대형 응용 프로그램을 개발할 때 다음과 같은 질문을 고려 합니다.

-   *어떻게 클라이언트 앱 백 엔드에 대 한 요청 수를 최소화 하 고 줄일 수에 여러 microservices 통신이 자주?*

인터넷을 통해 왕복 횟수를 증가 단일 UI 화면을 빌드할 수 있는 여러 microservices와 상호 작용 합니다. 대기 시간 및 UI 쪽 복잡성 증가합니다. 이상적으로 응답 효율적으로 집계 서버 쪽에서-이렇게 하면 줄어듭니다 대기 시간, 여러 데이터 동시에 다시 시도 하 고 일부 UI가 준비 되는 즉시 데이터를 표시할 수 있습니다.

-   *권한 부여, 데이터 변환 및 동적 요청 디스패치 같은 일반적인 문제를 처리 하려면 어떻게 해야 합니까?*

보안 및 모든 마이크로 서비스에서 권한 부여를 많은 개발 작업을 요구할 수와 같은 보안 및 일반적인 문제를 구현 합니다. 가능한 방법은 외부의 한 직접적인 액세스를 제한 하기 위해와 API 게이트웨이 같은 중앙된 위치에 이러한 일반적인 문제를 구현 하는 Docker 호스트 또는 내부 클러스터 내에서 서비스 사용 하도록 하는 것입니다.

-   *클라이언트 앱의 인터넷 환경 비 프로토콜을 사용 하는 서비스와 통신할 수는 방법*

(예: AMQP 또는 이진 프로토콜) 서버 쪽에서 사용 되는 프로토콜은 일반적으로 클라이언트 앱에서 지원 되지 않습니다. 따라서 요청 HTTP/HTTPS 같은 프로토콜을 통해 수행할 고 나중에 다른 프로토콜 변환 해야 합니다. A *중간자 개입* 방식은이 경우에는 데 도움이 됩니다.

-   *모바일 앱에 대 한 특히 외관 모양을 수는 방법*

여러 클라이언트 응용 프로그램의 요구에 대해 여러 microservices의 API는 잘 디자인할 수 있습니다. 예를 들어, 모바일 응용 프로그램의 요구 사항을 웹 응용 프로그램의 요구 사항 보다 다를 수 있습니다. 모바일 응용 프로그램 데이터 응답 더 효율적일 수 있도록 더욱 최적화 하기 위해 해야 할 수 있습니다. 여러 microservices에서 데이터를 집계 및 데이터의 단일 집합을 반환 하 고 경우에 따라 모바일 응용 프로그램에서 필요 하지 않은 응답 메시지의 모든 데이터를 제거 하 여 이렇게 할 수도 있습니다. 및 물론, 해당 데이터를 압축 될 수 있습니다. 다시, 외관 또는 모바일 앱에서의 microservices 사이의 API이이 시나리오에 대 한 편리할 수 있습니다.

## <a name="using-an-api-gateway"></a>API 게이트웨이 사용 하 여

디자인 하 고 크거나 복잡 한 마이크로 서비스 기반 응용 프로그램을 여러 클라이언트 앱을 빌드할 때 고려 하는 좋은 방법은 수는 [API 게이트웨이](http://microservices.io/patterns/apigateway.html)합니다. 이것이 microservices 그룹 특정 단일 액세스 지점을 제공 하는 서비스입니다. 비슷합니다는 [외관 패턴](https://en.wikipedia.org/wiki/Facade_pattern) object‑oriented 디자인에서 하지만 경우의 일부인 분산된 시스템입니다. API 게이트웨이 패턴도 라고도: "백 엔드 프런트 엔드에 대 한" [(BFF)](http://samnewman.io/patterns/architectural/bff/) 클라이언트 응용 프로그램의 요구 사항에 대해 생각 하는 동안 작성 하기 때문에 있습니다.

그림 4-13 마이크로 서비스 기반 아키텍처에는 사용자 지정 API 게이트웨이 맞출 수 있는 방법을 보여 줍니다.
해당 다이어그램에 강조 표시 해야, 다중 마주보는 단일 사용자 지정 API 게이트웨이 서비스가 사용 될 수 있습니다 및 다른 클라이언트 응용 프로그램입니다. 클라이언트 응용 프로그램에서 여러 다른 요구 사항에 따라 API 게이트웨이 서비스에서 증가 한 진화 하므로 팩트가 중요 한 위험을 수 있습니다. 결국 이러한 다른 요구 사항으로 인해 너무 커지면 수 있습니다 및 효과적으로 모놀리식 응용 프로그램 또는 모놀리식 서비스 상당히 비슷한 수 없습니다. 즉, 예를 들어 여러 서비스 또는 여러 개의 더 작은 API 게이트웨이 폼 팩터 유형 마다 하나씩의 API 게이트웨이 분할 하는 것은 권장 매우 유사 합니다.

![](./media/image13.png)

**그림 4-13**합니다. 사용자 지정 웹 API 서비스도 구현 된 API 게이트웨이 사용 하 여

이 예제에서는 컨테이너 실행 되는 사용자 지정 웹 API 서비스도 API 게이트웨이 구현 합니다.

앞에서 설명한 것 처럼 각 클라이언트 응용 프로그램의 요구 사항에 대 한 다른 외관을 가질 수 있습니다 여러 API 게이트웨이 구현 해야 합니다. 각 API 게이트웨이 다른 제공할 수 증명도에 따라 클라이언트 폼 팩터 특정 어댑터 코드는 아래에 여러 내부 microservices 호출을 구현 하 여 각 클라이언트 응용 프로그램에 맞게 조정 된 API입니다.

사용자 지정 API 게이트웨이 일반적으로 데이터 수집기에 것에 주의 해야 합니다. 일반적으로 단일 API 게이트웨이 응용 프로그램의 모든 내부 microservices을 집계 하는 것이 좋습니다 되지 않습니다. 그렇지 않으면 모놀리식 집계 나 orchestrator 역할 하며 모든 microservices 여 마이크로 서비스 자치를 위반 합니다. 따라서 API 게이트웨이 분리할 것인지 비즈니스 경계와 작동 하지을 기반으로 전체 응용 프로그램에 대 한 집계 합니다.

경우에 따라 세부적인 API 게이트웨이 수 자체적으로 마이크로 서비스 일 수도 있고도 도메인 또는 회사 이름 및 관련된 데이터. 비즈니스 또는 도메인에 따라 API 게이트웨이 경계 있으면 더 나은 설계를 얻을 수 있습니다 하는 데 도움이 됩니다.

세분화 된 API 게이트웨이의 개념은 비슷하지만 UI 컴퍼지션 서비스 때문에 API 게이트웨이 계층에서 세분성 microservices에 따라 더 많은 고급 복합 UI 응용 프로그램에 특히 유용할 수 있습니다. 이러한 작업을 나중에 논의 [microservices에 따라 복합 UI 만드는](#creating-composite-ui-based-on-microservices-including-visual-ui-shape-and-layout-generated-by-multiple-microservices)합니다.

따라서 대부분의 중간 규모 및 대규모 크기 방식을 응용 프로그램에 대 한 사용자가 작성 한 API 게이트웨이 사용 하는 일반적으로 좋은 방법은 단일 모놀리식 aggregator 또는 고유한 중앙 사용자 지정 API 게이트웨이 인정 하지는 않습니다.

같은 제품을 사용 하는 또 다른 방법은 [Azure API 관리](https://azure.microsoft.com/services/api-management/) 그림 4-14에서와 같이 합니다. 이 방법은 API 게이트웨이 요구 사항 해결 뿐 아니라 insights Api에서 수집 하는 같은 기능을 제공 합니다. API 관리 솔루션을 사용 하는 경우 API 게이트웨이 해당 전체 API 관리 솔루션 내에서 구성 요소입니다.

![](./media/image14.png)

**그림 4-14**합니다. Azure API 관리를 사용 하 여 API 게이트웨이에 대 한

이 경우 Azure API 관리 API 게이트웨이 들 수 있습니다 팩트 같은 제품을 사용 하 여 이므로 위험한 때문에 없는 경우 이러한 종류의 API 게이트웨이 "도출할", 즉는 모놀리식는 방향으로 발전 사용자 지정 C# 코드를 구현 하지 않는 구성 요소입니다. 

이 유형의 제품 더 통신 수신 위치 있습니다 수 또한 내부 microservices에서 Api에는 필터링 및이 단일 계층의 게시 된 Api에 권한을 적용에 대 한 역방향 프록시 역할을 합니다.

API 관리 시스템 도움말에서 사용할 수 있는 insights 얻게 Api 사용 되는 방식을 이해 하 고 수행 하는 방법입니다. 실시간 분석 보고서 근처 볼 수 있습니다 하 고 비즈니스에 영향을 줄 수 있는 추세를 식별 하 여이 수행 합니다. 또한 추가 온라인 및 오프 라인 분석을 위해 요청 및 응답 작업에 대 한 로그를 사용할 수 있습니다.

Azure API 관리 Api는 키, 토큰 및 IP 필터링을 사용 하 여 보호할 수 있습니다. 이러한 기능을 사용 하 여 유연 하 고 세분화 된 할당량 및 속도 제한 하 고, 모양과 정책을 사용 하 여 Api의 동작을 수정 하 고 응답 캐싱을 사용 하 여 성능을 향상 시킬 수 있도록 합니다.

이 가이드 및 참조 샘플 응용 프로그램 (eShopOnContainers)에서 Azure API 관리와 같은 PaaS 제품을 사용 하지 않고 일반 컨테이너에 집중할 수 있도록 아키텍처를 간단 하 고, 사용자 지정한 컨테이너 화 된 아키텍처를 제한 하는 했습니다. 하지만 큰 마이크로 서비스 기반 응용 프로그램의 Microsoft Azure에 배포 되는 경우 사용자 좋습니다 검토 하 고 API Gateway에 대 한 기반으로 Azure API 관리를 도입 합니다.

## <a name="drawbacks-of-the-api-gateway-pattern"></a>API 게이트웨이 패턴의 단점

-   가장 중요 한 단점은 API 게이트웨이 구현할 때 사용자는 연결 해당 계층 내부 microservices입니다. 다음과 같이 결합 응용 프로그램에 심각한 문제가 발생할 수 있습니다. Clemens Vaster, Azure Service Bus 팀에서 설계자는 자신의이 잠재적 문제 "새 ESB"로 가리킵니다 "[메시징 및 Microservices](https://www.youtube.com/watch?v=rXi5CLjIQ9k)" GOTO 2016에 세션입니다.

-   Microservices API 게이트웨이 사용 하는 추가 가능한 단일 실패 지점을 만듭니다.

-   API 게이트웨이 증가 한 응답 시간 추가 네트워크 호출으로 인해 발생할 수 있습니다. 그러나이 추가로 호출은 일반적으로 너무 많이 내부 microservices를 직접 호출 하는 인터페이스는 클라이언트가 보다 적은 영향을 미칩니다.

-   하지 확장할 제대로, API 게이트웨이 병목 상태가 될 수 있습니다.

-   사용자 지정 논리 및 데이터 집계를 포함 하는 경우 API 게이트웨이가 필요 추가 개발 비용 및 향후 유지 관리 합니다. 개발자는 각 마이크로 서비스 끝점을 노출 하기 위해 API 게이트웨이 업데이트 해야 합니다. 또한 내부 microservices에 구현 변경 API 게이트웨이 수준에서 코드 변경 내용이 발생할 수 있습니다. 그러나 API 게이트웨이가 바로 적용 하는 보안, 로깅 및 버전 관리 하는 경우 (as Azure API 관리를 사용 하는 경우)이 추가 개발 비용 적용 되지 않을 수 있습니다.

-   API 게이트웨이 단일 팀에서 개발 하는 경우 개발 병목 상태가 있을 수 있습니다. 이것이 이유 더 나은 방법은 하는 여러 가지 정교한 API 게이트웨이가 다양 한 클라이언트 요구 사항에 응답 하는 또 다른 이유입니다. 내부 microservices에서 작업 하는 다른 팀에서 소유 하는 레이어 또는 여러 영역에 내부적으로 API 게이트웨이 구분할 수도 없습니다.

## <a name="additional-resources"></a>추가 리소스

-   **Charles Richardson 합니다. 패턴: API 게이트웨이 / 백 엔드에 대 한 프런트 엔드**
    [*http://microservices.io/patterns/apigateway.html*](http://microservices.io/patterns/apigateway.html)

-   **Azure API 관리**
    [*https://azure.microsoft.com/services/api-management/*](https://azure.microsoft.com/services/api-management/)

-   **Udi Dahan 합니다. 서비스 지향 컴퍼지션**\
    [*http://udidahan.com/2014/07/30/service-oriented-composition-with-video/*](http://udidahan.com/2014/07/30/service-oriented-composition-with-video/)

-   **Clemens Vasters 합니다. 메시징 및 GOTO 2016에서 Microservices** (비디오) [ *https://www.youtube.com/watch?v=rXi5CLjIQ9k*](https://www.youtube.com/watch?v=rXi5CLjIQ9k)


>[!div class="step-by-step"]
[이전] (식별-마이크로 서비스-도메인-모델-boundaries.md) [다음] (통신-에-마이크로 서비스-architecture.md)
