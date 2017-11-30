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
# <a name="client-side-validation-validation-in-the-presentation-layers"></a><span data-ttu-id="fc28d-104">클라이언트 쪽 유효성 검사 (프레젠테이션 계층에서 유효성 검사)</span><span class="sxs-lookup"><span data-stu-id="fc28d-104">Client-side validation (validation in the presentation layers)</span></span>

<span data-ttu-id="fc28d-105">정보의 원본을 도메인 모델 이며 도메인 모델 수준에서 유효성 검사를 있어야 합니다는 궁극적으로, 경우에 유효성 검사가 도메인 모델 수준 (서버 쪽) 및 클라이언트 측 모두에서 계속 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc28d-105">Even when the source of truth is the domain model and ultimately you must have validation at the domain model level, validation can still be handled at both the domain model level (server side) and the client side.</span></span>

<span data-ttu-id="fc28d-106">클라이언트 쪽 유효성 검사는 사용자에 대 한 매우 편리 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc28d-106">Client-side validation is a great convenience for users.</span></span> <span data-ttu-id="fc28d-107">시간을 절약 그렇지 않은 경우 많은 비용이 들어가는지는 왕복에 대 한 대기 중인 유효성 검사 오류를 반환할 수 있는 서버.</span><span class="sxs-lookup"><span data-stu-id="fc28d-107">It saves time they would otherwise spend waiting for a round trip to the server that might return validation errors.</span></span> <span data-ttu-id="fc28d-108">비즈니스 관계에서 많은 시간과 비용, 노력에 몇 초 부분을 곱한 수백 번 매일 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc28d-108">In business terms, even a few fractions of seconds multiplied hundreds of times each day adds up to a lot of time, expense, and frustration.</span></span> <span data-ttu-id="fc28d-109">간단 하 고 즉시 유효성 검사를 사용 하면 보다 효율적으로 작동 하 고 더 좋은 품질 입력 및 출력을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc28d-109">Straightforward and immediate validation enables users to work more efficiently and produce better quality input and output.</span></span>

<span data-ttu-id="fc28d-110">뷰 모델 및 도메인 모델을 서로 다른 것 처럼 뷰 모델 유효성 검사 및 도메인 모델 유효성 검사와 유사 하지만 수 용도 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="fc28d-110">Just as the view model and the domain model are different, view model validation and domain model validation might be similar but serve a different purpose.</span></span> <span data-ttu-id="fc28d-111">우려되는 경우 (안 함 반복 직접 원칙) 드라이 대 한이 예제의 코드를 재사용할 수 결합, 의미할 수도 있습니다 및 엔터프라이즈 응용 프로그램에서 것이 더 중요 서버 쪽에 건조 원칙에 따라 보다 클라이언트 쪽 결합 하지를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc28d-111">If you are concerned about DRY (the Don’t Repeat Yourself principle), consider that in this case code reuse might also mean coupling, and in enterprise applications it is more important not to couple the server side to the client side than to follow the DRY principle.</span></span>

<span data-ttu-id="fc28d-112">도 클라이언트 쪽 유효성 검사를 사용할 경우 해야 항상 유효성 검사 명령을 하거나 Api 서버 가능한 공격 하므로 서버 코드에서 Dto를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc28d-112">Even when using client-side validation, you should always validate your commands or input DTOs in server code, because the server APIs are a possible attack vector.</span></span> <span data-ttu-id="fc28d-113">일반적으로 둘 다 수행 하는 최선의 방법은 되었으므로 UX 관점에서 볼 때 클라이언트 응용 프로그램의 경우 최선의 예방할 수 및 잘못 된 정보를 입력할 수 있는 사용자 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc28d-113">Usually, doing both is your best bet because if you have a client application, from a UX perspective, it is best to be proactive and not allow the user to enter invalid information.</span></span>

<span data-ttu-id="fc28d-114">따라서 클라이언트 코드에서 일반적으로 유효성을 검사할 있습니다는 Viewmodel입니다.</span><span class="sxs-lookup"><span data-stu-id="fc28d-114">Therefore, in client-side code you typically validate the ViewModels.</span></span> <span data-ttu-id="fc28d-115">클라이언트도 유효성을 검사할 수 있는 서비스에 보내기 전에 출력 Dto 또는 명령입니다.</span><span class="sxs-lookup"><span data-stu-id="fc28d-115">You could also validate the client output DTOs or commands before you send them to the services.</span></span>

<span data-ttu-id="fc28d-116">클라이언트 쪽 유효성 검사의 구현 빌드하는 클라이언트 응용 프로그램의 종류에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="fc28d-116">The implementation of client-side validation depends on what kind of client application you are building.</span></span> <span data-ttu-id="fc28d-117">대부분의.net에서 JavaScript 또는 TypeScript 코딩 되 고 해당 유효성 검사로 SPA 웹 응용 프로그램 코드를 사용 하 여 웹 MVC 웹 응용 프로그램의에서 데이터 유효성을 검사 하는 경우에 다른 수 있습니다 또는 Xamarin 및 C 코딩 된 모바일 앱\#합니다.</span><span class="sxs-lookup"><span data-stu-id="fc28d-117">It will be different if you are validating data in a web MVC web application with most of the code in .NET, an SPA web application with that validation being coded in JavaScript or TypeScript, or a mobile app coded with Xamarin and C\#.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fc28d-118">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="fc28d-118">Additional resources</span></span>

### <a name="validation-in-xamarin-mobile-apps"></a><span data-ttu-id="fc28d-119">Xamarin 모바일 앱의 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="fc28d-119">Validation in Xamarin mobile apps</span></span>

