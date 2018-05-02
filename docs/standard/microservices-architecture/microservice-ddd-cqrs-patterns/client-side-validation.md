---
title: 클라이언트 쪽 유효성 검사(프레젠테이션 레이어의 유효성 검사)
description: 컨테이너화된 .NET 응용 프로그램에 대한 .NET 마이크로 서비스 아키텍처 | 클라이언트 쪽 유효성 검사(프레젠테이션 레이어의 유효성 검사)
keywords: Docker, 마이크로 서비스, ASP.NET, 컨테이너
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 2057609c7f5c26668eac49cecce522135545e7dd
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="client-side-validation-validation-in-the-presentation-layers"></a><span data-ttu-id="111bc-104">클라이언트 쪽 유효성 검사(프레젠테이션 레이어의 유효성 검사)</span><span class="sxs-lookup"><span data-stu-id="111bc-104">Client-side validation (validation in the presentation layers)</span></span>

<span data-ttu-id="111bc-105">정보의 원본이 도메인 모델이며 궁극적으로 도메인 모델 수준에서 유효성 검사를 해야 하는 경우 도메인 모델 수준(서버 쪽) 및 클라이언트 쪽 모두에서 계속 유효성 검사를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="111bc-105">Even when the source of truth is the domain model and ultimately you must have validation at the domain model level, validation can still be handled at both the domain model level (server side) and the client side.</span></span>

<span data-ttu-id="111bc-106">클라이언트 쪽 유효성 검사는 사용자에게 매우 편리합니다.</span><span class="sxs-lookup"><span data-stu-id="111bc-106">Client-side validation is a great convenience for users.</span></span> <span data-ttu-id="111bc-107">그렇지 않은 경우 유효성 검사 오류를 반환할 수 있는 서버에 대한 왕복을 기다리는 데 드는 시간을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="111bc-107">It saves time they would otherwise spend waiting for a round trip to the server that might return validation errors.</span></span> <span data-ttu-id="111bc-108">비즈니스 용어로 몇 초를 매일 수백 번 반복하게 되면 많은 시간과 비용, 노력이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="111bc-108">In business terms, even a few fractions of seconds multiplied hundreds of times each day adds up to a lot of time, expense, and frustration.</span></span> <span data-ttu-id="111bc-109">간단하고 즉각적인 유효성 검사를 사용하면 사용자가 보다 효율적으로 작업하고 더 좋은 품질의 입력 및 출력을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="111bc-109">Straightforward and immediate validation enables users to work more efficiently and produce better quality input and output.</span></span>

<span data-ttu-id="111bc-110">보기 모델과 도메인 모델이 다른 것처럼 보기 모델 유효성 검사와 도메인 모델 유효성 검사는 유사하지만 용도가 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="111bc-110">Just as the view model and the domain model are different, view model validation and domain model validation might be similar but serve a different purpose.</span></span> <span data-ttu-id="111bc-111">DRY(반복 금지 원칙)에 대해 우려하는 경우 이 사례에서 코드를 재사용하면 결합될 수도 있음을 고려합니다. 또한 엔터프라이즈 응용 프로그램에서 서버 쪽을 클라이언트 쪽에 결합하는 것은 반복 금지 원칙을 따르는 것보다 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="111bc-111">If you are concerned about DRY (the Don’t Repeat Yourself principle), consider that in this case code reuse might also mean coupling, and in enterprise applications it is more important not to couple the server side to the client side than to follow the DRY principle.</span></span>

<span data-ttu-id="111bc-112">클라이언트 쪽 유효성 검사를 사용할 경우에도 서버 API가 가능한 공격 벡터일 수 있기 때문에 항상 서버 코드에서 명령 또는 DTO의 유효성을 검사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="111bc-112">Even when using client-side validation, you should always validate your commands or input DTOs in server code, because the server APIs are a possible attack vector.</span></span> <span data-ttu-id="111bc-113">클라이언트 응용 프로그램이 있는 경우 UX 관점에서 볼 때 예방하고 사용자가 잘못된 정보를 입력할 수 없도록 하는 것이 최선이기 때문에 일반적으로 둘 다 수행하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="111bc-113">Usually, doing both is your best bet because if you have a client application, from a UX perspective, it is best to be proactive and not allow the user to enter invalid information.</span></span>

<span data-ttu-id="111bc-114">따라서 일반적으로 클라이언트 쪽 코드에서 ViewModels의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="111bc-114">Therefore, in client-side code you typically validate the ViewModels.</span></span> <span data-ttu-id="111bc-115">서비스에 보내기 전에 클라이언트 출력 DTO 또는 명령의 유효성을 검사할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="111bc-115">You could also validate the client output DTOs or commands before you send them to the services.</span></span>

<span data-ttu-id="111bc-116">클라이언트 쪽 유효성 검사를 구현하는 작업은 빌드하는 클라이언트 응용 프로그램의 종류에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="111bc-116">The implementation of client-side validation depends on what kind of client application you are building.</span></span> <span data-ttu-id="111bc-117">.NET에서 대부분의 코드를 사용하는 웹 MVC 웹 응용 프로그램, JavaScript 또는 TypeScript로 코딩된 해당 유효성 검사를 사용하는 SPA 웹 응용 프로그램 또는 Xamarin 및 C\#을 사용하는 코딩된 모바일 앱의 데이터 유효성을 검사하는지에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="111bc-117">It will be different if you are validating data in a web MVC web application with most of the code in .NET, an SPA web application with that validation being coded in JavaScript or TypeScript, or a mobile app coded with Xamarin and C\#.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="111bc-118">추가 자료</span><span class="sxs-lookup"><span data-stu-id="111bc-118">Additional resources</span></span>

