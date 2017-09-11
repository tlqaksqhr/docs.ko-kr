---
title: "*= 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '*=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
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
ms.openlocfilehash: 2969ba3ce303da591353fd0114dccf752e63f2c3
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="-operator-c-reference"></a><span data-ttu-id="0399c-102">*= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="0399c-102">*= Operator (C# Reference)</span></span>
<span data-ttu-id="0399c-103">이항 곱하기 대입 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="0399c-103">The binary multiplication assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0399c-104">설명</span><span class="sxs-lookup"><span data-stu-id="0399c-104">Remarks</span></span>  
 <span data-ttu-id="0399c-105">다음과 같은 `*=` 대입 연산자를 사용하는 식의 경우</span><span class="sxs-lookup"><span data-stu-id="0399c-105">An expression using the `*=` assignment operator, such as</span></span>  
  
```  
x *= y  
```  
  
 <span data-ttu-id="0399c-106">위의 식은 아래의 식과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="0399c-106">is equivalent to</span></span>  
  
```  
x = x * y  
```  
  
 <span data-ttu-id="0399c-107">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="0399c-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="0399c-108">[* 연산자](../../../csharp/language-reference/operators/multiplication-operator.md)는 곱하기를 수행할 숫자 형식에 대해 미리 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0399c-108">The [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>  
  
 <span data-ttu-id="0399c-109">`*=` 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [* 연산자](../../../csharp/language-reference/operators/multiplication-operator.md)를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="0399c-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [* operator](../../../csharp/language-reference/operators/multiplication-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0399c-110">예제</span><span class="sxs-lookup"><span data-stu-id="0399c-110">Example</span></span>  
 <span data-ttu-id="0399c-111">[!code-cs[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="0399c-111">[!code-cs[csRefOperators#13](../../../csharp/language-reference/operators/codesnippet/CSharp/multiplication-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0399c-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0399c-112">See Also</span></span>  
 <span data-ttu-id="0399c-113">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="0399c-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="0399c-114">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="0399c-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="0399c-115">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="0399c-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

