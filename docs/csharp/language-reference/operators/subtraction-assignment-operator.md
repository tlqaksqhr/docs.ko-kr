---
title: -= 연산자(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- -=_CSharpKeyword
helpviewer_keywords:
- subtraction assignment operator (-=) [C#]
- -= operator (subtraction assignment ) [C#]
ms.assetid: 05c7d68a-423f-4de8-891b-cf24e8fb6ed7
ms.openlocfilehash: 2f37bfa303fb523840b15e896ee3b4a967eb5b2b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171457"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="9de84-102">-= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="9de84-102">-= Operator (C# Reference)</span></span>
<span data-ttu-id="9de84-103">빼기 대입 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="9de84-103">The subtraction assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9de84-104">설명</span><span class="sxs-lookup"><span data-stu-id="9de84-104">Remarks</span></span>  
 <span data-ttu-id="9de84-105">다음과 같은 `-=` 대입 연산자를 사용하는 식의 경우</span><span class="sxs-lookup"><span data-stu-id="9de84-105">An expression using the `-=` assignment operator, such as</span></span>  
  
```csharp  
x -= y  
```  
  
 <span data-ttu-id="9de84-106">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="9de84-106">is equivalent to</span></span>  
  
```csharp  
x = x - y  
```  
  
 <span data-ttu-id="9de84-107">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="9de84-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="9de84-108">[- 연산자](../../../csharp/language-reference/operators/subtraction-operator.md)의 의미는 `x` 및 `y`에 따라 달라집니다(숫자 피연산자의 경우 빼기, 대리자 피연산자의 경우 대리자 제거 등).</span><span class="sxs-lookup"><span data-stu-id="9de84-108">The meaning of the [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) is dependent on the types of `x` and `y` (subtraction for numeric operands, delegate removal for delegate operands, and so forth).</span></span>  
  
 <span data-ttu-id="9de84-109">`-=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [- 연산자](../../../csharp/language-reference/operators/subtraction-operator.md)를 오버로드할 수 있습니다([연산자](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="9de84-109">The `-=` operator cannot be overloaded directly, but user-defined types can overload the [- operator](../../../csharp/language-reference/operators/subtraction-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="9de84-110">또한 -= 연산자는 C#에서 이벤트 구독을 취소하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="9de84-110">The -= operator is also used in C# to unsubscribe from an event.</span></span> <span data-ttu-id="9de84-111">자세한 내용은 [방법: 이벤트 구독 및 구독 취소](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9de84-111">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9de84-112">예</span><span class="sxs-lookup"><span data-stu-id="9de84-112">Example</span></span>  
 [!code-csharp[csRefOperators#6](codesnippet/CSharp/subtraction-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="9de84-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9de84-113">See Also</span></span>  
 [<span data-ttu-id="9de84-114">C# 참조</span><span class="sxs-lookup"><span data-stu-id="9de84-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="9de84-115">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="9de84-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="9de84-116">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="9de84-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
