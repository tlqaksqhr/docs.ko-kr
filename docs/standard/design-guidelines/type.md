---
title: 형식 디자인 지침
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: af7511f4159fdbfe2d3f972dc927e9ee11fd586f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572891"
---
# <a name="type-design-guidelines"></a><span data-ttu-id="05fef-102">형식 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="05fef-102">Type Design Guidelines</span></span>
<span data-ttu-id="05fef-103">CLR 관점에서는 두 가지 범주의 형식-참조 형식과 값 형식-하지만 프레임 워크 디자인에 대 한 토론을 목적으로 각각의 특정 디자인 규칙 자체에 더 많은 논리 그룹으로 형식 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="05fef-103">From the CLR perspective, there are only two categories of types—reference types and value types—but for the purpose of a discussion about framework design, we divide types into more logical groups, each with its own specific design rules.</span></span>  
  
 <span data-ttu-id="05fef-104">클래스는 참조 형식의 일반적인 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="05fef-104">Classes are the general case of reference types.</span></span> <span data-ttu-id="05fef-105">대부분의 프레임 워크에 있는 형식의 대량을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="05fef-105">They make up the bulk of types in the majority of frameworks.</span></span> <span data-ttu-id="05fef-106">클래스는 다양 한 개체 지향 기능을 지원 하 고 일반의 적용 가능성 사람들이 미납 합니다.</span><span class="sxs-lookup"><span data-stu-id="05fef-106">Classes owe their popularity to the rich set of object-oriented features they support and to their general applicability.</span></span> <span data-ttu-id="05fef-107">기본 클래스와 추상 클래스는 확장성와 관련 된 특별 한 논리 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="05fef-107">Base classes and abstract classes are special logical groups related to extensibility.</span></span>  
  
 <span data-ttu-id="05fef-108">인터페이스는 참조 형식과 값 형식으로 구현할 수 있는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="05fef-108">Interfaces are types that can be implemented by both reference types and value types.</span></span> <span data-ttu-id="05fef-109">따라서 참조 형식과 값 형식의 다형적 계층의 루트도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05fef-109">They can thus serve as roots of polymorphic hierarchies of reference types and value types.</span></span> <span data-ttu-id="05fef-110">또한 기본적으로 CLR에서 지원 되지 않는 여러 상속을 시뮬레이트하려 인터페이스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05fef-110">In addition, interfaces can be used to simulate multiple inheritance, which is not natively supported by the CLR.</span></span>  
  
 <span data-ttu-id="05fef-111">구조체는 값 형식의 일반적인 경우는 및 언어 기본 형식에서와 유사한 간단한 형식에 대 한 예약 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="05fef-111">Structs are the general case of value types and should be reserved for small, simple types, similar to language primitives.</span></span>  
  
 <span data-ttu-id="05fef-112">열거형은 짧은 집합 주와 콘솔 색 등의 일 등의 값을 정의 하는 데 사용 되는 값 형식의 특별 한 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="05fef-112">Enums are a special case of value types used to define short sets of values, such as days of the week, console colors, and so on.</span></span>  
  
 <span data-ttu-id="05fef-113">정적 클래스는 형식 정적 멤버에 대 한 컨테이너 되도록 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="05fef-113">Static classes are types intended to be containers for static members.</span></span> <span data-ttu-id="05fef-114">일반적으로 다른 작업에 대 한 바로 가기를 제공에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="05fef-114">They are commonly used to provide shortcuts to other operations.</span></span>  
  
 <span data-ttu-id="05fef-115">대리자, 예외, 특성, 배열 및 컬렉션은 특정 용도 위한 참조 형식의 모든 특별 한 경우 및 설계 및 사용에 대 한 지침이이 가이드에서 다른 위치에서 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="05fef-115">Delegates, exceptions, attributes, arrays, and collections are all special cases of reference types intended for specific uses, and guidelines for their design and usage are discussed elsewhere in this book.</span></span>  
  
 <span data-ttu-id="05fef-116">**✓ 않습니다** 각 형식이 관련 되지 않은 기능의 임의 컬렉션 뿐 아니라 관련된 멤버의 잘 정의 된 집합 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="05fef-116">**✓ DO** ensure that each type is a well-defined set of related members, not just a random collection of unrelated functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="05fef-117">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="05fef-117">In This Section</span></span>  
 [<span data-ttu-id="05fef-118">클래스와 구조체 간의 선택</span><span class="sxs-lookup"><span data-stu-id="05fef-118">Choosing Between Class and Struct</span></span>](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [<span data-ttu-id="05fef-119">추상 클래스 디자인</span><span class="sxs-lookup"><span data-stu-id="05fef-119">Abstract Class Design</span></span>](../../../docs/standard/design-guidelines/abstract-class.md)  
 [<span data-ttu-id="05fef-120">정적 클래스 디자인</span><span class="sxs-lookup"><span data-stu-id="05fef-120">Static Class Design</span></span>](../../../docs/standard/design-guidelines/static-class.md)  
 [<span data-ttu-id="05fef-121">인터페이스 디자인</span><span class="sxs-lookup"><span data-stu-id="05fef-121">Interface Design</span></span>](../../../docs/standard/design-guidelines/interface.md)  
 [<span data-ttu-id="05fef-122">구조체 디자인</span><span class="sxs-lookup"><span data-stu-id="05fef-122">Struct Design</span></span>](../../../docs/standard/design-guidelines/struct.md)  
 [<span data-ttu-id="05fef-123">열거형 디자인</span><span class="sxs-lookup"><span data-stu-id="05fef-123">Enum Design</span></span>](../../../docs/standard/design-guidelines/enum.md)  
 [<span data-ttu-id="05fef-124">중첩 형식</span><span class="sxs-lookup"><span data-stu-id="05fef-124">Nested Types</span></span>](../../../docs/standard/design-guidelines/nested-types.md)  
 <span data-ttu-id="05fef-125">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="05fef-125">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="05fef-126">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="05fef-126">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05fef-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05fef-127">See Also</span></span>  
 [<span data-ttu-id="05fef-128">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="05fef-128">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
