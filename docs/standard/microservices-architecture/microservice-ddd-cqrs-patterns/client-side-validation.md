---
title: "클라이언트 쪽 유효성 검사 (프레젠테이션 계층에서 유효성 검사)"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 클라이언트 쪽 유효성 검사 (프레젠테이션 계층에서 유효성 검사)"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: db88a3b5c95afdc8d5a20094105f1f5991483ed6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="client-side-validation-validation-in-the-presentation-layers"></a>클라이언트 쪽 유효성 검사 (프레젠테이션 계층에서 유효성 검사)

정보의 원본을 도메인 모델 이며 도메인 모델 수준에서 유효성 검사를 있어야 합니다는 궁극적으로, 경우에 유효성 검사가 도메인 모델 수준 (서버 쪽) 및 클라이언트 측 모두에서 계속 처리할 수 있습니다.

클라이언트 쪽 유효성 검사는 사용자에 대 한 매우 편리 합니다. 시간을 절약 그렇지 않은 경우 많은 비용이 들어가는지는 왕복에 대 한 대기 중인 유효성 검사 오류를 반환할 수 있는 서버. 비즈니스 관계에서 많은 시간과 비용, 노력에 몇 초 부분을 곱한 수백 번 매일 추가 합니다. 간단 하 고 즉시 유효성 검사를 사용 하면 보다 효율적으로 작동 하 고 더 좋은 품질 입력 및 출력을 생성할 수 있습니다.

뷰 모델 및 도메인 모델을 서로 다른 것 처럼 뷰 모델 유효성 검사 및 도메인 모델 유효성 검사와 유사 하지만 수 용도 다릅니다. 우려되는 경우 (안 함 반복 직접 원칙) 드라이 대 한이 예제의 코드를 재사용할 수 결합, 의미할 수도 있습니다 및 엔터프라이즈 응용 프로그램에서 것이 더 중요 서버 쪽에 건조 원칙에 따라 보다 클라이언트 쪽 결합 하지를 고려 합니다.

도 클라이언트 쪽 유효성 검사를 사용할 경우 해야 항상 유효성 검사 명령을 하거나 Api 서버 가능한 공격 하므로 서버 코드에서 Dto를 입력 합니다. 일반적으로 둘 다 수행 하는 최선의 방법은 되었으므로 UX 관점에서 볼 때 클라이언트 응용 프로그램의 경우 최선의 예방할 수 및 잘못 된 정보를 입력할 수 있는 사용자 수 없습니다.

따라서 클라이언트 코드에서 일반적으로 유효성을 검사할 있습니다는 Viewmodel입니다. 클라이언트도 유효성을 검사할 수 있는 서비스에 보내기 전에 출력 Dto 또는 명령입니다.

클라이언트 쪽 유효성 검사의 구현 빌드하는 클라이언트 응용 프로그램의 종류에 따라 달라 집니다. 대부분의.net에서 JavaScript 또는 TypeScript 코딩 되 고 해당 유효성 검사로 SPA 웹 응용 프로그램 코드를 사용 하 여 웹 MVC 웹 응용 프로그램의에서 데이터 유효성을 검사 하는 경우에 다른 수 있습니다 또는 Xamarin 및 C 코딩 된 모바일 앱\#합니다.

## <a name="additional-resources"></a>추가 리소스

### <a name="validation-in-xamarin-mobile-apps"></a>Xamarin 모바일 앱의 유효성 검사

-   **텍스트 입력 및 표시 한 오류를 유효성 검사**
    [*https://developer.xamarin.com/recipes/ios/standard\_컨트롤/텍스트\_필드/유효성 검사\_입력 /*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)

-   **유효성 검사 콜백을**
    [*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)

### <a name="validation-in-aspnet-core-apps"></a>ASP.NET Core 응용 프로그램에서 유효성 검사

-   **Rick Anderson. 유효성 검사 추가**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a>SPA에서 유효성 검사 웹 앱 (각도 2, TypeScript JavaScript)

-   **Ado Kukic 합니다. 유효성 검사를 형성 하는 각도 2** **
     ** [ *https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)

-   **유효성 검사를 형성**
    [*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)

-   **유효성 검사 합니다.** 간편 설명서입니다.
    [*http://breeze.github.io/doc-js/validation.html*](http://breeze.github.io/doc-js/validation.html)

요약 하면, 다음은 유효성 검사 시에서 가장 중요 한 개념입니다.

-   엔터티 및 집계 자신의 일관성을 유지 하 고 "항상 유효" 해야 합니다. 집계 루트 같은 집계 내에서 다중 엔터티 일관성에 대 한 책임이 있습니다.

-   엔터티를 잘못 된 상태를 입력 해야 함을 생각 되 면 다양 한 개체 모델 사용을 고려-최종 도메인 엔터티를 만들 때까지 임시 DTO을 사용 하 여 예를 들어 있습니다.

-   집계 함수 등의 여러 관련된 개체를 만들어야 하는 경우만 유효 모두 만든 팩터리 패턴을 사용 하는 것이 좋습니다.

-   유효성 검사 프레임 워크는는 인프라 프레임 워크에 의존 강력한 해야 하기 때문에 가장 프레젠테이션 계층 또는 응용 프로그램/서비스 계층과 같은 특정 계층에 있지만 도메인 모델 계층에 없는 일반적으로 적합 합니다.

-   대부분의 경우에 클라이언트 쪽에 중복 유효성 검사 하는 것은 적절 한 경우 응용 프로그램은 사전 수 있기 때문에 합니다.


>[!div class="step-by-step"]
[이전] (도메인-모델-계층-validations.md) [다음] (도메인-이벤트-디자인-implementation.md)
