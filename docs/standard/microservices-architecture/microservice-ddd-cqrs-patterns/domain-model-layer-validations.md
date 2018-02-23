---
title: "도메인 모델 레이어에서 유효성 검사 디자인"
description: "컨테이너화된 .NET 응용 프로그램에 대한 .NET 마이크로 서비스 아키텍처 | 도메인 모델 레이어에서 유효성 검사 디자인"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: e7a111ce20039f8c87d3c3d63efdeaf38a4e1e96
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="designing-validations-in-the-domain-model-layer"></a><span data-ttu-id="e8f7c-104">도메인 모델 레이어에서 유효성 검사 디자인</span><span class="sxs-lookup"><span data-stu-id="e8f7c-104">Designing validations in the domain model layer</span></span>

<span data-ttu-id="e8f7c-105">DDD에서 유효성 검사 규칙을 고정으로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-105">In DDD, validation rules can be thought as invariants.</span></span> <span data-ttu-id="e8f7c-106">집계의 기본 역할은 해당 집계 내의 모든 엔터티에 대한 상태 변경 내용에 고정을 적용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-106">The main responsibility of an aggregate is to enforce invariants across state changes for all the entities within that aggregate.</span></span>

<span data-ttu-id="e8f7c-107">도메인 엔터티는 항상 유효한 엔터티여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-107">Domain entities should always be valid entities.</span></span> <span data-ttu-id="e8f7c-108">항상 true여야 하는 개체에 대한 특정 수의 고정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-108">There are a certain number of invariants for an object that should always be true.</span></span> <span data-ttu-id="e8f7c-109">예를 들어 주문 항목 개체는 항상 양의 정수 더하기 아티클 이름 및 가격이어야 하는 수량을 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-109">For example, an order item object always has to have a quantity that must be a positive integer, plus an article name and price.</span></span> <span data-ttu-id="e8f7c-110">따라서 고정 적용은 도메인 엔터티(특히 집계 루트)의 책임이며 엔터티 개체는 유효하지 않고 존재할 수 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-110">Therefore, invariants enforcement is the responsibility of the domain entities (especially of the aggregate root) and an entity object should not be able to exist without being valid.</span></span> <span data-ttu-id="e8f7c-111">고정 규칙은 단순히 계약으로 표시되고 위반될 때 예외 또는 알림이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-111">Invariant rules are simply expressed as contracts, and exceptions or notifications are raised when they are violated.</span></span>

