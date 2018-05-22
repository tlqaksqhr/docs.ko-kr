---
title: = 연산자(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- =_CSharpKeyword
helpviewer_keywords:
- = operator [C#]
ms.assetid: d802a6d5-32f0-42b8-b180-12f5a081bfc1
ms.openlocfilehash: 979250c91cfe2abdf7295ae3866cd6b4294285cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="39d07-102">= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="39d07-102">= Operator (C# Reference)</span></span>
<span data-ttu-id="39d07-103">대입 연산자(`=`)는 왼쪽 피연산자가 나타내는 저장소 위치, 속성 또는 인덱서에 오른쪽 피연산자의 값을 저장하고 그 값을 해당 결과로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="39d07-103">The assignment operator (`=`) stores the value of its right-hand operand in the storage location, property, or indexer denoted by its left-hand operand and returns the value as its result.</span></span> <span data-ttu-id="39d07-104">피연산자는 동일한 형식이어야 합니다(또는 오른쪽 피연산자를 왼쪽 피연산자의 형식으로 암시적으로 변환할 수 있어야 함).</span><span class="sxs-lookup"><span data-stu-id="39d07-104">The operands must be of the same type (or the right-hand operand must be implicitly convertible to the type of the left-hand operand).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="39d07-105">설명</span><span class="sxs-lookup"><span data-stu-id="39d07-105">Remarks</span></span>  
 <span data-ttu-id="39d07-106">대입 연산자는 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39d07-106">The assignment operator cannot be overloaded.</span></span> <span data-ttu-id="39d07-107">그러나 형식에 대한 암시적 변환 연산자를 정의할 수 있으며, 이 연산자를 통해 해당 형식에 대입 연산자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39d07-107">However, you can define implicit conversion operators for a type, which enable you to use the assignment operator with those types.</span></span> <span data-ttu-id="39d07-108">자세한 내용은 [변환 연산자 사용](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="39d07-108">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="39d07-109">예</span><span class="sxs-lookup"><span data-stu-id="39d07-109">Example</span></span>  
 [!code-csharp[csRefOperators#49](../../../csharp/language-reference/operators/codesnippet/CSharp/assignment-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="39d07-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="39d07-110">See Also</span></span>  
 [<span data-ttu-id="39d07-111">C# 참조</span><span class="sxs-lookup"><span data-stu-id="39d07-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="39d07-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="39d07-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="39d07-113">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="39d07-113">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
