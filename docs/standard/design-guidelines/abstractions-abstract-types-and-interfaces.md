---
title: 추상화(추상 형식 및 인터페이스)
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], abstract
- abstract interfaces [.NET Framework]
- abstract types [.NET Framework]
- types [.NET Framework], abstract
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f5863b4ae9cad940e4dd47ef93e07763916427f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573028"
---
# <a name="abstractions-abstract-types-and-interfaces"></a><span data-ttu-id="0c118-102">추상화(추상 형식 및 인터페이스)</span><span class="sxs-lookup"><span data-stu-id="0c118-102">Abstractions (Abstract Types and Interfaces)</span></span>
<span data-ttu-id="0c118-103">추상화 형식이 하는 계약에 설명 하지만 계약의 전체 구현을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c118-103">An abstraction is a type that describes a contract but does not provide a full implementation of the contract.</span></span> <span data-ttu-id="0c118-104">추상화는 일반적으로 추상 클래스 또는 인터페이스를 구현 하 고 참조 설명서는 계약을 구현 하는 형식의 필요한 의미 체계를 설명 하는 잘 정의 된 집합이 함께 제공 되 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c118-104">Abstractions are usually implemented as abstract classes or interfaces, and they come with a well-defined set of reference documentation describing the required semantics of the types implementing the contract.</span></span> <span data-ttu-id="0c118-105">.NET Framework의 가장 중요 한 추상화 같습니다 <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, 및 <xref:System.Object>합니다.</span><span class="sxs-lookup"><span data-stu-id="0c118-105">Some of the most important abstractions in the .NET Framework include <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, and <xref:System.Object>.</span></span>  
  
 <span data-ttu-id="0c118-106">추상화의 계약을 지 원하는 구체적인 형식이 구현 하 고 프레임 워크 Api 사용 (작동) 함께 구체적인이 형식을 사용 하 여 프레임 워크를 확장할 수 있습니다는 추상화입니다.</span><span class="sxs-lookup"><span data-stu-id="0c118-106">You can extend frameworks by implementing a concrete type that supports the contract of an abstraction and using this concrete type with framework APIs consuming (operating on) the abstraction.</span></span>  
  
 <span data-ttu-id="0c118-107">테스트 시간의 영향을 받지 않을 수 있는 의미 있는 고 유용한 추상화를 디자인 하기 매우 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="0c118-107">A meaningful and useful abstraction that is able to withstand the test of time is very difficult to design.</span></span> <span data-ttu-id="0c118-108">주요 문제는 올바른 집합의 멤버를 더 이상 및 더 적은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0c118-108">The main difficulty is getting the right set of members, no more and no fewer.</span></span> <span data-ttu-id="0c118-109">추상화에 너무 많은 멤버가 어렵거나도 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c118-109">If an abstraction has too many members, it becomes difficult or even impossible to implement.</span></span> <span data-ttu-id="0c118-110">약속 한 기능에 대 한 너무 적은 멤버에 많은 관심 있는 시나리오에서 의미가 없습니다 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c118-110">If it has too few members for the promised functionality, it becomes useless in many interesting scenarios.</span></span>  
  
 <span data-ttu-id="0c118-111">너무 많은 추상화는 프레임 워크에도 부정적인 영향을 프레임 워크의 유용성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c118-111">Too many abstractions in a framework also negatively affect usability of the framework.</span></span> <span data-ttu-id="0c118-112">구체적인 구현 및 추상화에 대 한 작동 Api의 큰 그림에 맞춰지는 방법은 알 수 없는 추상화를 이해 하기 매우 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="0c118-112">It is often quite difficult to understand an abstraction without understanding how it fits into the larger picture of the concrete implementations and the APIs operating on the abstraction.</span></span> <span data-ttu-id="0c118-113">또한 추상화 및 해당 멤버의 이름이 종종을 사용 하면 암호화 되어 차갑고 용도의 다양 한 상황을 이해 하지 않고으로 반드시 추상있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0c118-113">Also, names of abstractions and their members are necessarily abstract, which often makes them cryptic and unapproachable without first understanding the broader context of their usage.</span></span>  
  
 <span data-ttu-id="0c118-114">그러나 추상화는 다른 확장성 메커니즘 일치할 수 없습니다 종종 매우 강력한 확장성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c118-114">However, abstractions provide extremely powerful extensibility that the other extensibility mechanisms cannot often match.</span></span> <span data-ttu-id="0c118-115">제어 (IoC), 파이프라인, 및 등의 inversion 플러그 인과 같은 많은 아키텍처 패턴의 핵심 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0c118-115">They are at the core of many architectural patterns, such as plug-ins, inversion of control (IoC), pipelines, and so on.</span></span> <span data-ttu-id="0c118-116">프레임 워크의 테스트 용이성에 매우 중요 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0c118-116">They are also extremely important for testability of frameworks.</span></span> <span data-ttu-id="0c118-117">좋은 추상화는 단위 테스트 목적으로 많은 종속성을 삭제할 수 있도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c118-117">Good abstractions make it possible to stub out heavy dependencies for the purpose of unit testing.</span></span> <span data-ttu-id="0c118-118">요약 하자면, 추상화가 현대적인 개체 지향 프레임 워크의 반가운 풍부한 기능을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c118-118">In summary, abstractions are responsible for the sought-after richness of the modern object-oriented frameworks.</span></span>  
  
 <span data-ttu-id="0c118-119">**X DO NOT** 여러 구체적인 구현 및 Api를 사용 하는 추상화를 개발 하 여 테스트 하지 않는 한 추상화를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c118-119">**X DO NOT** provide abstractions unless they are tested by developing several concrete implementations and APIs consuming the abstractions.</span></span>  
  
 <span data-ttu-id="0c118-120">**✓ DO** 추상화를 디자인할 때, 추상 클래스와 인터페이스를 신중 하 게 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c118-120">**✓ DO** choose carefully between an abstract class and an interface when designing an abstraction.</span></span>  
  
 <span data-ttu-id="0c118-121">**✓ CONSIDER** 추상화의 구체적인 구현에 대 한 참조 테스트를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c118-121">**✓ CONSIDER** providing reference tests for concrete implementations of abstractions.</span></span> <span data-ttu-id="0c118-122">이러한 테스트는 구현 계약을 올바르게 구현 하는지 테스트 하려면 사용자가 허용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0c118-122">Such tests should allow users to test whether their implementations correctly implement the contract.</span></span>  
  
 <span data-ttu-id="0c118-123">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="0c118-123">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="0c118-124">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="0c118-124">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c118-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0c118-125">See Also</span></span>  
 [<span data-ttu-id="0c118-126">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="0c118-126">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="0c118-127">확장성을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="0c118-127">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
