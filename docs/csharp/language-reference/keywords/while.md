---
title: "while(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 420b409689d877c3e1ac744e8d7a65500cf8f964
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="while-c-reference"></a><span data-ttu-id="4ff7b-102">while(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="4ff7b-102">while (C# Reference)</span></span>
<span data-ttu-id="4ff7b-103">`while` 문은 지정된 식이 `false`로 평가될 때까지 문 또는 문의 블록을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4ff7b-103">The `while` statement executes a statement or a block of statements until a specified expression evaluates to `false`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ff7b-104">예제</span><span class="sxs-lookup"><span data-stu-id="4ff7b-104">Example</span></span>  
 [!code-csharp[csrefKeywordsIteration#5](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="4ff7b-105">예제</span><span class="sxs-lookup"><span data-stu-id="4ff7b-105">Example</span></span>  
 [!code-csharp[csrefKeywordsIteration#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_2.cs)]  
  
## <a name="example"></a><span data-ttu-id="4ff7b-106">예제</span><span class="sxs-lookup"><span data-stu-id="4ff7b-106">Example</span></span>  
 <span data-ttu-id="4ff7b-107">루프의 각 실행 전에 `while` 식의 테스트가 수행되므로 `while` 루프는 0번 이상 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4ff7b-107">Because the test of the `while` expression takes place before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="4ff7b-108">이는 한 번 이상 실행되는 [do](../../../csharp/language-reference/keywords/do.md) 루프와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4ff7b-108">This differs from the [do](../../../csharp/language-reference/keywords/do.md) loop, which executes one or more times.</span></span>  
  
 <span data-ttu-id="4ff7b-109">`while` 루프는 [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md) 또는 [throw](../../../csharp/language-reference/keywords/throw.md) 문이 루프 외부로 제어를 전송할 때 종료될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ff7b-109">A `while` loop can be terminated when a [break](../../../csharp/language-reference/keywords/break.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), or [throw](../../../csharp/language-reference/keywords/throw.md) statement transfers control outside the loop.</span></span> <span data-ttu-id="4ff7b-110">루프를 종료하지 않고 다음 반복으로 제어를 전달하려면 [continue](../../../csharp/language-reference/keywords/continue.md) 문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4ff7b-110">To pass control to the next iteration without exiting the loop, use the [continue](../../../csharp/language-reference/keywords/continue.md) statement.</span></span> <span data-ttu-id="4ff7b-111">`int n`의 증가에 따라 이전의 세 예제에서 출력이 달라지는 것을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="4ff7b-111">Notice the difference in output in the three previous examples, depending on where `int n` is incremented.</span></span> <span data-ttu-id="4ff7b-112">아래의 예제에서는 출력이 생성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4ff7b-112">In the example below no output is generated.</span></span>  
  
 [!code-csharp[csrefKeywordsIteration#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/while_3.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="4ff7b-113">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="4ff7b-113">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4ff7b-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ff7b-114">See Also</span></span>  
 [<span data-ttu-id="4ff7b-115">C# 참조</span><span class="sxs-lookup"><span data-stu-id="4ff7b-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="4ff7b-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="4ff7b-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4ff7b-117">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="4ff7b-117">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="4ff7b-118">while 문(C++)</span><span class="sxs-lookup"><span data-stu-id="4ff7b-118">while Statement (C++)</span></span>](/cpp/cpp/while-statement-cpp)  
 [<span data-ttu-id="4ff7b-119">반복 문</span><span class="sxs-lookup"><span data-stu-id="4ff7b-119">Iteration Statements</span></span>](../../../csharp/language-reference/keywords/iteration-statements.md)
