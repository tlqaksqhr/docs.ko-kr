---
title: continue 문(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 6a409fe8c7fd07342138eac11bfd1766014da1bd
ms.sourcegitcommit: ed7b4b9b77d35e94a35a2634e8c874f46603fb2b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36948357"
---
# <a name="continue-c-reference"></a><span data-ttu-id="96ac7-102">continue(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="96ac7-102">continue (C# Reference)</span></span>

<span data-ttu-id="96ac7-103">`continue` 문은 자신이 나타나는 바깥쪽 [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md) 또는 [foreach](../../../csharp/language-reference/keywords/foreach-in.md) 문의 다음 반복으로 제어를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="96ac7-103">The `continue` statement passes control to the next iteration of the enclosing [while](../../../csharp/language-reference/keywords/while.md), [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), or [foreach](../../../csharp/language-reference/keywords/foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="96ac7-104">예</span><span class="sxs-lookup"><span data-stu-id="96ac7-104">Example</span></span>

<span data-ttu-id="96ac7-105">이 예제에서 카운터는 1에서 10까지 계산하도록 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ac7-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="96ac7-106">`continue` 문을 `(i < 9)` 식과 함께 사용하면 `continue`와 `for` 본문의 끝 사이에 있는 문을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="96ac7-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="96ac7-107">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="96ac7-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="96ac7-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="96ac7-108">See also</span></span>

[<span data-ttu-id="96ac7-109">C# 참조</span><span class="sxs-lookup"><span data-stu-id="96ac7-109">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
[<span data-ttu-id="96ac7-110">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="96ac7-110">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
[<span data-ttu-id="96ac7-111">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="96ac7-111">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
[<span data-ttu-id="96ac7-112">break 문</span><span class="sxs-lookup"><span data-stu-id="96ac7-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)  
[<span data-ttu-id="96ac7-113">점프 문</span><span class="sxs-lookup"><span data-stu-id="96ac7-113">Jump Statements</span></span>](../../../csharp/language-reference/keywords/jump-statements.md)