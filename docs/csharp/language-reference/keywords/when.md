---
title: "when(C# 참조)"
ms.date: 2017-03-07
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- when_CSharpKeyword
- when
dev_langs:
- CSharp
helpviewer_keywords:
- when keyword [C#]
ms.assetid: dd543335-ae37-48ac-9560-bd5f047b9aea
caps.latest.revision: 30
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
ms.sourcegitcommit: 9ad2eff6eb527f00ce23f463e811aa748def62d0
ms.openlocfilehash: c391c6de51d41577d61278f43d58fade5b7c139f
ms.contentlocale: ko-kr
ms.lasthandoff: 08/11/2017

---
 # <a name="when-c-reference"></a><span data-ttu-id="8d904-102">when(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="8d904-102">when (C# Reference)</span></span>

<span data-ttu-id="8d904-103">`when` 상황별 키워드를 사용하여 두 가지 상황에서 필터 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d904-103">You can use the `when` contextual keyword to specify a filter condition in two contexts:</span></span>

- <span data-ttu-id="8d904-104">[try/catch](try-catch.md) 또는 [try/catch/finally](try-catch-finally.md) 블록의 `catch` 문에서</span><span class="sxs-lookup"><span data-stu-id="8d904-104">In the `catch` statement of a [try/catch](try-catch.md) or [try/catch/finally](try-catch-finally.md) block.</span></span>
- <span data-ttu-id="8d904-105">[switch](switch.md) 문의 `case` 레이블에서</span><span class="sxs-lookup"><span data-stu-id="8d904-105">In the `case` label of a [switch](switch.md) statement.</span></span>

## <a name="when-in-a-catch-statement"></a><span data-ttu-id="8d904-106">`catch` 문의 `when`</span><span class="sxs-lookup"><span data-stu-id="8d904-106">`when` in a `catch` statement</span></span>

<span data-ttu-id="8d904-107">C# 6부터, 특정 예외에 대한 처리기를 실행하기 위해 참이 되어야 하는 조건을 지정하기 위해 `catch` 문에서 `When`을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d904-107">Starting with C# 6, `When` can be used in a `catch` statement to specify a condition that must be true for the handler for a specific exception to execute.</span></span> <span data-ttu-id="8d904-108">사용되는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8d904-108">Its syntax is:</span></span>

```csharp
catch ExceptionType [e] when (expr)
```
<span data-ttu-id="8d904-109">여기서 *expr*은 부울 값으로 계산되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8d904-109">where *expr* is an expression that evaluates to a Boolean value.</span></span> <span data-ttu-id="8d904-110">`true`가 반환되면 예외 처리기가 실행되고, `false`가 반환되면 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d904-110">If it returns `true`, the exception handler executes; if `false`, it does not.</span></span> 

<span data-ttu-id="8d904-111">다음 예제는 `when` 키워드를 사용하여 예외 메시지의 텍스트에 따라 @System.Net.HttpRequestException에 대한 처리기를 조건부로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8d904-111">The following example uses the `when` keyword to conditionally execute handlers for an @System.Net.HttpRequestException depending on the text of the exception message.</span></span>

 <span data-ttu-id="8d904-112">[!code-cs[when-with-catch](../../../../samples/snippets/csharp/language-reference/keywords/when/catch.cs)]</span><span class="sxs-lookup"><span data-stu-id="8d904-112">[!code-cs[when-with-catch](../../../../samples/snippets/csharp/language-reference/keywords/when/catch.cs)]</span></span>  
  
## <a name="when-in-a-switch-statement"></a><span data-ttu-id="8d904-113">`switch` 문의 `when`</span><span class="sxs-lookup"><span data-stu-id="8d904-113">`when` in a `switch` statement</span></span>

<span data-ttu-id="8d904-114">7부터 `case` 레이블은 더 이상 상호 배타적일 필요가 없으며 `case` 레이블이 `switch` 문에 나타나는 순서로 어떤 스위치 블록을 실행할지를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d904-114">Starting with 7, `case` labels no longer need be mutually exclusive, and the order in which `case` labels appear in a `switch` statement can determine which switch block executes.</span></span> <span data-ttu-id="8d904-115">필터 조건도 참인 경우에만 관련 사례 레이블을 참으로 만드는 필터 조건을 지정하려면 `when` 키워드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d904-115">The `when` keyword can be used to specify a filter condition that causes its associated case label to be true only if the filter condition is also true.</span></span> <span data-ttu-id="8d904-116">사용되는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8d904-116">Its syntax is:</span></span>

```csharp
case (expr) when (when-condition):
```
<span data-ttu-id="8d904-117">여기서 *expr*은 일치 식과 비교되는 상수 패턴 또는 형식 패턴이며 *when-condition*은 부울 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8d904-117">where *expr* is a constant pattern or type pattern that is compared to the match expression, and *when-condition* is any Boolean expression.</span></span> 

<span data-ttu-id="8d904-118">다음 예제에서는 `when` 키워드를 사용하여 영역이 0인 `Shape` 개체를 테스트하고 영역이 0보다 큰 다양한 `Shape` 개체를 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="8d904-118">The following example uses the `when` keyword to test for `Shape` objects that have an area of zero, as well as to test for a variety of `Shape` objects that have an area greater than zero.</span></span> 

 <span data-ttu-id="8d904-119">[!code-cs[when-with-case#1](../../../../samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="8d904-119">[!code-cs[when-with-case#1](../../../../samples/snippets/csharp/language-reference/keywords/when/when.cs#1)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="8d904-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8d904-120">See also</span></span> 
  [<span data-ttu-id="8d904-121">switch 문</span><span class="sxs-lookup"><span data-stu-id="8d904-121">switch statement</span></span>](switch.md)  
  [<span data-ttu-id="8d904-122">try/catch 문</span><span class="sxs-lookup"><span data-stu-id="8d904-122">try/catch statement</span></span>](try-catch.md)  
  [<span data-ttu-id="8d904-123">try/catch/finally 문</span><span class="sxs-lookup"><span data-stu-id="8d904-123">try/catch/finally statement</span></span>](try-catch-finally.md) 


