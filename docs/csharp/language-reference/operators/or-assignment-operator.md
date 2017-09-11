---
title: "|= 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '|=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
caps.latest.revision: 16
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
ms.openlocfilehash: f1c0a92414739efc2ab091871e80852737fdf931
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="82b53-102">|= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="82b53-102">|= Operator (C# Reference)</span></span>
<span data-ttu-id="82b53-103">OR 대입 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="82b53-103">The OR assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="82b53-104">설명</span><span class="sxs-lookup"><span data-stu-id="82b53-104">Remarks</span></span>  
 <span data-ttu-id="82b53-105">다음과 같은 `|=` 대입 연산자를 사용하는 식의 경우</span><span class="sxs-lookup"><span data-stu-id="82b53-105">An expression using the `|=` assignment operator, such as</span></span>  
  
```  
x |= y  
```  
  
 <span data-ttu-id="82b53-106">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="82b53-106">is equivalent to</span></span>  
  
```  
x = x | y  
```  
  
 <span data-ttu-id="82b53-107">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="82b53-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="82b53-108">[&#124; 연산자](../../../csharp/language-reference/operators/or-operator.md)는 정수 피연산자에 대한 비트 논리적 OR 연산과 부울 피연산자에 대한 논리적 OR 연산을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="82b53-108">The [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) performs a bitwise logical OR operation on integral operands and logical OR on bool operands.</span></span>  
  
 <span data-ttu-id="82b53-109">`|=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [&#124; 연산자](../../../csharp/language-reference/operators/or-operator.md)를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="82b53-109">The `|=` operator cannot be overloaded directly, but user-defined types can overload the [&#124; operator](../../../csharp/language-reference/operators/or-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="82b53-110">예제</span><span class="sxs-lookup"><span data-stu-id="82b53-110">Example</span></span>  
 <span data-ttu-id="82b53-111">[!code-cs[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="82b53-111">[!code-cs[csRefOperators#10](../../../csharp/language-reference/operators/codesnippet/CSharp/or-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82b53-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82b53-112">See Also</span></span>  
 <span data-ttu-id="82b53-113">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="82b53-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="82b53-114">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="82b53-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="82b53-115">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="82b53-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

