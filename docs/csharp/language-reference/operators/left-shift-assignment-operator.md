---
title: '&lt;&lt;= 연산자(C# 참조)'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
caps.latest.revision: 16
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b5c2a177182561075442afc3f1b76603c6646bd6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="f315f-102">&lt;&lt;= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="f315f-102">&lt;&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="f315f-103">왼쪽 시프트 대입 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="f315f-103">The left-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f315f-104">설명</span><span class="sxs-lookup"><span data-stu-id="f315f-104">Remarks</span></span>  
 <span data-ttu-id="f315f-105">다음 형태의 식이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="f315f-105">An expression of the form</span></span>  
  
```  
x <<= y  
```  
  
 <span data-ttu-id="f315f-106">이 식은 다음과 같이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="f315f-106">is evaluated as</span></span>  
  
```  
x = x << y  
```  
  
 <span data-ttu-id="f315f-107">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="f315f-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="f315f-108">[<< 연산자](../../../csharp/language-reference/operators/left-shift-operator.md)는 `y`로 지정된 비트 수만큼 `x`를 왼쪽으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="f315f-108">The [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) shifts `x` left by the number of bits specified by `y`.</span></span>  
  
 <span data-ttu-id="f315f-109">`<<=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [<< 연산자](../../../csharp/language-reference/operators/left-shift-operator.md)를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="f315f-109">The `<<=` operator cannot be overloaded directly, but user-defined types can overload the [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f315f-110">예제</span><span class="sxs-lookup"><span data-stu-id="f315f-110">Example</span></span>  
 [!code-csharp[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="f315f-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f315f-111">See Also</span></span>  
 [<span data-ttu-id="f315f-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="f315f-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f315f-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="f315f-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f315f-114">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="f315f-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
