---
title: '방법: 포인터로 멤버 액세스(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], member access
ms.assetid: 1e998498-8c85-4a78-8ce2-4d8c20f08342
ms.openlocfilehash: 20f0dd18bb5ca132d05335953958d8f747b6abc4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-access-a-member-with-a-pointer-c-programming-guide"></a><span data-ttu-id="dc297-102">방법: 포인터로 멤버 액세스(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="dc297-102">How to: Access a Member with a Pointer (C# Programming Guide)</span></span>
<span data-ttu-id="dc297-103">안전하지 않은 컨텍스트에서 선언된 구조체 멤버에 액세스하기 위해 다음 예제에 제시된 멤버 액세스 연산자를 사용할 수 있습니다. 여기에서 `p`는 멤버 `x`가 포함된 [구조체](../../../csharp/language-reference/keywords/struct.md)에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dc297-103">To access a member of a struct that is declared in an unsafe context, you can use the member access operator as shown in the following example in which `p` is a pointer to a [struct](../../../csharp/language-reference/keywords/struct.md) that contains a member `x`.</span></span>  
  
```  
CoOrds* p = &home;  
p -> x = 25; //member access operator ->  
```  
  
## <a name="example"></a><span data-ttu-id="dc297-104">예</span><span class="sxs-lookup"><span data-stu-id="dc297-104">Example</span></span>  
 <span data-ttu-id="dc297-105">이 예제에서는 `x` 및 `y`라는 두 좌표가 포함된 [구조체](../../../csharp/language-reference/keywords/struct.md) `CoOrds`를 선언하고 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="dc297-105">In this example, a [struct](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, that contains the two coordinates `x` and `y` is declared and instantiated.</span></span> <span data-ttu-id="dc297-106">멤버 액세스 연산자 `->`와 인스턴스 `home`에 대한 포인터를 사용하면 `x`와 `y`에 값이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc297-106">By using the member access operator `->` and a pointer to the instance `home`, `x` and `y` are assigned values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc297-107">`p->x` 식은 `(*p).x` 식과 동일하며 두 식 중 어느 식을 사용해도 같은 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc297-107">Notice that the expression `p->x` is equivalent to the expression `(*p).x`, and you can obtain the same result by using either of the two expressions.</span></span>  
  
 [!code-csharp[csProgGuidePointers#9](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#10](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_2.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="dc297-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc297-108">See Also</span></span>  
 [<span data-ttu-id="dc297-109">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="dc297-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="dc297-110">포인터 식</span><span class="sxs-lookup"><span data-stu-id="dc297-110">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="dc297-111">포인터 형식</span><span class="sxs-lookup"><span data-stu-id="dc297-111">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="dc297-112">유형</span><span class="sxs-lookup"><span data-stu-id="dc297-112">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="dc297-113">unsafe</span><span class="sxs-lookup"><span data-stu-id="dc297-113">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="dc297-114">fixed 문</span><span class="sxs-lookup"><span data-stu-id="dc297-114">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="dc297-115">stackalloc</span><span class="sxs-lookup"><span data-stu-id="dc297-115">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