-   <span data-ttu-id="fc28d-120">**텍스트 입력 및 표시 한 오류를 유효성 검사**
    [*https://developer.xamarin.com/recipes/ios/standard\_컨트롤/텍스트\_필드/유효성 검사\_입력 /*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span><span class="sxs-lookup"><span data-stu-id="fc28d-120">**Validate Text Input and Show Errors**
[*https://developer.xamarin.com/recipes/ios/standard\_controls/text\_field/validate\_input/*](https://developer.xamarin.com/recipes/ios/standard_controls/text_field/validate_input/)</span></span>

-   <span data-ttu-id="fc28d-121">**유효성 검사 콜백을**
    [*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span><span class="sxs-lookup"><span data-stu-id="fc28d-121">**Validation Callback**
[*https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/*](https://developer.xamarin.com/samples/xamarin-forms/XAML/ValidationCallback/)</span></span>

### <a name="validation-in-aspnet-core-apps"></a><span data-ttu-id="fc28d-122">ASP.NET Core 응용 프로그램에서 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="fc28d-122">Validation in ASP.NET Core apps</span></span>

-   <span data-ttu-id="fc28d-123">**Rick Anderson. 유효성 검사 추가**
    [*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span><span class="sxs-lookup"><span data-stu-id="fc28d-123">**Rick Anderson. Adding validation**
[*https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation*](https://docs.microsoft.com/aspnet/core/tutorials/first-mvc-app/validation)</span></span>

### <a name="validation-in-spa-web-apps-angular-2-typescript-javascript"></a><span data-ttu-id="fc28d-124">SPA에서 유효성 검사 웹 앱 (각도 2, TypeScript JavaScript)</span><span class="sxs-lookup"><span data-stu-id="fc28d-124">Validation in SPA Web apps (Angular 2, TypeScript, JavaScript)</span></span>

-   <span data-ttu-id="fc28d-125">**Ado Kukic 합니다. 유효성 검사를 형성 하는 각도 2** **
     ** [ *https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span><span class="sxs-lookup"><span data-stu-id="fc28d-125">**Ado Kukic. Angular 2 Form Validation** **
**[*https://scotch.io/tutorials/angular-2-form-validation*](https://scotch.io/tutorials/angular-2-form-validation)</span></span>

-   <span data-ttu-id="fc28d-126">**유효성 검사를 형성**
    [*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span><span class="sxs-lookup"><span data-stu-id="fc28d-126">**Form Validation**
[*https://angular.io/docs/ts/latest/cookbook/form-validation.html*](https://angular.io/docs/ts/latest/cookbook/form-validation.html)</span></span>

-   <span data-ttu-id="fc28d-127">**유효성 검사 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fc28d-127">**Validation.**</span></span> <span data-ttu-id="fc28d-128">간편 설명서입니다.</span><span class="sxs-lookup"><span data-stu-id="fc28d-128">Breeze documentation.</span></span>
    [<span data-ttu-id="fc28d-129">*http://breeze.github.io/doc-js/validation.html*</span><span class="sxs-lookup"><span data-stu-id="fc28d-129">*http://breeze.github.io/doc-js/validation.html*</span></span>](http://breeze.github.io/doc-js/validation.html)

<span data-ttu-id="fc28d-130">요약 하면, 다음은 유효성 검사 시에서 가장 중요 한 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="fc28d-130">In summary, these are the most important concepts in regards to validation:</span></span>

-   <span data-ttu-id="fc28d-131">엔터티 및 집계 자신의 일관성을 유지 하 고 "항상 유효" 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc28d-131">Entities and aggregates should enforce their own consistency and be "always valid”.</span></span> <span data-ttu-id="fc28d-132">집계 루트 같은 집계 내에서 다중 엔터티 일관성에 대 한 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc28d-132">Aggregate roots are responsible for multi-entity consistency within the same aggregate.</span></span>

-   <span data-ttu-id="fc28d-133">엔터티를 잘못 된 상태를 입력 해야 함을 생각 되 면 다양 한 개체 모델 사용을 고려-최종 도메인 엔터티를 만들 때까지 임시 DTO을 사용 하 여 예를 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc28d-133">If you think that an entity needs to enter an invalid state, consider using a different object model—for example, using a temporary DTO until you create the final domain entity.</span></span>

-   <span data-ttu-id="fc28d-134">집계 함수 등의 여러 관련된 개체를 만들어야 하는 경우만 유효 모두 만든 팩터리 패턴을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fc28d-134">If you need to create several related objects, such as an aggregate, and they are only valid once all of them have been created, consider using the Factory pattern.</span></span>

-   <span data-ttu-id="fc28d-135">유효성 검사 프레임 워크는는 인프라 프레임 워크에 의존 강력한 해야 하기 때문에 가장 프레젠테이션 계층 또는 응용 프로그램/서비스 계층과 같은 특정 계층에 있지만 도메인 모델 계층에 없는 일반적으로 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc28d-135">Validation frameworks are best used in specific layers, such as the presentation layer or the application/service layer, but usually not in the domain model layer, because you would need to take a strong dependency on an infrastructure framework.</span></span>

-   <span data-ttu-id="fc28d-136">대부분의 경우에 클라이언트 쪽에 중복 유효성 검사 하는 것은 적절 한 경우 응용 프로그램은 사전 수 있기 때문에 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc28d-136">In most of the cases, having redundant validation in the client side is good, because the application can be proactive.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="fc28d-137">[이전] (도메인-모델-계층-validations.md) [다음] (도메인-이벤트-디자인-implementation.md)</span><span class="sxs-lookup"><span data-stu-id="fc28d-137">[Previous] (domain-model-layer-validations.md) [Next] (domain-events-design-implementation.md)</span></span>
