---
title: "%= 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '%=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- modulus assignment operator (=%) [C#]
- '%= assignment operator (modulus assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
caps.latest.revision: 20
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
ms.openlocfilehash: 48484a0593102c92304803e5c0697501b0e26e0e
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="b647a-102">%= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="b647a-102">%= Operator (C# Reference)</span></span>
<span data-ttu-id="b647a-103">나머지 대입 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="b647a-103">The remainder assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b647a-104">설명</span><span class="sxs-lookup"><span data-stu-id="b647a-104">Remarks</span></span>  
 <span data-ttu-id="b647a-105">다음과 같은 `%=` 대입 연산자를 사용하는 식의 경우</span><span class="sxs-lookup"><span data-stu-id="b647a-105">An expression using the `%=` assignment operator, such as</span></span>  
  
```  
x %= y  
```  
  
 <span data-ttu-id="b647a-106">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="b647a-106">is equivalent to</span></span>  
  
```  
x = x % y  
```  
  
 <span data-ttu-id="b647a-107">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="b647a-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="b647a-108">[% 연산자](../../../csharp/language-reference/operators/modulus-operator.md)는 나누기 후 나머지를 계산하기 위해 숫자 형식에 대해 미리 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b647a-108">The [% operator](../../../csharp/language-reference/operators/modulus-operator.md) is predefined for numeric types to compute the remainder after division.</span></span>  
  
 <span data-ttu-id="b647a-109">`%=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [% 연산자](../../../csharp/language-reference/operators/modulus-operator.md)를 오버로드할 수 있습니다([연산자(C# 참조)](../../../csharp/language-reference/keywords/operator.md)).</span><span class="sxs-lookup"><span data-stu-id="b647a-109">The `%=` operator cannot be overloaded directly, but user-defined types can overload the [% operator](../../../csharp/language-reference/operators/modulus-operator.md) (see [operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b647a-110">예제</span><span class="sxs-lookup"><span data-stu-id="b647a-110">Example</span></span>  
 <span data-ttu-id="b647a-111">[!code-cs[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b647a-111">[!code-cs[csRefOperators#4](../../../csharp/language-reference/operators/codesnippet/CSharp/modulus-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b647a-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b647a-112">See Also</span></span>  
 <span data-ttu-id="b647a-113">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="b647a-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="b647a-114">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b647a-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="b647a-115">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="b647a-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

