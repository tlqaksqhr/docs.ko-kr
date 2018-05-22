---
title: goto(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: 2dd70a30b885dcdae9637b02e8c34ac39f4879fb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="goto-c-reference"></a><span data-ttu-id="611df-102">goto(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="611df-102">goto (C# Reference)</span></span>
<span data-ttu-id="611df-103">`goto` 문은 레이블 지정된 문으로 직접 프로그램 컨트롤을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="611df-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>  
  
 <span data-ttu-id="611df-104">`goto`는 일반적으로 `switch` 문에서 switch-case 레이블 또는 기본 레이블로 컨트롤을 전송하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="611df-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>  
  
 <span data-ttu-id="611df-105">`goto` 문은 많이 중첩된 루프를 회피하는 데도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="611df-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>  
  
## <a name="example"></a><span data-ttu-id="611df-106">예</span><span class="sxs-lookup"><span data-stu-id="611df-106">Example</span></span>  
 <span data-ttu-id="611df-107">다음 예제에서는 [switch](../../../csharp/language-reference/keywords/switch.md) 문에서 `goto`의 사용 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="611df-107">The following example demonstrates using `goto` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="611df-108">예</span><span class="sxs-lookup"><span data-stu-id="611df-108">Example</span></span>  
 <span data-ttu-id="611df-109">다음 예제에서는 `goto`를 사용하여 중첩된 루프에서 벗어나는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="611df-109">The following example demonstrates using `goto` to break out from nested loops.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="611df-110">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="611df-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="611df-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="611df-111">See Also</span></span>  
 [<span data-ttu-id="611df-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="611df-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="611df-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="611df-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="611df-114">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="611df-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="611df-115">goto 문</span><span class="sxs-lookup"><span data-stu-id="611df-115">goto Statement</span></span>](/cpp/cpp/goto-statement-cpp)  
 [<span data-ttu-id="611df-116">점프 문</span><span class="sxs-lookup"><span data-stu-id="611df-116">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
