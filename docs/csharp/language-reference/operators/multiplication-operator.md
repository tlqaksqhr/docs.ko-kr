---
title: "* 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '*_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
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
ms.openlocfilehash: 165ca8f797eb8d03ae1dec8c0ec5e1f4b31cb050
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="6260d-102">* 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="6260d-102">* Operator (C# Reference)</span></span>
<span data-ttu-id="6260d-103">곱하기 연산자(`*`)는 피연산자의 곱을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="6260d-103">The multiplication operator (`*`), which computes the product of its operands.</span></span>  <span data-ttu-id="6260d-104">역참조 연산자를 사용하면 포인터를 읽고 쓸 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6260d-104">Also, the dereference operator, which allows reading and writing to a pointer.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6260d-105">설명</span><span class="sxs-lookup"><span data-stu-id="6260d-105">Remarks</span></span>  
 <span data-ttu-id="6260d-106">모든 숫자 형식에는 곱하기 연산자가 미리 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6260d-106">All numeric types have predefined multiplication operators.</span></span>  
  
 <span data-ttu-id="6260d-107">`*` 연산자는 포인터 형식의 선언과 포인터의 역참조에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6260d-107">The `*` operator is also used to declare pointer types and to dereference pointers.</span></span> <span data-ttu-id="6260d-108">이 연산자는 [unsafe](../../../csharp/language-reference/keywords/unsafe.md) 키워드로 표시되었으며 [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) 컴파일러 옵션이 필요한 안전하지 않은 컨텍스트에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6260d-108">This operator can only be used in unsafe contexts, denoted by the use of the [unsafe](../../../csharp/language-reference/keywords/unsafe.md) keyword, and requiring the [/unsafe](../../../csharp/language-reference/compiler-options/unsafe-compiler-option.md) compiler option.</span></span>  <span data-ttu-id="6260d-109">역참조 연산자를 간접 참조 연산자라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="6260d-109">The dereference operator is also known as the indirection operator.</span></span>  
  
 <span data-ttu-id="6260d-110">사용자 정의 형식으로 이항 `*` 연산자를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="6260d-110">User-defined types can overload the binary `*` operator (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="6260d-111">이항 연산자가 오버로드되면 해당 대입 연산자도 암시적으로 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="6260d-111">When a binary operator is overloaded, the corresponding assignment operator, if any, is also implicitly overloaded.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6260d-112">예제</span><span class="sxs-lookup"><span data-stu-id="6260d-112">Example</span></span>  
 <span data-ttu-id="6260d-113">[!code-cs[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="6260d-113">[!code-cs[csRefOperators#50](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="6260d-114">예제</span><span class="sxs-lookup"><span data-stu-id="6260d-114">Example</span></span>  
 <span data-ttu-id="6260d-115">[!code-cs[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="6260d-115">[!code-cs[csRefOperators#51](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-operator_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6260d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6260d-116">See Also</span></span>  
 <span data-ttu-id="6260d-117">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="6260d-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="6260d-118">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="6260d-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="6260d-119">[안전하지 않은 코드 및 포인터](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="6260d-119">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 [<span data-ttu-id="6260d-120">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="6260d-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

