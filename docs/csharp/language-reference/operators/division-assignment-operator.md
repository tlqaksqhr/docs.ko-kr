---
title: "/= 연산자(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /=_CSharpKeyword
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
caps.latest.revision: "17"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 26096d9b5dfc565c9933f1ed8ffb241dc900d9ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="d929f-102">/= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="d929f-102">/= Operator (C# Reference)</span></span>
<span data-ttu-id="d929f-103">나누기 대입 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="d929f-103">The division assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d929f-104">주의</span><span class="sxs-lookup"><span data-stu-id="d929f-104">Remarks</span></span>  
 <span data-ttu-id="d929f-105">다음과 같은 `/=` 대입 연산자를 사용하는 식의 경우</span><span class="sxs-lookup"><span data-stu-id="d929f-105">An expression using the `/=` assignment operator, such as</span></span>  
  
```  
x /= y  
```  
  
 <span data-ttu-id="d929f-106">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="d929f-106">is equivalent to</span></span>  
  
```  
x = x / y  
```  
  
 <span data-ttu-id="d929f-107">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="d929f-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="d929f-108">[/ 연산자](../../../csharp/language-reference/operators/division-operator.md)는 나누기를 수행할 숫자 형식에 대해 미리 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d929f-108">The [/ operator](../../../csharp/language-reference/operators/division-operator.md) is predefined for numeric types to perform division.</span></span>  
  
 <span data-ttu-id="d929f-109">`/=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [/ 연산자](../../../csharp/language-reference/operators/division-operator.md)를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="d929f-109">The `/=` operator cannot be overloaded directly, but user-defined types can overload the [/ operator](../../../csharp/language-reference/operators/division-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="d929f-110">모든 복합 대입 연산자에서 이진 연산자를 암시적으로 오버로드하면 해당하는 복합 대입 연산자가 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="d929f-110">On all compound assignment operators, overloading the binary operator implicitly overloads the equivalent compound assignment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d929f-111">예제</span><span class="sxs-lookup"><span data-stu-id="d929f-111">Example</span></span>  
 [!code-csharp[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d929f-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d929f-112">See Also</span></span>  
 [<span data-ttu-id="d929f-113">C# 참조</span><span class="sxs-lookup"><span data-stu-id="d929f-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d929f-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d929f-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d929f-115">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="d929f-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
