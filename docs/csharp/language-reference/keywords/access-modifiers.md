---
title: "액세스 한정자(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 23f99d0925aefde7ef43888d16e888a0943dfc21
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="809db-102">액세스 한정자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="809db-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="809db-103">액세스 한정자는 멤버 또는 형식의 선언된 접근성을 지정하는 데 사용되는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="809db-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="809db-104">이 섹션에서는 다음 네 가지 액세스 한정자를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="809db-104">This section introduces the four access modifiers:</span></span>  
  
-   [<span data-ttu-id="809db-105">public</span><span class="sxs-lookup"><span data-stu-id="809db-105">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
  
-   [<span data-ttu-id="809db-106">protected</span><span class="sxs-lookup"><span data-stu-id="809db-106">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
  
-   [<span data-ttu-id="809db-107">internal</span><span class="sxs-lookup"><span data-stu-id="809db-107">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
  
-   [<span data-ttu-id="809db-108">private</span><span class="sxs-lookup"><span data-stu-id="809db-108">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
  
 <span data-ttu-id="809db-109">다음 6 개 액세스 가능성 수준 액세스 한정자를 사용 하 여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="809db-109">The following six accessibility levels can be specified using the access modifiers:</span></span>  
  
 <span data-ttu-id="809db-110">`public`: 액세스가 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="809db-110">`public`: Access is not restricted.</span></span>  
  
 <span data-ttu-id="809db-111">`protected`: 액세스가 포함하는 클래스 또는 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="809db-111">`protected`: Access is limited to the containing class or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="809db-112">`internal`: 액세스가 현재 어셈블리로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="809db-112">`internal`: Access is limited to the current assembly.</span></span>  
  
 <span data-ttu-id="809db-113">[`protected internal`](../../../csharp/language-reference/keywords/protected-internal.md): 액세스는 현재 어셈블리 또는 포함 하는 클래스에서 파생 된 형식으로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="809db-113">[`protected internal`](../../../csharp/language-reference/keywords/protected-internal.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="809db-114">`private`: 액세스가 포함하는 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="809db-114">`private`: Access is limited to the containing type.</span></span>  

 <span data-ttu-id="809db-115">[`private protected`](../../../csharp/language-reference/keywords/private-protected.md): 액세스가 포함 하는 클래스 또는 포함 하는 현재 어셈블리 내의 클래스에서 파생 된 형식으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="809db-115">[`private protected`](../../../csharp/language-reference/keywords/private-protected.md): Access is limited to the containing class or types derived from the containing class within the current assembly.</span></span>  
  
 <span data-ttu-id="809db-116">이 섹션에서는 다음 내용도 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="809db-116">This section also introduces the following:</span></span>  
  
-   <span data-ttu-id="809db-117">[액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md): 네 가지 액세스 한정자를 사용 하 여 6 개 수준의 내게 필요한 옵션을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="809db-117">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md): Using the four access modifiers to declare six levels of accessibility.</span></span>  
  
-   <span data-ttu-id="809db-118">[접근성 도메인](../../../csharp/language-reference/keywords/accessibility-domain.md): 프로그램 섹션에서 멤버를 참조할 수 있는 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="809db-118">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
-   <span data-ttu-id="809db-119">[접근성 수준 사용에 대한 제한](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): 선언된 접근성 수준 사용에 대한 제한 사항 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="809db-119">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="809db-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="809db-120">See Also</span></span>  
 [<span data-ttu-id="809db-121">C# 참조</span><span class="sxs-lookup"><span data-stu-id="809db-121">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="809db-122">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="809db-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="809db-123">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="809db-123">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="809db-124">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="809db-124">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="809db-125">액세스 키워드</span><span class="sxs-lookup"><span data-stu-id="809db-125">Access Keywords</span></span>](../../../csharp/language-reference/keywords/access-keywords.md)  
 [<span data-ttu-id="809db-126">한정자</span><span class="sxs-lookup"><span data-stu-id="809db-126">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)
