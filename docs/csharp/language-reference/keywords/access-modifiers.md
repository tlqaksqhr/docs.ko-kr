---
title: "액세스 한정자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- access modifiers [C#]
ms.assetid: 61c3fa51-c00f-48cb-9b49-c805dedd62d7
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a3ad46580561500d9f011da4997007023a3bc844
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="access-modifiers-c-reference"></a><span data-ttu-id="c9621-102">액세스 한정자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="c9621-102">Access Modifiers (C# Reference)</span></span>
<span data-ttu-id="c9621-103">액세스 한정자는 멤버 또는 형식의 선언된 접근성을 지정하는 데 사용되는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="c9621-103">Access modifiers are keywords used to specify the declared accessibility of a member or a type.</span></span> <span data-ttu-id="c9621-104">이 섹션에서는 다음 네 가지 액세스 한정자를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="c9621-104">This section introduces the four access modifiers:</span></span>  
  
-   [<span data-ttu-id="c9621-105">public</span><span class="sxs-lookup"><span data-stu-id="c9621-105">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
  
-   [<span data-ttu-id="c9621-106">protected</span><span class="sxs-lookup"><span data-stu-id="c9621-106">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
  
-   [<span data-ttu-id="c9621-107">internal</span><span class="sxs-lookup"><span data-stu-id="c9621-107">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)  
  
-   [<span data-ttu-id="c9621-108">private</span><span class="sxs-lookup"><span data-stu-id="c9621-108">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
  
 <span data-ttu-id="c9621-109">액세스 한정자를 사용하여 다음 다섯 가지 접근성 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9621-109">The following five accessibility levels can be specified using the access modifiers:</span></span>  
  
 <span data-ttu-id="c9621-110">`public`: 액세스가 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c9621-110">`public`: Access is not restricted.</span></span>  
  
 <span data-ttu-id="c9621-111">`protected`: 액세스가 포함하는 클래스 또는 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9621-111">`protected`: Access is limited to the containing class or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="c9621-112">`Internal`: 액세스가 현재 어셈블리로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9621-112">`Internal`: Access is limited to the current assembly.</span></span>  
  
 <span data-ttu-id="c9621-113">[protected internal](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md): 액세스가 현재 어셈블리 또는 포함하는 클래스에서 파생된 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9621-113">[protected internal](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md): Access is limited to the current assembly or types derived from the containing class.</span></span>  
  
 <span data-ttu-id="c9621-114">`private`: 액세스가 포함하는 형식으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="c9621-114">`private`: Access is limited to the containing type.</span></span>  
  
 <span data-ttu-id="c9621-115">이 섹션에서는 다음 내용도 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="c9621-115">This section also introduces the following:</span></span>  
  
-   <span data-ttu-id="c9621-116">[접근성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md): 네 가지 액세스 한정자를 사용하여 다섯 가지 접근성 수준을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="c9621-116">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md): Using the four access modifiers to declare five levels of accessibility.</span></span>  
  
-   <span data-ttu-id="c9621-117">[접근성 도메인](../../../csharp/language-reference/keywords/accessibility-domain.md): 프로그램 섹션에서 멤버를 참조할 수 있는 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c9621-117">[Accessibility Domain](../../../csharp/language-reference/keywords/accessibility-domain.md): Specifies where, in the program sections, a member can be referenced.</span></span>  
  
-   <span data-ttu-id="c9621-118">[접근성 수준 사용에 대한 제한](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): 선언된 접근성 수준 사용에 대한 제한 사항 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="c9621-118">[Restrictions on Using Accessibility Levels](../../../csharp/language-reference/keywords/restrictions-on-using-accessibility-levels.md): A summary of the restrictions on using declared accessibility levels.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9621-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9621-119">See Also</span></span>  
 <span data-ttu-id="c9621-120">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c9621-120">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="c9621-121">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="c9621-121">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="c9621-122">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="c9621-122">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="c9621-123">[액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="c9621-123">[Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) </span></span>  
 <span data-ttu-id="c9621-124">[액세스 키워드](../../../csharp/language-reference/keywords/access-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="c9621-124">[Access Keywords](../../../csharp/language-reference/keywords/access-keywords.md) </span></span>  
 [<span data-ttu-id="c9621-125">한정자</span><span class="sxs-lookup"><span data-stu-id="c9621-125">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)

