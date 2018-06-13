---
title: '&lt;&lt;= 연산자(C# 참조)'
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: e5f3886670baa34b0360501ee15280b93fac36bc
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
ms.locfileid: "34171795"
---
# <a name="ltlt-operator-c-reference"></a><span data-ttu-id="44d0b-102">&lt;&lt;= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="44d0b-102">&lt;&lt;= Operator (C# Reference)</span></span>
<span data-ttu-id="44d0b-103">왼쪽 시프트 대입 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="44d0b-103">The left-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="44d0b-104">설명</span><span class="sxs-lookup"><span data-stu-id="44d0b-104">Remarks</span></span>  
 <span data-ttu-id="44d0b-105">다음 형태의 식이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="44d0b-105">An expression of the form</span></span>  
  
```csharp  
x <<= y  
```  
  
 <span data-ttu-id="44d0b-106">이 식은 다음과 같이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d0b-106">is evaluated as</span></span>  
  
```csharp  
x = x << y  
```  
  
 <span data-ttu-id="44d0b-107">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="44d0b-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="44d0b-108">[<< 연산자](../../../csharp/language-reference/operators/left-shift-operator.md)는 `y`로 지정된 비트 수만큼 `x`를 왼쪽으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="44d0b-108">The [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) shifts `x` left by the number of bits specified by `y`.</span></span>  
  
 <span data-ttu-id="44d0b-109">`<<=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [<< 연산자](../../../csharp/language-reference/operators/left-shift-operator.md)를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="44d0b-109">The `<<=` operator cannot be overloaded directly, but user-defined types can overload the [<< operator](../../../csharp/language-reference/operators/left-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="44d0b-110">예</span><span class="sxs-lookup"><span data-stu-id="44d0b-110">Example</span></span>  
 [!code-csharp[csRefOperators#12](../../../csharp/language-reference/operators/codesnippet/CSharp/left-shift-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="44d0b-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="44d0b-111">See Also</span></span>  
 [<span data-ttu-id="44d0b-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="44d0b-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="44d0b-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="44d0b-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="44d0b-114">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="44d0b-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
