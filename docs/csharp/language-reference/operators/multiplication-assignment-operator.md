---
title: '*= 연산자(C# 참조)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: dc2201f78e1e05bd0ccdea04522896c00294bdd6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="b0d17-102">\*= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="b0d17-102">\*= Operator (C# Reference)</span></span>
<span data-ttu-id="b0d17-103">이항 곱하기 대입 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="b0d17-103">The binary multiplication assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b0d17-104">설명</span><span class="sxs-lookup"><span data-stu-id="b0d17-104">Remarks</span></span>  
 <span data-ttu-id="b0d17-105">다음과 같은 `*=` 대입 연산자를 사용하는 식의 경우</span><span class="sxs-lookup"><span data-stu-id="b0d17-105">An expression using the `*=` assignment operator, such as</span></span>  
  
```  
x *= y  
```  
  
 <span data-ttu-id="b0d17-106">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="b0d17-106">is equivalent to</span></span>  
  
```  
x = x * y  
```  
  
 <span data-ttu-id="b0d17-107">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0d17-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="b0d17-108">[\* 연산자](../../../csharp/language-reference/operators/multiplication-operator.md)는 곱하기를 수행할 숫자 형식에 대해 미리 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0d17-108">The [\* operator](../../../csharp/language-reference/operators/multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>  
  
 <span data-ttu-id="b0d17-109">`*=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [* 연산자](../../../csharp/language-reference/operators/multiplication-operator.md)를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="b0d17-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0d17-110">예제</span><span class="sxs-lookup"><span data-stu-id="b0d17-110">Example</span></span>  
 [!code-csharp[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b0d17-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b0d17-111">See Also</span></span>  
 [<span data-ttu-id="b0d17-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="b0d17-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="b0d17-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="b0d17-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b0d17-114">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="b0d17-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
