---
title: foreach, in(C# 참조)
ms.date: 05/24/2018
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 7613590686f7f7ec6439da4a2bb672e524ab01e8
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34565708"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="7a2ef-102">foreach, in(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="7a2ef-102">foreach, in (C# Reference)</span></span>

<span data-ttu-id="7a2ef-103">`foreach` 문은 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 인터페이스를 구현하는 형식의 인스턴스에 있는 각 요소에 대해 문 또는 문 블록을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="7a2ef-104">`foreach` 문은 해당 형식으로 제한되지 않으며 다음 조건을 충족하는 모든 형식의 인스턴스에 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-104">The `foreach` statement is not limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="7a2ef-105">반환 형식이 클래스, 구조체 또는 인터페이스 유형인 public 매개 변수가 없는 `GetEnumerator` 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="7a2ef-106">`GetEnumerator` 메서드의 반환 형식이 public `Current` 속성과 반환 형식이 <xref:System.Boolean>인 public 매개 변수가 없는 `MoveNext` 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="7a2ef-107">`foreach` 문 블록 내 원하는 지점에서 [break](break.md) 문을 사용하여 루프를 중단하거나 [continue](continue.md) 문을 사용하여 루프의 다음 반복을 한 단계 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-107">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="7a2ef-108">[goto](goto.md), [return](return.md) 또는 [throw](throw.md) 문으로 `foreach` 루프를 종료할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-108">You also can exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="examples"></a><span data-ttu-id="7a2ef-109">예제</span><span class="sxs-lookup"><span data-stu-id="7a2ef-109">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="7a2ef-110">다음 예제는 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 구현하는 <xref:System.Collections.Generic.List%601> 형식의 인스턴스와 함께 `foreach` 문의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-110">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

<span data-ttu-id="7a2ef-111">다음 예제에서는 인터페이스를 구현하지 않는 <xref:System.Span%601?displayProperty=nameWithType> 형식의 인스턴스와 함께 `foreach` 문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7a2ef-111">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

[!code-csharp-interactive[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="7a2ef-112">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="7a2ef-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7a2ef-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7a2ef-113">See also</span></span>

[<span data-ttu-id="7a2ef-114">foreach 문(C# 언어 사)</span><span class="sxs-lookup"><span data-stu-id="7a2ef-114">The foreach statement (C# language specification)</span></span>](/dotnet/csharp/language-reference/language-specification/statements#the-foreach-statement)  
[<span data-ttu-id="7a2ef-115">배열에 foreach 사용</span><span class="sxs-lookup"><span data-stu-id="7a2ef-115">Using foreach with Arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)  
[<span data-ttu-id="7a2ef-116">for</span><span class="sxs-lookup"><span data-stu-id="7a2ef-116">for</span></span>](for.md)  
[<span data-ttu-id="7a2ef-117">반복 문</span><span class="sxs-lookup"><span data-stu-id="7a2ef-117">Iteration Statements</span></span>](iteration-statements.md)  
[<span data-ttu-id="7a2ef-118">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="7a2ef-118">C# Keywords</span></span>](index.md)  
[<span data-ttu-id="7a2ef-119">C# 참조</span><span class="sxs-lookup"><span data-stu-id="7a2ef-119">C# Reference</span></span>](../index.md)  
[<span data-ttu-id="7a2ef-120">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="7a2ef-120">C# Programming Guide</span></span>](../../programming-guide/index.md)  