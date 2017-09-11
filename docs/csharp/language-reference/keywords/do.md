---
title: "do(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- do_CSharpKeyword
- do
dev_langs:
- CSharp
helpviewer_keywords:
- do keyword [C#]
ms.assetid: 50725f79-9ba6-4898-aa78-6e331568a1bb
caps.latest.revision: 22
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
ms.openlocfilehash: 58a9361c440bc1b17c5ab929ff7b45ba71ce50a4
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="do-c-reference"></a><span data-ttu-id="d7d7a-102">do(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="d7d7a-102">do (C# Reference)</span></span>
<span data-ttu-id="d7d7a-103">`do` 문은 지정된 식이 `false`로 계산될 때까지 문 또는 문의 블록을 반복해서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d7d7a-103">The `do` statement executes a statement or a block of statements repeatedly until a specified expression evaluates to `false`.</span></span> <span data-ttu-id="d7d7a-104">루프의 본문이 단일 문으로 구성되지 않은 경우 중괄호(`{}`)로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d7d7a-104">The body of the loop must be enclosed in braces, `{}`, unless it consists of a single statement.</span></span> <span data-ttu-id="d7d7a-105">이 경우 중괄호는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="d7d7a-105">In that case, the braces are optional.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7d7a-106">예제</span><span class="sxs-lookup"><span data-stu-id="d7d7a-106">Example</span></span>  
 <span data-ttu-id="d7d7a-107">다음 예제에서는 `x` 변수가 5보다 작은 한 `do-while` 루프 문이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7d7a-107">In the following example, the `do-while` loop statements execute as long as the variable `x` is less than 5.</span></span>  
  
 <span data-ttu-id="d7d7a-108">[!code-cs[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d7d7a-108">[!code-cs[csrefKeywordsIteration#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/do_1.cs)]</span></span>  
  
 <span data-ttu-id="d7d7a-109">[while](../../../csharp/language-reference/keywords/while.md) 문과 달리 `do-while` 루프는 조건식이 계산되기 전에 한 번 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7d7a-109">Unlike the [while](../../../csharp/language-reference/keywords/while.md) statement, a `do-while` loop is executed one time before the conditional expression is evaluated.</span></span>  
  
 <span data-ttu-id="d7d7a-110">`do-while` 블록의 어느 지점에서나 [break](../../../csharp/language-reference/keywords/break.md) 문을 사용하여 루프를 중단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7d7a-110">At any point in the `do-while` block, you can break out of the loop using the [break](../../../csharp/language-reference/keywords/break.md) statement.</span></span> <span data-ttu-id="d7d7a-111">[continue](../../../csharp/language-reference/keywords/continue.md) 문을 사용하여 `while` 식 계산 문을 직접 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7d7a-111">You can step directly to the `while` expression evaluation statement by using the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="d7d7a-112">`while` 식이 true로 계산될 경우 루프의 첫 번째 문에서 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7d7a-112">If the `while` expression evaluates to true, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="d7d7a-113">식이 false로 계산될 경우 `do-while` 루프 다음의 첫 번째 문에서 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d7d7a-113">If the expression evaluates to false, execution continues at the first statement after the `do-while` loop.</span></span>  
  
 <span data-ttu-id="d7d7a-114">또한 `do-while` 루프는 [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) 또는 [throw](../../../csharp/language-reference/keywords/throw.md) 문으로 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d7d7a-114">A `do-while` loop can also be exited by the [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statements.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d7d7a-115">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="d7d7a-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d7d7a-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d7d7a-116">See Also</span></span>  
 <span data-ttu-id="d7d7a-117">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d7d7a-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d7d7a-118">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d7d7a-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d7d7a-119">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="d7d7a-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="d7d7a-120">[do-while 문(C++)](/cpp/cpp/do-while-statement-cpp) </span><span class="sxs-lookup"><span data-stu-id="d7d7a-120">[do-while Statement (C++)](/cpp/cpp/do-while-statement-cpp) </span></span>  
 [<span data-ttu-id="d7d7a-121">반복 문</span><span class="sxs-lookup"><span data-stu-id="d7d7a-121">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)

