---
title: "&gt;&gt;= 연산자(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- '>>=_CSharpKeyword'
dev_langs:
- CSharp
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
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
ms.openlocfilehash: 64f387e475681ffc76f113435ba090b40780dda3
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="1ab81-102">&gt;&gt;= 연산자(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="1ab81-102">&gt;&gt;= Operator (C# Reference)</span></span>
<span data-ttu-id="1ab81-103">오른쪽 시프트 대입 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="1ab81-103">The right-shift assignment operator.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ab81-104">설명</span><span class="sxs-lookup"><span data-stu-id="1ab81-104">Remarks</span></span>  
 <span data-ttu-id="1ab81-105">다음 형태의 식이 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="1ab81-105">An expression of the form</span></span>  
  
```  
x >>= y  
```  
  
 <span data-ttu-id="1ab81-106">이 식은 다음과 같이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ab81-106">is evaluated as</span></span>  
  
```  
x = x >> y  
```  
  
 <span data-ttu-id="1ab81-107">단, `x`가 한 번만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ab81-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="1ab81-108">[>> 연산자](../../../csharp/language-reference/operators/right-shift-operator.md)는 `y`로 지정된 양만큼 `x`를 오른쪽으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="1ab81-108">The [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) shifts `x` right by an amount specified by `y`.</span></span>  
  
 <span data-ttu-id="1ab81-109">>>= 연산자를 직접 오버로드할 수는 없지만 사용자 정의 형식은 [>> 연산자](../../../csharp/language-reference/operators/right-shift-operator.md)를 오버로드할 수 있습니다([operator](../../../csharp/language-reference/keywords/operator.md) 참조).</span><span class="sxs-lookup"><span data-stu-id="1ab81-109">The >>= operator cannot be overloaded directly, but user-defined types can overload the [>> operator](../../../csharp/language-reference/operators/right-shift-operator.md) (see [operator](../../../csharp/language-reference/keywords/operator.md)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ab81-110">예제</span><span class="sxs-lookup"><span data-stu-id="1ab81-110">Example</span></span>  
 <span data-ttu-id="1ab81-111">[!code-cs[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="1ab81-111">[!code-cs[csRefOperators#11](../../../csharp/language-reference/operators/codesnippet/CSharp/right-shift-assignment-operator_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ab81-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ab81-112">See Also</span></span>  
 <span data-ttu-id="1ab81-113">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="1ab81-113">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="1ab81-114">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="1ab81-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="1ab81-115">C# 연산자</span><span class="sxs-lookup"><span data-stu-id="1ab81-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)

