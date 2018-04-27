---
title: 특성 1
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
caps.latest.revision: 16
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c169586091f0e7e094e0231f9e247e8907371ec4
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2018
---
# <a name="attributes"></a><span data-ttu-id="22f60-102">특성</span><span class="sxs-lookup"><span data-stu-id="22f60-102">Attributes</span></span>
<span data-ttu-id="22f60-103"><xref:System.Attribute?displayProperty=nameWithType> 기본 클래스 사용자 지정 특성을 정의 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-103"><xref:System.Attribute?displayProperty=nameWithType> is a base class used to define custom attributes.</span></span>  
  
 <span data-ttu-id="22f60-104">특성은 어셈블리, 형식, 멤버 및 매개 변수 같은 프로그래밍 요소에 추가할 수 있는 주석입니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-104">Attributes are annotations that can be added to programming elements such as assemblies, types, members, and parameters.</span></span> <span data-ttu-id="22f60-105">이러한 어셈블리의 메타 데이터에 저장 되 고 리플렉션 Api를 사용 하 여 런타임에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-105">They are stored in the metadata of the assembly and can be accessed at runtime using the reflection APIs.</span></span> <span data-ttu-id="22f60-106">예를 들어 프레임 워크 정의 <xref:System.ObsoleteAttribute>, 하는 형식 또는 멤버는 형식 또는 멤버가 사용 되지 않습니다 나타냅니다에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-106">For example, the Framework defines the <xref:System.ObsoleteAttribute>, which can be applied to a type or a member to indicate that the type or member has been deprecated.</span></span>  
  
 <span data-ttu-id="22f60-107">특성에는 특성과 관련 된 추가 데이터를 전송 하는 하나 이상의 속성이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-107">Attributes can have one or more properties that carry additional data related to the attribute.</span></span> <span data-ttu-id="22f60-108">예를 들어 `ObsoleteAttribute` 에 릴리스 하는 방법에 대 한 추가 정보를 수행할 수 사용 되지 않는 API를 바꾸는 새 Api의 설명 및 형식 또는 멤버가 더 이상 사용 되지 (를) 가져왔습니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-108">For example, `ObsoleteAttribute` could carry additional information about the release in which a type or a member got deprecated and the description of the new APIs replacing the obsolete API.</span></span>  
  
 <span data-ttu-id="22f60-109">특성이 적용 될 때 특성의 일부 속성을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-109">Some properties of an attribute must be specified when the attribute is applied.</span></span> <span data-ttu-id="22f60-110">이 라고 필수 속성 또는 필수 인수를 위치 생성자 매개 변수로 나타내므로 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-110">These are referred to as the required properties or required arguments, because they are represented as positional constructor parameters.</span></span> <span data-ttu-id="22f60-111">예를 들어는 <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> 의 속성은 <xref:System.Diagnostics.ConditionalAttribute> 필수 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-111">For example, the <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> property of the <xref:System.Diagnostics.ConditionalAttribute> is a required property.</span></span>  
  
 <span data-ttu-id="22f60-112">반드시 특성이 적용 될 때 지정 해야 하는 속성은 선택적 속성 (또는 선택적 인수) 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-112">Properties that do not necessarily have to be specified when the attribute is applied are called optional properties (or optional arguments).</span></span> <span data-ttu-id="22f60-113">설정 가능한 속성으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-113">They are represented by settable properties.</span></span> <span data-ttu-id="22f60-114">컴파일러는 특성이 적용 될 때 이러한 속성을 설정 하는 특수 한 구문을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-114">Compilers provide special syntax to set these properties when an attribute is applied.</span></span> <span data-ttu-id="22f60-115">예를 들어는 <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> 속성은 선택적 인수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-115">For example, the <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property represents an optional argument.</span></span>  
  
 <span data-ttu-id="22f60-116">**✓ 않습니다** "특성" 접미사를 사용 하 여 사용자 지정 특성 클래스 이름</span><span class="sxs-lookup"><span data-stu-id="22f60-116">**✓ DO** name custom attribute classes with the suffix "Attribute."</span></span>  
  
 <span data-ttu-id="22f60-117">**✓ 않습니다** 적용 된 <xref:System.AttributeUsageAttribute> 사용자 지정 특성에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-117">**✓ DO** apply the <xref:System.AttributeUsageAttribute> to custom attributes.</span></span>  
  
 <span data-ttu-id="22f60-118">**✓ 않습니다** 옵션 인수에 대해 설정 가능한 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-118">**✓ DO** provide settable properties for optional arguments.</span></span>  
  
 <span data-ttu-id="22f60-119">**✓ 않습니다** 필수 인수에 대 한 가져오기 전용 속성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-119">**✓ DO** provide get-only properties for required arguments.</span></span>  
  
 <span data-ttu-id="22f60-120">**✓ 않습니다** 필수 인수에 해당 하는 속성을 초기화할 생성자 매개 변수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-120">**✓ DO** provide constructor parameters to initialize properties corresponding to required arguments.</span></span> <span data-ttu-id="22f60-121">각 매개 변수에 해당 하는 속성으로 (있지만와 서로 다른 대/소문자 구분) 동일한 이름은 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-121">Each parameter should have the same name (although with different casing) as the corresponding property.</span></span>  
  
 <span data-ttu-id="22f60-122">**하지 말고 X** 에 해당 하는 선택적 인수 속성을 초기화할 생성자 매개 변수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-122">**X AVOID** providing constructor parameters to initialize properties corresponding to the optional arguments.</span></span>  
  
 <span data-ttu-id="22f60-123">즉, 생성자 및 setter를 모두 설정할 수 있는 속성이 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-123">In other words, do not have properties that can be set with both a constructor and a setter.</span></span> <span data-ttu-id="22f60-124">이 지침에서는 인수는 선택 사항이 며 더 필요 하 고 동일한 작업을 수행 하는 두 가지는 피할 수 있는 명확히 명시 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-124">This guideline makes very explicit which arguments are optional and which are required, and avoids having two ways of doing the same thing.</span></span>  
  
 <span data-ttu-id="22f60-125">**하지 말고 X** 사용자 지정 특성 생성자 오버 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-125">**X AVOID** overloading custom attribute constructors.</span></span>  
  
 <span data-ttu-id="22f60-126">인수는 필수 및 선택적 사용자에 게 통신 명확 하 게 생성자가 하나만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-126">Having only one constructor clearly communicates to the user which arguments are required and which are optional.</span></span>  
  
 <span data-ttu-id="22f60-127">**✓ 않습니다** 사용자 지정 특성 클래스를 가능 하면 항상 봉인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-127">**✓ DO** seal custom attribute classes, if possible.</span></span> <span data-ttu-id="22f60-128">이렇게 하면 특성에 대 한 조회가 속도가 빨라집니다.</span><span class="sxs-lookup"><span data-stu-id="22f60-128">This makes the look-up for the attribute faster.</span></span>  
  
 <span data-ttu-id="22f60-129">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="22f60-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="22f60-130">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="22f60-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22f60-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="22f60-131">See Also</span></span>  
 [<span data-ttu-id="22f60-132">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="22f60-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="22f60-133">사용 지침</span><span class="sxs-lookup"><span data-stu-id="22f60-133">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
