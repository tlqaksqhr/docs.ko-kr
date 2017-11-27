---
title: "추상화 구현을 위한 기본 클래스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- abstractions [.NET Framework]
- base classes, abstractions
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6c8cd779dba0e7ce559e29af7b16bf04b3d0dc2d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="base-classes-for-implementing-abstractions"></a><span data-ttu-id="ab478-102">추상화 구현을 위한 기본 클래스</span><span class="sxs-lookup"><span data-stu-id="ab478-102">Base Classes for Implementing Abstractions</span></span>
<span data-ttu-id="ab478-103">엄격히 말해서, 클래스는 다른 클래스에서 파생 된 경우 기본 클래스를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab478-103">Strictly speaking, a class becomes a base class when another class is derived from it.</span></span> <span data-ttu-id="ab478-104">그러나이 섹션에서는 목적으로 기본 클래스는 클래스는 일반적인 추상화를 제공 합니다. 또는 일부를 다시 사용 다른 클래스에 대 한 기본 구현을 통해 상속을 주로.</span><span class="sxs-lookup"><span data-stu-id="ab478-104">For the purpose of this section, however, a base class is a class designed mainly to provide a common abstraction or for other classes to reuse some default implementation though inheritance.</span></span> <span data-ttu-id="ab478-105">일반적으로 기본 클래스 추상화 계층의 루트에 맨 아래에 몇 가지 사용자 지정 구현이 사이의 상속 계층 구조 가운데에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab478-105">Base classes usually sit in the middle of inheritance hierarchies, between an abstraction at the root of a hierarchy and several custom implementations at the bottom.</span></span>  
  
 <span data-ttu-id="ab478-106">추상화를 구현 하기 위한 도우미 구현으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab478-106">They serve as implementation helpers for implementing abstractions.</span></span> <span data-ttu-id="ab478-107">예를 들어이 항목의 순서가 지정 된 컬렉션에 대 한 프레임 워크의 추상화 중 하나는 <xref:System.Collections.Generic.IList%601> 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ab478-107">For example, one of the Framework’s abstractions for ordered collections of items is the <xref:System.Collections.Generic.IList%601> interface.</span></span> <span data-ttu-id="ab478-108">구현 <xref:System.Collections.Generic.IList%601> 하며, 하므로 프레임 워크를 제공 몇 가지 기본 클래스와 같은 <xref:System.Collections.ObjectModel.Collection%601> 및 <xref:System.Collections.ObjectModel.KeyedCollection%602>, 사용자 지정 컬렉션을 구현 하기 위한 도우미로 역할입니다.</span><span class="sxs-lookup"><span data-stu-id="ab478-108">Implementing <xref:System.Collections.Generic.IList%601> is not trivial, and therefore the Framework provides several base classes, such as <xref:System.Collections.ObjectModel.Collection%601> and <xref:System.Collections.ObjectModel.KeyedCollection%602>, which serve as helpers for implementing custom collections.</span></span>  
  
 <span data-ttu-id="ab478-109">너무 많은 구현이 포함 경향이 때문에 기본 클래스를 직접 추상화 역할을 적합 하지 일반적으로 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ab478-109">Base classes are usually not suited to serve as abstractions by themselves, because they tend to contain too much implementation.</span></span> <span data-ttu-id="ab478-110">예를 들어는 `Collection<T>` 기본 클래스 구현 제네릭이 아닌을 구현 한다는 사실에 관련 된 많은 포함 `IList` 인터페이스 (제네릭이 아닌 컬렉션을 더 잘 통합) 하 고는 한다는 사실에 항목의 컬렉션에 저장 해당 필드 중 하나에 메모리입니다.</span><span class="sxs-lookup"><span data-stu-id="ab478-110">For example, the `Collection<T>` base class contains lots of implementation related to the fact that it implements the nongeneric `IList` interface (to integrate better with nongeneric collections) and to the fact that it is a collection of items stored in memory in one of its fields.</span></span>  
  
 <span data-ttu-id="ab478-111">앞에서 설명한 대로 기본 클래스 추상화를 구현 해야 하는 사용자에 대 한 중요 한 도움말을 제공할 수 있지만 동시에은 중요 한 문제가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab478-111">As previously discussed, base classes can provide invaluable help for users who need to implement abstractions, but at the same time they can be a significant liability.</span></span> <span data-ttu-id="ab478-112">노출 영역을 추가 상속 계층 구조 깊이 늘고 되 고 있으므로 개념적으로 프레임 워크를 복잡 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab478-112">They add surface area and increase the depth of inheritance hierarchies and so conceptually complicate the framework.</span></span> <span data-ttu-id="ab478-113">따라서 프레임 워크의 사용자에 게 중요 한 가치를 제공 하는 경우에 기본 클래스를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab478-113">Therefore, base classes should be used only if they provide significant value to the users of the framework.</span></span> <span data-ttu-id="ab478-114">기본 클래스에서 상속 하는 대신 내부 구현에 대 한 사례 위임을 강력 하 게 고려해 야 프레임 워크의 구현자에만 값을 제공 하는 경우 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="ab478-114">They should be avoided if they provide value only to the implementers of the framework, in which case delegation to an internal implementation instead of inheritance from a base class should be strongly considered.</span></span>  
  
 <span data-ttu-id="ab478-115">**✓ 고려** 함으로써 기본 추상 멤버가 포함 하지 않는 경우에 추상 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="ab478-115">**✓ CONSIDER** making base classes abstract even if they don’t contain any abstract members.</span></span> <span data-ttu-id="ab478-116">이 명확 하 게 통신 하는 사용자 클래스에서 상속 하는 데에 디자인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab478-116">This clearly communicates to the users that the class is designed solely to be inherited from.</span></span>  
  
 <span data-ttu-id="ab478-117">**✓ 고려** 주요 시나리오 형식에서 별도 네임 스페이스에 기본 클래스를 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab478-117">**✓ CONSIDER** placing base classes in a separate namespace from the mainline scenario types.</span></span> <span data-ttu-id="ab478-118">기본적으로 기본 클래스는 오버 로드는 고급 확장성 시나리오와 따라서는 대부분의 사용자와 관련이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab478-118">By definition, base classes are intended for advanced extensibility scenarios and therefore are not interesting to the majority of users.</span></span>  
  
 <span data-ttu-id="ab478-119">**하지 말고 X** 클래스가 공용 Api에서 사용 하기 위한 경우 "기본" 접미사를 사용 하 여 기본 클래스 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab478-119">**X AVOID** naming base classes with a "Base" suffix if the class is intended for use in public APIs.</span></span>  
  
 <span data-ttu-id="ab478-120">*일부 © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="ab478-120">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ab478-121">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="ab478-121">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab478-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ab478-122">See Also</span></span>  
 [<span data-ttu-id="ab478-123">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="ab478-123">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="ab478-124">확장성을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="ab478-124">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
