---
title: "시각적 UI 셰이프 및 여러 microservices에 의해 생성 된 레이아웃을 포함 하 여 microservices에 따라 복합 UI 만들기"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 시각적 UI 셰이프 및 여러 microservices에 의해 생성 된 레이아웃을 포함 하 여 microservices에 따라 복합 UI 만들기"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 4b32fed5eb0de02b01665efa4368eb83e3fda08d
ms.sourcegitcommit: e99dfadbca1992c187179b6a3b42bef44534ebb6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2017
---
# <a name="creating-composite-ui-based-on-microservices-including-visual-ui-shape-and-layout-generated-by-multiple-microservices"></a>시각적 UI 셰이프 및 여러 microservices에 의해 생성 된 레이아웃을 포함 하 여 microservices에 따라 복합 UI 만들기

데이터 및 논리를 처리 하는 서버 쪽 Microservices 아키텍처 자주 시작 합니다. 그러나 UI microservices도에 따라 응용 프로그램을 디자인 하는 고급 방법이입니다. 즉, 서버와는 microservices 소비는 모놀리식 클라이언트 앱에서 microservices 필요 없이 microservices에서 생성 되는 복합 UI 필요 합니다. 이 방법에서는 빌드할 microservices 논리 및 시각적 표현 모두 완료 될 수 있습니다.

그림 4-20 방금 microservices 모놀리식 클라이언트 응용 프로그램에서을 사용 하는 간단한 방법을 보여 줍니다. 물론, HTML 및 JavaScript를 생성 하는 사이는 ASP.NET MVC 서비스가 있을 수 있습니다. 그림에는 단일 (모놀리식) 클라이언트 UI 사용 (HTML 및 JavaScript) UI 셰이프 아니라 논리와 데이터에만 집중는 microservices 있는지를 강조 하는 단순화 된 버전입니다.

![](./media/image20.png)

**그림 4-20**합니다. 백 엔드 microservices 소비 모놀리식 UI 응용 프로그램

반면, 복합 UI는 정확 하 게 생성 및 microservices 자체에 의해 구성 되었습니다. 일부는 microservices UI의 특정 영역의 시각적 모양을 구동합니다. 주요 차이가 클라이언트 UI 구성 요소 (예: TS 클래스) 템플릿에 기반 있으며 해당 템플릿에 대 한 데이터 셰이핑 UI ViewModel는 각 마이크로 서비스에서 제공 합니다.

클라이언트 응용 프로그램 시작 시 각 클라이언트 UI 구성 요소 (예: TypeScript 클래스)에 자동으로 등록는 인프라 마이크로 서비스를 지정된 된 시나리오에 대 한 Viewmodel를 제공할 수 있습니다. 마이크로 서비스의 모양을 변경 되 면 UI도 변경 됩니다.

그림 4-21이 복합 UI 접근 방법의 버전을 보여 줍니다. 이 단순 하 여, 다양 한 기술을 기반으로 하는 세분화 된 파트를 집계 하는 다른 microservices 해야할-을 개발 하는 일반적인 웹 접근 방식 (ASP.NET MVC) 또는 SPA (단일 페이지 응용 프로그램)에 따라 다릅니다.

![](./media/image21.png)

**그림 4-21**합니다. 백 엔드 microservices 모양이 지정 복합 UI 응용 프로그램의 예

각 해당 UI 컴퍼지션 microservices 작은 API 게이트웨이 유사 합니다. 그러나이 경우 각은 작은 UI 영역에 대 한 합니다.

따라서 덜 UI 기술, 사용 중인 또는 microservices에 의해 발생 하는 복합 UI 접근 방식을 좀 더 어렵습니다 수 있습니다. 예를 들어, 동일한 기술을 SPA를 구축 하기 위한 또는 네이티브 모바일 앱을 사용 하는 기존 웹 응용 프로그램을 구축 하기 위한 사용 하지 것입니다 (마찬가지로이 방법은 좀 더 어렵습니다 될 수 있는 Xamarin 앱을 개발 하는 경우).

[eShopOnContainers](http://aka.ms/MicroservicesArchitecture) 예제 응용 프로그램 여러 가지 이유로 모놀리식 UI 접근 방식을 사용 합니다. 첫째, 것은 microservices 및 컨테이너에 대해 소개 합니다. 복합 UI 더 높은 수준의 있지만 복잡성 디자인 하 고 UI를 개발 하는 경우 더 이상 필요 합니다. 둘째, eShopOnContainers 제공 기본 모바일 앱에 Xamarin을 만들 때와 더 복잡 한 C 클라이언트에 따라\# 쪽입니다.

그러나 좋습니다 복합 microservices를 기반으로 UI에 대 한 자세한 내용을 보려면 다음 참조를 사용할 수 있습니다.

## <a name="additional-resources"></a>추가 리소스

-   **ASP.NET (특정의 Workshop)를 사용 하 여 복합 UI**
    [*http://go.particular.net/workshop-composite-ui-demo*](http://go.particular.net/workshop-composite-ui-demo)

-   **Ruben Oostinga 합니다. Microservices 아키텍처에서 모놀리식 프런트 엔드**
    [*http://blog.xebia.com/the-monolithic-frontend-in-the-microservices-architecture/*](http://blog.xebia.com/the-monolithic-frontend-in-the-microservices-architecture/)

-   **Mauro Servienti 합니다. 더 나은 UI 배치 비밀**
    [*https://particular.net/blog/secret-of-better-ui-composition*](https://particular.net/blog/secret-of-better-ui-composition)

-   **Viktor Farcic 합니다. 웹 프런트 엔드 구성 요소를 포함 하 여 Microservices에**
    [*https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/*](https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/)

-   **Microservices 아키텍처에 대 한 프런트 엔드를 관리합니다.**\
    [*http://allegro.tech/2016/03/Managing-Frontend-in-the-microservices-architecture.html*](http://allegro.tech/2016/03/Managing-Frontend-in-the-microservices-architecture.html)


>[!div class="step-by-step"]
[이전] (microservices-주소 지정 기능-service-registry.md) [다음] (복원 력 있는-높은-가용성-microservices.md)
