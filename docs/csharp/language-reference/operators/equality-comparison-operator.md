---
title: "== 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- ==_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- == operator [C#]
- equality operator [C#]
ms.assetid: 34c6b597-caa2-4855-a7cd-38ecdd11bd07
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0e3ba284bc700e943b108adfec89d14aba41851a
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="ae47b-102">== 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="ae47b-102">== Operator (C# Reference)</span></span>
<span data-ttu-id="ae47b-103">미리 정의된 값 형식의 경우 같음 연산자(`==`)는 피연산자의 값이 같으면 true, 같지 않으면 `false`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ae47b-103">For predefined value types, the equality operator (`==`) returns true if the values of its operands are equal, `false` otherwise.</span></span> <span data-ttu-id="ae47b-104">[string](../../../csharp/language-reference/keywords/string.md)을 제외한 참조 형식의 경우 `==`은 두 피연산자가 동일한 개체를 참조하면 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ae47b-104">For reference types other than [string](../../../csharp/language-reference/keywords/string.md), `==` returns `true` if its two operands refer to the same object.</span></span> <span data-ttu-id="ae47b-105">`string` 형식의 경우 `==`은 문자열의 값을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="ae47b-105">For the `string` type, `==` compares the values of the strings.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae47b-106">설명</span><span class="sxs-lookup"><span data-stu-id="ae47b-106">Remarks</span></span>  
 <span data-ttu-id="ae47b-107">사용자 정의 값 형식은 `==` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="ae47b-107">User-defined value types can overload the `==` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="ae47b-108">사용자 정의 참조 형식의 경우도 마찬가지입니다. 하지만 기본적으로 `==`은 미리 정의된 참조 형식과 사용자 정의 참조 형식 모두에 대해 위에서 설명한 대로 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="ae47b-108">So can user-defined reference types, although by default `==` behaves as described above for both predefined and user-defined reference types.</span></span> <span data-ttu-id="ae47b-109">`==` 연산자가 오버로드되면 [!=](../../../csharp/language-reference/operators/not-equal-operator.md) 또한 오버로드되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae47b-109">If `==` is overloaded, [!=](../../../csharp/language-reference/operators/not-equal-operator.md) must also be overloaded.</span></span> <span data-ttu-id="ae47b-110">정수 계열 형식에 대한 연산은 일반적으로 열거형에서 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae47b-110">Operations on integral types are generally allowed on enumeration.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae47b-111">예제</span><span class="sxs-lookup"><span data-stu-id="ae47b-111">Example</span></span>  
 <span data-ttu-id="ae47b-112">[!code-cs[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ae47b-112">[!code-cs[csRefOperators#36](../../../csharp/language-reference/operators/codesnippet/CSharp/equality-comparison-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae47b-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae47b-113">See Also</span></span>  
 <span data-ttu-id="ae47b-114">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ae47b-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="ae47b-115">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ae47b-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="ae47b-116">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="ae47b-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

