---
title: foreach, in(C# 참조)
ms.date: 06/29/2018
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: d3ce1122c54c14b1baf35641f28d062a2855d335
ms.sourcegitcommit: 736ec4d3e2c74895b47a0d36126657b95da383c9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2018
ms.locfileid: "37140270"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="1c6a6-102">foreach, in(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="1c6a6-102">foreach, in (C# Reference)</span></span>

<span data-ttu-id="1c6a6-103">`foreach` 문은 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 인터페이스를 구현하는 형식의 인스턴스에 있는 각 요소에 대해 문 또는 문 블록을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a6-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="1c6a6-104">`foreach` 문은 해당 형식으로 제한되지 않으며 다음 조건을 충족하는 모든 형식의 인스턴스에 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a6-104">The `foreach` statement is not limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="1c6a6-105">반환 형식이 클래스, 구조체 또는 인터페이스 유형인 public 매개 변수가 없는 `GetEnumerator` 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a6-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="1c6a6-106">`GetEnumerator` 메서드의 반환 형식이 public `Current` 속성과 반환 형식이 <xref:System.Boolean>인 public 매개 변수가 없는 `MoveNext` 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a6-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="1c6a6-107">`foreach` 문 블록 내 원하는 지점에서 [break](break.md) 문을 사용하여 루프를 중단하거나 [continue](continue.md) 문을 사용하여 루프의 다음 반복을 한 단계 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a6-107">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="1c6a6-108">[goto](goto.md), [return](return.md) 또는 [throw](throw.md) 문으로 `foreach` 루프를 종료할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a6-108">You also can exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="examples"></a><span data-ttu-id="1c6a6-109">예제</span><span class="sxs-lookup"><span data-stu-id="1c6a6-109">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="1c6a6-110">다음 예제는 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 구현하는 <xref:System.Collections.Generic.List%601> 형식의 인스턴스와 함께 `foreach` 문의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a6-110">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

[!code-csharp-interactive[list example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#1)]

<span data-ttu-id="1c6a6-111">다음 예제에서는 인터페이스를 구현하지 않는 <xref:System.Span%601?displayProperty=nameWithType> 형식의 인스턴스와 함께 `foreach` 문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a6-111">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

[!code-csharp[span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#2)]

<span data-ttu-id="1c6a6-112">C# 7.3부터는 열거자의 `Current` 속성이 [참조 반환 값](../../programming-guide/classes-and-structs/ref-returns.md)(`ref T` 여기서 `T`는 컬렉션 요소의 형식임)을 반환하는 경우 `ref` 또는 `ref readonly` 한정자를 사용하여 반복 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a6-112">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](../../programming-guide/classes-and-structs/ref-returns.md) (`ref T` where `T` is the type of the collection element), you can declare the iteration variable with the `ref` or `ref readonly` modifier.</span></span> <span data-ttu-id="1c6a6-113">다음 예제에서는 `ref` 반복 변수를 사용하여 stackalloc 배열의 각 항목 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a6-113">The following example uses a `ref` iteration variable to set the value of each item in a stackalloc array.</span></span> <span data-ttu-id="1c6a6-114">`ref readonly` 버전은 컬렉션을 반복하여 모든 값을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a6-114">The `ref readonly` version iterates the collection to print all the values.</span></span> <span data-ttu-id="1c6a6-115">`readonly` 선언은 암시적 로컬 변수 선언을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a6-115">The `readonly` declaration uses an implicit local variable declaration.</span></span> <span data-ttu-id="1c6a6-116">명시적으로 변수 선언을 입력하므로 `ref` 또는 `ref readonly`에서 암시적 변수 선언을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c6a6-116">Implicit variable declarations can be used with either `ref` or `ref readonly` declarations, as can explicitly typed variable declarations.</span></span>

[!code-csharp[ref span example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#RefSpan)]

## <a name="c-language-specification"></a><span data-ttu-id="1c6a6-117">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="1c6a6-117">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="1c6a6-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c6a6-118">See also</span></span>

[<span data-ttu-id="1c6a6-119">foreach 문(C# 언어 사)</span><span class="sxs-lookup"><span data-stu-id="1c6a6-119">The foreach statement (C# language specification)</span></span>](/dotnet/csharp/language-reference/language-specification/statements#the-foreach-statement)  
[<span data-ttu-id="1c6a6-120">배열에 foreach 사용</span><span class="sxs-lookup"><span data-stu-id="1c6a6-120">Using foreach with Arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)  
[<span data-ttu-id="1c6a6-121">for</span><span class="sxs-lookup"><span data-stu-id="1c6a6-121">for</span></span>](for.md)  
[<span data-ttu-id="1c6a6-122">반복 문</span><span class="sxs-lookup"><span data-stu-id="1c6a6-122">Iteration Statements</span></span>](iteration-statements.md)  
[<span data-ttu-id="1c6a6-123">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="1c6a6-123">C# Keywords</span></span>](index.md)  
[<span data-ttu-id="1c6a6-124">C# 참조</span><span class="sxs-lookup"><span data-stu-id="1c6a6-124">C# Reference</span></span>](../index.md)  
[<span data-ttu-id="1c6a6-125">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="1c6a6-125">C# Programming Guide</span></span>](../../programming-guide/index.md)  