### <a name="validation-in-xamarin-mobile-apps"></a><span data-ttu-id="111bc-119">Xamarin 모바일 앱의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="111bc-119">Validation in Xamarin mobile apps</span></span>

-   <span data-ttu-id="111bc-120">**텍스트 입력 유효성 검사 및 오류 표시**
    [*https://developer.xamarin.com/recipes/ios/standard\_컨트롤/텍스트\_필드/유효성 검사\_입력/*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span><span class="sxs-lookup"><span data-stu-id="111bc-120">**Validate Text Input and Show Errors**
[*https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span></span>

-   <span data-ttu-id="111bc-121">**유효성 검사 콜백**
    [*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span><span class="sxs-lookup"><span data-stu-id="111bc-121">**Validation Callback**
[*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span></span>

### <a name="validation-in-aspnet-core-apps"></a><span data-ttu-id="111bc-122">ASP.NET Core 앱의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="111bc-122">Validation in ASP.NET Core apps</span></span>

-   <span data-ttu-id="111bc-123">**Rick Anderson. 유효성 검사 추가**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="111bc-123">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a><span data-ttu-id="111bc-124">SPA 웹앱의 유효성 검사(Angular 2, TypeScript, JavaScript)</span><span class="sxs-lookup"><span data-stu-id="111bc-124">Validation in SPA Web apps (Angular 2, TypeScript, JavaScript)</span></span>

-   <span data-ttu-id="111bc-125">**Ado Kukic. Angular 2 양식 유효성 검사** **
    **[*https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span><span class="sxs-lookup"><span data-stu-id="111bc-125">**Ado Kukic. Angular 2 Form Validation** **
**[*https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span></span>

-   <span data-ttu-id="111bc-126">**양식 유효성 검사**
    [*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span><span class="sxs-lookup"><span data-stu-id="111bc-126">**Form Validation**
[*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span></span>

-   <span data-ttu-id="111bc-127">**유효성 검사**</span><span class="sxs-lookup"><span data-stu-id="111bc-127">**Validation.**</span></span> <span data-ttu-id="111bc-128">Breeze 설명서</span><span class="sxs-lookup"><span data-stu-id="111bc-128">Breeze documentation.</span></span>
    [*https://breeze.github.io/doc-js/validation.html*](https://breeze.github.io/doc-js/validation.html)

<span data-ttu-id="111bc-129">요약하면 유효성 검사에 관해 가장 중요한 개념은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="111bc-129">In summary, these are the most important concepts in regards to validation:</span></span>

-   <span data-ttu-id="111bc-130">엔터티 및 집계는 고유한 일관성을 적용하고 "항상 유효"해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="111bc-130">Entities and aggregates should enforce their own consistency and be "always valid”.</span></span> <span data-ttu-id="111bc-131">집계 루트는 동일한 집계 내에서 다중 엔터티 일관성을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="111bc-131">Aggregate roots are responsible for multi-entity consistency within the same aggregate.</span></span>

-   <span data-ttu-id="111bc-132">엔터티가 잘못된 상태를 입력해야 하는 경우 다양한 개체 모델을 사용하는 것이 좋습니다. 예를 들어 최종 도메인 엔터티를 만들 때까지 임시 DTO를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="111bc-132">If you think that an entity needs to enter an invalid state, consider using a different object model—for example, using a temporary DTO until you create the final domain entity.</span></span>

-   <span data-ttu-id="111bc-133">집계 함수와 같은 여러 관련 개체를 만들어야 하고 해당 개체를 모두 만들어야만 유효한 경우 팩터리 패턴을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="111bc-133">If you need to create several related objects, such as an aggregate, and they are only valid once all of them have been created, consider using the Factory pattern.</span></span>

-   <span data-ttu-id="111bc-134">유효성 검사 프레임워크는 프레젠테이션 계층 또는 응용 프로그램/서비스 계층과 같은 특정 계층에서 사용되기에 적합하지만 인프라 프레임워크에 대한 종속성이 커야 하기 때문에 도메인 모델 계층에서는 일반적으로 적합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="111bc-134">Validation frameworks are best used in specific layers, such as the presentation layer or the application/service layer, but usually not in the domain model layer, because you would need to take a strong dependency on an infrastructure framework.</span></span>

-   <span data-ttu-id="111bc-135">대부분의 경우에 응용 프로그램이 예방적일 수 있기 때문에 클라이언트 쪽에서 중복 유효성을 검사하는 것이 적절합니다.</span><span class="sxs-lookup"><span data-stu-id="111bc-135">In most of the cases, having redundant validation in the client side is good, because the application can be proactive.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="111bc-136">[이전](domain-model-layer-validations.md) [다음](domain-events-design-implementation.md)</span><span class="sxs-lookup"><span data-stu-id="111bc-136">[Previous] (domain-model-layer-validations.md) [Next] (domain-events-design-implementation.md)</span></span>
