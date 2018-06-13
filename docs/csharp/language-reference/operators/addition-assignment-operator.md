---
title: += 연산자(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- +=_CSharpKeyword
helpviewer_keywords:
- += operator [C#]
- addition assignment operator (+=) [C#]
ms.assetid: 9cdf97e6-331d-492b-85e1-3ec3171484e9
ms.openlocfilehash: bcd56acad8e2b08585e5ae60f1c3cf8183b5664a
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171881"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="23222-102">+= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="23222-102">+= Operator (C# Reference)</span></span>
<span data-ttu-id="23222-103">더하기 대입 연산자.</span><span class="sxs-lookup"><span data-stu-id="23222-103">The addition assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="23222-104">설명</span><span class="sxs-lookup"><span data-stu-id="23222-104">Remarks</span></span>  
 <span data-ttu-id="23222-105">다음과 같은 `+=` 대입 연산자를 사용하는 식의 경우</span><span class="sxs-lookup"><span data-stu-id="23222-105">An expression using the `+=` assignment operator, such as</span></span>  
  
```csharp  
x += y  
```  
  
 <span data-ttu-id="23222-106">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="23222-106">is equivalent to</span></span>  
  
```csharp  
x = x + y  
```  
  
 <span data-ttu-id="23222-107">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="23222-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="23222-108">[+ 연산자](../../../csharp/language-reference/operators/addition-operator.md)의 의미는 `x`와 `y`의 형식에 따라 달라집니다(숫자 피연산자의 경우 더하기, 문자열 피연산자의 경우 연결 등).</span><span class="sxs-lookup"><span data-stu-id="23222-108">The meaning of the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) depends on the types of `x` and `y` (addition for numeric operands, concatenation for string operands, and so forth).</span></span>  
  
 <span data-ttu-id="23222-109">`+=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [+ 연산자](../../../csharp/language-reference/operators/addition-operator.md)를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="23222-109">The `+=` operator cannot be overloaded directly, but user-defined types can overload the [+ operator](../../../csharp/language-reference/operators/addition-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
 <span data-ttu-id="23222-110">`+=` 연산자는 이벤트에 대한 응답으로 호출될 메서드를 지정하는 데에도 사용됩니다. 이러한 메서드를 이벤트 처리기라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="23222-110">The `+=` operator is also used to specify a method that will be called in response to an event; such methods are called event handlers.</span></span> <span data-ttu-id="23222-111">이 컨텍스트에서 `+=` 연산자를 사용하는 것을 *이벤트 구독*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="23222-111">The use of the `+=` operator in this context is referred to as *subscribing to an event*.</span></span> <span data-ttu-id="23222-112">자세한 내용은 [방법: 이벤트 구독 및 구독 취소](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) 및 [대리자](../../../csharp/programming-guide/delegates/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23222-112">For more information, see [How to: Subscribe to and Unsubscribe from Events](../../../csharp/programming-guide/events/how-to-subscribe-to-and-unsubscribe-from-events.md) and [Delegates](../../../csharp/programming-guide/delegates/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="23222-113">예</span><span class="sxs-lookup"><span data-stu-id="23222-113">Example</span></span>  
 [!code-csharp[csRefOperators#35](../../../csharp/language-reference/operators/codesnippet/CSharp/addition-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="23222-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="23222-114">See Also</span></span>  
 [<span data-ttu-id="23222-115">C# 참조</span><span class="sxs-lookup"><span data-stu-id="23222-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="23222-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="23222-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="23222-117">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="23222-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
