---
title: return(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: 29d2b8e28ae6240b9d06b82695efe1736404c5cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="return-c-reference"></a><span data-ttu-id="79294-102">return(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="79294-102">return (C# Reference)</span></span>
<span data-ttu-id="79294-103">`return` 문은 해당 문이 나타나는 메서드의 실행을 종료하고 제어를 호출 메서드로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79294-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="79294-104">선택적 값을 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79294-104">It can also return an optional value.</span></span> <span data-ttu-id="79294-105">메서드가 `void` 형식인 경우 `return` 문을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79294-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>  
  
 <span data-ttu-id="79294-106">return 문이 `try` 블록 안에 있으면 `finally` 블록(있는 경우)은 제어가 호출 메서드로 반환되기 전에 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="79294-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79294-107">예</span><span class="sxs-lookup"><span data-stu-id="79294-107">Example</span></span>  
 <span data-ttu-id="79294-108">다음 예제에서 `CalculateArea()` 메서드는 `area` 로컬 변수를 [double](../../../csharp/language-reference/keywords/double.md) 값으로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79294-108">In the following example, the method `CalculateArea()` returns the local variable `area` as a [double](../../../csharp/language-reference/keywords/double.md) value.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="79294-109">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="79294-109">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="79294-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79294-110">See Also</span></span>  
 [<span data-ttu-id="79294-111">C# 참조</span><span class="sxs-lookup"><span data-stu-id="79294-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="79294-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="79294-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="79294-113">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="79294-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="79294-114">return 문</span><span class="sxs-lookup"><span data-stu-id="79294-114">return Statement</span></span>](/cpp/cpp/return-statement-cpp)  
 [<span data-ttu-id="79294-115">점프 문</span><span class="sxs-lookup"><span data-stu-id="79294-115">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
