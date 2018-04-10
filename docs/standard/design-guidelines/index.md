---
title: 프레임워크 디자인 지침
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- libraries, .NET Framework class library
- class library design guidelines [.NET Framework], about
- class library design guidelines [.NET Framework]
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
caps.latest.revision: 14
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c48b3cbaae4155a894ba77263505b2ca85238427
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="framework-design-guidelines"></a><span data-ttu-id="00785-102">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="00785-102">Framework Design Guidelines</span></span>
<span data-ttu-id="00785-103">이 섹션을 확장 하 고.NET Framework와 상호 작용 하는 라이브러리를 디자인 하기 위한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="00785-103">This section provides guidelines for designing libraries that extend and interact with the .NET Framework.</span></span> <span data-ttu-id="00785-104">목표를 통합된 프로그래밍 모델 개발에 사용 되는 프로그래밍 언어와 독립적을 제공 하 여의 사용 편이성과 API 일관성을 확인 하는 라이브러리 디자이너 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00785-104">The goal is to help library designers ensure API consistency and ease of use by providing a unified programming model that is independent of the programming language used for development.</span></span> <span data-ttu-id="00785-105">클래스와.NET Framework를 확장 하는 구성 요소를 개발 하는 경우 이러한 지침을 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="00785-105">We recommend that you follow these design guidelines when developing classes and components that extend the .NET Framework.</span></span> <span data-ttu-id="00785-106">일관성 없는 라이브러리 부정적인 개발자 생산성에 영향을 줍니다 디자인과 채택 하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="00785-106">Inconsistent library design adversely affects developer productivity and discourages adoption.</span></span>  
  
 <span data-ttu-id="00785-107">지침 내용 접두어로 추가 되는 간단한 권장 사항을으로 구성 됩니다 `Do`, `Consider`, `Avoid`, 및 `Do not`합니다.</span><span class="sxs-lookup"><span data-stu-id="00785-107">The guidelines are organized as simple recommendations prefixed with the terms `Do`, `Consider`, `Avoid`, and `Do not`.</span></span> <span data-ttu-id="00785-108">이러한 지침 클래스 라이브러리 디자이너 여러 솔루션 간의 장단점을 이해를 돕기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="00785-108">These guidelines are intended to help class library designers understand the trade-offs between different solutions.</span></span> <span data-ttu-id="00785-109">올바른 라이브러리 디자인 이러한 지침을 위반가 필요로 하는 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="00785-109">There might be situations where good library design requires that you violate these design guidelines.</span></span> <span data-ttu-id="00785-110">이러한 경우는 드물게 발생 해야 하 고 결정 하는 데는 명확 하 고 매력적인 이유가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="00785-110">Such cases should be rare, and it is important that you have a clear and compelling reason for your decision.</span></span>  
  
 <span data-ttu-id="00785-111">이러한 지침은 책에서 발췌 되었습니다 *Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴*Krzysztof Cwalina 및 Brad Abrams 합니다.</span><span class="sxs-lookup"><span data-stu-id="00785-111">These guidelines are excerpted from the book *Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition*, by Krzysztof Cwalina and Brad Abrams.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="00785-112">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="00785-112">In This Section</span></span>  
 [<span data-ttu-id="00785-113">명명 지침</span><span class="sxs-lookup"><span data-stu-id="00785-113">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 <span data-ttu-id="00785-114">어셈블리, 네임 스페이스, 형식 및 멤버 클래스 라이브러리의 이름 지정에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="00785-114">Provides guidelines for naming assemblies, namespaces, types, and members in class libraries.</span></span>  
  
 [<span data-ttu-id="00785-115">형식 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="00785-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 <span data-ttu-id="00785-116">정적 및 추상 클래스, 인터페이스, 열거형, 구조체 및 기타 형식 사용에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="00785-116">Provides guidelines for using static and abstract classes, interfaces, enumerations, structures, and other types.</span></span>  
  
 [<span data-ttu-id="00785-117">멤버 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="00785-117">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 <span data-ttu-id="00785-118">디자인 하 고 속성, 메서드, 생성자, 필드, 이벤트, 연산자 및 매개 변수를 사용 하 여 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="00785-118">Provides guidelines for designing and using properties, methods, constructors, fields, events, operators, and parameters.</span></span>  
  
 [<span data-ttu-id="00785-119">확장성을 위한 디자인</span><span class="sxs-lookup"><span data-stu-id="00785-119">Designing for Extensibility</span></span>](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 <span data-ttu-id="00785-120">이벤트, 가상 멤버 및 콜백을 사용 하 여 서브클래싱 같은 확장성 메커니즘을 설명 하 고 프레임 워크의 요구 사항에 가장 잘 맞는 하는 메커니즘을 선택 하는 방법에 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="00785-120">Discusses extensibility mechanisms such as subclassing, using events, virtual members, and callbacks, and explains how to choose the mechanisms that best meet your framework's requirements.</span></span>  
  
 [<span data-ttu-id="00785-121">예외 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="00785-121">Design Guidelines for Exceptions</span></span>](../../../docs/standard/design-guidelines/exceptions.md)  
 <span data-ttu-id="00785-122">디자인를 발생 시키는 및 검색 예외에 대 한 디자인 지침을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="00785-122">Describes design guidelines for designing, throwing, and catching exceptions.</span></span>  
  
 [<span data-ttu-id="00785-123">사용 지침</span><span class="sxs-lookup"><span data-stu-id="00785-123">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 <span data-ttu-id="00785-124">공용 형식 배열, 특성, 컬렉션 등을 사용 하 여 직렬화를 지원 하며 같음 연산자를 오버 로드에 대 한 지침을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="00785-124">Describes guidelines for using common types such as arrays, attributes, and collections, supporting serialization, and overloading equality operators.</span></span>  
  
 [<span data-ttu-id="00785-125">일반 디자인 패턴</span><span class="sxs-lookup"><span data-stu-id="00785-125">Common Design Patterns</span></span>](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 <span data-ttu-id="00785-126">선택 하 고 종속성 속성과 dispose 패턴을 구현 하기 위한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="00785-126">Provides guidelines for choosing and implementing dependency properties and the dispose pattern.</span></span>  
  
 <span data-ttu-id="00785-127">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="00785-127">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="00785-128">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="00785-128">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00785-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="00785-129">See Also</span></span>  
 [<span data-ttu-id="00785-130">개요</span><span class="sxs-lookup"><span data-stu-id="00785-130">Overview</span></span>](../../../docs/framework/get-started/overview.md)  
 [<span data-ttu-id="00785-131">.NET Framework에 대 한 로드맵</span><span class="sxs-lookup"><span data-stu-id="00785-131">Roadmap for the .NET Framework</span></span>](http://msdn.microsoft.com/library/0b46b7c6-9163-4f99-8e58-0d1ee7da8c67)  
 [<span data-ttu-id="00785-132">개발 가이드</span><span class="sxs-lookup"><span data-stu-id="00785-132">Development Guide</span></span>](../../../docs/framework/development-guide.md)
