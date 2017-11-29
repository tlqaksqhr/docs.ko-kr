---
title: "봉인"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- limiting extensibility
- classes [.NET Framework], sealing
- preventing customization
- sealed classes
ms.assetid: cc42267f-bb7a-427a-845e-df97408528d4
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8caa253a3f17c58f542317de579c4f7832c4efac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="sealing"></a><span data-ttu-id="6bad7-102">봉인</span><span class="sxs-lookup"><span data-stu-id="6bad7-102">Sealing</span></span>
<span data-ttu-id="6bad7-103">개체 지향 프레임 워크의 기능 중 하나는 개발자가 확장 하 고 프레임 워크 디자이너에서 예기치 않은 방식으로 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-103">One of the features of object-oriented frameworks is that developers can extend and customize them in ways unanticipated by the framework designers.</span></span> <span data-ttu-id="6bad7-104">이 기능과 확장 가능한 디자인의 위험 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-104">This is both the power and danger of extensible design.</span></span> <span data-ttu-id="6bad7-105">사용자 프레임 워크를 디자인할 때 즉,이 필요한 경우 확장성을 위해 신중 하 게 디자인 하 고는 것은 위험 확장성을 제한할 매우 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-105">When you design your framework, it is, therefore, very important to carefully design for extensibility when it is desired, and to limit extensibility when it is dangerous.</span></span>  
  
 <span data-ttu-id="6bad7-106">확장성을 방해 하는 강력한 메커니즘을 봉인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-106">A powerful mechanism that prevents extensibility is sealing.</span></span> <span data-ttu-id="6bad7-107">클래스 또는 개별 멤버 봉인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-107">You can seal either the class or individual members.</span></span> <span data-ttu-id="6bad7-108">클래스 사용자를 클래스에서 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-108">Sealing a class prevents users from inheriting from the class.</span></span> <span data-ttu-id="6bad7-109">멤버를 봉인 사용자를에서 특정 멤버를 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-109">Sealing a member prevents users from overriding a particular member.</span></span>  
  
 <span data-ttu-id="6bad7-110">**X 하지 않으면** 이유가 할 필요 없이 클래스를 봉인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-110">**X DO NOT** seal classes without having a good reason to do so.</span></span>  
  
 <span data-ttu-id="6bad7-111">확장성 시나리오를 생각할 수 때문에 클래스를 봉인 아닌 경우 하는 이유</span><span class="sxs-lookup"><span data-stu-id="6bad7-111">Sealing a class because you cannot think of an extensibility scenario is not a good reason.</span></span> <span data-ttu-id="6bad7-112">프레임 워크 사용자 편의 멤버를 추가 하는 등 다양 한 nonobvious 이유로 클래스에서 상속 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-112">Framework users like to inherit from classes for various nonobvious reasons, like adding convenience members.</span></span> <span data-ttu-id="6bad7-113">참조 [봉인 되지 않은 클래스](../../../docs/standard/design-guidelines/unsealed-classes.md) nonobvious 대 한 예에 대 한 사용자 확인 하려는 형식에서 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-113">See [Unsealed Classes](../../../docs/standard/design-guidelines/unsealed-classes.md) for examples of nonobvious reasons users want to inherit from a type.</span></span>  
  
 <span data-ttu-id="6bad7-114">클래스에 대 한 좋은 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-114">Good reasons for sealing a class include the following:</span></span>  
  
-   <span data-ttu-id="6bad7-115">클래스는 정적 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-115">The class is a static class.</span></span> <span data-ttu-id="6bad7-116">참조 [정적 클래스 디자인](../../../docs/standard/design-guidelines/static-class.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-116">See [Static Class Design](../../../docs/standard/design-guidelines/static-class.md).</span></span>  
  
-   <span data-ttu-id="6bad7-117">클래스 상속 된 보호 된 멤버에 중요 한 보안 암호를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-117">The class stores security-sensitive secrets in inherited protected members.</span></span>  
  
-   <span data-ttu-id="6bad7-118">많은 가상 멤버를 상속 하는 클래스 및 봉인의 개별적으로 비용에는 봉인 되지 않은 클래스를 끝낼 이점 보다 높을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-118">The class inherits many virtual members and the cost of sealing them individually would outweigh the benefits of leaving the class unsealed.</span></span>  
  
-   <span data-ttu-id="6bad7-119">클래스에는 매우 빠른 런타임 조회를 필요로 하는 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-119">The class is an attribute that requires very fast runtime look-up.</span></span> <span data-ttu-id="6bad7-120">봉인 된 봉인 되지 않은 것 보다 약간 더 높은 성능 수준을 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-120">Sealed attributes have slightly higher performance levels than unsealed ones.</span></span> <span data-ttu-id="6bad7-121">참조 [특성](../../../docs/standard/design-guidelines/attributes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-121">See [Attributes](../../../docs/standard/design-guidelines/attributes.md).</span></span>  
  
 <span data-ttu-id="6bad7-122">**X 하지 않으면** 보호 또는 가상 멤버를 sealed 형식으로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-122">**X DO NOT** declare protected or virtual members on sealed types.</span></span>  
  
 <span data-ttu-id="6bad7-123">기본적으로 sealed 형식에서 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-123">By definition, sealed types cannot be inherited from.</span></span> <span data-ttu-id="6bad7-124">즉, sealed 형식에 대해 보호 된 멤버를 호출할 수 없습니다, 봉인 된 형식에 대 한 가상 메서드를 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-124">This means that protected members on sealed types cannot be called, and virtual methods on sealed types cannot be overridden.</span></span>  
  
 <span data-ttu-id="6bad7-125">**✓ 고려** 재정의할 수 있는 멤버가 봉인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-125">**✓ CONSIDER** sealing members that you override.</span></span>  
  
 <span data-ttu-id="6bad7-126">가상 멤버 소개에서 발생할 수 있는 문제 (에 설명 된 [가상 멤버](../../../docs/standard/design-guidelines/virtual-members.md)) 있지만에 약간도 재정의를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-126">Problems that can result from introducing virtual members (discussed in [Virtual Members](../../../docs/standard/design-guidelines/virtual-members.md)) apply to overrides as well, although to a slightly lesser degree.</span></span> <span data-ttu-id="6bad7-127">재정의가 봉인 하면 상속 계층 구조에서 해당 시점에서 시작 하는 이러한 문제 로부터 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bad7-127">Sealing an override shields you from these problems starting from that point in the inheritance hierarchy.</span></span>  
  
 <span data-ttu-id="6bad7-128">*일부 © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="6bad7-128">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6bad7-129">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="6bad7-129">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bad7-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6bad7-130">See Also</span></span>  
 [<span data-ttu-id="6bad7-131">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="6bad7-131">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="6bad7-132">확장성을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="6bad7-132">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [<span data-ttu-id="6bad7-133">봉인 되지 않은 클래스</span><span class="sxs-lookup"><span data-stu-id="6bad7-133">Unsealed Classes</span></span>](../../../docs/standard/design-guidelines/unsealed-classes.md)
