---
title: ^= 연산자(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- ^=_CSharpKeyword
helpviewer_keywords:
- ^= operator [C#]
ms.assetid: 3658ff9a-61cd-467e-ad6b-8fbf1cfbaae4
ms.openlocfilehash: b868f2cdbfa8a80f89a12e6194a30154481f0b07
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172375"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="a6d9a-102">^= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="a6d9a-102">^= Operator (C# Reference)</span></span>
<span data-ttu-id="a6d9a-103">배타적 OR 대입 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="a6d9a-103">The exclusive-OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6d9a-104">설명</span><span class="sxs-lookup"><span data-stu-id="a6d9a-104">Remarks</span></span>  
 <span data-ttu-id="a6d9a-105">다음 형태의 식이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d9a-105">An expression of the form</span></span>  
  
```csharp  
x ^= y  
```  
  
 <span data-ttu-id="a6d9a-106">이 식은 다음과 같이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6d9a-106">is evaluated as</span></span>  
  
```csharp  
x = x ^ y  
```  
  
 <span data-ttu-id="a6d9a-107">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6d9a-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="a6d9a-108">[^ 연산자](../../../csharp/language-reference/operators/xor-operator.md)는 정수 피연산자에 대한 배타적 비트 OR 연산과 [bool](../../../csharp/language-reference/keywords/bool.md) 피연산자에 대한 배타적 논리 OR 연산을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a6d9a-108">The [^ operator](../../../csharp/language-reference/operators/xor-operator.md) performs a bitwise exclusive-OR operation on integral operands and logical exclusive-OR on [bool](../../../csharp/language-reference/keywords/bool.md) operands.</span></span>  
  
 <span data-ttu-id="a6d9a-109">^= 연산자는 직접 오버로드할 수 없지만 사용자 정의 형식은 [^ 연산자](../../../csharp/language-reference/operators/xor-operator.md)를 오버로드할 수 있습니다([연산자](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="a6d9a-109">The ^= operator cannot be overloaded directly, but user-defined types can overload the [^ operator](../../../csharp/language-reference/operators/xor-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a6d9a-110">예</span><span class="sxs-lookup"><span data-stu-id="a6d9a-110">Example</span></span>  
 [!code-csharp[csRefOperators#23](../../../csharp/language-reference/operators/codesnippet/CSharp/xor-assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="a6d9a-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a6d9a-111">See Also</span></span>  
 [<span data-ttu-id="a6d9a-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="a6d9a-112">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="a6d9a-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="a6d9a-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="a6d9a-114">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="a6d9a-114">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
