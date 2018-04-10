---
title: 액세스 한정자(C# 참조)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d63cf724a2364059e5f3327254a9ec95f7493e5e
ms.sourcegitcommit: d2da0142247ef42a219a5d2907f153e62dc6ea0d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/01/2018
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="27056-102">액세스 한정자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="27056-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="27056-103">액세스 한정자는 멤버 또는 형식의 선언된 접근성을 지정하는 데 사용되는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="27056-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="27056-104">이 섹션에서는 다음 네 가지 액세스 한정자를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="27056-104">This section introduces the four access modifiers:</span></span>  
  
-   `public`
-   `protected`
-   `internal`
-   `private`
  
 <span data-ttu-id="27056-105">액세스 한정자를 사용하여 다음 여섯 가지 접근성 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27056-105">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
- <span data-ttu-id="27056-106">[`public`](public.md): 액세스가 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="27056-106">[`public`](public.md): Access is not restricted.</span></span>  
  
- <span data-ttu-id="27056-107">[`protected`](protected.md): 액세스가 포함하는 클래스 또는 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="27056-107">[`protected`](protected.md): Access is limited to the containing class or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="27056-108">[`internal`](internal.md): 액세스가 현재 어셈블리로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="27056-108">[`internal`](internal.md): Access is limited to the current assembly.</span></span>  
  
- <span data-ttu-id="27056-109">[`protected internal`](protected-internal.md): 액세스가 현재 어셈블리 또는 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="27056-109">[`protected internal`](protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
- <span data-ttu-id="27056-110">[`private`](private.md): 액세스가 포함하는 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="27056-110">[`private`](private.md): Access is limited to the containing type.</span></span>  

- <span data-ttu-id="27056-111">[`private protected`](private-protected.md): 액세스가 포함하는 클래스 또는 현재 어셈블리 내의 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="27056-111">[`private protected`](private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="27056-112">이 섹션에서는 다음 내용도 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="27056-112">This section also introduces the following:</span></span>  
  
-   <span data-ttu-id="27056-113">[접근성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md): 네 가지 액세스 한정자를 사용하여 여섯 가지 접근성 수준을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="27056-113">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
-   <span data-ttu-id="27056-114">[접근성 도메인](../../../csharp/language-reference/keywords/accessibility-domain.md): 프로그램 섹션에서 멤버를 참조할 수 있는 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="27056-114">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
-   <span data-ttu-id="27056-115">[접근성 수준 사용에 대한 제한](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): 선언된 접근성 수준 사용에 대한 제한 사항 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="27056-115">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27056-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27056-116">See Also</span></span>  
 [<span data-ttu-id="27056-117">C# 참조</span><span class="sxs-lookup"><span data-stu-id="27056-117">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="27056-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="27056-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="27056-119">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="27056-119">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="27056-120">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="27056-120">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="27056-121">액세스 키워드</span><span class="sxs-lookup"><span data-stu-id="27056-121">Access Keywords</span></span>](../../../csharp/language-reference/keywords/access-keywords.md)  
 [<span data-ttu-id="27056-122">한정자</span><span class="sxs-lookup"><span data-stu-id="27056-122">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
