---
title: "! 연산자(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- '! operator [C#]'
- logical negation operator (!) [C#]
- NOT operator [C#]
ms.assetid: f5ae133f-8f64-4560-b34f-cd9cd5eed4ad
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3560be4067fdb7a51c6073d2ec159b7d04c00eaa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="-operator-c-reference"></a><span data-ttu-id="d582e-103">!</span><span class="sxs-lookup"><span data-stu-id="d582e-103">!</span></span> <span data-ttu-id="d582e-104">연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="d582e-104">Operator (C# Reference)</span></span>
<span data-ttu-id="d582e-105">논리적 부정 연산자(`!`)는 해당 피연산자를 부정하는 단항 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="d582e-105">The logical negation operator (`!`) is a unary operator that negates its operand.</span></span> <span data-ttu-id="d582e-106">`bool`에 대해 정의되며, 해당 피연산자가 `false`인 경우에만 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d582e-106">It is defined for `bool` and returns `true` if and only if its operand is `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d582e-107">설명</span><span class="sxs-lookup"><span data-stu-id="d582e-107">Remarks</span></span>  
 <span data-ttu-id="d582e-108">사용자 정의 형식은 `!` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="d582e-108">User-defined types can overload the `!` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d582e-109">예제</span><span class="sxs-lookup"><span data-stu-id="d582e-109">Example</span></span>  
 [!code-csharp[csRefOperators#7](../../../csharp/language-reference/operators/codesnippet/CSharp/logical-negation-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="d582e-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d582e-110">See Also</span></span>  
 [<span data-ttu-id="d582e-111">C# 참조</span><span class="sxs-lookup"><span data-stu-id="d582e-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d582e-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="d582e-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d582e-113">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="d582e-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
