---
title: 추상 클래스 디자인
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines, abstract classes
- abstract classes, design guidelines
- class library design guidelines [.NET Framework], classes
- classes [.NET Framework], abstract
- classes [.NET Framework], design guidelines
- type design guidelines, classes
ms.assetid: d3646e6d-5c1f-4922-8fb0-ec5effb30d60
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28052cc6848d77acbdf8e9381146ca6fb06c15d2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570568"
---
# <a name="abstract-class-design"></a><span data-ttu-id="b7cb1-102">추상 클래스 디자인</span><span class="sxs-lookup"><span data-stu-id="b7cb1-102">Abstract Class Design</span></span>
<span data-ttu-id="b7cb1-103">**X 하지 않으면** 추상 형식에 public 또는 protected 내부 생성자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7cb1-103">**X DO NOT** define public or protected internal constructors in abstract types.</span></span>  
  
 <span data-ttu-id="b7cb1-104">생성자는 사용자가이 형식의 인스턴스를 만들 해야 하는 경우에 공용 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7cb1-104">Constructors should be public only if users will need to create instances of the type.</span></span> <span data-ttu-id="b7cb1-105">추상 형식의 인스턴스를 만들 수 없는 공용 생성자를 포함 하는 추상 형식 되므로 없습니다 제대로 디자인 되 고 사용자에 게 잘못 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7cb1-105">Because you cannot create instances of an abstract type, an abstract type with a public constructor is incorrectly designed and misleading to the users.</span></span>  
  
 <span data-ttu-id="b7cb1-106">**✓ 않습니다** 추상 클래스에는 protected 또는 내부 생성자를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7cb1-106">**✓ DO** define a protected or an internal constructor in abstract classes.</span></span>  
  
 <span data-ttu-id="b7cb1-107">Protected 생성자는이 더 일반적 및 단순히 작성 한 하위 유형을 자체 초기화 작업을 수행 하기 위해 기본 클래스를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7cb1-107">A protected constructor is more common and simply allows the base class to do its own initialization when subtypes are created.</span></span>  
  
 <span data-ttu-id="b7cb1-108">클래스를 정의 하는 어셈블리에는 추상 클래스의 구체적 구현 제한 하는 내부 생성자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b7cb1-108">An internal constructor can be used to limit concrete implementations of the abstract class to the assembly defining the class.</span></span>  
  
 <span data-ttu-id="b7cb1-109">**✓ 않습니다** 배송 된 각 추상 클래스에서 상속 하는 구체적인 형식이 하나 이상 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7cb1-109">**✓ DO** provide at least one concrete type that inherits from each abstract class that you ship.</span></span>  
  
 <span data-ttu-id="b7cb1-110">이 사용이 하면 유효성을 검사 하는 추상 클래스의 디자인을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7cb1-110">Doing this helps to validate the design of the abstract class.</span></span> <span data-ttu-id="b7cb1-111">예를 들어 <xref:System.IO.FileStream?displayProperty=nameWithType> 는의 구현에서 <xref:System.IO.Stream?displayProperty=nameWithType> 추상 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="b7cb1-111">For example,  <xref:System.IO.FileStream?displayProperty=nameWithType> is an implementation of the <xref:System.IO.Stream?displayProperty=nameWithType> abstract class.</span></span>  
  
 <span data-ttu-id="b7cb1-112">*Portions © 2005, 2009 Microsoft Corporation. 모든 권리 보유.*</span><span class="sxs-lookup"><span data-stu-id="b7cb1-112">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="b7cb1-113">*피어슨 교육, Inc.에서의 사용 권한으로 재인쇄 [Framework 디자인 지침: 규칙, 특징 및 다시 사용할 수 있는.NET 라이브러리를 2nd Edition에 대 한 패턴](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina 및 Brad Abrams 게시 하 여 2008 년 10 월 22 일 Microsoft Windows 개발 시리즈의 일부로: Addison Wesley Professional.*</span><span class="sxs-lookup"><span data-stu-id="b7cb1-113">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7cb1-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b7cb1-114">See Also</span></span>  
 [<span data-ttu-id="b7cb1-115">형식 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="b7cb1-115">Type Design Guidelines</span></span>](../../../docs/standard/design-guidelines/type.md)  
 [<span data-ttu-id="b7cb1-116">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="b7cb1-116">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
