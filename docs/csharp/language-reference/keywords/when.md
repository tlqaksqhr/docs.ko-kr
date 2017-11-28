---
title: "when(C# 참조)"
ms.date: 03/07/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- when_CSharpKeyword
- when
helpviewer_keywords: when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
caps.latest.revision: "30"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f453d9f4b443d7adeeb0ab628b4ddad1a0116e49
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2017
---
 # <a name="when-c-reference"></a><span data-ttu-id="2e16f-102">when(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="2e16f-102">when (C# Reference)</span></span>

<span data-ttu-id="2e16f-103">`when` 상황별 키워드를 사용하여 두 가지 상황에서 필터 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e16f-103">You can use the `when` contextual keyword to specify a filter condition in two contexts:</span></span>

- <span data-ttu-id="2e16f-104">[try/catch](try-catch.md) 또는 [try/catch/finally](try-catch-finally.md) 블록의 `catch` 문에서</span><span class="sxs-lookup"><span data-stu-id="2e16f-104">In the `catch` statement of a [try/catch](try-catch.md) or [try/catch/finally](try-catch-finally.md) block.</span></span>
- <span data-ttu-id="2e16f-105">[switch](switch.md) 문의 `case` 레이블에서</span><span class="sxs-lookup"><span data-stu-id="2e16f-105">In the `case` label of a [switch](switch.md) statement.</span></span>

## <a name="when-in-a-catch-statement"></a><span data-ttu-id="2e16f-106">`catch` 문의 `when`</span><span class="sxs-lookup"><span data-stu-id="2e16f-106">`when` in a `catch` statement</span></span>

<span data-ttu-id="2e16f-107">C# 6부터, 특정 예외에 대한 처리기를 실행하기 위해 참이 되어야 하는 조건을 지정하기 위해 `catch` 문에서 `When`을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e16f-107">Starting with C# 6, `When` can be used in a `catch` statement to specify a condition that must be true for the handler for a specific exception to execute.</span></span> <span data-ttu-id="2e16f-108">사용되는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2e16f-108">Its syntax is:</span></span>

```csharp
catch ExceptionType [e] when (expr)
```
<span data-ttu-id="2e16f-109">여기서 *expr*은 부울 값으로 계산되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="2e16f-109">where *expr* is an expression that evaluates to a Boolean value.</span></span> <span data-ttu-id="2e16f-110">`true`가 반환되면 예외 처리기가 실행되고, `false`가 반환되면 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e16f-110">If it returns `true`, the exception handler executes; if `false`, it does not.</span></span> 

<span data-ttu-id="2e16f-111">다음 예제는 `when` 키워드를 사용하여 예외 메시지의 텍스트에 따라 <xref:System.Net.Http.HttpRequestException>에 대한 처리기를 조건부로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2e16f-111">The following example uses the `when` keyword to conditionally execute handlers for an <xref:System.Net.Http.HttpRequestException> depending on the text of the exception message.</span></span>

 [!code-csharp[when-with-catch](../../../../samples/snippets/csharp/language-reference/keywords/when/catch.cs)]  
  
## <a name="when-in-a-switch-statement"></a><span data-ttu-id="2e16f-112">`switch` 문의 `when`</span><span class="sxs-lookup"><span data-stu-id="2e16f-112">`when` in a `switch` statement</span></span>

<span data-ttu-id="2e16f-113">7부터 `case` 레이블은 더 이상 상호 배타적일 필요가 없으며 `case` 레이블이 `switch` 문에 나타나는 순서로 어떤 스위치 블록을 실행할지를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e16f-113">Starting with 7, `case` labels no longer need be mutually exclusive, and the order in which `case` labels appear in a `switch` statement can determine which switch block executes.</span></span> <span data-ttu-id="2e16f-114">필터 조건도 참인 경우에만 관련 사례 레이블을 참으로 만드는 필터 조건을 지정하려면 `when` 키워드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e16f-114">The `when` keyword can be used to specify a filter condition that causes its associated case label to be true only if the filter condition is also true.</span></span> <span data-ttu-id="2e16f-115">사용되는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2e16f-115">Its syntax is:</span></span>

```csharp
case (expr) when (when-condition):
```
<span data-ttu-id="2e16f-116">여기서 *expr*은 일치 식과 비교되는 상수 패턴 또는 형식 패턴이며 *when-condition*은 부울 식입니다.</span><span class="sxs-lookup"><span data-stu-id="2e16f-116">where *expr* is a constant pattern or type pattern that is compared to the match expression, and *when-condition* is any Boolean expression.</span></span> 

<span data-ttu-id="2e16f-117">다음 예제에서는 `when` 키워드를 사용하여 영역이 0인 `Shape` 개체를 테스트하고 영역이 0보다 큰 다양한 `Shape` 개체를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="2e16f-117">The following example uses the `when` keyword to test for `Shape` objects that have an area of zero, as well as to test for a variety of `Shape` objects that have an area greater than zero.</span></span> 

 [!code-csharp[when-with-case#1](../../../../samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]  

## <a name="see-also"></a><span data-ttu-id="2e16f-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e16f-118">See also</span></span> 
  [<span data-ttu-id="2e16f-119">switch 문</span><span class="sxs-lookup"><span data-stu-id="2e16f-119">switch statement</span></span>](switch.md)  
  [<span data-ttu-id="2e16f-120">try/catch 문</span><span class="sxs-lookup"><span data-stu-id="2e16f-120">try/catch statement</span></span>](try-catch.md)  
  [<span data-ttu-id="2e16f-121">try/catch/finally 문</span><span class="sxs-lookup"><span data-stu-id="2e16f-121">try/catch/finally statement</span></span>](try-catch-finally.md) 

