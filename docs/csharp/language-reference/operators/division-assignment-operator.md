---
title: "/= 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /=_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- division assignment operator (/=) [C#]
- /= (division assignment operator) [C#]
ms.assetid: 50fc02b0-ee9c-4c3e-b58d-d591282caf1c
caps.latest.revision: 17
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
ms.openlocfilehash: 5e105bf11f5413d77d62be4177ed22ba420312c3
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="e99b9-102">/= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="e99b9-102">/= Operator (C# Reference)</span></span>
<span data-ttu-id="e99b9-103">나누기 대입 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="e99b9-103">The division assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e99b9-104">주의</span><span class="sxs-lookup"><span data-stu-id="e99b9-104">Remarks</span></span>  
 <span data-ttu-id="e99b9-105">다음과 같은 `/=` 대입 연산자를 사용하는 식의 경우</span><span class="sxs-lookup"><span data-stu-id="e99b9-105">An expression using the `/=` assignment operator, such as</span></span>  
  
```  
x /= y  
```  
  
 <span data-ttu-id="e99b9-106">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="e99b9-106">is equivalent to</span></span>  
  
```  
x = x / y  
```  
  
 <span data-ttu-id="e99b9-107">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="e99b9-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="e99b9-108">[/ 연산자](../../../csharp/language-reference/operators/division-operator.md)는 나누기를 수행할 숫자 형식에 대해 미리 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e99b9-108">The [/ operator](../../../csharp/language-reference/operators/division-operator.md) is predefined for numeric types to perform division.</span></span>  
  
 <span data-ttu-id="e99b9-109">`/=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [/ 연산자](../../../csharp/language-reference/operators/division-operator.md)를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="e99b9-109">The `/=` operator cannot be overloaded directly, but user-defined types can overload the [/ operator](../../../csharp/language-reference/operators/division-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span> <span data-ttu-id="e99b9-110">모든 복합 대입 연산자에서 이진 연산자를 암시적으로 오버로드하면 해당하는 복합 대입 연산자가 오버로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="e99b9-110">On all compound assignment operators, overloading the binary operator implicitly overloads the equivalent compound assignment.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e99b9-111">예제</span><span class="sxs-lookup"><span data-stu-id="e99b9-111">Example</span></span>  
 <span data-ttu-id="e99b9-112">[!code-cs[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="e99b9-112">[!code-cs[csRefOperators#5](codesnippet/CSharp/division-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e99b9-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e99b9-113">See Also</span></span>  
 <span data-ttu-id="e99b9-114">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="e99b9-114">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="e99b9-115">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="e99b9-115">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="e99b9-116">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="e99b9-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

