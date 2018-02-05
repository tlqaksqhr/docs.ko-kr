---
title: "공용 형식 시스템 및 공용 언어 사양"
description: "CTS(공용 형식 시스템) 및 CLS(공용 언어 사양)를 사용하여 .NET이 여러 언어를 지원할 수 있도록 하는 방법을 알아봅니다."
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: 3b1f5725-ac94-4f17-8e5f-244442438a4d
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d7626b0a6a902465416187b2c09d624dfe9a9773
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="common-type-system--common-language-specification"></a><span data-ttu-id="87130-104">공용 형식 시스템 및 공용 언어 사양</span><span class="sxs-lookup"><span data-stu-id="87130-104">Common Type System & Common Language Specification</span></span>

<span data-ttu-id="87130-105">두 용어는 .NET 환경에서 자유롭게 사용되지만, 실제로 .NET 구현에서 어떻게 다중 언어 개발을 사용할 수 있고 어떻게 작동하는지 이해하는 데 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="87130-105">Again, two terms that are freely used in the .NET world, they actually are crucial to understand how a .NET implementation enables multi-language development and to understand how it works.</span></span>

## <a name="common-type-system"></a><span data-ttu-id="87130-106">공용 형식 시스템</span><span class="sxs-lookup"><span data-stu-id="87130-106">Common Type System</span></span>

<span data-ttu-id="87130-107">먼저 .NET 구현이 _언어 독립적_임에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="87130-107">To start from the beginning, remember that a .NET implementation is _language agnostic_.</span></span> <span data-ttu-id="87130-108">단순히 프로그래머가 IL로 컴파일할 수 있는 모든 언어로 코드를 작성할 수 있다는 의미는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="87130-108">This doesn’t just mean that a programmer can write her code in any language that can be compiled to IL.</span></span> <span data-ttu-id="87130-109">이는 프로그래머가 .NET 구현에서 사용할 수 있는 다른 언어로 작성된 코드를 조작할 수 있어야 함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="87130-109">It also means that she needs to be able to interact with code written in other languages that are able to be used on a .NET implementation.</span></span>

<span data-ttu-id="87130-110">이 작업을 투명하게 수행하려면 지원되는 모든 형식을 설명하는 일반적인 방법이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87130-110">In order to do this transparently, there has to be a common way to describe all supported types.</span></span> <span data-ttu-id="87130-111">이 역할을 담당하는 것이 CTS(공용 형식 시스템)입니다.</span><span class="sxs-lookup"><span data-stu-id="87130-111">This is what the Common Type System (CTS) is in charge of doing.</span></span> <span data-ttu-id="87130-112">CTS는 다음과 같은 몇 가지 작업을 수행하도록 작성되었습니다.</span><span class="sxs-lookup"><span data-stu-id="87130-112">It was made to do several things:</span></span>

*   <span data-ttu-id="87130-113">언어 간 실행을 위한 프레임워크를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="87130-113">Establish a framework for cross-language execution.</span></span>
*   <span data-ttu-id="87130-114">.NET 구현에서 다양한 언어 구현을 지원하는 개체 지향 모델을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="87130-114">Provide an object-oriented model to support implementing various languages on a .NET implementation.</span></span>
*   <span data-ttu-id="87130-115">형식으로 작업할 때 모든 언어가 따라야 하는 규칙 집합을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="87130-115">Define a set of rules that all languages must follow when it comes to working with types.</span></span>
*   <span data-ttu-id="87130-116">응용 프로그램 개발에 사용되는 기본 형식(즉, `Boolean`, `Byte`, `Char` 등)이 포함된 라이브러리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="87130-116">Provide a library that contains the basic primitive types that are used in application development (such as, `Boolean`, `Byte`, `Char` etc.)</span></span>

<span data-ttu-id="87130-117">CTS는 지원해야 하는 두 가지 종류의 형식, 즉 참조와 값 형식을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="87130-117">CTS defines two main kinds of types that should be supported: reference and value types.</span></span> <span data-ttu-id="87130-118">해당 이름이 정의를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="87130-118">Their names point to their definitions.</span></span>

<span data-ttu-id="87130-119">참조 형식의 개체는 개체의 실제 값에 대한 참조로 표시됩니다. 여기서 참조는 C/C++의 포인터와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="87130-119">Reference types’ objects are represented by a reference to the object’s actual value; a reference here is similar to a pointer in C/C++.</span></span> <span data-ttu-id="87130-120">단순히 개체의 값이 있는 메모리 위치를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="87130-120">It simply refers to a memory location where the objects’ values are.</span></span> <span data-ttu-id="87130-121">이는 이러한 형식의 사용 방법에 큰 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87130-121">This has a profound impact on how these types are used.</span></span> <span data-ttu-id="87130-122">예를 들어 변수에 참조 형식을 할당한 다음 해당 변수를 메서드에 전달하는 경우 개체의 변경 내용이 주 개체에 반영됩니다. 복사 작업이 수행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87130-122">If you assign a reference type to a variable and then pass that variable into a method, for instance, any changes to the object will be reflected on the main object; there is no copying.</span></span>

