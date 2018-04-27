---
title: 인터페이스 디자인
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 8636653ca856693961cbfc73e9170410ed2cd361
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="interface-design"></a><span data-ttu-id="b29ad-102">인터페이스 디자인</span><span class="sxs-lookup"><span data-stu-id="b29ad-102">Interface Design</span></span>
<span data-ttu-id="b29ad-103">대부분의 Api는 클래스 및 구조체를 사용 하 여 모델링 가장 있지만 사례를 인터페이스 보다 적절 한 파일이 나 옵션만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b29ad-103">Although most APIs are best modeled using classes and structs, there are cases in which interfaces are more appropriate or are the only option.</span></span>  
  
 <span data-ttu-id="b29ad-104">CLR 다중 상속을 지원 하지 않습니다 (즉, CLR 클래스에서에서 상속할 수 없습니다 둘 이상의 기본 클래스), 하지만 기본 클래스에서 상속 하는 것 외에도 하나 이상의 인터페이스를 구현할 형식 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b29ad-104">The CLR does not support multiple inheritance (i.e., CLR classes cannot inherit from more than one base class), but it does allow types to implement one or more interfaces in addition to inheriting from a base class.</span></span> <span data-ttu-id="b29ad-105">따라서 여러 상속 결과를 얻을 인터페이스가 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b29ad-105">Therefore, interfaces are often used to achieve the effect of multiple inheritance.</span></span> <span data-ttu-id="b29ad-106">예를 들어 <xref:System.IDisposable> disposability 독립적으로 참여 해야 할 다른 상속 계층을 지원 하기 위한 형식을 허용 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b29ad-106">For example, <xref:System.IDisposable> is an interface that allows types to support disposability independent of any other inheritance hierarchy in which they want to participate.</span></span>  
  
 <span data-ttu-id="b29ad-107">인터페이스는 적절 한 정의 다른 상황에서 일부 값 형식은 같은 여러 형식을 지원할 수 있는 공통 인터페이스를 만드는 중인 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b29ad-107">The other situation in which defining an interface is appropriate is in creating a common interface that can be supported by several types, including some value types.</span></span> <span data-ttu-id="b29ad-108">값 형식 이외의 형식에서 상속할 수 없습니다 <xref:System.ValueType>, 인터페이스를 구현할 수 있지만, 일반적인 기본 형식을 제공 하기 위해 유일한 옵션은 인터페이스를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29ad-108">Value types cannot inherit from types other than <xref:System.ValueType>, but they can implement interfaces, so using an interface is the only option in order to provide a common base type.</span></span>  
  
 <span data-ttu-id="b29ad-109">**✓ 않습니다** 값 형식을 포함 하는 형식의 집합 지원을 받기 위해 일부 공통 API 해야 하는 경우 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29ad-109">**✓ DO** define an interface if you need some common API to be supported by a set of types that includes value types.</span></span>  
  
 <span data-ttu-id="b29ad-110">**✓ 고려** 이미 다른 형식에서 상속 되는 형식에서 해당 기능을 지 원하는 데 필요한 경우 인터페이스를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29ad-110">**✓ CONSIDER** defining an interface if you need to support its functionality on types that already inherit from some other type.</span></span>  
  
 <span data-ttu-id="b29ad-111">**하지 말고 X** 표식 인터페이스 (멤버 없이 인터페이스)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29ad-111">**X AVOID** using marker interfaces (interfaces with no members).</span></span>  
  
 <span data-ttu-id="b29ad-112">클래스 (표식) 특정 특성을 가진 것으로 표시 해야 할 경우 일반적으로 사용 하 여 인터페이스가 아닌 사용자 지정 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="b29ad-112">If you need to mark a class as having a specific characteristic (marker), in general, use a custom attribute rather than an interface.</span></span>  
  
 <span data-ttu-id="b29ad-113">**✓ 않습니다** 인터페이스의 구현 하는 하나 이상의 형식을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29ad-113">**✓ DO** provide at least one type that is an implementation of an interface.</span></span>  
  
 <span data-ttu-id="b29ad-114">이 사용이 하면 인터페이스의 디자인 유효성 검사를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29ad-114">Doing this helps to validate the design of the interface.</span></span> <span data-ttu-id="b29ad-115">예를 들어 <xref:System.Collections.Generic.List%601> 는의 구현에서 <xref:System.Collections.Generic.IList%601> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b29ad-115">For example, <xref:System.Collections.Generic.List%601> is an implementation of the <xref:System.Collections.Generic.IList%601> interface.</span></span>  
  
 <span data-ttu-id="b29ad-116">**✓ 않습니다** 정의 하는 각 인터페이스를 사용 하는 하나 이상의 API를 제공 (매개 변수 또는 속성으로 인터페이스 하는 메서드는 인터페이스와 입력).</span><span class="sxs-lookup"><span data-stu-id="b29ad-116">**✓ DO** provide at least one API that consumes each interface you define (a method taking the interface as a parameter or a property typed as the interface).</span></span>  
  
 <span data-ttu-id="b29ad-117">이 사용이 하면 인터페이스 디자인 유효성 검사를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29ad-117">Doing this helps to validate the interface design.</span></span> <span data-ttu-id="b29ad-118">예를 들어 <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> 소비는 <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b29ad-118">For example, <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> consumes the <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> interface.</span></span>  
  
 <span data-ttu-id="b29ad-119">**X 하지 않으면** 이전에 제공한 하는 인터페이스에 멤버를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29ad-119">**X DO NOT** add members to an interface that has previously shipped.</span></span>  
  
 <span data-ttu-id="b29ad-120">이렇게 하면 인터페이스의 구현 작동 하지 않으므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29ad-120">Doing so would break implementations of the interface.</span></span> <span data-ttu-id="b29ad-121">버전 관리 문제를 방지 하기 위해 새 인터페이스를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29ad-121">You should create a new interface in order to avoid versioning problems.</span></span>  
  
 <span data-ttu-id="b29ad-122">이러한 지침에 설명 된 경우를 제외 하 고, 일반적으로 선택 해야 인터페이스 대신 클래스에 관리 되는 코드 재사용 가능한 라이브러리 디자인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29ad-122">Except for the situations described in these guidelines, you should, in general, choose classes rather than interfaces in designing managed code reusable libraries.</span></span>  
  
 <span data-ttu-id="b29ad-123">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="b29ad-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b29ad-124">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="b29ad-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b29ad-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b29ad-125">See Also</span></span>  
 [<span data-ttu-id="b29ad-126">형식 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="b29ad-126">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="b29ad-127">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="b29ad-127">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