<span data-ttu-id="e8f7c-112">이에 대한 이유는 개체가 있어 본 적 없어야 하는 상태에 있으므로 많은 버그가 발생하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-112">The reasoning behind this is that many bugs occur because objects are in a state they should never have been in.</span></span> <span data-ttu-id="e8f7c-113">다음은 [온라인 토론](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/)에서 Greg Young의 좋은 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-113">The following is a good explanation from Greg Young in an [online discussion](http://jeffreypalermo.com/blog/the-fallacy-of-the-always-valid-entity/):</span></span>

<span data-ttu-id="e8f7c-114">사용자 프로필을 사용하는 SendUserCreationEmailService가 있다고 제안해 보겠습니다. 해당 서비스에서 해당 이름이 Null이 아니라고 어떻게 합리화할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="e8f7c-114">Let's propose we now have a SendUserCreationEmailService that takes a UserProfile ... how can we rationalize in that service that Name is not null?</span></span> <span data-ttu-id="e8f7c-115">다시 확인할까요?</span><span class="sxs-lookup"><span data-stu-id="e8f7c-115">Do we check it again?</span></span> <span data-ttu-id="e8f7c-116">또는 확인을 하지 않고 낙관할 가능성이 있습니다. 누군가가 당신에게 보내기 전에 유효성 검사를 고려했기를 희망합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-116">Or more likely ... you just don't bother to check and "hope for the best"—you hope that someone bothered to validate it before sending it to you.</span></span> <span data-ttu-id="e8f7c-117">물론 TDD를 사용하여 작성해야 하는 첫 번째 테스트 중 하나는 Null 이름으로 고객에게 보내면 오류를 발생시켜야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-117">Of course, using TDD one of the first tests we should be writing is that if I send a customer with a null name that it should raise an error.</span></span> <span data-ttu-id="e8f7c-118">하지만 이러한 종류의 테스트를 계속해서 다시 작성하면 "잠깐, Null이 되는 이름을 허용하지 않았다면 이런 모든 테스트를 하지 않았을텐데"라는 것을 깨닫게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-118">But once we start writing these kinds of tests over and over again we realize ... "wait if we never allowed name to become null we wouldn't have all of these tests"</span></span>

## <a name="implementing-validations-in-the-domain-model-layer"></a><span data-ttu-id="e8f7c-119">도메인 모델 레이어에서 유효성 검사 구현</span><span class="sxs-lookup"><span data-stu-id="e8f7c-119">Implementing validations in the domain model layer</span></span>

<span data-ttu-id="e8f7c-120">유효성 검사는 도메인 엔터티 생성자 또는 엔터티를 업데이트할 수 있는 메서드에서 일반적으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-120">Validations are usually implemented in domain entity constructors or in methods that can update the entity.</span></span> <span data-ttu-id="e8f7c-121">데이터를 확인하고 유효성 검사에 실패하는 경우 예외를 발생하는 것과 같은 유효성 검사를 구현하는 여러 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-121">There are multiple ways to implement validations, such as verifying data and raising exceptions if the validation fails.</span></span> <span data-ttu-id="e8f7c-122">유효성 검사에 대해 사양 패턴을 사용하고 발생할 때 각 유효성 검사에 대한 예외를 반환하는 대신 오류 컬렉션을 반환하는 알림 패턴과 같은 더 많은 고급 패턴이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-122">There are also more advanced patterns such as using the Specification pattern for validations, and the Notification pattern to return a collection of errors instead of returning an exception for each validation as it occurs.</span></span>

### <a name="validating-conditions-and-throwing-exceptions"></a><span data-ttu-id="e8f7c-123">조건 유효성 검사 및 예외 throw</span><span class="sxs-lookup"><span data-stu-id="e8f7c-123">Validating conditions and throwing exceptions</span></span>

<span data-ttu-id="e8f7c-124">다음 코드 예제에서는 예외를 발생시켜 도메인 엔터티에서 유효성을 검사하는 가장 간단한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-124">The following code example shows the simplest approach to validation in a domain entity by raising an exception.</span></span> <span data-ttu-id="e8f7c-125">이 섹션 끝의 참조 테이블에서 이전에 설명한 패턴을 기반으로 하는 더 많은 고급 구현에 대한 링크를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-125">In the references table at the end of this section you can see links to more advanced implementations based on the patterns we have discussed previously.</span></span>

```csharp
public void SetAddress(Address address)
{
    _shippingAddress = address?? throw new ArgumentNullException(nameof(address));
}
```

<span data-ttu-id="e8f7c-126">적절한 예제는 내부 상태가 변경되지 않았거나 메서드에 대한 모든 변경이 발생했다는 것을 확인해야 함을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-126">A better example would demonstrate the need to ensure that either the internal state did not change, or that all the mutations for a method occurred.</span></span> <span data-ttu-id="e8f7c-127">예를 들어 다음 구현은 개체를 유효하지 않은 상태에 둘 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-127">For example, the following implementation would leave the object in an invalid state:</span></span>

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

<span data-ttu-id="e8f7c-128">상태 값이 유효하지 않은 경우 첫 번째 주소 줄 및 도시는 이미 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-128">If the value of the state is invalid, the first address line and the city have already been changed.</span></span> <span data-ttu-id="e8f7c-129">잘못된 주소를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-129">That might make the address invalid.</span></span>

<span data-ttu-id="e8f7c-130">만들어진 후 엔터티가 유효한지 확인하도록 예외를 발생시켜 엔터티 생성자에서 유사한 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-130">A similar approach can be used in the entity’s constructor, raising an exception to make sure that the entity is valid once it is created.</span></span>

### <a name="using-validation-attributes-in-the-model-based-on-data-annotations"></a><span data-ttu-id="e8f7c-131">데이터 주석을 기반으로 하는 모델에서 유효성 검사 특성 사용</span><span class="sxs-lookup"><span data-stu-id="e8f7c-131">Using validation attributes in the model based on data annotations</span></span>

<span data-ttu-id="e8f7c-132">다른 방법은 데이터 주석을 기반으로 하는 유효성 검사 특성을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-132">Another approach is to use validation attributes based on data annotations.</span></span> <span data-ttu-id="e8f7c-133">유효성 검사 특성은 모델 유효성 검사를 구성하는 방법을 제공하며 데이터베이스 테이블의 필드에 대한 유효성 검사와 개념적으로 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-133">Validation attributes provide a way to configure model validation, which is similar conceptually to validation on fields in database tables.</span></span> <span data-ttu-id="e8f7c-134">데이터 형식이나 필수 필드를 할당하는 등 제약 조건이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-134">This includes constraints such as assigning data types or required fields.</span></span> <span data-ttu-id="e8f7c-135">다른 종류의 유효성 검사에는 신용 카드 번호, 전화 번호 또는 이메일 주소와 같은 비즈니스 규칙을 적용하기 위해 데이터에 패턴을 적용하는 것이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-135">Other types of validation include applying patterns to data to enforce business rules, such as a credit card number, phone number, or email address.</span></span> <span data-ttu-id="e8f7c-136">유효성 검사 특성은 요구 사항을 쉽게 적용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-136">Validation attributes make it easy to enforce requirements.</span></span>

<span data-ttu-id="e8f7c-137">그러나 다음 코드에서와 같이 이 방법은 MVC 컨트롤러에서 호출해야 하는 Microsoft.AspNetCore.Mvc.ModelState에서 ModelState.IsValid에 대한 종속성을 사용하기 때문에 DDD 모델에서 매우 귀찮을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-137">However, as shown in the following code, this approach might be too intrusive in a DDD model, because it takes a dependency on ModelState.IsValid from Microsoft.AspNetCore.Mvc.ModelState, which you must call from your MVC controllers.</span></span> <span data-ttu-id="e8f7c-138">모델 유효성 검사는 각 컨트롤러 작업을 호출하기 전에 발생하며, ModelState.IsValid 호출의 결과를 검사하고 적절하게 반응하는 것은 컨트롤러 메서드의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-138">The model validation occurs prior to each controller action being invoked, and it is the controller method’s responsibility to inspect the result of calling ModelState.IsValid and react appropriately.</span></span> <span data-ttu-id="e8f7c-139">이를 사용하는 결정은 모델을 해당 인프라와 함께 하도록 밀접하게 결합하려는 방법에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-139">The decision to use it depends on how tightly coupled you want the model to be with that infrastructure.</span></span>

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

<span data-ttu-id="e8f7c-140">그러나 DDD의 관점에서 도메인 모델은 엔터티의 동작 메서드에서 예외를 사용하거나 유효성 검사 규칙을 적용하도록 사양 및 알림 패턴을 구현하여 가장 잘 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-140">However, from a DDD point of view, the domain model is best kept lean with the use of exceptions in your entity’s behavior methods, or by implementing the Specification and Notification patterns to enforce validation rules.</span></span> <span data-ttu-id="e8f7c-141">ASP.NET Core의 데이터 주석과 같은 유효성 검사 프레임워크 또는 FluentValidation과 같은 다른 유효성 검사 프레임워크는 응용 프로그램 프레임워크를 호출하기 위해 요구 사항을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-141">Validation frameworks like data annotations in ASP.NET Core or any other validation frameworks like FluentValidation carry a requirement to invoke the application framework.</span></span> <span data-ttu-id="e8f7c-142">예를 들어 데이터 주석에서 ModelState.IsValid 메서드를 호출할 때 ASP.NET 컨트롤러를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-142">For example, when calling the ModelState.IsValid method in data annotations, you need to invoke ASP.NET controllers.</span></span>

<span data-ttu-id="e8f7c-143">UI 계층 내에서 모델 유효성 검사를 허용하도록 입력을 허용하는 ViewModel 클래스(도메인 엔터티 대신)의 응용 프로그램 계층에서 데이터 주석을 사용하는 것이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-143">It can make sense to use data annotations at the application layer in ViewModel classes (instead of domain entities) that will accept input, to allow for model validation within the UI layer.</span></span> <span data-ttu-id="e8f7c-144">그러나 도메인 모델 내의 유효성 검사를 제외하고 수행되어서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-144">However, this should not be done at the exclusion of validation within the domain model.</span></span>

### <a name="validating-entities-by-implementing-the-specification-pattern-and-the-notification-pattern"></a><span data-ttu-id="e8f7c-145">사양 패턴 및 알림 패턴을 구현하여 엔터티의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="e8f7c-145">Validating entities by implementing the Specification pattern and the Notification pattern</span></span>

<span data-ttu-id="e8f7c-146">마지막으로 도메인 모델에서 유효성 검사를 구현하는 보다 정교한 방법은 나중에 나열된 추가 리소스의 일부에서 설명된 것처럼 알림 패턴과 함께 사양 패턴을 구현하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-146">Finally, a more elaborate approach to implementing validations in the domain model is by implementing the Specification pattern in conjunction with the Notification pattern, as explained in some of the additional resources listed later.</span></span>

<span data-ttu-id="e8f7c-147">이러한 패턴 중 하나만 사용할 수도 있습니다. 예를 들어 제어 문을 사용하여 수동으로 유효성을 검사하지만 유효성 검사 오류 목록을 배치하고 반환하도록 알림 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-147">It is worth mentioning that you can also use just one of those patterns—for example, validating manually with control statements, but using the Notification pattern to stack and return a list of validation errors.</span></span>

### <a name="using-deferred-validation-in-the-domain"></a><span data-ttu-id="e8f7c-148">도메인에서 지연된 유효성 검사 사용</span><span class="sxs-lookup"><span data-stu-id="e8f7c-148">Using deferred validation in the domain</span></span>

<span data-ttu-id="e8f7c-149">도메인에서 지연된 유효성 검사를 처리하는 다양한 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-149">There are various approaches to deal with deferred validations in the domain.</span></span> <span data-ttu-id="e8f7c-150">Vaughn Vernon은 그의 저서 [도메인 기반 디자인 구현](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577)의 유효성 검사에 대한 섹션에서 이에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-150">In his book [Implementing Domain-Driven Design](https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577), Vaughn Vernon discusses these in the section on validation.</span></span>

### <a name="two-step-validation"></a><span data-ttu-id="e8f7c-151">2단계 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="e8f7c-151">Two-step validation</span></span>

<span data-ttu-id="e8f7c-152">또한 2단계 유효성 검사를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-152">Also consider two-step validation.</span></span> <span data-ttu-id="e8f7c-153">명령 DTO(데이터 전송 개체) 및 엔터티 내 도메인 수준 유효성 검사에서 필드 수준 유효성 검사를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-153">Use field-level validation on your command Data Transfer Objects (DTOs) and domain-level validation inside your entities.</span></span> <span data-ttu-id="e8f7c-154">유효성 검사 오류를 쉽게 처리할 수 있도록 예외 대신 결과 개체를 반환하여 이를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-154">You can do this by returning a result object instead exceptions in order to make it easier to deal with the validation errors.</span></span>

<span data-ttu-id="e8f7c-155">예를 들어 데이터 주석과 함께 필드 유효성 검사를 사용하여 유효성 검사 정의를 중복하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e8f7c-155">Using field validation with data annotations, for example, you do not duplicate the validation definition.</span></span> <span data-ttu-id="e8f7c-156">그러나 실행은 DTO의 경우 서버 쪽 및 클라이언트 쪽 모두가 될 수 있습니다(예: 명령 및 Viewmodel).</span><span class="sxs-lookup"><span data-stu-id="e8f7c-156">The execution, though, can be both server-side and client-side in the case of DTOs (commands and ViewModels, for instance).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="e8f7c-157">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="e8f7c-157">Additional resources</span></span>

-   <span data-ttu-id="e8f7c-158">**Rachel Appel. ASP.NET Core MVC의 모델 유효성 검사 소개**
    [*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)</span><span class="sxs-lookup"><span data-stu-id="e8f7c-158">**Rachel Appel. Introduction to model validation in ASP.NET Core MVC**
[*https://docs.microsoft.com/aspnet/core/mvc/models/validation*](https://docs.microsoft.com/aspnet/core/mvc/models/validation)</span></span>

-   <span data-ttu-id="e8f7c-159">**Rick Anderson. 유효성 검사 추가**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="e8f7c-159">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

-   <span data-ttu-id="e8f7c-160">**Martin Fowler. 유효성 검사에서 알림으로 throw되는 예외 대체**
    [*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)</span><span class="sxs-lookup"><span data-stu-id="e8f7c-160">**Martin Fowler. Replacing Throwing Exceptions with Notification in Validations**
[*https://martinfowler.com/articles/replaceThrowWithNotification.html*](https://martinfowler.com/articles/replaceThrowWithNotification.html)</span></span>

-   <span data-ttu-id="e8f7c-161">**사양 및 알림 패턴**
    [*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)</span><span class="sxs-lookup"><span data-stu-id="e8f7c-161">**Specification and Notification Patterns**
[*https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns*](https://www.codeproject.com/Tips/790758/Specification-and-Notification-Patterns)</span></span>

-   <span data-ttu-id="e8f7c-162">**Lev Gorodinski. DDD(도메인 기반 디자인)에서 유효성 검사**
    [*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)</span><span class="sxs-lookup"><span data-stu-id="e8f7c-162">**Lev Gorodinski. Validation in Domain-Driven Design (DDD)**
[*http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/*](http://gorodinski.com/blog/2012/05/19/validation-in-domain-driven-design-ddd/)</span></span>

-   <span data-ttu-id="e8f7c-163">**Colin Jack. 도메인 모델 유효성 검사**
    [*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)</span><span class="sxs-lookup"><span data-stu-id="e8f7c-163">**Colin Jack. Domain Model Validation**
[*http://colinjack.blogspot.com/2008/03/domain-model-validation.html*](http://colinjack.blogspot.com/2008/03/domain-model-validation.html)</span></span>

-   <span data-ttu-id="e8f7c-164">**Jimmy Bogard. DDD 세계에서 유효성 검사**
    [*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)</span><span class="sxs-lookup"><span data-stu-id="e8f7c-164">**Jimmy Bogard. Validation in a DDD world**
[*https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/*](https://lostechies.com/jimmybogard/2009/02/15/validation-in-a-ddd-world/)</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="e8f7c-165">[이전] (enumeration-classes-over-enum-types.md) [다음] (client-side-validation.md)</span><span class="sxs-lookup"><span data-stu-id="e8f7c-165">[Previous] (enumeration-classes-over-enum-types.md) [Next] (client-side-validation.md)</span></span>
