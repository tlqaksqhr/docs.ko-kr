---
title: ~ 연산자(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- ~_CSharpKeyword
helpviewer_keywords:
- tilde (~) one's complement operator [C#]
- ~ operator [C#]
- ~ [C#], bitwise complement operator
- bitwise complement operator [C#]
ms.assetid: 11bc078a-50e2-4d7e-9896-67ef669dc602
ms.openlocfilehash: 25b157fafde7d2b75cd8b112848a01e9b3fb0db2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="-operator-c-reference"></a><span data-ttu-id="0ed88-102">~ 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="0ed88-102">~ Operator (C# Reference)</span></span>
<span data-ttu-id="0ed88-103">`~` 연산자는 피연산자에 대해 비트 보수 연산을 수행하며, 각 비트를 반대로 하는 효과가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-103">The `~` operator performs a bitwise complement operation on its operand, which has the effect of reversing each bit.</span></span> <span data-ttu-id="0ed88-104">비트 보수 연산자는 [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) 및 [ulong](../../../csharp/language-reference/keywords/ulong.md)에 대해 미리 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-104">Bitwise complement operators are predefined for [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), and [ulong](../../../csharp/language-reference/keywords/ulong.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0ed88-105">또한 `~` 기호는 종료자를 선언하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-105">The `~` symbol also is used to declare finalizers.</span></span> <span data-ttu-id="0ed88-106">자세한 내용은 [종료자](../../../csharp/programming-guide/classes-and-structs/destructors.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ed88-106">For more information, see [Finalizers](../../../csharp/programming-guide/classes-and-structs/destructors.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0ed88-107">설명</span><span class="sxs-lookup"><span data-stu-id="0ed88-107">Remarks</span></span>  
 <span data-ttu-id="0ed88-108">사용자 정의 형식은 `~` 연산자를 오버로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-108">User-defined types can overload the `~` operator.</span></span> <span data-ttu-id="0ed88-109">자세한 내용은 [operator](../../../csharp/language-reference/keywords/operator.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0ed88-109">For more information, see [operator](../../../csharp/language-reference/keywords/operator.md).</span></span> <span data-ttu-id="0ed88-110">정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0ed88-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ed88-111">예</span><span class="sxs-lookup"><span data-stu-id="0ed88-111">Example</span></span>  
 [!code-csharp[csRefOperators#25](../../../csharp/language-reference/operators/codesnippet/CSharp/bitwise-complement-operator_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="0ed88-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0ed88-112">See Also</span></span>  
 [<span data-ttu-id="0ed88-113">C# 참조</span><span class="sxs-lookup"><span data-stu-id="0ed88-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="0ed88-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="0ed88-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="0ed88-115">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="0ed88-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="0ed88-116">종료자</span><span class="sxs-lookup"><span data-stu-id="0ed88-116">Finalizers</span></span>](../../../csharp/programming-guide/classes-and-structs/destructors.md)
