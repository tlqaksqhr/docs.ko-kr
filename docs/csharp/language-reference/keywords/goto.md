---
title: "goto(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: aa12a7547cfcd4a2076b5b0a308139f8a823f482
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="goto-c-reference"></a><span data-ttu-id="be074-102">goto(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="be074-102">goto (C# Reference)</span></span>
<span data-ttu-id="be074-103">`goto` 문은 레이블 지정된 문으로 직접 프로그램 컨트롤을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="be074-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>  
  
 <span data-ttu-id="be074-104">`goto`는 일반적으로 `switch` 문에서 switch-case 레이블 또는 기본 레이블로 컨트롤을 전송하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="be074-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>  
  
 <span data-ttu-id="be074-105">`goto` 문은 많이 중첩된 루프를 회피하는 데도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="be074-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be074-106">예제</span><span class="sxs-lookup"><span data-stu-id="be074-106">Example</span></span>  
 <span data-ttu-id="be074-107">다음 예제에서는 [switch](../../../csharp/language-reference/keywords/switch.md) 문에서 `goto`의 사용 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="be074-107">The following example demonstrates using `goto` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="be074-108">예제</span><span class="sxs-lookup"><span data-stu-id="be074-108">Example</span></span>  
 <span data-ttu-id="be074-109">다음 예제에서는 `goto`를 사용하여 중첩된 루프에서 벗어나는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="be074-109">The following example demonstrates using `goto` to break out from nested loops.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/goto_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="be074-110">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="be074-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="be074-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be074-111">See Also</span></span>  
 [<span data-ttu-id="be074-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="be074-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="be074-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="be074-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="be074-114">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="be074-114">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="be074-115">goto 문</span><span class="sxs-lookup"><span data-stu-id="be074-115">goto Statement</span></span>](/cpp/cpp/goto-statement-cpp)  
 [<span data-ttu-id="be074-116">점프 문</span><span class="sxs-lookup"><span data-stu-id="be074-116">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
