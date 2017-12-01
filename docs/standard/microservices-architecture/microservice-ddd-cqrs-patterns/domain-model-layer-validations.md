---
title: "도메인 모델 계층에서 유효성 검사를 디자인합니다."
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 도메인 모델 계층에서 유효성 검사를 디자인합니다."
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f4870d0568c3539f296bcb3f577291cb0250cfca
ms.sourcegitcommit: 62d3e3e74c1b7ffa927590012c0b9f87de1b0848
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="designing-validations-in-the-domain-model-layer"></a>도메인 모델 계층에서 유효성 검사를 디자인합니다.

DDD, 유효성 검사 규칙을 고정으로 생각할 수 있습니다. 집계의 기본 역할은 고정 블록 전체에 해당 집계 내에서 모든 엔터티에 대 한 상태 변경을 적용할입니다.

도메인 엔터티 유효한 엔터티 항상 있어야 합니다. 항상 true 여야 하는 개체에 대 한 고정에 대 한 특정 여러 가지가 있습니다. 예를 들어 주문 항목이 개체 및 해야 하는 양의 정수 및 아티클 이름을 가격 수량을 항상에 있습니다. 고정 적용 됩니다 (특히 집계 루트)의 도메인 엔터티 책임 하 고 엔터티 개체를 유효하지 없이 존재 하도록 수 있어야 합니다. 따라서 합니다. 고정 규칙은 단순히 계약 00z 하 고 예외 또는 알림을 위반 될 때 발생 합니다.

이 이유는 많은 버그가 발생할 해야 하지에 있었던 상태의 개체는는입니다. 다음은에 Greg Young에서 잘 설명은 [온라인 토론](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):

… 사용자 프로필 어떻게 수 म 근거를 확보 해야 이름이 null이 아닌 해당 서비스에 사용 하는 SendUserCreationEmailService 했습니다 제안 보겠습니다? 마십시오 했습니다 체크 다시? 또는 가능성이 더... 하면 방금 필요가 없다는 확인 하 고 "는 가장에 대 한 경험 을"-하고자 하는지는 사용자을 찾는 중에 사용자에 게 보내기 전에 유효성을 검사 합니다. 물론, 우리는 null 이름을 고객 보낼 오류를 발생 시켜야 하는 경우 작성 해야 하는 첫 번째 테스트 TDD 하나를 사용 합니다. 하지만 이러한 종류의 테스트를 반복 해 서 다시 작성 시작 이라는 사실을 인식... "म 이름이 될 수 없는 경우 대기 null 않았을 이러한 모든 테스트"

## <a name="implementing-validations-in-the-domain-model-layer"></a>도메인 모델 계층에서 유효성 검사 구현

유효성 검사가 도메인 엔터티 생성자 또는 엔터티를 업데이트할 수 있는 방법에 일반적으로 구현 됩니다. 유효성 검사를 확인 하는 중 데이터 유효성 검사에 실패 하는 경우 발생 한 예외 등을 구현 하는 방법은 여러 가지입니다. 유효성 검사에 대 한 사양 패턴을 사용 하는 등 고급 패턴 한 후 각 유효성 검사에 대 한 예외를 반환 하는 대신 오류 컬렉션을 반환 하는 알림 패턴 있습니다.

### <a name="validating-conditions-and-throwing-exceptions"></a>조건 유효성을 검사 하 고 예외를 throw

다음 코드 예제에서는 예외를 발생 시켜 도메인 엔터티 유효성 검사는 가장 간단한 방식은 보여 줍니다. 이 섹션의 끝에 참조 테이블에서 이전에 설명한 패턴을 기반으로 하는 고급 구현에 대 한 링크를 볼 수 있습니다.

```csharp
public void SetAddress(Address address)
{
    _shippingAddress = address?? throw new ArgumentNullException(nameof(address));
}
```

적절 한 예제는 내부 상태가 변경 되지 않은 또는 메서드에 대 한 모든 변경이 발생 한 보장 하기 위해 필요를 보여 줍니다. 예를 들어 다음 구현은 유효 하지 않은 상태에서 개체가 남을 수 있습니다.:

```csharp
public void SetAddress(string line1, string line2,
    string city, string state, int zip)
{
    _shipingAddress.line1 = line1 ?? throw new ...
    _shippingAddress.line2 = line2;
    _shippingAddress.city = city ?? throw new ...
    _shippingAddress.state = (IsValid(state) ? state : throw new …);
}
```

상태 값 유효 하지 않을 경우 첫 번째 주소 줄 고 도시 이미 변경 되었습니다. 잘못 된 주소를 만들 수 있는 합니다.

만든 후 엔터티가 유효한 지 확인 하려면 예외를 발생 시키는 엔터티 생성자에서 유사한 방법을 사용할 수 있습니다.

### <a name="using-validation-attributes-in-the-model-based-on-data-annotations"></a>데이터 주석을 기반으로 모델의 유효성 검사 특성을 사용 하 여

다른 방법은 기반으로 데이터 주석 유효성 검사 특성을 사용 하는 것입니다. 유효성 검사 특성은 데이터베이스 테이블의 필드에 유효성 검사에 개념적으로 비슷합니다 모델 유효성 검사를 구성 하는 방법을 제공 합니다. 데이터 형식이 나 필수 필드를 할당 하는 등 제약 조건을 포함 됩니다. 다른 종류의 유효성 검사는 신용 카드 번호, 전화 번호 등의 비즈니스 규칙을 적용 하는 데이터 패턴을 적용 하는 또는 전자 메일 주소입니다. 유효성 검사 특성을 한결 요구 사항을 적용 하 집니다.

