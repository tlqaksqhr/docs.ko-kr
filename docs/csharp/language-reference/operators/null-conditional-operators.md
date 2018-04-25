---
title: Null 조건부 연산자(C# 및 Visual Basic)
ms.date: 04/03/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- null-conditional operators [C#]
- null-conditional operators [Visual Basic]
- ?. operator [C#]
- ?. operator [Visual Basic]
- ?[] operator [C#]
- ?[] operator [Visual Basic]
ms.assetid: 9c7b2c8f-a785-44ca-836c-407bfb6d27f5
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3ffeaa3c2088d0bb2c000704cfe312b0f9453b68
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2018
---
# <a name="-and--null-conditional-operators-c-and-visual-basic"></a><span data-ttu-id="3cbc8-102">?.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-102">?.</span></span> <span data-ttu-id="3cbc8-103">및 ?[] Null 조건부 연산자(C# 및 Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3cbc8-103">and ?[] null-conditional Operators (C# and Visual Basic)</span></span>
<span data-ttu-id="3cbc8-104">멤버 액세스(`?.`) 또는 인덱스(`?[]`) 작업을 수행하기 전에 null을 테스트하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-104">Used to test for null before performing a member access (`?.`) or index (`?[]`) operation.</span></span>  <span data-ttu-id="3cbc8-105">이러한 연산자는 null 검사의 처리를 위해 작성하는 코드의 양을 줄이는 데 도움이 되며 특히 데이터 구조에서 아래로 내려가는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-105">These operators help you write less code to handle null checks, especially for descending into data structures.</span></span>  
  
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
  
 <span data-ttu-id="3cbc8-106">Null 조건부 연산자는 단락 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-106">The null-condition operators are short-circuiting.</span></span>  <span data-ttu-id="3cbc8-107">조건부 멤버 액세스 및 인덱스 작업 체인의 한 작업에서 null을 반환하면 체인 실행의 나머지 부분이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-107">If one operation in a chain of conditional member access and index operation returns null, then the rest of the chain’s execution stops.</span></span>  <span data-ttu-id="3cbc8-108">다음 예제에서 `E`는 `A`, `B` 또는 `C`가 Null로 평가되는 경우 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-108">In the following example, `E` doesn't execute if `A`, `B`, or `C` evaluates to null.</span></span>
  
```csharp
A?.B?.C?.Do(E);
A?.B?.C?[E];
```

```vb
A?.B?.C?.Do(E);
A?.B?.C?(E);
```  
  
 <span data-ttu-id="3cbc8-109">또한 null 조건 멤버 액세스는 훨씬 더 적은 코드를 사용하여 스레드로부터 안전한 방식으로 대리자를 호출하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-109">Another use for the null-condition member access is invoking delegates in a thread-safe way with much less code.</span></span>  <span data-ttu-id="3cbc8-110">이전 방식에서는 다음과 같은 코드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-110">The old way requires code like the following:</span></span>  
  
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
  
 <span data-ttu-id="3cbc8-111">새로운 방식은 훨씬 더 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-111">The new way is much simpler:</span></span>  
  
```csharp
PropertyChanged?.Invoke(e)  
```  

```vb
PropertyChanged?.Invoke(e)
```  
  
 <span data-ttu-id="3cbc8-112">새로운 방식은 컴파일러가 `PropertyChanged`를 한 번만 평가하는 코드를 생성하고 결과를 임시 변수에 유지하기 때문에 스레드로부터 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-112">The new way is thread-safe because the compiler generates code to evaluate `PropertyChanged` one time only, keeping the result in a temporary variable.</span></span>  
  
 <span data-ttu-id="3cbc8-113">null 조건부 대리자 호출 구문 `PropertyChanged?(e)`가 없기 때문에 `Invoke` 메서드를 명시적으로 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-113">You need to explicitly call the `Invoke` method because there is no null-conditional delegate invocation syntax `PropertyChanged?(e)`.</span></span>  
  
## <a name="language-specifications"></a><span data-ttu-id="3cbc8-114">언어 사양</span><span class="sxs-lookup"><span data-stu-id="3cbc8-114">Language Specifications</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
 <span data-ttu-id="3cbc8-115">자세한 내용은 [Visual Basic 언어 참조](../../../visual-basic/language-reference/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3cbc8-115">For more information, see the [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3cbc8-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3cbc8-116">See Also</span></span>  
 [<span data-ttu-id="3cbc8-117">??(Null 병합 연산자)</span><span class="sxs-lookup"><span data-stu-id="3cbc8-117">?? (null-coalescing operator)</span></span>](null-conditional-operator.md)  
 [<span data-ttu-id="3cbc8-118">C# 참조</span><span class="sxs-lookup"><span data-stu-id="3cbc8-118">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="3cbc8-119">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="3cbc8-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3cbc8-120">Visual Basic 언어 참조</span><span class="sxs-lookup"><span data-stu-id="3cbc8-120">Visual Basic Language Reference</span></span>](../../../visual-basic/language-reference/index.md)  
 [<span data-ttu-id="3cbc8-121">Visual Basic 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="3cbc8-121">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