<span data-ttu-id="87130-123">값 형식은 그 반대이며, 개체가 해당 값으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="87130-123">Value types are the opposite, where the objects are represented by their values.</span></span> <span data-ttu-id="87130-124">변수에 값 형식을 할당하는 경우 기본적으로 개체의 값이 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="87130-124">If you assign a value type to a variable, you are essentially copying a value of the object.</span></span>

<span data-ttu-id="87130-125">CTS는 각각 특정 의미 체계와 사용법이 있는 여러 형식 범주를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="87130-125">CTS defines several categories of types, each with their specific semantics and usage:</span></span>

*   <span data-ttu-id="87130-126">클래스</span><span class="sxs-lookup"><span data-stu-id="87130-126">Classes</span></span>
*   <span data-ttu-id="87130-127">구조체</span><span class="sxs-lookup"><span data-stu-id="87130-127">Structures</span></span>
*   <span data-ttu-id="87130-128">열거형</span><span class="sxs-lookup"><span data-stu-id="87130-128">Enums</span></span>
*   <span data-ttu-id="87130-129">인터페이스</span><span class="sxs-lookup"><span data-stu-id="87130-129">Interfaces</span></span>
*   <span data-ttu-id="87130-130">대리자</span><span class="sxs-lookup"><span data-stu-id="87130-130">Delegates</span></span>

<span data-ttu-id="87130-131">CTS는 액세스 한정자, 유효한 형식 멤버, 상속 및 오버로드 작동 방식 등 형식의 다른 모든 속성도 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="87130-131">CTS also defines all other properties of the types, such as access modifiers, what are valid type members, how inheritance and overloading works and so on.</span></span> <span data-ttu-id="87130-132">이러한 내용에 대한 자세한 설명은 이 기초 문서의 범위를 벗어나지만 끝에 있는 [추가 리소스](#more-resources) 섹션에서 해당 항목을 다루는 자세한 콘텐츠의 링크를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87130-132">Unfortunately, going deep into any of those is beyond the scope of an introductory article such as this, but you can consult [More resources](#more-resources) section at the end for links to more in-depth content that covers these topics.</span></span>

## <a name="common-language-specification"></a><span data-ttu-id="87130-133">공용 언어 사양</span><span class="sxs-lookup"><span data-stu-id="87130-133">Common Language Specification</span></span>

<span data-ttu-id="87130-134">완전한 상호 운용성 시나리오를 사용하려면 코드로 만든 모든 개체가 이 개체(및 해당 _호출자_)를 사용하는 언어에서 몇 가지 공통점을 가지고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87130-134">To enable full interoperability scenarios, all objects that are created in code must rely on some commonality in the languages that are consuming them (are their _callers_).</span></span> <span data-ttu-id="87130-135">다양한 언어가 있으므로 .NET 구현은 CLS(**공용 언어 사양**)에서 이러한 공통점을 지정했습니다.</span><span class="sxs-lookup"><span data-stu-id="87130-135">Since there are numerous different languages, .NET has specified those commonalities in something called the **Common Language Specification** (CLS).</span></span> <span data-ttu-id="87130-136">CLS는 일반적인 여러 응용 프로그램에 필요한 기능 집합을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="87130-136">CLS defines a set of features that are needed by many common applications.</span></span> <span data-ttu-id="87130-137">또한 .NET 구현을 기반으로 하여 구현된 모든 언어에서 지원해야 하는 사항에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="87130-137">It also provides a sort of recipe for any language that is implemented on top of .NET on what it needs to support.</span></span>

<span data-ttu-id="87130-138">CLS는 CTS의 하위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="87130-138">CLS is a subset of the CTS.</span></span> <span data-ttu-id="87130-139">즉, CLS 규칙이 더 엄격한 경우가 아니면 CTS의 모든 규칙이 CLS에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="87130-139">This means that all of the rules in the CTS also apply to the CLS, unless the CLS rules are more strict.</span></span> <span data-ttu-id="87130-140">CLS의 규칙만 사용하여 구성 요소가 빌드된 경우 해당 API에 CLS 기능만 표시되며 **CLS 규격**이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="87130-140">If a component is built using only the rules in the CLS, that is, it exposes only the CLS features in its API, it is said to be **CLS-compliant**.</span></span> <span data-ttu-id="87130-141">예를 들어 `<framework-librares>`는 .NET 구현에서 지원되는 모든 언어에서 작동해야 하므로 정확히 CLS 규격입니다.</span><span class="sxs-lookup"><span data-stu-id="87130-141">For instance, the `<framework-librares>` are CLS-compliant precisely because they need to work across all of the languages that are supported on .NET.</span></span>

<span data-ttu-id="87130-142">아래 [추가 리소스](#more-resources) 섹션의 문서를 통해 CLS의 모든 기능에 대한 개요를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87130-142">You can consult the documents in the [More Resources](#more-resources) section below to get an overview of all the features in the CLS.</span></span>

## <a name="more-resources"></a><span data-ttu-id="87130-143">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="87130-143">More resources</span></span>

*   [<span data-ttu-id="87130-144">공용 형식 시스템</span><span class="sxs-lookup"><span data-stu-id="87130-144">Common Type System</span></span>](./base-types/common-type-system.md)
*   [<span data-ttu-id="87130-145">공용 언어 사양</span><span class="sxs-lookup"><span data-stu-id="87130-145">Common Language Specification</span></span>](language-independence-and-language-independent-components.md)
