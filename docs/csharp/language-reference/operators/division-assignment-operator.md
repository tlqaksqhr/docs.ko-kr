---
title: /= 연산자(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
ms.openlocfilehash: c31ff374e6af4c08c329a971fdd8af169e239395
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="77921-102">/= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="77921-102">/= Operator (C# Reference)</span></span>
<span data-ttu-id="77921-103">나누기 대입 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="77921-103">The division assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="77921-104">설명</span><span class="sxs-lookup"><span data-stu-id="77921-104">Remarks</span></span>  
 <span data-ttu-id="77921-105">다음과 같은 `/=` 대입 연산자를 사용하는 식의 경우</span><span class="sxs-lookup"><span data-stu-id="77921-105">An expression using the `/=` assignment operator, such as</span></span>  
  
```csharp  
x /= y  
```  
  
 <span data-ttu-id="77921-106">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="77921-106">is equivalent to</span></span>  
  
```csharp  
x = x / y  
```  
  
 <span data-ttu-id="77921-107">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="77921-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="77921-108">[/ 연산자](../../../csharp/language-reference/operators/division-operator.md)는 나누기를 수행할 숫자 형식에 대해 미리 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77921-108">The [/ operator](../../../csharp/language-reference/operators/division-operator.md) is predefined for numeric types to perform division.</span></span>  
  
 <span data-ttu-id="77921-109">`/=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [/ 연산자](../../../csharp/language-reference/operators/division-operator.md)를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="77921-109">The `/=` operator cannot be overloaded directly, but user-defined types can overload the [/ operator](../../../csharp/language-reference/operators/division-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="77921-110">모든 복합 대입 연산자에서 이진 연산자를 암시적으로 오버로드하면 해당하는 복합 대입 연산자가 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="77921-110">On all compound assignment operators, overloading the binary operator implicitly overloads the equivalent compound assignment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77921-111">예</span><span class="sxs-lookup"><span data-stu-id="77921-111">Example</span></span>  
 [!code-csharp[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="77921-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="77921-112">See Also</span></span>  
 [<span data-ttu-id="77921-113">C# 참조</span><span class="sxs-lookup"><span data-stu-id="77921-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="77921-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="77921-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="77921-115">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="77921-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
