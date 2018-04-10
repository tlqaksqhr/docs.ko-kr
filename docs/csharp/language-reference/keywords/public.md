---
title: public(C# 참조)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
caps.latest.revision: 21
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 197ef4a2a8544d439b0c34ec14bb7752b760ea06
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="public-c-reference"></a><span data-ttu-id="24349-102">public(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="24349-102">public (C# Reference)</span></span>
<span data-ttu-id="24349-103">`public` 키워드는 형식 및 형식 멤버에 대한 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="24349-103">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="24349-104">공용 액세스는 허용 범위가 가장 큰 액세스 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="24349-104">Public access is the most permissive access level.</span></span> <span data-ttu-id="24349-105">다음 예제와 같이, 공용 멤버 액세스에 대한 제한은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="24349-105">There are no restrictions on accessing public members, as in this example:</span></span>  
  
```  
class SampleClass  
{  
    public int x; // No access restrictions.  
}  
```  
  
 <span data-ttu-id="24349-106">자세한 내용은 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) 및 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="24349-106">See [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) for more information.</span></span>  
  
## <a name="example"></a><span data-ttu-id="24349-107">예제</span><span class="sxs-lookup"><span data-stu-id="24349-107">Example</span></span>  
 <span data-ttu-id="24349-108">다음 예제에서는 두 개의 클래스, `PointTest` 및 `MainClass`를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="24349-108">In the following example, two classes are declared, `PointTest` and `MainClass`.</span></span> <span data-ttu-id="24349-109">`PointTest`의 공용 멤버 `x` 및 `y`는 `MainClass`에서 직접 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="24349-109">The public members `x` and `y` of `PointTest` are accessed directly from `MainClass`.</span></span>  
  
 [!code-csharp[csrefKeywordsModifiers#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/public_1.cs)]  
  
 <span data-ttu-id="24349-110">`public` 액세스 수준을 [private](../../../csharp/language-reference/keywords/private.md) 또는 [protected](../../../csharp/language-reference/keywords/protected.md)로 변경하면 오류 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="24349-110">If you change the `public` access level to [private](../../../csharp/language-reference/keywords/private.md) or [protected](../../../csharp/language-reference/keywords/protected.md), you will get the error message:</span></span>  
  
 <span data-ttu-id="24349-111">보호 수준 때문에 'PointTest.y'에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="24349-111">'PointTest.y' is inaccessible due to its protection level.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="24349-112">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="24349-112">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="24349-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="24349-113">See Also</span></span>  
 [<span data-ttu-id="24349-114">C# 참조</span><span class="sxs-lookup"><span data-stu-id="24349-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="24349-115">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="24349-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="24349-116">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="24349-116">Access Modifiers</span></span>](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)  
 [<span data-ttu-id="24349-117">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="24349-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="24349-118">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="24349-118">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="24349-119">액세스 수준</span><span class="sxs-lookup"><span data-stu-id="24349-119">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="24349-120">한정자</span><span class="sxs-lookup"><span data-stu-id="24349-120">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="24349-121">private</span><span class="sxs-lookup"><span data-stu-id="24349-121">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="24349-122">protected</span><span class="sxs-lookup"><span data-stu-id="24349-122">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)  
 [<span data-ttu-id="24349-123">internal</span><span class="sxs-lookup"><span data-stu-id="24349-123">internal</span></span>](../../../csharp/language-reference/keywords/internal.md)
