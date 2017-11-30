---
title: "return(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
caps.latest.revision: "18"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 90c84b51c6ee57864eac552bc488c9f9c15e9394
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="return-c-reference"></a><span data-ttu-id="74468-102">return(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="74468-102">return (C# Reference)</span></span>
<span data-ttu-id="74468-103">`return` 문은 해당 문이 나타나는 메서드의 실행을 종료하고 제어를 호출 메서드로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="74468-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="74468-104">선택적 값을 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74468-104">It can also return an optional value.</span></span> <span data-ttu-id="74468-105">메서드가 `void` 형식인 경우 `return` 문을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74468-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>  
  
 <span data-ttu-id="74468-106">return 문이 `try` 블록 안에 있으면 `finally` 블록(있는 경우)은 제어가 호출 메서드로 반환되기 전에 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="74468-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74468-107">예제</span><span class="sxs-lookup"><span data-stu-id="74468-107">Example</span></span>  
 <span data-ttu-id="74468-108">다음 예제에서는 메서드 `CalculateArea()` 지역 변수를 반환 `area` 로 [double](../../../csharp/language-reference/keywords/double.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="74468-108">In the following example, the method `CalculateArea()` returns the local variable `area` as a [double](../../../csharp/language-reference/keywords/double.md) value.</span></span>  
  
 [!code-csharp[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="74468-109">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="74468-109">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="74468-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74468-110">See Also</span></span>  
 [<span data-ttu-id="74468-111">C# 참조</span><span class="sxs-lookup"><span data-stu-id="74468-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="74468-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="74468-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="74468-113">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="74468-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="74468-114">return 문</span><span class="sxs-lookup"><span data-stu-id="74468-114">return Statement</span></span>](/cpp/cpp/return-statement-cpp)  
 [<span data-ttu-id="74468-115">점프 문</span><span class="sxs-lookup"><span data-stu-id="74468-115">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)