그러나 다음 코드에서와 같이이 접근 방식을 수 있습니다 DDD 모델에는 너무 방해가에서 MVC 컨트롤러에서 호출 해야 Microsoft.AspNetCore.Mvc.ModelState ModelState.IsValid에 종속성을 사용 하기 때문에 합니다. 모델 유효성 검사가 호출 되는 각 컨트롤러 동작 하기 전에 수행 하 고 컨트롤러 메서드 호출 ModelState.IsValid의 결과 검사 하 고 적절 하 게 대응 해야 합니다. 방법에 따라 사용 하도록 결정 밀접 하 게 하려는 모델 인프라에 있는 것입니다.

```csharp
using System.ComponentModel.DataAnnotations;
// Other using statements ...
// Entity is a custom base class which has the ID
public class Product : Entity
{
    [Required]
    [StringLength(100)]
    public string Title { get; private set; }

    [Required]
    [Range(0, 999.99)]
    public decimal Price { get; private set; }

    [Required]
    [VintageProduct(1970)]
    [DataType(DataType.Date)]
    public DateTime ReleaseDate { get; private set; }

    [Required]
    [StringLength(1000)]
    public string Description { get; private set; }

    // Constructor...
    // Additional methods for entity logic and constructor...
}
```

그러나 한 DDD 관점에서 도메인 모델 가장 잘 유지 되 lean 예외를 사용 하 여 회사의 동작 메서드를 사용 하거나 유효성 검사 규칙을 적용 하 한 사양 및 알림 패턴을 구현 합니다. 응용 프로그램 프레임 워크를 호출 하는 요구 사항 같은 ASP.NET Core에 대 한 데이터 주석 유효성 검사 프레임 워크 또는 FluentValidation와 같은 다른 유효성 검사 프레임 워크를 수행 합니다. 예를 들어 데이터 주석에서 ModelState.IsValid 메서드를 호출할 때 ASP.NET 컨트롤러를 호출 해야 합니다.

UI 계층 내에서 모델 유효성 검사를 허용 하도록 입력을 허용 합니다 (도메인 엔터티) 대신 ViewModel 클래스에서 응용 프로그램 계층에서 데이터 주석을 사용 하는 어떤 것이 가능 합니다. 그러나 하지 이렇게 해야에서 도메인 모델 내에서 유효성 검사를 제외 합니다.

### <a name="validating-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a>사양 패턴 및 알림 패턴을 구현 하 여 엔터티를 유효성 검사

마지막으로 나오는 추가 리소스 중 일부에 설명 된 대로 알림 패턴와 함께에서 사양 패턴을 구현 하 여 도메인 모델에서 유효성 검사를 구현 하는 보다 정교한 접근 방식이입니다.

패턴 중 하나만 사용할 수도 있습니다 점을 알아야-예를 들어 제어 문, 수동 유효성 검사 하지만 알림 패턴을 사용 하 여 유효성 검사 오류 목록을 반환 하 합니다.

### <a name="using-deferred-validation-in-the-domain"></a>지연 된 유효성 검사를 사용 하 여 도메인에 있는

도메인의 지연 된 유효성 검사를 처리 하는 방법은 다양 한 가지가 있습니다. 저서인에서 [Implementing Domain-Driven 디자인](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577), Vaughn Vernon 섹션에서 이러한 유효성 검사에 설명 합니다.

### <a name="two-step-validation"></a>2 단계 유효성 검사

또한 2 단계 유효성 검사를 고려 합니다. 명령 데이터 전송 개체 (Dto) 및 엔터티 내 도메인 수준 유효성 검사에서 필드 수준 유효성 검사를 사용 합니다. 반환 하 여 결과 개체 대신 예외 보다 쉽게 유효성 검사 오류를 처리할 수 있도록 하면 됩니다.

필드 유효성 검사를 사용 하 여 데이터 주석을 사용한, 예를 들어 하면 중복 되지 않는 유효성 검사 정의 합니다. 을 실행 하지만 수 서버 쪽 및 클라이언트 쪽 Dto의 경우 모두 (명령 및 Viewmodel, 예를 들어).

## <a name="additional-resources"></a>추가 리소스

-   **Rachel Appel 합니다. ASP.NET Core MVC에서 모델 유효성 검사 소개**
    [*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)

-   **Rick Anderson. 유효성 검사 추가**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)

-   **Martin Fowler. 유효성 검사에서 알림 사용 하 여 예외를 Throw 교체**
    [*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)

-   **사양 및 알림 패턴**
    [*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)

-   **레프 Gorodinski 합니다. 도메인 기반 디자인 (DDD)에서 유효성 검사**
    [*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)

-   **Colin 잭 합니다. 도메인 모델 유효성 검사**
    [*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)

-   **Jimmy Bogard. 유효성 검사는 DDD 세계에서**
    [*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)


>[!div class="step-by-step"]
[이전] (열거형-클래스-over-enum-types.md) [다음] (클라이언트 쪽 validation.md)
