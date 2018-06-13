---
title: '&amp;= 연산자(C# 참조)'
ms.date: 07/20/2015
f1_keywords:
- '&=_CSharpKeyword'
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
ms.openlocfilehash: 092f46ddd8ca52e2d705200768c93a3473f1520f
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172050"
---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="360bb-102">&amp;= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="360bb-102">&amp;= Operator (C# Reference)</span></span>
<span data-ttu-id="360bb-103">AND 대입 연산자.</span><span class="sxs-lookup"><span data-stu-id="360bb-103">The AND assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="360bb-104">설명</span><span class="sxs-lookup"><span data-stu-id="360bb-104">Remarks</span></span>  
 <span data-ttu-id="360bb-105">다음과 같은 `&=` 대입 연산자를 사용하는 식의 경우</span><span class="sxs-lookup"><span data-stu-id="360bb-105">An expression using the `&=` assignment operator, such as</span></span>  
  
```csharp  
x &= y  
```  
  
 <span data-ttu-id="360bb-106">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="360bb-106">is equivalent to</span></span>  
  
```csharp  
x = x & y  
```  
  
 <span data-ttu-id="360bb-107">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="360bb-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="360bb-108">[& 연산자](../../../csharp/language-reference/operators/and-operator.md)는 정수 피연산자에 대한 비트 논리적 AND 연산과 `bool` 피연산자에 대한 논리적 AND 연산을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="360bb-108">The [& operator](../../../csharp/language-reference/operators/and-operator.md) performs a bitwise logical AND operation on integral operands and logical AND on `bool` operands.</span></span>  
  
 <span data-ttu-id="360bb-109">`&=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 이항 [& 연산자](../../../csharp/language-reference/operators/and-operator.md)를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="360bb-109">The `&=` operator cannot be overloaded directly, but user-defined types can overload the binary [& operator](../../../csharp/language-reference/operators/and-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="360bb-110">예</span><span class="sxs-lookup"><span data-stu-id="360bb-110">Example</span></span>  
 [!code-csharp[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="360bb-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="360bb-111">See Also</span></span>  
 [<span data-ttu-id="360bb-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="360bb-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="360bb-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="360bb-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="360bb-114">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="360bb-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
