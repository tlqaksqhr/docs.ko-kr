---
title: "throw(C# 참조)"
ms.date: 03/02/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- throw
- throw_CSharpKeyword
helpviewer_keywords:
- throw statement [C#]
- throw expression [C#]
- throw keyword [C#]
ms.assetid: 5ac4feef-4b1a-4c61-aeb4-61d549e5dd42
caps.latest.revision: "22"
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e56bd8f8b6bfcc7c8f1eb2df6ac157e28adac331
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="throw-c-reference"></a><span data-ttu-id="869c2-102">throw(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="869c2-102">throw (C# Reference)</span></span>
<span data-ttu-id="869c2-103">프로그램 실행 중 예외 발생 신호를 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="869c2-103">Signals the occurrence of an exception during program execution.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="869c2-104">주의</span><span class="sxs-lookup"><span data-stu-id="869c2-104">Remarks</span></span>

<span data-ttu-id="869c2-105">`throw`의 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="869c2-105">The syntax of `throw` is:</span></span>

```csharp
throw [e]
```
<span data-ttu-id="869c2-106">여기서 `e`는 <xref:System.Exception?displayProperty=nameWithType>에서 파생된 클래스의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="869c2-106">where `e` is an instance of a class derived from <xref:System.Exception?displayProperty=nameWithType>.</span></span> <span data-ttu-id="869c2-107">다음 예제에서는 `throw` 문을 사용하여 `GetNumber`라는 메서드에 전달된 인수가 내부 배열의 유효한 인덱스에 해당하지 않는 경우  <xref:System.IndexOutOfRangeException> 을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="869c2-107">The following example uses the `throw` statement to throw an <xref:System.IndexOutOfRangeException> if the argument passed to a method named `GetNumber` does not correspond to a valid index of an internal array.</span></span>

[!code-csharp[csrefKeyword#1](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#1)]  

<span data-ttu-id="869c2-108">그러면 메서드 호출자가 `try-catch` 또는 `try-catch-finally` 블록을 사용하여 throw된 예외를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="869c2-108">Method callers then use a `try-catch` or `try-catch-finally` block to handle the thrown exception.</span></span> <span data-ttu-id="869c2-109">다음 예제에서는 `GetNumber` 메서드에 의해 throw된 예외를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="869c2-109">The following example handles the exception thrown by the `GetNumber` method.</span></span>

[!code-csharp[csrefKeyword#2](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-1.cs#2)]  

## <a name="re-throwing-an-exception"></a><span data-ttu-id="869c2-110">예외 다시 throw</span><span class="sxs-lookup"><span data-stu-id="869c2-110">Re-throwing an exception</span></span>

<span data-ttu-id="869c2-111">`catch` 블록에서 `throw`를 사용하여 `catch` 블록에서 처리된 예외를 다시 throw할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="869c2-111">`throw` can also be used in a `catch` block to re-throw an exception handled in a `catch` block.</span></span>  <span data-ttu-id="869c2-112">이 경우 `throw`는 예외 피연산자를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="869c2-112">In this case, `throw` does not take an exception operand.</span></span> <span data-ttu-id="869c2-113">이는 메서드가 호출자의 인수를 다른 일부 라이브러리 메서드에 전달하고 라이브러리 메서드가 호출자에게 전달되어야 하는 예외를 throw하는 경우에 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="869c2-113">It is most useful when a method passes on an argument from a caller to some other library method, and the library method throws an exception that must be passed on to the caller.</span></span> <span data-ttu-id="869c2-114">예를 들어 다음 예제에서는 초기화되지 않은 문자열의 첫 번째 문자를 검색하려고 할 때 throw되는 <xref:System.NullReferenceException>을 다시 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="869c2-114">For example, the following example re-throws an <xref:System.NullReferenceException> that is thrown when attempting to retrieve the first character of an uninitialized string.</span></span> 

[!code-csharp[csrefKeyword#3](../../../../samples/snippets/csharp/language-reference/keywords/throw/throw-3.cs#3)]  

> [!IMPORTANT]
> <span data-ttu-id="869c2-115">`catch` 블록의 `throw e` 구문을 사용하여 호출자에게 전달하는 새 예외를 인스턴스화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="869c2-115">You can also use the `throw e` syntax in a `catch` block to instantiate a new exception that you pass on to the caller.</span></span> <span data-ttu-id="869c2-116">이 경우 <xref:System.Exception.StackTrace> 속성에서 제공되는 원래 예외의 스택 추적이 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="869c2-116">In this case, the stack trace of the original exception, which is available from the <xref:System.Exception.StackTrace> property, is not preserved.</span></span>
 
## <a name="the-throw-expression"></a><span data-ttu-id="869c2-117">`throw` 식</span><span class="sxs-lookup"><span data-stu-id="869c2-117">The `throw` expression</span></span>

<span data-ttu-id="869c2-118">C# 7부터 `throw`를 문뿐만 아니라 식으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="869c2-118">Starting with C# 7, `throw` can be used as an expression as well as a statement.</span></span> <span data-ttu-id="869c2-119">이렇게 하면 이전에 지원되지 않은 상황에서 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="869c2-119">This allows an exception to be thrown in contexts that were previously unsupported.</span></span> <span data-ttu-id="869c2-120">여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="869c2-120">These include:</span></span>

- <span data-ttu-id="869c2-121">[조건 연산자](../operators/conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="869c2-121">[the conditional operator](../operators/conditional-operator.md).</span></span> <span data-ttu-id="869c2-122">다음 예제에서는 `throw` 식을 사용하여 메서드에 빈 문자열 배열이 전달된 경우 <xref:System.ArgumentException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="869c2-122">The following example uses a `throw` expression to throw an <xref:System.ArgumentException> if a method is passed an empty string array.</span></span> <span data-ttu-id="869c2-123">C# 7 이전에는 이 논리가 `if`/`else` 문에 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="869c2-123">Before C# 7, this logic would need to appear in an `if`/`else` statement.</span></span>

   [!code-csharp[csrefKeyword#4](../../../../samples/snippets/csharp/language-reference/keywords/throw/conditional.cs#1)]  
  
- <span data-ttu-id="869c2-124">[Null 병합 연산자](../operators/null-conditional-operator.md).</span><span class="sxs-lookup"><span data-stu-id="869c2-124">[the null-coalescing operator](../operators/null-conditional-operator.md).</span></span> <span data-ttu-id="869c2-125">다음 예제에서는 `throw` 식에 Null 병합 연산자를 사용하여 `Name` 속성에 할당된 문자열이 `null`인 경우 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="869c2-125">In the following example, a `throw` expression is used with a null-coalescing operator to throw an exception if the string assigned to a `Name` property is `null`.</span></span>
 
   [!code-csharp[csrefKeyword#5](../../../../samples/snippets/csharp/language-reference/keywords/throw/coalescing.cs#1)]  
 
- <span data-ttu-id="869c2-126">식 본문 [람다](../../lambda-expressions.md) 또는 메서드.</span><span class="sxs-lookup"><span data-stu-id="869c2-126">an expression-bodied [lambda](../../lambda-expressions.md) or method.</span></span> <span data-ttu-id="869c2-127">다음 예제에서는 <xref:System.DateTime> 값으로 변환이 지원되지 않기 때문에 <xref:System.InvalidCastException>을 throw하는 식 본문 메서드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="869c2-127">The following example illustrates an expression-bodied method that throws an <xref:System.InvalidCastException> because a conversion to a <xref:System.DateTime> value is not supported.</span></span>
 
   [!code-csharp[csrefKeyword#6](../../../../samples/snippets/csharp/language-reference/keywords/throw/exp-bodied.cs#1)]  
 
  
## <a name="c-language-specification"></a><span data-ttu-id="869c2-128">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="869c2-128">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="869c2-129">참고 항목</span><span class="sxs-lookup"><span data-stu-id="869c2-129">See Also</span></span>  
 [<span data-ttu-id="869c2-130">C# 참조</span><span class="sxs-lookup"><span data-stu-id="869c2-130">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="869c2-131">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="869c2-131">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="869c2-132">try-catch</span><span class="sxs-lookup"><span data-stu-id="869c2-132">try-catch</span></span>](../../../csharp/language-reference/keywords/try-catch.md)  
 [<span data-ttu-id="869c2-133">Try, catch 및 throw 문 c + +</span><span class="sxs-lookup"><span data-stu-id="869c2-133">The try, catch, and throw Statements in C++</span></span>](../../../csharp/language-reference/keywords/try-catch.md)  
 [<span data-ttu-id="869c2-134">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="869c2-134">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="869c2-135">예외 처리 문</span><span class="sxs-lookup"><span data-stu-id="869c2-135">Exception Handling Statements</span></span>](../../../csharp/language-reference/keywords/exception-handling-statements.md)  
 [<span data-ttu-id="869c2-136">방법: 명시적으로 예외 Throw</span><span class="sxs-lookup"><span data-stu-id="869c2-136">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
