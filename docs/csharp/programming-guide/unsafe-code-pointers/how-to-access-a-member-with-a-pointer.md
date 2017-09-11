---
title: "방법: 포인터로 멤버 액세스(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], member access
ms.assetid: 1e998498-8c85-4a78-8ce2-4d8c20f08342
caps.latest.revision: 16
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
ms.openlocfilehash: ca24b7d930e7b6c61a3db89a431f1ec3aaec77c8
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-access-a-member-with-a-pointer-c-programming-guide"></a><span data-ttu-id="9ca7c-102">방법: 포인터로 멤버 액세스(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="9ca7c-102">How to: Access a Member with a Pointer (C# Programming Guide)</span></span>
<span data-ttu-id="9ca7c-103">안전하지 않은 컨텍스트에서 선언된 구조체 멤버에 액세스하기 위해 다음 예제에 제시된 멤버 액세스 연산자를 사용할 수 있습니다. 여기에서 `p`는 멤버 `x`가 포함된 [구조체](../../../csharp/language-reference/keywords/struct.md)에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9ca7c-103">To access a member of a struct that is declared in an unsafe context, you can use the member access operator as shown in the following example in which `p` is a pointer to a [struct](../../../csharp/language-reference/keywords/struct.md) that contains a member `x`.</span></span>  
  
```  
CoOrds* p = &home;  
p -> x = 25; //member access operator ->  
```  
  
## <a name="example"></a><span data-ttu-id="9ca7c-104">예제</span><span class="sxs-lookup"><span data-stu-id="9ca7c-104">Example</span></span>  
 <span data-ttu-id="9ca7c-105">이 예제에서는 `x` 및 `y`라는 두 좌표가 포함된 [구조체](../../../csharp/language-reference/keywords/struct.md) `CoOrds`를 선언하고 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="9ca7c-105">In this example, a [struct](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, that contains the two coordinates `x` and `y` is declared and instantiated.</span></span> <span data-ttu-id="9ca7c-106">멤버 액세스 연산자 `->`와 인스턴스 `home`에 대한 포인터를 사용하면 `x`와 `y`에 값이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="9ca7c-106">By using the member access operator `->` and a pointer to the instance `home`, `x` and `y` are assigned values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ca7c-107">`p->x` 식은 `(*p).x` 식과 동일하며 두 식 중 어느 식을 사용해도 같은 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9ca7c-107">Notice that the expression `p->x` is equivalent to the expression `(*p).x`, and you can obtain the same result by using either of the two expressions.</span></span>  
  
 <span data-ttu-id="9ca7c-108">[!code-cs[csProgGuidePointers#9](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="9ca7c-108">[!code-cs[csProgGuidePointers#9](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_1.cs)]</span></span>  
  
 <span data-ttu-id="9ca7c-109">[!code-cs[csProgGuidePointers#10](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="9ca7c-109">[!code-cs[csProgGuidePointers#10](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ca7c-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9ca7c-110">See Also</span></span>  
 <span data-ttu-id="9ca7c-111">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="9ca7c-111">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="9ca7c-112">[포인터 식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="9ca7c-112">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="9ca7c-113">[포인터 형식](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="9ca7c-113">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="9ca7c-114">[형식](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="9ca7c-114">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="9ca7c-115">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="9ca7c-115">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="9ca7c-116">[fixed 문](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="9ca7c-116">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="9ca7c-117">stackalloc</span><span class="sxs-lookup"><span data-stu-id="9ca7c-117">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

