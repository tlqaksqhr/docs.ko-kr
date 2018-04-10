---
title: -- 연산자(C# 참조)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- --_CSharpKeyword
helpviewer_keywords:
- -- operator [C#]
- decrement operator (--) [C#]
ms.assetid: 6b9cfe86-63c7-421f-9379-c9690fea8720
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4eb68143103d44defeac7191e7c4ce7d1ee90e9b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="---operator-c-reference"></a><span data-ttu-id="8cc98-102">-- 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="8cc98-102">-- Operator (C# Reference)</span></span>
<span data-ttu-id="8cc98-103">감소 연산자(`--`)는 피연산자를 1씩 감소시킵니다.</span><span class="sxs-lookup"><span data-stu-id="8cc98-103">The decrement operator (`--`) decrements its operand by 1.</span></span> <span data-ttu-id="8cc98-104">감소 연산자는 피연산자 앞이나 뒤에 나타날 수 있습니다(`--variable` 및 `variable--`).</span><span class="sxs-lookup"><span data-stu-id="8cc98-104">The decrement operator can appear before or after its operand: `--variable` and `variable--`.</span></span> <span data-ttu-id="8cc98-105">첫 번째 형태는 전위 감소 연산입니다.</span><span class="sxs-lookup"><span data-stu-id="8cc98-105">The first form is a prefix decrement operation.</span></span> <span data-ttu-id="8cc98-106">연산 결과는 감소된 후의 피연산자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8cc98-106">The result of the operation is the value of the operand "after" it has been decremented.</span></span> <span data-ttu-id="8cc98-107">두 번째 형태는 후위 감소 연산입니다.</span><span class="sxs-lookup"><span data-stu-id="8cc98-107">The second form is a postfix decrement operation.</span></span> <span data-ttu-id="8cc98-108">연산 결과는 감소되기 전의 피연산자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8cc98-108">The result of the operation is the value of the operand "before" it has been decremented.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8cc98-109">설명</span><span class="sxs-lookup"><span data-stu-id="8cc98-109">Remarks</span></span>  
 <span data-ttu-id="8cc98-110">숫자 및 열거형 형식에는 미리 정의된 감소 연산자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cc98-110">Numeric and enumeration types have predefined decrement operators.</span></span>  
  
 <span data-ttu-id="8cc98-111">사용자 정의 형식은 `--` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="8cc98-111">User-defined types can overload the `--` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="8cc98-112">정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cc98-112">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8cc98-113">예제</span><span class="sxs-lookup"><span data-stu-id="8cc98-113">Example</span></span>  
 [!code-csharp[csRefOperators#8](../../../csharp/language-reference/operators/codesnippet/CSharp/decrement-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="8cc98-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8cc98-114">See Also</span></span>  
 [<span data-ttu-id="8cc98-115">C# 참조</span><span class="sxs-lookup"><span data-stu-id="8cc98-115">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="8cc98-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8cc98-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="8cc98-117">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="8cc98-117">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
