---
title: "&amp;= 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '&=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- AND assignment operator (&=) [C#]
- '&= operator [C#]'
ms.assetid: e8d58f3f-72dd-4b5a-b995-452fcce7e6bb
caps.latest.revision: 15
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
ms.openlocfilehash: 6dec8de5077c07150ea37b88979e7b59b231d610
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="amp-operator-c-reference"></a><span data-ttu-id="dde13-102">&amp;= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="dde13-102">&amp;= Operator (C# Reference)</span></span>
<span data-ttu-id="dde13-103">AND 대입 연산자.</span><span class="sxs-lookup"><span data-stu-id="dde13-103">The AND assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dde13-104">설명</span><span class="sxs-lookup"><span data-stu-id="dde13-104">Remarks</span></span>  
 <span data-ttu-id="dde13-105">다음과 같은 `&=` 대입 연산자를 사용하는 식의 경우</span><span class="sxs-lookup"><span data-stu-id="dde13-105">An expression using the `&=` assignment operator, such as</span></span>  
  
```  
x &= y  
```  
  
 <span data-ttu-id="dde13-106">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="dde13-106">is equivalent to</span></span>  
  
```  
x = x & y  
```  
  
 <span data-ttu-id="dde13-107">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="dde13-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="dde13-108">[& 연산자](../../../csharp/language-reference/operators/and-operator.md)는 정수 피연산자에 대한 비트 논리적 AND 연산과 `bool` 피연산자에 대한 논리적 AND 연산을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="dde13-108">The [& operator](../../../csharp/language-reference/operators/and-operator.md) performs a bitwise logical AND operation on integral operands and logical AND on `bool` operands.</span></span>  
  
 <span data-ttu-id="dde13-109">`&=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 이항 [& 연산자](../../../csharp/language-reference/operators/and-operator.md)를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="dde13-109">The `&=` operator cannot be overloaded directly, but user-defined types can overload the binary [& operator](../../../csharp/language-reference/operators/and-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="dde13-110">예제</span><span class="sxs-lookup"><span data-stu-id="dde13-110">Example</span></span>  
 <span data-ttu-id="dde13-111">[!code-cs[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="dde13-111">[!code-cs[csRefOperators#34](../../../csharp/language-reference/operators/codesnippet/CSharp/and-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dde13-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dde13-112">See Also</span></span>  
 <span data-ttu-id="dde13-113">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="dde13-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="dde13-114">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="dde13-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="dde13-115">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="dde13-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

