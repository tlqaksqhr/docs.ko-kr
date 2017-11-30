---
title: "Null 조건부 연산자(C# 및 Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c95b4079cf4e71c0ef9cd436ec230337f512229a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="null-conditional-operators-c-and-visual-basic"></a><span data-ttu-id="83f59-102">Null 조건부 연산자(C# 및 Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="83f59-102">Null-conditional Operators (C# and Visual Basic)</span></span>
<span data-ttu-id="83f59-103">멤버 액세스(`?.`) 또는 인덱스(`?[`) 작업을 수행하기 전에 null을 테스트하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="83f59-103">Used to test for null before performing a member access (`?.`) or index (`?[`) operation.</span></span>  <span data-ttu-id="83f59-104">이러한 연산자는 null 검사의 처리를 위해 작성하는 코드의 양을 줄이는 데 도움이 되며 특히 데이터 구조에서 아래로 내려가는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="83f59-104">These operators help you write less code to handle null checks, especially for descending into data structures.</span></span>  
  
```csharp  
int? length = customers?.Length; // null if customers is null   
Customer first = customers?[0];  // null if customers is null  
int? count = customers?[0]?.Orders?.Count();  // null if customers, the first customer, or Orders is null  
```  
  
```vb  
Dim length = customers?.Length  ' null if customers is null  
Dim first as Customer = customers?(0)  ' null if customers is null  
Dim count as Integer? = customers?(0)?.Orders?.Count()  ' null if customers, the first customer, or Orders is null  
```  
  
 <span data-ttu-id="83f59-105">마지막 예제에서는 null 조건 연산자가 단락임을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="83f59-105">The last example demonstrates that the null-condition operators are short-circuiting.</span></span>  <span data-ttu-id="83f59-106">조건부 멤버 액세스 및 인덱스 작업 체인의 한 작업에서 null을 반환하면 체인 실행의 나머지 부분이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="83f59-106">If one operation in a chain of conditional member access and index operation returns null, then the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="83f59-107">식에서 우선 순위가 낮은 다른 작업은 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="83f59-107">Other operations with lower precedence in the expression continue.</span></span>  <span data-ttu-id="83f59-108">예를 들어 다음 식에서 `E`는 두 번째 줄에서 실행되고 `??` 및 `==` 작업이 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="83f59-108">For example, `E` in the following executes in the second line, and the `??` and `==` operations execute.</span></span>  <span data-ttu-id="83f59-109">첫 번째 줄에서 `??`는 주기를 단축하고 `E`는 왼쪽이 null이 아닌 값으로 평가되면 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="83f59-109">In the first line, the `??` short circuits and `E` does not execute when the left side evaluates to non-null.</span></span>
  
```csharp
A?.B?.C?[0] ?? E  
A?.B?.C?[0] == E  
```

```vb
A?.B?.C?(0) ?? E  
A?.B?.C?(0) == E  
```  
  
 <span data-ttu-id="83f59-110">또한 null 조건 멤버 액세스는 훨씬 더 적은 코드를 사용하여 스레드로부터 안전한 방식으로 대리자를 호출하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="83f59-110">Another use for the null-condition member access is invoking delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="83f59-111">이전 방식에서는 다음과 같은 코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="83f59-111">The old way requires code like the following:</span></span>  
  
```csharp  
var handler = this.PropertyChanged;  
if (handler != null)  
    handler(…);
```  
  
```vb  
Dim handler = AddressOf(Me.PropertyChanged)  
If handler IsNot Nothing  
    Call handler(…)  
```  
  
 <span data-ttu-id="83f59-112">새로운 방식은 훨씬 더 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="83f59-112">The new way is much simpler:</span></span>  
  
```csharp
PropertyChanged?.Invoke(e)  
```  

```vb
PropertyChanged?.Invoke(e)
```  
  
 <span data-ttu-id="83f59-113">새로운 방식은 컴파일러가 `PropertyChanged`를 한 번만 평가하는 코드를 생성하고 결과를 임시 변수에 유지하기 때문에 스레드로부터 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="83f59-113">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span>  
  
 <span data-ttu-id="83f59-114">null 조건부 대리자 호출 구문 `PropertyChanged?(e)`가 없기 때문에 `Invoke` 메서드를 명시적으로 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83f59-114">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>  <span data-ttu-id="83f59-115">허용하는 모호한 구문 분석 상황이 너무 많습니다.</span><span class="sxs-lookup"><span data-stu-id="83f59-115">There were too many ambiguous parsing situations to allow it.</span></span>  
  
## <a name="language-specifications"></a><span data-ttu-id="83f59-116">언어 사양</span><span class="sxs-lookup"><span data-stu-id="83f59-116">Language Specifications</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
 <span data-ttu-id="83f59-117">자세한 내용은 [Visual Basic 언어 참조](../../../visual-basic/language-reference/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83f59-117">For more information, see the [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83f59-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83f59-118">See Also</span></span>  
 [<span data-ttu-id="83f59-119">?? (null 병합 연산자)</span><span class="sxs-lookup"><span data-stu-id="83f59-119">?? (null-coalescing operator)</span></span>](null-conditional-operator.md)  
 [<span data-ttu-id="83f59-120">C# 참조</span><span class="sxs-lookup"><span data-stu-id="83f59-120">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="83f59-121">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="83f59-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="83f59-122">Visual Basic 언어 참조</span><span class="sxs-lookup"><span data-stu-id="83f59-122">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
 [<span data-ttu-id="83f59-123">Visual Basic 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="83f59-123">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
