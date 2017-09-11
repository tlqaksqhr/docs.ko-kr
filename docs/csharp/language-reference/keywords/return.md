---
title: "return(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- return_CSharpKeyword
- return
dev_langs:
- CSharp
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
caps.latest.revision: 18
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
ms.openlocfilehash: 596375a1cba8f5ecbad636a6829c1a0599f8c0f4
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="return-c-reference"></a><span data-ttu-id="8bc9b-102">return(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="8bc9b-102">return (C# Reference)</span></span>
<span data-ttu-id="8bc9b-103">`return` 문은 해당 문이 나타나는 메서드의 실행을 종료하고 제어를 호출 메서드로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8bc9b-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="8bc9b-104">선택적 값을 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc9b-104">It can also return an optional value.</span></span> <span data-ttu-id="8bc9b-105">메서드가 `void` 형식인 경우 `return` 문을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8bc9b-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>  
  
 <span data-ttu-id="8bc9b-106">return 문이 `try` 블록 안에 있으면 `finally` 블록(있는 경우)은 제어가 호출 메서드로 반환되기 전에 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bc9b-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8bc9b-107">예제</span><span class="sxs-lookup"><span data-stu-id="8bc9b-107">Example</span></span>  
 <span data-ttu-id="8bc9b-108">다음 예제에서 `A()` 메서드는 `Area` 변수를 [double](../../../csharp/language-reference/keywords/double.md) 값으로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8bc9b-108">In the following example, the method `A()` returns the variable `Area` as a [double](../../../csharp/language-reference/keywords/double.md) value.</span></span>  
  
 <span data-ttu-id="8bc9b-109">[!code-cs[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8bc9b-109">[!code-cs[csrefKeywordsJump#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/return_1.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="8bc9b-110">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="8bc9b-110">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8bc9b-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8bc9b-111">See Also</span></span>  
 <span data-ttu-id="8bc9b-112">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="8bc9b-112">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="8bc9b-113">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8bc9b-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="8bc9b-114">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="8bc9b-114">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="8bc9b-115">[return 문](/cpp/cpp/return-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="8bc9b-115">[return Statement](/cpp/cpp/return-statement-cpp) </span></span>  
 [<span data-ttu-id="8bc9b-116">점프 문</span><span class="sxs-lookup"><span data-stu-id="8bc9b-116">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)

