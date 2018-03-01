---
title: "|= 연산자(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: aac4fd6016b65daa15da4bd3a414f385edce7c22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="06dcb-102">|= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="06dcb-102">|= Operator (C# Reference)</span></span>
<span data-ttu-id="06dcb-103">OR 대입 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="06dcb-103">The OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06dcb-104">설명</span><span class="sxs-lookup"><span data-stu-id="06dcb-104">Remarks</span></span>  
 <span data-ttu-id="06dcb-105">다음과 같은 `|=` 대입 연산자를 사용하는 식의 경우</span><span class="sxs-lookup"><span data-stu-id="06dcb-105">An expression using the `|=` assignment operator, such as</span></span>  
  
```  
x |= y  
```  
  
 <span data-ttu-id="06dcb-106">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="06dcb-106">is equivalent to</span></span>  
  
```  
x = x | y  
```  
  
 <span data-ttu-id="06dcb-107">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="06dcb-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="06dcb-108">[&#124; 연산자](../../../csharp/language-reference/operators/or-operator.md)는 정수 피연산자에 대한 비트 논리적 OR 연산과 부울 피연산자에 대한 논리적 OR 연산을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="06dcb-108">The [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) performs a bitwise logical OR operation on integral operands and logical OR on bool operands.</span></span>  
  
 <span data-ttu-id="06dcb-109">`|=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [&#124; 연산자](../../../csharp/language-reference/operators/or-operator.md)를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="06dcb-109">The `|=` operator cannot be overloaded directly, but user-defined types can overload the [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="06dcb-110">예제</span><span class="sxs-lookup"><span data-stu-id="06dcb-110">Example</span></span>  
 [!code-csharp[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="06dcb-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06dcb-111">See Also</span></span>  
 [<span data-ttu-id="06dcb-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="06dcb-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="06dcb-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="06dcb-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="06dcb-114">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="06dcb-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
